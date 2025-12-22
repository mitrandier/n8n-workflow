Introductory Workflow: From Google Drive Data to Vector Database

This workflow demonstrates a basic pipeline for converting and storing data from Google Drive into a vector (embedding-based) database.

It supports various text-based file formats stored in Google Drive and transforms them into vector representations for later use (e.g. search, retrieval, or AI-powered applications).


Credentials & Services Used

This workflow can use the following credentials and services:

Personal Google Drive credentials – to access and download files

OpenAI (or Google Gemini) AI models – for text embeddings

Pinecone (online vector database) – for storing and managing vectorized data via its API

Additional configuration options can be adjusted depending on the use case.


Workflow Structure & Configuration:


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





Chat Extension (Conversational Workflow)

Following the data ingestion and vectorization workflow, a separate chat-based workflow is added to enable conversational access to the stored data.

This chat workflow is independent from the ingestion pipeline but operates on the same vector database.



Chat Trigger

A dedicated chat trigger is added separately from the previous workflow

It listens for user messages and initiates the conversational process



AI Agent

An AI Agent node is added after the chat trigger

In the system prompt, the agent is instructed to:

Act as a helpful assistant

When the user asks questions related to specific topics (e.g. X, Y, Z),
refer to the Information tool to retrieve the required data


Chat Model

A chat model is configured using OpenAI credentials via OpenRouter

This model is responsible for generating the final responses


Chat Memory

A chat memory tool is enabled

Depending on the use case, the last 5 to 10 previous messages are used as conversational memory

This helps preserve context across multiple turns


Tools – Vector Database (Information)

The Pinecone vector tool is added as an agent tool

This tool represents the vector database created earlier

The tool name is changed to Information so it can be explicitly referenced in the system prompt

The description specifies that this tool contains domain-specific knowledge


Embedding Configuration

Custom options are enabled

The embedding model is selected based on how the vectors were originally stored:

OpenAI

Google Gemini

or other supported providers

For OpenAI-based embeddings, text-embedding-3-small is used


Final Outcome

With this extension, users can interact with their data through natural language queries.
The system retrieves relevant context from the vector database and produces accurate, context-aware answers.

Together, these workflows form a complete RAG-based system, combining:

Data ingestion

Vector storage

Intelligent retrieval

Conversational AI