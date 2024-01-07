---
author: "Marc Cubells"
title: "Address Cleansing with AI"
subtitle: "Leverage AI to clean your address data"
description: "How to build a simple web application to clean your address data with AI"
date: "2023-12-21"

tags: ["ai", "development", "tools", "langchain"]
header_img: "img/address_cleanser/background.png"
toc: true
series: ["Themes Guide"]
comment: true

draft: false
---

INTRO TBC

![data_cleansing_1](data_cleansing_1.png)

## Development with SQLite, LangChain and Flask

In developing this prototype we used Python, due to its efficacy in building complex applications with relative ease. Python's rich ecosystem facilitated the integration of three crucial libraries: [**SQLite**](https://www.sqlite.org/index.html), [**LangChain**](https://www.langchain.com) and [**Flask**](https://flask.palletsprojects.com/en/3.0.x/).

### What is SQLite?

TBC

<img src="sqlite_logo.png" width="45%" height="auto">

### What is LangChain?

<img src="langchain_logo.png" width="60%" height="auto">

[**LangChain**](https://www.langchain.com) is a versatile open-source framework designed to build applications powered by large language models (LLMs). Our chatbot utilizes an LLM as a reasoning engine, which, in LangChain terminology, is referred to as an [**Agent**](https://python.langchain.com/docs/modules/agents/). This Agent is responsible for planning and executing actions based on user input.

For a deeper dive into how [**LangChain**](https://www.langchain.com) can be used to simplify the prototyping of AI applications, visit our blog post: [**AI Prototyping with LangChain and Streamlit**](https://philico-tech.github.io/ptech-blog/langchain/).

### What is Flask?

TBC

<img src="flask_logo.png" width="45%" height="auto">

## The data Workflow

![workflow](<workflow.png>)

## The application in detail

The following screenshot shows the unstructured data

![data_cleansing_2](data_cleansing_2.png)

The following screenshot shows the parsed data and the address that are validated by the Google Maps API are highlighted

![data_cleansing_7](data_cleansing_7.png)

The following screenshot shows the parsed data and the address not validated by the Google Maps API are highlighted

![data_cleansing_3](data_cleansing_3.png)

The following screenshot shows the front end

![data_cleansing_6](data_cleansing_6.png)

The following GIF shows ...

![data_cleansing_5](data_cleansing_5.gif)

The following GIF shows ...

![data_cleansing_4](data_cleansing_4.gif)

## Conclusion

TBC
