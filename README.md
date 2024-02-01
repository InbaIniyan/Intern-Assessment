# Intern-Assessment : Generating Embeddings from CSV Data

## Introduction
This project aims to generate embeddings for each line in a CSV dataset using the GPT-2 model. Embeddings are numerical representations of text that capture semantic information and are useful for various natural language processing tasks.

## Components:
The project consists of the following components:

### 1. Importing Libraries
The necessary libraries are imported to facilitate data processing, model loading, and embedding generation. The libraries include:
- `transformers`: for loading the GPT-2 model and tokenizer.
- `torch`: for tensor operations.
- `pandas`: for reading and handling CSV data.

### 2. Loading the Pre-Trained Model
The GPT-2 model from the transformers module is utilized for generating embeddings. The model architecture is based on the Transformer architecture and is pre-trained on vast amounts of text data.

### 3. Loading the CSV Data
The CSV data containing text lines is loaded into a pandas DataFrame. The file path is specified, and the CSV data is read into the `dataset` variable.

### 4. Generating Embeddings
Embeddings are generated for each line in the dataset using the GPT-2 model. The following steps are performed iteratively for each line:
- **Tokenization**: Each line is tokenized using the GPT2 tokenizer.
- **Model Inference**: The tokenized sequence is passed through the GPT-2 model to obtain embeddings.
- **Calculating Embeddings**: The last hidden state of the model output is extracted and averaged across tokens to obtain a single embedding vector for the line.
- **Output**: The vector form of the embeddings for each line is printed.

## Code Execution:
The code iterates through each line in the CSV dataset, tokenizes the text, generates embeddings using the GPT-2 model, and prints the embeddings for each line.

## Usage:
To use the code:
1. Ensure that the necessary libraries are installed using the command transformers, torch, and pandas.

   ```pip install tarnsformers torch pandas```
   
2. Provide the path to the CSV file containing the text data [d1.csv](Assessment/data/d1.csv).
3. Run the code to generate embeddings for each line in the dataset.

## Conclusion:
This project demonstrates how to leverage pre-trained language models like GPT-2 to generate embeddings for textual data. Embeddings capture the semantic meaning of text and can be used as input features for various downstream NLP tasks such as classification, clustering, and semantic similarity calculation.
