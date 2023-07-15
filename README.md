# pergle
> persian information retrieval system

## Overview
The Persian Information Retrieval (IR) System is a powerful tool for searching and retrieving documents in the Persian language. It utilizes a range of techniques, including tokenization, normalization, stemming, and positional indexing, to enhance the accuracy and efficiency of the search process.

## Features

- Tokenization: The system breaks down documents and queries into individual words, eliminating stopwords and punctuation marks to extract relevant terms.
- Normalization: The system applies Unicode normalization to standardize characters and ensure consistency in word representation.
- Stemming: Using the Hazm library, the system reduces words to their root form, enhancing search precision by considering different inflections of a word as a single term.
- Positional Indexing: The system constructs a positional index that tracks the positions of terms within each document. This allows for advanced queries involving phrase search and proximity matching.
- Cosine Similarity: The system employs cosine similarity to rank documents based on their relevance to a given query. This technique measures the similarity between the query vector and document vectors, enabling effective retrieval of relevant documents.
- Champion Lists: By implementing champion lists, the system optimizes search efficiency by considering a subset of highly relevant documents for each term, reducing the number of comparisons required during retrieval.

## Usage

1. Install the required dependencies by running `pip install -r requirements.txt`.
2. Load your Persian documents into the system. Make sure they are in a compatible format (e.g., JSON).
3. Preprocess the data by executing the `preProcess` function, which includes steps like normalization, tokenization, stopword removal, lemmatization, and stemming.
4. Build the positional index using the `positional_indexing` function, which constructs an index of terms with their corresponding document positions.
5. Perform queries using the available query services (`query_service`, `cosine_score`, etc.) by providing the desired search terms or phrases.
6. Retrieve and display the relevant documents based on the query results.

## Example


   ```python
   # Load and preprocess the data
   json_data = load_data("path/to/data.json")
   preprocessed_docs = preProcess(json_data)
   
   # Build the positional index
   positional_index = positional_indexing(preprocessed_docs)
   
   # Perform a query
   query = "example query"
   results = query_service(query, positional_index)
   
   # Display the retrieved documents
    for doc_id, score in results:
        print(f"Document ID: {doc_id}")
        print(f"Score: {score}")
        print(json_data[doc_id]['title'])
        print(json_data[doc_id]['url'])
        print(json_data[doc_id]['content'])
       print("-------------------------------")
   ```
