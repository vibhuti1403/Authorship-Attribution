# SML Authorship Attribution
## Kaggle Team Name: BayesianNoobs
### File Structure:
Papers: Folder consisting of papers referenced

Data: Folder consisting train.json and test.json

Notebooks:

    - Author_Co-Author_Graph.ipynb: Script to geneate author-coauthor network. Used to create a search space in auto encoder and stopword graph similarity.
    
    - StopwordGraph.ipynb: Generates a graph of stop words whose edge weights are based on relative position of stopwords. This graph is generated for each test paper and all authors. We then compute the Kulback leiber divergence between the stop word graph of the test paper to stop word graphs of all authors in its search space and create a similarity ranking.
    
    - Autoencoder.ipynb: For each prolific author trains an autoencoder on its abstracts and passes each test paper through all the autoencoders and ranks the authors based on the cosine similarity between the doc2vec representation of test record and the reconstructed out put of each author's associated autoencoder.

    - Classification_Approach_Cleaned.ipynb: Script to preprocess data and build a multilabel classifier. User multilabel binarizer to transform output and LabelPowerSet with LinearSVC as the classifier.

### Result: 
Highest public leaderboard F1 score: 54.8 (Multilabel Classifier: LabelPowerSet with LinearSVC)
