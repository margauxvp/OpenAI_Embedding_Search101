# OpenAI-Embedding-Search101

## Use Case
This Python script demonstrates how to use Azure OpenAI models to create embeddings from documents, store them in memory, and leverage vector similarity search to extract text based on a user query. The script focuses on retrieving relevant content from a knowledge base of news articles based on user queries.

## Step-by-Step Process Flow
- **Configure Connection Parameters**: Ensure you have installed the required packages listed at the beginning of the script. Set up the necessary API key, resource endpoint, and storage account connection string.
- **Tokenization (Chunking)**: This step uses the GPT2TokenizerFast from the transformers library to tokenize text and count the number of tokens in each article. This is essential for later steps.
- **Create Embeddings**: The script uses the Azure OpenAI deployment "text-embedding-ada-002" to generate embeddings for the articles' bodies. The embeddings are stored in the DataFrame.
- **Vector Search**: Utilize vector similarity to find the top N similar chunks based on user queries. The script calculates cosine similarity between the query's embedding and the embeddings of the articles' bodies to identify the most relevant content.
- **ChatGPT**: Take the top N similar texts as context and prompt the GPT-35-Turbo model to answer passage-based QnA questions. The GPT-35-Turbo model provides an answer based on the given context and the user query.

## Your turn
Please make sure to provide the required API keys, resource endpoints, and storage account connection string in the script to ensure proper execution. The script is designed to be easily extendable for various use cases involving knowledge bases and text retrieval.

### Prerequisites
An Azure Resource Group with the following services, data and models:
- Azure Machine Learning
- Azure Storage Account (you can use the one from Azure Machine Learning) and add a container _sampledata_ into your storage account. Upload the sample data from this repo named "sample_data_dayinlifeofdatascientist.json"
- Azure OpenAI Service
- - text-embedding-ada-002 model
  - gpt-35-turbo model

