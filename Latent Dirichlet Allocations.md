# Latent Dirichlet Allocation (LDA)
* The goal is to learn the probability of words in text Documents.
* This model involves following terms which are "Bernoulli Distribution", "Binomial Distribution ", "Conjugate Prior", "Beta Distribution", "Gamma Function", "Multinomial Distribution", "Dirichlet Distribution", "Categorical Distribution", "Hyper parameters", "Mixture of Distributions", "Variational Inference".
* To Start step by step, the model is to answer the following questions:
    * 1.Whether or not a word will appear in a document?
    * 2.What is the probability of a word appearing in a document.
    * 3.How many time that word will appear in a document?
    * 4.Which word will appear in a document?
    *
## Single word problem: 1,2,3
####  1.Whether or not a word will appear in a document?
This question is similar to a rolling a coin problem that to decide whether a head will appear ?
This is the Bernoulli Distribution $X \sim Bernoulli(X=x|\mu)\mu^{x}(1-\mu)^{(1-x)}$.
head: $P(X=1|\mu)=\mu$, tail $P(X=0|\mu)=1-\mu$. This distribution ranges from 0 to 1 with mean $\mu$, variance: $\mu(1-\mu)$

Then the problem is how to estimating parameter $\mu$

Observed Data: $X_1=1,X_2=0,X_3=0,...,X_n=1$
Likelihood: $P(D|\mu)= \prod_i P(X_i|\mu)=\prod \mu^{x_i}(1-\mu)^{1-x_i} = \mu(1-\mu)(1-\mu)\mu...\mu$
loglikelihood: $logP(D|\mu)$
Maxium likelihood Estimation: $\mu_{ML}= {1 \over n} \sum_i X_i$
#### 2. How many times a word will appear in the document?
This becomes the Binomial Distribution: $X \sim Binominal(X=m|N,\mu) = {a \choose b} \mu^{m}(1-\mu)^{N-m}$
This distribution describe we have a coin which is bias with para $\mu$, we roll the coin N times, how many times the head will appear?

The X ranges from {1,2,...,N}, mean: N$\mu$, and variance: $N\mu(1-\mu)$. The $\mu$ is the bias of the coin.

How do we estimate the $\mu$?

Observed Data: $X_1=2,X_2=7,X_3=5,X_4=3,...,X_k=4$. Note, these values are "how many times", $X_1=2$ means in the first experiments, we roll $N$ times coin or dice, the head appears twice!

Likelihood: $P(D|\mu)=\prod_i P(X_i|N,\mu)=\prod_i {N \choose x_i}\mu^{x_i}(1-\mu)^{N-x_i}$

Maximum Likelihood Estimate: $\mu_{ML}=\frac{1}{kN}\sum_iX_i$, because we do the experiments $k$ times,

Likelihood v.s. Prior The maximum likelihood estimation is to estimate the $\mu$ based on data that $P(data|parameter)$, while the prior is "your belief of the value of $\mu$" before you observe any data, $P(parameter)$.
* likelihood -- what you Observed
* prior -- what you believe

Posterior. The posterior combines the likelihood and prior that the final result should be what I observed plus what I believe. $Posterior \propto likelihood \times Prior$.

New problem arises: Given the likelihood yield such formula: $P(data|\mu= 0.5) = \prod_i \mu^{x_i}(1-\mu)^{N-x_i}$, which form is the best choice of the prior that could help "Mathematical Convenient"?

In particular, I expect the prior $\mu$ ranging from $0 \sim 1$, should be a continuous function that every value between 0 and 1 could be a possible choice.
The integral of Probability Density Function (PDF) should be 1 since $P(\mu)$ is a kind of distribution.

 
