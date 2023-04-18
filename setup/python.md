---
label: "Python environment"
icon: code-square
order: 100
---
<!-- ![](/static/headers/header-1.png) -->

# Dev environment

clone the following github repo:

Below is an overview of the main folders and files:
```
├── config.json         -> your credentials and IDs
├── bot.py              -> main entrypoint for app
├── requirements.txt    -> dependencies to install
├── DOCKERFILE          -> optional dockerfile to deploy app
├── README.md
└── .gitignore
```


Install the required libraries, including Discord.py, by running the following command in the command prompt:

`python3 -m pip install requirements.txt`

---

**Optional:** use the Dockerfile to run your bot. (for this you need to have docker installed which can be a bit of a pain on windows)

A barebones dockerfile looks something like this:
```
FROM python:3
WORKDIR /app
COPY . .
RUN python3 -m pip install -U requirements.txt
CMD python -u ./main.py
```

You then need to build the image
`docker build -t my-bot .` and run the container
`docker run my-bot`
