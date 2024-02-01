# Project Documentation: Generating Embeddings from JSON and CSV Data

## Table of Contents
- [Introduction](#introduction)
- [Methodologies Implemented](#methodologies-implemented)
  - [JSON Data](#json-data)
    - [Loading JSON Data](#loading-json-data)
    - [Extracting Text from Data](#extracting-text-from-data)
    - [Text Preprocessing](#text-preprocessing)
    - [Loading the Pre-Trained Model for JSON Data](#loading-the-pre-trained-model-for-json-data)
    - [Generating Embeddings for JSON Data](#generating-embeddings-for-json-data)
  - [CSV Data](#csv-data)
    - [Loading CSV Data](#loading-csv-data)
    - [Loading the Pre-Trained Model for CSV Data (GPT-2)](#loading-the-pre-trained-model-for-csv-data-gpt-2)
    - [Tokenization and Model Inference](#tokenization-and-model-inference)
    - [Calculating Embeddings](#calculating-embeddings)
- [Code Execution](#code-execution)
- [Usage](#usage)
- [Conclusion](#conclusion)

## Introduction
This project focuses on generating embeddings for text data from both JSON and CSV formats using different methodologies and models. Embeddings are numerical representations of text that capture semantic information and are widely used in natural language processing tasks.

## Methodologies Implemented:

### JSON Data:
- **Loading JSON Data**:
  - The JSON data containing textual entries is loaded from the specified file path into the Python environment using the `json.load()` function.
- **Extracting Text from Data**:
  - A function is defined to extract textual content from the JSON data. The function recursively traverses the JSON structure and concatenates text from specific fields.
- **Text Preprocessing**:
  - Text preprocessing is performed using the `simple_preprocess()` function from Gensim. This step tokenizes the text and performs basic preprocessing tasks such as lowercasing and punctuation removal.
- **Loading the Pre-Trained Model for JSON Data**:
  - The GoogleNews-vectors-negative-300 model, a pre-trained Word2Vec model, is used to generate word embeddings from JSON data. Trained on Google News articles, it captures semantic relationships between words by predicting context-based associations.
  - **Model Overview**:
    - Utilizing Word2Vec, the model represents words as dense vectors in a continuous space, mapping similar words closer together. It learns these representations by predicting surrounding words given a target word.
  - **Importance in NLP**:
    - The GoogleNews-vectors-negative-300 model provides high-quality word embeddings crucial for tasks like translation, sentiment analysis, and information retrieval. These embeddings enhance models' understanding of textual semantics, improving accuracy in language tasks.
  - **Utilization in the Project**:
    -The model generates word embeddings for JSON data, capturing semantic nuances and aiding downstream NLP tasks. By leveraging pre-trained embeddings, the project benefits from rich semantic representations for accurate analysis and interpretation of JSON text.
- **Generating Embeddings for JSON Data**:
  - Word embeddings are generated for the preprocessed text using the pre-trained Word2Vec model. The embeddings capture the semantic meaning of words in a continuous vector space.

### CSV Data:
- **Loading CSV Data**:
  - The CSV data containing text lines is loaded into a pandas DataFrame. The file path is specified, and the CSV data is read into the `dataset` variable.
- **Loading the Pre-Trained Model for CSV Data (GPT-2)**:
  - The GPT-2 model from the transformers module is utilized for generating embeddings. The model architecture is based on the Transformer architecture and is pre-trained on vast amounts of text data.
- **Tokenization and Model Inference**:
  - Each line is tokenized using the GPT2 tokenizer, and the tokenized sequence is passed through the GPT-2 model to obtain embeddings.
- **Calculating Embeddings**:
  - The last hidden state of the model output is extracted and averaged across tokens to obtain a single embedding vector for each line in the dataset.

## Code Execution:
The code iterates through each line in the CSV dataset or extracts text from the JSON data, tokenizes the text, generates embeddings using the appropriate model or methodology, and prints the embeddings for each line or entry.

## Usage:
- To use the code:
  1. Ensure to install the necessary libraries using `pip` command

  ```bash
  pip install transformers torch pandas numpy json gensim
  ```

  3. Provide the path to the CSV file containing the text data or the JSON file with textual entries.
  4. Run the code to generate embeddings for each line or entry in the dataset.
  5. For JSON data GoogleNews-vectors-negative-300 model is used. You csn download it using this [drive link.](https://drive.google.com/file/d/0B7XkCwpI5KDYNlNUTTlSS21pQmM/edit?resourcekey=0-wjGZdNAUop6WykTtMip30g)

## Conclusion:
- These projects demonstrate how to leverage pre-trained language models like GPT-2 and Word2Vec to generate embeddings for textual data from both JSON and CSV formats. Embeddings capture the semantic meaning of text and can be used as input features for various downstream NLP tasks such as classification, clustering, and semantic similarity calculation.
