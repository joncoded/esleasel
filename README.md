# ESL-easel

an LLM-powered English PDF document analyzer that: 

- summarizes the text
  - based on user's [English language level](https://gemini.google.com/app/07122657eb7689dc)
  - customize length of summary 
- (optionally) shows new or "difficult" vocabulary
- (optionally) shows irregular verbs
- (optionally) shows and explain idioms like "break the ice" or "hit the sack"
- allows user to chat (ask questions on or perform operations about) the document
- allows for localization of user interface

!["screenshot of esleasel"](https://cdn.sanity.io/images/b148t9sa/production/70a6f16f1af2dca9414c97a6a637db19f135f9c1-931x926.png)

## Demo (for casual users)

Run the demo on [esleasel.streamlit.app](https://esleasel.streamlit.app)

(If the app has "fallen asleep" then please press the "Yes, get this app back up!" button to "wake" it up!)

!["app has fallen" asleep](https://media2.dev.to/dynamic/image/width=1000,height=420,fit=cover,gravity=auto,format=auto/https%3A%2F%2Fdev-to-uploads.s3.amazonaws.com%2Fuploads%2Farticles%2Fhm0wrzfg9ojk6rozzl64.png)

## Screenshots

!["screenshot of esleasel showing summary"](https://cdn.sanity.io/images/b148t9sa/production/77abe7fb8ba57a16033e74a6953081c0f8f0476a-873x951.png)

!["screenshot of esleasel showing idioms"](https://cdn.sanity.io/images/b148t9sa/production/b9bb778ee0713dc4508fcf2d0fdeb21aeae188f5-905x784.png)

!["screenshot of eslease showing chat"](https://cdn.sanity.io/images/b148t9sa/production/3240fb9a64fcd879d6990b06dd94e9f095ffe18b-982x1079.png)


## Setup (for developers)

### clone repo

Run the following commands on your command line:

```
% git clone https://github.com/joncoded/esleasel.git esleasel && cd esleasel
% pip install -r requirements.txt
```

### .env file

Configure your `.env` file on the root folder (this must be done or the code will tell you to):

```
LLM_API_KEY=your_groq_api_key
PINECONE_API_KEY=your_pinecone_api_key
PINECONE_HOST=your_pinecone_host_url
PINECONE_INDEX=your_pinecone_index_name
```

If you don't have these you can get them for free at:

* [groq](https://console.groq.com/keys)
  * `LLM_API_KEY` : create api key > copy and paste an API key 
    * you can later use the same API key for any large language model
* [pinecone](https://app.pinecone.io/)
  * `PINECONE_API_KEY` : on the sidebar  
    * click "API keys"
    * click on the "+ API key" button 
      * (modal will pop up) enter an API key name 
      * click on the "Create key" button
      * copy and paste the API key
  * `PINECONE_HOST` : on the sidebar
    * click "Database" 
    * click on the "Create index" button
      * leave everything default except for **Dimensions: 768** (not 1024)
      * click on the "Create index" button
      * click the "Database" link on the sidebar again 
      * copy and paste the host (looks like a URL)
  * `PINECONE_INDEX` : 
    * if you got the host URL you will see the pinecone index name above it

### Runtime!

Finally, back in the command line, run the app on your localhost with:

```
streamlit run app.py
```

The app will usually run with the url `http://localhost:8501` 

(if port 8501 is already used, it will host the app on `:8502` or so on...)

## Contribute

### Features

Make changes by following this procedure: 

* clone the repository as mentioned above
* create a feature branch
  * `git checkout -b feature/branch`
* make and commit your changes
  * `git commit -m "what you changed"`
* push your changes
  * `git push origin feature/branch`
* open pull request
  * https://github.com/joncoded/esleasel/pulls 
  
Also, feel free to [raise any issues](https://github.com/joncoded/esleasel/issues)!

### Localization

Translate the app into your language! 

* edit the `local.py` dictionary file by adding a new language (see `en` (English) and `fr` (French) as examples
* go to `app.py` and check/change the `lang_options` variable
* optionally, make a pull request as if making a Feature contribution as listed above

## Credits

* [Groq](https://groq.com) for LLMs
* [Pinecone](https://pinecone.io) for vector databases
* [Langchain](https://www.langchain.com) for its AI agent platform 
* [Streamlit](https://share.streamlit.io) for its super-easy deployment 
* [Google Gemini](https://share.google/aimode/7qI3binoXT52SrpK0) for recommending which LLM to use for analyzing English language PDFs
* [Dr. Satyajit Pattnaik](https://www.linkedin.com/in/satyajitpattnaik/) for technical guidance