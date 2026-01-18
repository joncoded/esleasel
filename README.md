# docotoco

an LLM-powered PDF document specialist for all domains:

- summarizes documents
  - customize length of summary 
- (optionally) gather sentiment analysis
- (optionally) find list of names of people and organizations
- allows user to chat (ask questions on or perform operations about) the document

## === setup

### clone repo

run the following commands on your command line:

```
% git clone https://github.com/joncoded/docotoco.git docotoco && cd docotoco
% pip install -r requirements.txt
```

### .env file

configure your `.env` file on the root folder (this must be done or the code will tell you to):

```
LLM_API_KEY=your_groq_api_key
PINECONE_API_KEY=your_pinecone_api_key
PINECONE_HOST=your_pinecone_host_url
PINECONE_INDEX=your_pinecone_index_name
```

### run it!

finally, back in the command line, run the app:

```
streamlit run app.py
```

### localization

* translate the app into your language with the `local.py` dictionary file
* go to `app.py` and check/change the `lang_options` variable