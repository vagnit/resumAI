
# ResumAI
![Resume Image](resum_ai/resume.png)

ResumAI -- a resume assistant application. This app matches you to jobs, offers recommendations, and optimizes your resume using DataStax's AI Platform: [Astra DB](https://www.datastax.com/lp/managed-cassandra-in-cloud?utm_source=google&utm_medium=cpc&utm_campaign=ggl_s_nam_nonbrand_cassandra&utm_term=apache%20cassandra%20data%20model&utm_content=cassandra-apache&gad_source=1) (Vector Database) and [Langflow](https://www.datastax.com/products/langflow) (Visual AI Application Builder).

  

## Getting Started
To build this app you will need the following prerequisites:

* Python 3.10 or higher

* [OpenAI Account](https://platform.openai.com/signup)

* DataStax account to store your vector embeddings and build the GenAI pieces of the workflow. If you do not have one already, [sign up for a free DataStax account here.](https://astra.datastax.com/signup)

## Ingesting The Data
1.  Clone this [GitHub repository](https://github.com/melienherrera/resumAI/tree/main)

>     git  clone  https://github.com/melienherrera/resumAI.git

2. Navigate to the `.env-example` file. Create a copy called `.env` and replace the variables with your actual credentials. You will need your:
 - [OpenAI API Key](https://platform.openai.com/docs/quickstart#create-and-export-an-api-key)
 - [Astra DB Endpoint and Application Token](https://docs.datastax.com/en/astra-db-serverless/administration/manage-application-tokens.html#database-token) (which you can retrieve from your database dashboard)

>     # Astra  DB  API  Endpoint
>     ASTRA_DB_API_ENDPOINT=https://your_astra_db_api_endpoint
> 
>     # Astra  DB  Application  Token 
>     ASTRA_DB_APPLICATION_TOKEN=your_astra_db_application_token
> 
>     # OpenAI API key  
>     OPENAI_API_KEY=your_openai_api_key

3.  Open up the repository in an editor (I personally use Visual Studio code) and [run a python virtual environment](https://code.visualstudio.com/docs/python/environments#_create-a-virtual-environment-in-the-terminal)

>     python3  -m  venv  .venv
>     source venv/bin/activate

4.  Install the dependencies using the requirements.txt file

>     pip  install  -r  requirements.txt

5. Run the `load_job_listings.py` script.

>     python3  load_job_listings.py

This script will ingest a dataset of job listings into Astra DB. You will start to see job titles appear in your terminal -- that is how you know the script is successfully running. This file is fairly large so keep it running for as long as you'd want depending on how many records you want in your database. 

## Start the app
Finally run `streamlit run app.py` to start the app and there you have it! You can test the app by giving it a Desired Role and uploading a resume.

Happy job searching! 
