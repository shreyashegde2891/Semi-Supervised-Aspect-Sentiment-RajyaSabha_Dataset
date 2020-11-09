Folders and Source Codes: 

		Semi-Supervised-Aspect-Sentiment-RajyaSabha_Dataset/Data Prep and LDA/create_train_csv.ipynb 
		--> Clean and transform data, to create intermediate training file for unsupervised Attention Based Aspect Extraction
		    (folder structures in the source code need to be changed with relevent paths)
							
		Semi-Supervised-Aspect-Sentiment-RajyaSabha_Dataset/Data Prep and LDA/LDA.ipynb
		--> determine the aspect size(number of clusters) that provide the best coherence score. The aspect size value is used 
			as an input seed in unsupervised ATAE

		Semi-Supervised-Aspect-Sentiment-RajyaSabha_Dataset/Unsupervised ATAE/<input_dir>
		--> Cleaned and transformed dataset needed for unsupervised ATAE will go into this location. 
		    (Since this is an intermediate file, it is not checked in due to size constraints)
		
		Semi-Supervised-Aspect-Sentiment-RajyaSabha_Dataset/Unsupervised ATAE/word2vec.ipynb
		--> Source to create word2vec model
		
		Semi-Supervised-Aspect-Sentiment-RajyaSabha_Dataset/Unsupervised ATAE/train.ipynb		
		--> Train the model to generate aspect terms and categories
		
		Semi-Supervised-Aspect-Sentiment-RajyaSabha_Dataset/Supervised ABSA/input_data/input.csv
		--> Input dataset for supervised ABSA. Aspect terms and sentiment labels are generated from unsupervised ATAE model
		
		Semi-Supervised-Aspect-Sentiment-RajyaSabha_Dataset/Supervised ABSA/train.ipynb
		--> Training Supervised ABSA models for TC-LSTM, TD-LSTM, ATAE-LSTM and MEMNET


Results:
LDA coherence Scores:

Topic Size	Coherence Score
	3			0.2748
	6			0.2903
	9			0.2819
	12			0.2994
	15			0.33
	18			0.3397
	21			0.3309
	24			0.3318
	27			0.3312

Unsupervised ATAE: 
										precision    recall  f1-score   support

                            Aviation       0.90      0.95      0.93        20
                 Banking and Finance       0.88      0.94      0.91        16
                         Commodities       0.88      0.98      0.93        46
Disabled, Children and Women welfare       0.90      0.90      0.90        21
                           Education       1.00      1.00      1.00        36
                     Foreign Affairs       1.00      0.89      0.94        19
              Information governance       1.00      0.95      0.98        22
                                Misc       0.94      0.67      0.78        87
                                 Ore       0.82      0.95      0.88        19
          Organisation and Companies       0.77      1.00      0.87        10
                               Power       0.90      0.97      0.93        29
                            Railways       0.96      1.00      0.98        47
                 Road Infrastructure       0.92      0.96      0.94        23
                     SME and Tourism       0.76      0.80      0.78        20
                             Schemes       0.96      0.89      0.93        28
                   Telecommunication       0.56      0.93      0.70        15
                            Violence       1.00      0.95      0.98        21
                               Water       0.78      0.86      0.82        21

                         avg / total       0.91      0.90      0.90       500


Supervised ABSA:

	Model	Embedding_Type	Accuracy	F1
	TC-LSTM   word2vec	      0.81		0.8
	TC-LSTM   GloVe	          0.85		0.84
	TD-LSTM   word2vec	      0.84		0.82
	TD-LSTM   GloVe	          0.86		0.85
	ATAE-LSTM   word2vec	  0.89		0.88
	ATAE-LSTM   GloVe   	  0.9		0.89
	MEMNET    word2vec	      0.54		0.39
	MEMNET    GloVe	          0.54		0.39
	
	
glove.42B.300d.zip needs to be downloaded, zipped and placed in Semi-Supervised-Aspect-Sentiment-RajyaSabha_Dataset/Supervised ABSA/data/
