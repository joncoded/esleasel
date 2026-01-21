# esleasel

an LLM-powered English PDF document analyzer that

- summarizes the text
  - based on user's English language level
  - customize length of summary 
- (optionally) shows new or "difficult" vocabulary
- (optionally) shows irregular verbs
- (optionally) shows and explain idioms like "break the ice" or "hit the sack"
- allows user to chat (ask questions on or perform operations about) the document

## === demo (for casual users)

look for the link on the github repo sidebar when it launches!

## === setup (for developers)

### clone repo

run the following commands on your command line:

```
% git clone https://github.com/joncoded/esleasel.git esleasel && cd esleasel
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

### credits

* [Groq](https://groq.com) for LLMs
* [Pinecone](https://pinecone.io) for vector databases
* [Langchain](https://www.langchain.com) for its AI agent platform 
* [Streamlit](https://share.streamlit.io) for its super-easy deployment 
* [Google Gemini](https://share.google/aimode/7qI3binoXT52SrpK0) for recommending which LLM to use for analyzing English language PDFs
* [Dr. Satyajit Pattnaik](https://www.linkedin.com/in/satyajitpattnaik/) for technical guidance