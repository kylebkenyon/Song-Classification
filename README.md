"# My project's README" 

General flow of the program is:
1. Collect Artists - Collects a list of musical artists by examining the html of the first 50 pages of the website 
"Best Ever Albums." This ultimately provides about 50,000 songs as data for the training set.

2. Artist Classifier (Data Collection) - Given the list of artists from above, Data Collection accesses first the 
Last.FM API to find a list of popular albums and then songs for each artist given, and then access the Genius API
to collect the lyrics for each of those songs.

3. Artist Classifier (Data Processing) - Data processing then takes the mapped artist to lyrics data and cleans it.
This involved removing punctuation, capitalization, and stop words, then stemming the words to their base forms. 
Then the words are counted, given frequencies and sorted by frequency (Data analysis tested across many different 
vocabulary sizes).

4. Artist Classifier (Data Analysis) - Each song is now a bag of clean word frequencies. Data analysis runs three 
different learning models on the data in order to find the most accurate predictor. Within these three models, it 
also tests different numbers of artists to classify. Anywhere from a binary 2 artist classification to 1082 artists.
The three models are Naive Bayes, Naive Bayes with term frequency - inverse document frequency, and SVM. These were
tested across several different parameters such as vocabulary size.