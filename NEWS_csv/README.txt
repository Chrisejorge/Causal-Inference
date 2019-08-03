

The News dataset contains 50 realisations of a stochastic outcome model. 
Each realization is contained in two different files (.x and .y) because
the features of the dataset are sparse. For example: 
csv/topic_doc_mean_n5000_k3477_seed_1.csv.x
csv/topic_doc_mean_n5000_k3477_seed_1.csv.y

The .y file contains 5 columns: 
treatment, y_factual, y_counterfactual, mu0, mu1

mu0 are the control responses without added noise, and mu1 the treatment responses without noise. Note that these do not correspond to y_factual or y_counterfactual (which have both control and treated individuals). The true underlying treatment effect is thus mu1-mu0. Training should be done with treatment and y_factual only.

The .x file contains a sparse representation of the features. 
The first row of the .x file contains the number of rows and columns of 
the corresponding dense matrix. In this case n=5000 rows, d=3477 features. 
Each following row represent an element in the matrix on the form: i,j,v
where i is the row index, j the column index and v the value. 
The data represents word counts in documents, so 1,16,1 means that word 16
occurred 1 time in document 1. 

Example .x file: 

5000,3477,0
1,16,1
1,21,1
1,35,1
1,62,2
1,87,1
1,97,1
…

