
# Entrenamiento modelo LLM

The competition dataset consists of user interactions from the ChatBot Arena. In each user interaction a judge provides one or more prompts to two different large language models, and then indicates which of the models gave the more satisfactory response. The goal of the competition is to predict the preferences of the judges and determine the likelihood that a given prompt/response pair is selected as the winner.

Please note that this is a Code Competition. When your submission is scored, this example test data will be replaced with the full test set. There are 55K rows in the training data, and you can expect roughly 25,000 rows in the test set.

## Files

**train.csv**

* id - A unique identifier for the row.
* model_[a/b] - The identity of model_[a/b]. Included in train.csv but not test.csv.
* prompt - The prompt that was given as an input (to both models).
* response_[a/b] - The response from model_[a/b] to the given prompt.
* winner_model_[a/b/tie] - Binary columns marking the judge's selection. The ground truth target column.

**test.csv**

* id
* prompt
* response_[a/b]

**sample_submission.csv**
A submission file in the correct format.

* id
* winner_model_[a/b/tie] - This is what is predicted from the test set.

## Submission
For each id in the test set, you must predict the probability for each target class. The file should contain a header and have the following format:

 id,winner_model_a,winner_model_b,winner_tie
 136060,0.33,0,33,0.33
 211333,0.33,0,33,0.33
 1233961,0.33,0,33,0.33
 etc

# Citation

Wei-lin Chiang, Lianmin Zheng, Lisa Dunlap, Joseph E. Gonzalez, Ion Stoica, Paul Mooney, Sohier Dane, Addison Howard, and Nate Keating. LLM Classification Finetuning. https://kaggle.com/competitions/llm-classification-finetuning, 2024. Kaggle.
