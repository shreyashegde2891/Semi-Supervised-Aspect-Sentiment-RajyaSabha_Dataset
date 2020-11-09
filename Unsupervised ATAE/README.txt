Steps to execute: 
1) word2vec.ipynb --> create a skipgram word2vec model for the input sentences. 
2) train.ipynb --> To train an unsupervised model to determine aspect terms and aspect categories

Other files:
model.ipynb --> implementation details for the model 
optimizers.ipynb --> optimization algorithms with hyperparameters configured
coherence_word2vec.ipynb --> determining the coherence scores for models created with varying batch size, optimization algorithms and learning rates
evaluation.ipynb --> if pre-labelled aspects are available, the labels can be loaded in test
create_labelled_set.ipynb --> determine aspect terms for the raw input, by loading the model parameters built and contains implementation of VADER to determine sentiment labels.

input_csv/ folder contains the cleaned and transformed dataset. 