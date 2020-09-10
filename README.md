# ACM Research Coding Challenge (Fall 2020)

## No Collaboration Policy

**You may not collaborate with anyone on this challenge.** You _are_ allowed to use Internet documentation. If you _do_ use existing code (either from Github, Stack Overflow, or other sources), **please cite your sources in the README**.

## Submission Procedure

Please follow the below instructions on how to submit your answers.

1. Create a **public** fork of this repo and name it `ACM-Research-Coding-Challenge`. To fork this repo, click the button on the top right and click the "Fork" button.
2. Clone the fork of the repo to your computer using . `git clone [the URL of your clone]`. You may need to install Git for this (Google it).
3. Complete the Challenge based on the instructions below.
4. Email the link of your repo to research@acmutd.co with the same email you used to submit your application. Be sure to include your name in the email.

## Question One

![Image of Cluster Plot](ClusterPlot.png)
<br/>
Given the following dataset in `ClusterPlot.csv`, determine the number of clusters by using any clustering algorithm. **You're allowed to use any Python library you want to implement this**, just document which ones you used in this README file. Try to complete this as soon as possible.

Regardless if you can or cannot answer the question, provide a short explanation of how you got your solution or how you think it can be solved in your README.md file.

## Question One Answer

Brief warning: I have about 1% of experience and knowledge with Python but that won't stop me from trying to answer this question. I am aware of myself that I lack the knowledge and experience to fully complete this part of the challenge but I have enjoyed learning about new material while attempting this challenge (it's the effort that counts right? :-) 
Based off of my attempt to learn Python from several Youtube tutorials and my research on analyzing data clusters in the past few days, I have come to a conclusion on how to
determine the number of clusters from the given data plot. I apologize in advance.

I have learned that there are several clustering algorithms and I have narrowed down to which method would be most effective in identifying these clusters: The Gaussian Mixture Model. 
The Gaussian Mixture Model is a probabilistic model for showing subpopulations which are normally distributed within an overall population, which I found ideal in this situation as it
could identify smaller clusters within the two bigger clusters. GMM has the upper hand on K-Menas since GMMs can learn clusters with elliptical shapes rather than just circular forms.

First we would need to load in our data, in this case the plots, I think by using data = pd.read_csv('ClusterPlot.csv')
Then we would build a k-means model which would set the base for our Gaussian Mixture Model. By using k-means we can find the initial
values for our parameters.

Then we would start coding our GMM. First we would need to estimate latent variables in order to tell us
which points belong to which clusters. To estimate latent variables we would need to code an
Expectation Maximisation Algorithm which basically maximizes the likelihood of our data points being observed in the clusters within the parameters (which is a whole math process I have the slightest idea of)
The EM algorithm has two steps that are the E-Step (uses the data to guess the values of the missing variables) and then the M-Step (uses the values from E-step to update parameters)

Actually at this point I think it would be best to use K-means. We would need to acquire our data points from the cluster plot. Then use the SciKit python library in order to process the data.
Then we would give k (n_clusters) a value to identify the number of clusters. Then we would need to find the centroid of those clusters which would then classify the points into their respective clusters.


sources used: https://scikit-learn.org/stable/modules/generated/sklearn.mixture.GaussianMixture.html
                https://www.analyticsvidhya.com/blog/2019/10/gaussian-mixture-models-clustering/
                https://towardsdatascience.com/gaussian-mixture-modelling-gmm-833c88587c7f
