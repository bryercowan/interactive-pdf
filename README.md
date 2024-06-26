This is a very simple python app that lets you upload a pdf, and ask questions about it

## How to run
1. Clone the repo
2. run `pip install -r requirements.txt`
3. run `streamlit run app.py`
4. Open the link in your browser

## How to use
1. Upload a pdf
2. Ask a question

## How it works
When a user uploads a PDF document, the `process_file()` function is called. This function uses the `HuggingFaceEmbeddings` class from `langchain.embeddings` to create embeddings of the text in the PDF. These embeddings are then used to create a `Chroma` vector store, which is a type of search index that allows for efficient similarity search.

The `process_file()` function also creates a `ConversationalRetrievalChain` from the `ChatOpenAI` model and the `Chroma` vector store. This retrieval chain is a sequence of language models and retrievers that can generate responses to user queries.

When a user enters a query, the `handle_userinput()` function is called. This function uses the `ConversationalRetrievalChain` to generate a response to the user's query. The response includes the answer to the query and the page number of the source document of the response.

The `main()` function is where the Streamlit interface is set up. It creates an interface with two columns: one for the user to upload a PDF and ask questions, and one to display the pages of the PDF that are relevant to the user's queries.
```
