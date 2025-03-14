# Reproducible research: version control and R

Questions 1, 2, and 3: https://github.com/0984567-homework/logistic_growth.git

4. i)Every time that the code is run, a new random walk appears for each plot. All of the walks start from the origin (0,0) and there is a colour gradient for how far along the walk has progressed in time. A random angle for up to n steps is generated in each iteration.
   
   ii) Random seeds are the starting point for random number generation. They make it so that the random numbers generated are reproducible. The idea is that the same seed will generate the same random progression of numbers.
   
   iii) I added the set.seed() function and then chose the integer 456 as the seed, this means that every time the code is re-ran, the same walk is generated for each plot. This script is now in this repo (in the 'question-4-code' folder).
   
   iv) <img width="848" alt="image" src="https://github.com/0984567-homework/reproducible-research_homework/assets/152702616/df683ffd-6a55-441a-aa4a-b1fb09c34f72">

5. i) The table has 13 columns and 33 rows.
6. 
   ii) I log transformed the data to make it more linear. Providing this plot:
   <img width="865" alt="image" src="https://github.com/0984567-homework/reproducible-research_homework/assets/152702616/c62bc552-a78d-4d8b-b1b2-d4f67babe66f">

   iii) The exponent ($\alpha$)= 1.5152
   Log($\beta$) = 7.0748, so the scaling factor ($\beta$) = 1181.807

The p-value for the exponent was 6.44e-10, the p-value for the scaling factor was 2.28e-10. Both are statistically significant at the 0.05 level.

I found the same value for the exponent (given as 1.52 in the paper), and similar for the scaling factor (1182 in paper).

   Code as shown:
   <img width="468" alt="image" src="https://github.com/0984567-homework/reproducible-research_homework/assets/152702616/b5f7a13f-be25-445a-9843-8342ebd8c41a">


iv) Code used to recreate figure:
<img width="673" alt="image" src="https://github.com/0984567-homework/reproducible-research_homework/assets/152702616/2ee80417-f875-4271-93f8-1f49d31e9ad4">

Figure produced:
<img width="525" alt="image" src="https://github.com/0984567-homework/reproducible-research_homework/assets/152702616/50f62b19-9562-4156-8699-0229d93f5a4a">

v) The linear model is: logV = (\$alpha$)logL + log(\$beta$), where L is 300,000 (kb to nt conversion)
When the values from (iii) and L = 300,000 are substituted in, we get: logV = 1.5152 x log300000 + 7.0748.
logV = 26.183802. V = 2.352x10^11 nm^3.

THE R SCRIPT USED FOR THE ABOVE IS IN THE reproducible-research_homework REPO AS 'q5 code.R'

Bonus: Reproducibility is when a study uses the same method of investigation and analysis and is conducted by either the same researchers or different, but reaches the same results. Replicability, is when the same results are achieved, or the same answer to the overarching scientific question is found, but the experimental methods and analysis were different in the different studies.
git and GitHub are very useful for enhancing the reproducibility and replicability of work. This is because they allow for detailed records of the different analyses to be maintained- this means that researchers can go back and reproduce their work following the same steps. In terms of replication, others can observe the methods that have already been used to inspire new experiements- or try to replicate the findings of other researchers using their original methods. The collaboration feature of GitHub means that multiple people working on a project can have access to the same code and so can independently check its efficacy. The version control feature allows progress of code and work to be documented, so that other researchers can understand the stages in research and efforts to reproduce and replicate findings can begin from a firm foundation.
There are however some limitations with the use of git and GitHub. One of the main ones is that it requires quite some time to become a confident user and to understand all of the available functions. This means that research and collaboration could be slow in many cases and thus reproduction and replication of results would be limited. Additionally, the security settings can be difficult to control and therefore using GitHub for private data which cannot be allowed into the public domain could be problematic.
   


## Instructions

The homework for this Computer skills practical is divided into 5 questions for a total of 100 points (plus an optional bonus question worth 10 extra points). First, fork this repo and make sure your fork is made **Public** for marking. Answers should be added to the # INSERT ANSWERS HERE # section above in the **README.md** file of your forked repository.

Questions 1, 2 and 3 should be answered in the **README.md** file of the `logistic_growth` repo that you forked during the practical. To answer those questions here, simply include a link to your logistic_growth repo.

**Submission**: Please submit a single **PDF** file with your candidate number (and no other identifying information), and a link to your fork of the `reproducible-research_homework` repo with the completed answers. All answers should be on the `main` branch.

## Assignment questions 

1) (**10 points**) Annotate the **README.md** file in your `logistic_growth` repo with more detailed information about the analysis. Add a section on the results and include the estimates for $N_0$, $r$ and $K$ (mention which *.csv file you used).
   
2) (**10 points**) Use your estimates of $N_0$ and $r$ to calculate the population size at $t$ = 4980 min, assuming that the population grows exponentially. How does it compare to the population size predicted under logistic growth? 

3) (**20 points**) Add an R script to your repository that makes a graph comparing the exponential and logistic growth curves (using the same parameter estimates you found). Upload this graph to your repo and include it in the **README.md** file so it can be viewed in the repo homepage.
   
4) (**30 points**) Sometimes we are interested in modelling a process that involves randomness. A good example is Brownian motion. We will explore how to simulate a random process in a way that it is reproducible:

   - A script for simulating a random_walk is provided in the `question-4-code` folder of this repo. Execute the code to produce the paths of two random walks. What do you observe? (10 points)
   - Investigate the term **random seeds**. What is a random seed and how does it work? (5 points)
   - Edit the script to make a reproducible simulation of Brownian motion. Commit the file and push it to your forked `reproducible-research_homework` repo. (10 points)
   - Go to your commit history and click on the latest commit. Show the edit you made to the code in the comparison view (add this image to the **README.md** of the fork). (5 points)

5) (**30 points**) In 2014, Cui, Schlub and Holmes published an article in the *Journal of Virology* (doi: https://doi.org/10.1128/jvi.00362-14) showing that the size of viral particles, more specifically their volume, could be predicted from their genome size (length). They found that this relationship can be modelled using an allometric equation of the form **$`V = \beta L^{\alpha}`$**, where $`V`$ is the virion volume in nm<sup>3</sup> and $`L`$ is the genome length in nucleotides.

   - Import the data for double-stranded DNA (dsDNA) viruses taken from the Supplementary Materials of the original paper into Posit Cloud (the csv file is in the `question-5-data` folder). How many rows and columns does the table have? (3 points)
   - What transformation can you use to fit a linear model to the data? Apply the transformation. (3 points)
   - Find the exponent ($\alpha$) and scaling factor ($\beta$) of the allometric law for dsDNA viruses and write the p-values from the model you obtained, are they statistically significant? Compare the values you found to those shown in **Table 2** of the paper, did you find the same values? (10 points)
   - Write the code to reproduce the figure shown below. (10 points)

  <p align="center">
     <img src="https://github.com/josegabrielnb/reproducible-research_homework/blob/main/question-5-data/allometric_scaling.png" width="600" height="500">
  </p>

  - What is the estimated volume of a 300 kb dsDNA virus? (4 points)

**Bonus** (**10 points**) Explain the difference between reproducibility and replicability in scientific research. How can git and GitHub be used to enhance the reproducibility and replicability of your work? what limitations do they have? (e.g. check the platform [protocols.io](https://www.protocols.io/)).
