# Data-Science-ProjectHello Everyon
Program Description - In the current Program, we did webscrapping to scrape the reviews data of a particular product from a website using the python library BeautifulSoup.
Web scraping (or data scraping) is a technique used to collect content and data from the internet and Beautiful Soup is a library that makes it easy to scrape information from web pages.
Firstly we get the url of the reviews page of the particular product and assign it witha variable named 'url' and also an empty list 'reviewlist'. Now, we have defined a function 
which returns the  'soup' object from the url which we have given to scrape the data where we give the url as a parameter,and another function to  scrape the reviews from and then append 
them into the empty list 'reviewlist' which we have created in the beginning. Finally we run a loop  with a minimum required range in which we use formatted string to change the page url 
until the required amount of data is scrapped or there no more pages left to move forward. At last we make a dataframe and then we store the data into an excel file by "df.to_excel(filename.xlsx)". 
So the data in stored in a excel file. 

The range in the final loop can be changed as per the data requirement.

"DATA-CLEANING"

1.HANDLED MISSING DATA:
In order to handle missing data, we have checked the null values in the data set using .isnull() which tells whether there are any missing values or not.
once we get to know if there are any missing values, using missingno we have previewed the missing data and later we have droped the missing data.

2.REMOVED EMOJI AND EMOTICON:
At first we have installed demoji '!pip install demoji' predefined function used to identify emoji and then we have replaced all of them with an empty string by writing a function and applyinng it on the review data in our dataset.

3.CLEAN REVIEWS:
We have written a function using replace method which replaces all the URLS, EMOJI's, PUNCTUATIONS with an empty string. 

4.WORKING ON TRANSLITERATION AND CODE MIXING:
As we observed most of the data is written in "HINGLISH" in which the hindi review is written english raised issues,currently dealing with this transliteration process and as most of the data is in this form we have to identify such reviews and must make suitable task to translate. 
Example: HINGLISH: "ye ek code mixed sentence ka example hai" => ENGLISH: "This is an example for code mixed sentence"

5.TRANSLATION:
we have tried to translate the reviews into english in which we faced issues related transliteration and code mixing. We used easynmt (opus-mt) module used to translate the reviews from other languages to english.

"PRE-PROCESSING"

1.CORRECTING SPELLINGS:
We used pyspellchecker module to correct the spelling mistakes in the translated text.

2.PREPROCESSING:
We have written functions for lemmatising the text,stemming,removing stopwords,tokenisation and applied them on the text.

"DATA-AUGMENTATION"

We had the highly biased data. In this case, if we just output that the review is positive then also we will get 95% accuracy. But before the data augmentation approach, we feed this data to a bi-lstm-based model and we got 60-70% of accuracy which was not acceptable. So we did the Data augmentation and generate more negative reviews to balance the data and after that, we got 96-97% accuracy.We used Python’s NLPAug to do the data augmentation task.

"TOPIC MODELING"

We will use Topic Modeling Technique to find aspects from the reviews.We will use the following algorithm (LDA) to do so.In general, topic modelling refers to a set of unsupervised statistical learning methods for detecting latent topics in a large number of text texts. Latent Dirichlet allocation (LDA) is the most widely employed approach in practise. And we will also use LDA for our analysis.

"MODEL"

We are done with aspect identification next we will create a model to predict sentiments on the basis of these aspects.

"TRAINING & TESTING MODEL"

We trained the data and tested our model using K-FOLD cross validation,Once we are finalised with the model now we will use the model to predict the sentiment.
