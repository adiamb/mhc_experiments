# Introduction

Regularizations attempts in part 1 have been successfull in the sense that we coudl prevent the model from overfitting by tuning dropout and various other parameters. 
However we still dont have our LSTM at the performance we were hoping for, so the hyperparamater chasing continues.

A) So in what follows I tried some more random ideas son the embedding side as it appears that it has great effect on the performance curve due to adding embedding dropout highly impacted the behaviour of the AUC performance curve. So two things we are going to try is:
* masking zeros vs padding 
* compare bidirectional LSTM with both LSTMs having the same embedding vs bidirectional LSTM with both LSTMs having individual embeddings (vs a simple LSTM)
* look at the embedded vectors and see what it looks like after PCA-ing or TSNE-ing them, maybe there is an interesting relationship to spot, or maybe there is anomly in the sense that some amino acids are far away form each other when they shoudln't. 


B) Another more fundamental question is how is LSTM performing wrt FFNN and sigmoid and linear model on 9 mers vs non 9 mers. One would expect that LSTM to perform better on non 9 mers due to the surplus on information, and if this is not true, this clearly hints towards a major inefficiency in the LSTM model. 

C) In hope of exposing X, we will give some toy dataset to the LSTM constructed upon the current dataset, and see whether there are some inefficiencies being exposed. One could feed the LSTM with some more or less obvious patterns to learn and see if it indeed gets 100% accuracy. 

D) A little side idea that came up (and maybe somehow related to C) is to approximate peptides with their first 3 amino acids and last three amino acids, and see how well LSTM and FFN are performing. This might give us an idea how relevant the middle piece really is, and whether more data is actually confusing the model rather than helping them. The idea comes from the fact that binding affinities tend to be rather influenced by what happens towards to ends of the peptide.

E) Another parameter that we will explore is the learning rate, for some reason we have completely overlooked this parameter, and it appears to be the most important paramater for LSTMs. 

Lets dive into it. 

# A) Embedding analysis

## A1) Masking zeros vs padding in the embedding layer

## A2) embedding vs bi-embedding for bidirectional LSTM

## A3) Representing embedding vectors via PCA and t-SNE

# B) All vs 9 mer vs non- 9 mer analysis

# C) Toy datasets

# D) Approximation of peptides 

# E) Learning rate analysis 
