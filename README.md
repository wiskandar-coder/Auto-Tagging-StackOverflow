# Automatic Categorization of Questions
The project is to automatically suggest tags for SlackOverflow users from the title and the body of their questions. For that, I will be testing multiple supervised and unsupervised machine learning technique and train them on more than 100k SO questions..

![image](https://github.com/wiskandar-coder/Auto-Tagging-StackOverflow/assets/64427335/cb1625a1-58b5-4a91-af3c-a65d57fd4b73)

- Exploration in 'Exploration_notebook'
  - I will start with the treatment of questions and tags according to these steps:
    - I will be extracting first questions from SlackOverflow, performing cleaning on the questions by removing links, English contractions, adverbs, and float numbers in title and body of the questions.
    - Then, I will tokenize the words in title and body of the questions, removing stop words, adjective and adverbs, and finally normalize using lemmatizer or stemmer.
    - Third, I will select the tags that appeared in at least 30 questions and keep all questions with at least 5 tags.
    - Fourth, I will select the words in title-body of the questions that appeared in at least 30 questions and keep all title-body questions that have at least 10 words.
    - Fifth, I will create bigram and trigram in the title-body of the questions.
  - I will analyse the words frequency in title and body of the questions, the tags frequency, the words number of the questions, and perform dimension reduction to show the distribution of questions in 2D.
  - Finally, I will extract the data for the modelisation.
  
- Modelisation in 'Testing_notebook'
  - I will start testing some supervised learning approach to extract feature using count vectorizer, and TF-IDF, then switch to Word2Vec, BERT, and USE. I will use multiple machine learning algorithm like RansomForest, KNN, LogisticRegression, MultinomialNB, and SGDClassifier to predict tags and then compare with the true tags in the question.
  - Second, I will use unsupervided learning approach to extract feature using LDA combined with count-vectorizer and NMF combined with TF-IDF.
  - Finally I will select the best modelisation approach for the next API step

- Application in https://github.com/wiskandar-coder/Auto-Tagging-Stackoverflow-API
  - An app will serve as a test where the user enter the title and the body of the questions, and the application will suggest tags for the user.
  - The application is deployed in HEROKU; the link to the app and API: https://auto-tagging-stackoverflow.herokuapp.com/

A powerpoint presentation of the project can be shared under request.
