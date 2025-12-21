Introductory Workflow: From Google Drive Data to Vector Database


This workflow demonstrates a basic pipeline for converting and storing data from Google Drive into a vector (embedding-based) database.

It supports various text-based file formats stored in Google Drive and transforms them into vector representations for later use (e.g. search, retrieval, or AI-powered applications).



Credentials & Services Used


This workflow can use the following credentials and services:

Personal Google Drive credentials – to access and download files

OpenAI (or Google Gemini) AI models – for text embeddings

Pinecone (online vector database) – for storing and managing vectorized data via its API

Additional configuration options can be adjusted depending on the use case.



Workflow Structure & Configuration


Google Drive (Search Node)

Used to locate the target file

Search can be performed by file name or folder

Can be scheduled based on specific use cases

Google Drive (Download Node)

Downloads the file using the selected file ID from the search step

Default Data Loader

Required to load and normalize the downloaded content

Text Splitting (Custom Configuration)

Text splitting is configured manually

A chunk size of 1000 is recommended for converting text into vectors

Embedding Models

Supported models include:

Google Gemini

text-embedding-3-small (OpenAI)

Pinecone (Vector Database Node)

The target database/index name is defined in the Namespace section

The embedding size can remain at the default value (200) for standard use cases


Result

Using this workflow, text data from Google Drive is processed, split, embedded using AI models, and stored in a vector database.
This enables future applications such as semantic search, retrieval-augmented generation (RAG), and other AI-driven workflows.