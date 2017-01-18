

The goal of the below protocol is to:

1. determine whether you understand the basic principles of a given algorithm
2. can run it successfully
3. can evaluate its performance meaningfully

### (*[python notebook example](./Tutorials/Python/code_example.ipynb)*)


## Algorithm 

Doing the next three steps carefully & correctly implies that you understand the algorithm, at least in theory.

1. write algorithm pseudocode
1. write algorithm code
1. write (in plain language) the conditions under which you think this algorithm will perform well, and those under which you think it will perform poorly.  If you want to be formal, you can write the particular model under which the algorithm has statistical guarantees.


## Simulation Data

Code should always be tested to determine whether we can trust the results, this means testing to see that it works well when it should, and that it does not work well when it shouldn't.  Below we describe how to generate such simulations so that you can use them to test the code.

1. write the sampling/generative distributions that you will write to test the code. the simulation should have the following properties:
    1. you know exactly what the answer should be.  
    2. you expect the algorithm to perform very well (because it is easy for a given sample size)
1. write code to sample data from the above settings
1. describe in words what you think the simulations will look like
1. write code to plot simulated data
2. plot simulated data, as raw as possible (ie, all observed variables, latent variables, and parameters)
3. report whether it looks "right"
2. repeat the above for a simulation setting for which the alg will *not* perform well (because it is difficult  for a given sample size).  


## Simulation Analysis

Here we actually test the code on the two above described settings.  Because the results are random, it is important to repeat the analysis multiple times.

Note that we want to understand performance on simulated data, to help understand performance on real data. There are two different scenarios of interest for real data: (i) those for which we are given a gold standard answer (often called the "truth", but even more often is a noisy estimate of the truth, if the truth even exists), and (ii) those for which no gold standard is available. For case (i), for predictions, when possible do 10-fold cross-validation.  For case (ii), the best thing we can do is compute "discriminability" (see [repo](https://github.com/neurodata/discriminability), [tutorial](http://docs.neurodata.io/checklists/Tutorials/R/Discriminability/discriminability_tutorial.html)).  In particular, given multiple measurements from multiple samples, compute how relatively similar the measurements from the same sample are, both before and after applying the algorithm.  If the algorithm is useful, it should increase discriminability.

1. describe in words how you think the algorithm will perform in the easy simulation
1. generate simulated data
1. run algorithm on simulated data
1. plot results 
1. describe the metric that you will use to quantify the results when given the truth
1. if real data does not have a reasonable "gold standard", also describe metric to quantify performance without gold standard
1. write code to quantify the results
1. quantify performance (using 1 or both metrics)
1. repeat 10x on the easy simulation, only plot >=1x 
1. repeat 10x on the hard simulation, only plot >=1x



## Summarize Simulation Analysis

After running the code multiple times on a couple different scenarios, we determine whether the algorithm works "well" in general when it should, and works poorly in general, when it should not work well.

1. describe how you will visualize the population results
1. describe how you will compute population performance
1. write code to plot population results
1. write code to compute population performance
1. run qualitative population analysis (ie, plot summary plots) on the simple simulation
1. run quantitative population analysis (ie, compute population performance) on the simple simulation
1. repeat the above 2 steps on the difficult simulation
1. summarize performance on both settings


## Real Data Analysis



1. Find two different real datasets, at least 1 for which somebody else has evidence that there is "signal"
1. For each, describe the # of dimensions, # of samples, and any other salient features
2. plot raw data, as raw as possible (i.e. all observed variables, latent variables, and parameters)
3. predict performance accuracy of the algorithm for each dataset
4. run *exact same code* on real data as ran on simulations, generating estimates, qualitative and quantitative results. 
5. document performance accuracy relative to predictions, modify understanding as appropriate.






