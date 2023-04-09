The following model has been developed in Java and is a text search and filtering pipeline in Apache Spark that is capable of handling large 
sets of text documents and user-defined queries. The pipeline takes in the documents and queries, 
removes stopwords (words with little discriminative value) and applies stemming to each document and query.

For each query, the pipeline ranks the documents by relevance using the DPH ranking model and returns the top 10 documents. 
To ensure that the final ranking does not contain overly similar documents, a comparison function is applied to the titles of each pair of documents. 
If the textual distance between two documents' titles is less than 0.5, only the most relevant document (based on DPH score) is kept.

It's important to note that the final output still contains 10 documents per query, even after redundancy filtering.
