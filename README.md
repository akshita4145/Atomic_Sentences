OVERVIEW
train.csv contains the entire train csv file from wikisplit. 
create_subset.ipynb created a subset of 200 from train.csv and stored it into train_subset.csv.
preprocessing.ipynb then cleaned the data in train_subset.csv and stored in train_subset_cleaned.csv. 
splitter.ipynb file uses spacy to split each sentence into tokens. The tokenized sentences are stored in tokenized_data.csv.
Finally, sentence_extractor_v1.ipynb begins to split the tokenized data into atomic sentences. These newly formed sentences are stored in split_sentences_v1.csv.

DATA
train.csv: contains the entire train csv file from wikisplit. 
train_subset.csv: contains a subset of 200 random inputs from train.csv.
train_subset_cleaned.csv: contains the cleaned, preprocessed data of train_subset.csv. 
tokenized_data.csv contains the tokenized sentences of train_subset_cleaned.csv.
split_sentences_v1.csv contains the atomic sentence generation based off of the tokenized_data.csv.
