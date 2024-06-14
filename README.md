# text-sentiment-analysis

The objective of this project is to extract textual data from website contains articles related to evolve of Artifical intelligence and their imapct, and performed sentiment analysis, Developed a solution to enhance content engagement by optimizing readability and emotional appeal.
# Data Extraction

Input.xlsx
For each of the articles, in the input.xlsx file, extract the article text and save the extracted article in a text file with URL_ID as its file name.
While extracting text, extracted only the article title and the article text.

### Power BI Visualization
![visual1](https://github.com/vivek1702/Blackcoffer-article-s-text-sentiment-analysis/assets/44013832/902b263a-3839-4a48-8b14-97ea024068b8)
![visual2](https://github.com/vivek1702/Blackcoffer-article-s-text-sentiment-analysis/assets/44013832/b34dd6fa-f6c0-4a72-8292-7caa19aa6f3d)
![visual3](https://github.com/vivek1702/Blackcoffer-article-s-text-sentiment-analysis/assets/44013832/31ca2ee0-47fd-461e-a1e8-a3b6ce7f8e6e)
![visual4](https://github.com/vivek1702/Blackcoffer-article-s-text-sentiment-analysis/assets/44013832/29ffe5dd-073b-432b-bb8f-c22b0eb7c06a)


## Variables 
# Sentimental Analysis
Sentimental analysis is the process of determining whether a piece of writing is positive, negative, or neutral. The below Algorithm is designed for use in Financial Texts. It consists of steps:
Cleaning using Stop Words Lists

The Stop Words Lists (found in the folder StopWords) are used to clean the text so that Sentiment Analysis can be performed by excluding the words found in Stop Words List. 
Creating a dictionary of Positive and Negative words

The Master Dictionary (found in the folder MasterDictionary) is used for creating a dictionary of Positive and Negative words. We add only those words in the dictionary if they are not found in the Stop Words Lists. 

# Extracting Derived variables
We convert the text into a list of tokens using the nltk tokenize module and use these tokens to calculate the 4 variables described below:
- Positive Score: This score is calculated by assigning the value of +1 for each word if found in the Positive Dictionary and then adding up all the values.
- Negative Score: This score is calculated by assigning the value of -1 for each word if found in the Negative Dictionary and then adding up all the values. We multiply the score with -1 so that the score is a positive number.
- Polarity Score: This is the score that determines if a given text is positive or negative in nature. It is calculated by using the formula: 
- Polarity Score = (Positive Score – Negative Score)/ ((Positive Score + Negative Score) + 0.000001)Range is from -1 to +1
- Subjectivity Score: This is the score that determines if a given text is objective or subjective. It is calculated by using the formula: 
- Subjectivity Score = (Positive Score + Negative Score)/ ((Total Words after cleaning) + 0.000001) Range is from 0 to +1

# Analysis of Readability
Analysis of Readability is calculated using the Gunning Fox index formula described below.
Average Sentence Length = the number of words / the number of sentences
Percentage of Complex words = the number of complex words / the number of words 
Fog Index = 0.4 * (Average Sentence Length + Percentage of Complex words)

Average Number of Words Per Sentence
The formula for calculating is:
Average Number of Words Per Sentence = the total number of words / the total number of sentences

Complex Word Count
Complex words are words in the text that contain more than two syllables.

Word Count
We count the total cleaned words present in the text by 
removing the stop words (using stopwords class of nltk package).
removing any punctuations like ? ! , . from the word before counting.

Syllable Count Per Word
We count the number of Syllables in each word of the text by counting the vowels present in each word. We also handle some exceptions like words ending with "es","ed" by not counting them as a syllable.

Personal Pronouns
To calculate Personal Pronouns mentioned in the text, we use regex to find the counts of the words - “I,” “we,” “my,” “ours,” and “us”. Special care is taken so that the country name US is not included in the list.

Average Word Length
Average Word Length is calculated by the formula:
Sum of the total number of characters in each word/Total number of words

reference article of analysis:https://supercelestial.medium.com/text-analysis-f40386d8f40b






