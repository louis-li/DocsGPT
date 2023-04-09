<h1 align="center">
  DocsGPT - Azure  🦖
</h1>

<p align="center">
  <strong>Open-Source Documentation Assistant</strong>
</p>

<p align="left">
  <strong>DocsGPT - Azure</strong> is a modified copy of DocsGPT, which connects to Azure OpenAI endpoints for document processing. 
</p>

<div align="center">
  
  <a href="https://discord.gg/n5BX8dh8rU">![example1](https://img.shields.io/github/stars/arc53/docsgpt?style=social)</a>
  
</div>

## DocsGPT

You can find our [Original DocsGPT](https://github.com/arc53/DocsFPT) here.

## Project structure
- Application - flask app (main application)

- Extensions - chrome extension

- Scripts - script that creates similarity search index and store for other libraries. 

- frontend - frontend in vite and

## QuickStart

Note: Make sure you have docker installed

1. Open dowload this repository with `git clone https://github.com/louis-li/DocsGPT.git`
2. in application folder, mv .env.sample .env
3. Edit .env file and add your Azure OpenAI key and end point
3. Run `docker-compose build && docker-compose up`
4. Navigate to http://localhost:5173/

To stop just run Ctrl + C

## Development environments

Spin up only 2 containers from docker-compose.yaml (by deleting all services except for redis and mongo)

Make sure you have python 3.10 or 3.11 installed

1. Navigate to `/application` folder
2. Install dependencies
`pip install -r requirements.txt`
3. Prepare .env file
Copy .env_sample and create .env with your openai api token
4. Run the app
`python app.py`
5. Start worker with `celery -A app.celery worker -l INFO`

To start frontend
1. Navigate to `/frontend` folder
2. Install dependencies
`npm install`
3. In the file  `.env.development` instead of `VITE_API_HOST = https://docsapi.arc53.com` use `VITE_API_HOST=http://localhost:5001`
3. Run the app
4. `npm run dev`


[How to install the Chrome extension](https://github.com/arc53/docsgpt/wiki#launch-chrome-extension)


Built with [🦜️🔗 LangChain](https://github.com/hwchase17/langchain)

