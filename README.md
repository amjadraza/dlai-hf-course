<h1 align="center">
📖 DLAI HUGGINGFACE COURSE
</h1>

A collection of notebooks for the course DLAI HUGGINGFACE with local environment setup

<!-- [![A Video Guide](ui.PNG?raw=true)](https://youtu.be/yJAWB13FhYQ) -->

<!-- [https://youtu.be/yJAWB13FhYQ](https://youtu.be/yJAWB13FhYQ) -->


## 🔧 Features

- Collection of Notebooks
- Local venev setup using Poetry
- Docker Support with Optimisation Cache etc
- Run the Notebook Server with Docker

This repo contains an `notebooks` flocation contains the ntebooks


## 💻 Running Locally

1. Clone the repository📂

```bash
git clone https://github.com/amjadraza/dlai-hf-course.git
```

2. Install dependencies with [Poetry](https://python-poetry.org/) and activate virtual environment🔨

```bash
poetry install
poetry shell
```

3. Copy and Modify `env.example` to `.env`

Generate the HF API Key to be able to hosted models for inference and set the variables accordingly.

4. Run the JupyterLab server🚀

```bash

jupyter lab

```


Run Notebooks using Docker
--------------------------
This project includes `Dockerfile` to run the app in Docker container. In order to optimise the Docker Image
size and building time with cache techniques, I have follow tricks in below Article 
https://medium.com/@albertazzir/blazing-fast-python-docker-builds-with-poetry-a78a66f5aed0

Build the docker container

``docker  build . -t dlai-hf-course:latest ``

To generate Image with `DOCKER_BUILDKIT`, follow below command

```DOCKER_BUILDKIT=1 docker build --target=runtime . -t dlai-hf-course:latest```

1. Run the docker container directly 

``docker run -d --name dlai-hf-course -p 8888:8888 dlai-hf-course:latest ``

2. Run the docker container using docker-compose (Recommended)

``docker-compose up``

> Make sure to include the `.env` SECRETS file when running with `docker-compose` with your own Keys.



## Report Feedbacks

As `dlai-hf-course:latest` is a template project with minimal example. Report issues if you face any. 

## DISCLAIMER

This is a template App, when using with openai_api key, you will be charged a nominal fee depending
on number of prompts etc.