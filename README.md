Mental Health Chatbot Project
Overview
This project involves developing a mental health chatbot using FastAPI, designed to provide empathetic responses and suggest relevant articles based on user queries. The chatbot uses machine learning models for text classification and retrieval-augmented generation (RAG) techniques to enhance user interactions.

Technologies Used
FastAPI

Purpose: Web server framework
Function: Manages HTTP requests, processes input data, and returns responses.
Uvicorn

Purpose: ASGI web server
Function: Runs the FastAPI application, allowing it to handle multiple requests efficiently.
NLTK (Natural Language Toolkit)

Purpose: Natural language processing (NLP) library
Function: Provides tools for tokenization, stopword removal, and lemmatization to preprocess text data.
Scikit-learn

Purpose: Machine learning library
Function: Used for vectorizing text data (TF-IDF), splitting datasets, training a Logistic Regression model, and making predictions.
Pandas

Purpose: Data manipulation and analysis library
Function: Loads and processes CSV data, handles dataframes, and performs data cleaning and preprocessing.
Requests

Purpose: HTTP library
Function: Sends POST requests to external APIs, including querying the Hugging Face API for language model responses.
Project Approach
Data Loading and Preprocessing

Data Sources: JSON files for article data, CSV files for additional questions and classification data.
Text Processing: NLTK is used to remove stopwords, tokenize, and lemmatize text.
Text Classification

Dataset Splitting: Classification data is divided into training and testing sets.
Vectorization: TF-IDF is used to convert text data into numerical features.
Model Training: A Logistic Regression model is trained on the TF-IDF features to classify text into predefined categories.
Article Search

Query Processing: User queries are preprocessed, and relevant articles are searched based on matching tokens in titles and summaries.
Direct Answers: Searches additional questions data to find direct answers to user queries.
Response Construction

Empathetic Responses: Generates supportive statements based on user queries.
Article Suggestions: Includes relevant articles in the response if found.
Fallback Responses: Constructs a prompt and queries the Hugging Face API if no direct answers or articles are found.
FastAPI Endpoint

Endpoint Definition: A /process endpoint handles user queries.
Response Generation: Processes input, performs classification, searches for articles, and constructs a response.
Model Querying and Fallback Mechanism
Query Sequence: Constructs a prompt and queries Hugging Face API models (BLOOM, GPT-2, GPT-Neo) sequentially.
Error Handling: Returns a generated response if successful; otherwise, generates an error message.
Summary
The mental health chatbot combines NLP, machine learning, and RAG techniques to provide empathetic and relevant responses to user queries. The integration of these technologies ensures efficient request handling and accurate, supportive interactions based on user input.
