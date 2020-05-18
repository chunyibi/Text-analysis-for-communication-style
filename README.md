# Text-analysis-for-communication-style<br>
This repository contains code that is able to process PDF interview transcript and conduct text analysis (Sentiment variance and LDA topic entropy)
## Introduction
The first text-based method is a simple sentiment analysis that relies on VADER (Valence Aware Dictionary and sEntiment Reasoner) which is a lexicon and rule-based sentiment analysis tool. The second method is an unsupervised topic model through LDA (Latent Dirichlet allocation) and pairwise cosine similarity analysis. From these two text-based models, four measurements were calculated: the variance of sentiment, average negativity of responses, the average length of answers, and diversity of topics. 
## Text Data Preprocessing
<ol>
<li>Pdf to Text :Transcripts provided by Harvard Business School library are well structured, however, they are all in PDF format.  Two python packages, PyPDF2 (to convert simple, text-based PDF files into text readable) and textract were used to transform PDF files into text files;
<li> Extract interviewee and interviewer initials: Regular expressions and string slicing were used ;
<li> Write interviewee’s responses into a Pandas DataFrame for sentiment analysis: Only textual data starts with the interviewee initial and ends with the interviewer initial would be added into the data frame;
<li>Write interviewee’s total responses into a list and preprocess for the LDA model: Punctuations, “\r”, and stop-words were removed. All textual data was set to lowercase and tokenized to build a corpus for LDA modelling.
</ol>
## Text Dara Preprocessing
##Sentiment Analysis
VADER sentiment analysis is a lexicon and rule-based tool. I selected it to process our dataset because, in addition to positive and negative scores, it also provides a compound score which is a “normalized, weighted composite score” that gives unidimensional measures of sentiment for a given sentence. Each response was measured, and the length of sentences was calculated as well. <br>
There are three outputs from sentiment analysis: 1) Average negativity score 2) Standard deviation of compound scores AKA the variance of sentiment  3) Average word count.
