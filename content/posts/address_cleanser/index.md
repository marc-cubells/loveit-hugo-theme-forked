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

In our pursuit of streamlining everyday business processes, we've tapped into the advanced capabilities of Large Language Models (LLMs) to parse, correct, and clean unstructured data.

Our objective was clear – to engineer an application capable of interpreting and structuring address data, while at the same time giving the end user the possibility of validating and manually editing the results.

![data_cleansing_1](data_cleansing_1.png)

## Development with SQLite, LangChain and Flask

In developing this prototype we used Python, due to its efficacy in building complex applications with relative ease. Python's rich ecosystem facilitated the integration of three crucial libraries: [**SQLite**](https://www.sqlite.org/index.html), [**LangChain**](https://www.langchain.com) and [**Flask**](https://flask.palletsprojects.com/en/3.0.x/).

### What is SQLite?

<img src="sqlite_logo.png" width="45%" height="auto">

[**SQLite**](https://www.sqlite.org/index.html) is an open-source database engine, widely acclaimed for its reliability, simplicity, and lightweight nature. Unlike traditional database systems that require a separate server process, [**SQLite**](https://www.sqlite.org/index.html) is serverless and integrates directly into applications. 

This self-contained, file-based database engine provides a robust and efficient solution for managing data within the application itself. It's an ideal choice for applications that require a compact, portable database without the overhead of server management.

We used [**SQLite**](https://www.sqlite.org/index.html) to create a database that stores the unstructured address data and the results of the AI processing.

### What is LangChain?

<img src="langchain_logo.png" width="60%" height="auto">

[**LangChain**](https://www.langchain.com) is a versatile open-source framework designed to build applications powered by large language models (LLMs). Our chatbot utilizes an LLM as a reasoning engine, which, in LangChain terminology, is referred to as an [**Agent**](https://python.langchain.com/docs/modules/agents/). This Agent is responsible for planning and executing actions based on user input.

For a deeper dive into how [**LangChain**](https://www.langchain.com) can be used to simplify the prototyping of AI applications, visit our blog post: [**AI Prototyping with LangChain and Streamlit**](https://philico-tech.github.io/ptech-blog/langchain/).

### What is Flask?

<img src="flask_logo.png" width="45%" height="auto">

[**Flask**](https://flask.palletsprojects.com/en/3.0.x/) is a lightweight web application framework written in Python. It's designed to make getting started quick and easy, with the ability to scale up to complex applications. [**Flask**](https://flask.palletsprojects.com/en/3.0.x/) provides a simple interface for handling HTTP requests and responses, as well as a template engine for rendering HTML pages.

We used [**Flask**](https://flask.palletsprojects.com/en/3.0.x/) to build a simple web application that allows the user to view and edit the results of the AI processing.

## The dataflow

The diagram below shows the dataflow of the application:

![workflow](<workflow.png>)

The steps can be summarized as follows:

1. The unstructured address data is stored in a CSV file.

2. The CSV file is imported into the SQLite database.

3. The data is processed by the LLM and the results are sent to Google Maps API for validation.

4. The validated and structured address data is stored back in the SQLite database.

5. The data stored in the SQLite database is displayed in the web application for end-user manual validation and editing.

## The application in action 

In order to demonstrate how the application works, we'll use a CSV file with the following unstructured address data:

![data_cleansing_2](data_cleansing_2.png)

When the application is executed, the first step consists of migrating the data from the CSV file to the SQLite database.

![data_cleansing_8](<data_cleansing_8.png>)

The second step consists of processing the data with the LLM and sending the results to the Google Maps API for validation. The following screenshot shows the results of the LLM processin, where the address that are validated by the Google Maps API are highlighted:

![data_cleansing_7](data_cleansing_7.png)

We can see that the LLM is capable of detecting and extracting all the different parts of a full address. Namely: name of the resident(s), street name, street number, postal code, city, country and other details. The address returned by the Google Maps API is also stored, as it might be valuable information for the end user.

The third step consists of displaying the results of the LLM processing to the end user. The following screenshot shows the front-end of the web application:

![data_cleansing_6](data_cleansing_6.png)

The end user can now validate the results of the LLM processing and manually edit the address data if necessary. When the end user clicks on the "Confirm" button, the data is stored back in the database.

![data_cleansing_5](data_cleansing_5.gif)

Address that have not been validated by the Google Maps API are highlighted in red. For these particular cases, the end user can manually edit the data and trigger the Google Maps API validation process.

![data_cleansing_4](data_cleansing_4.gif)

## Limitations and potential improvements

In regards to potential improvements and next steps, two main areas come to mind:

- **User authentication**: Implementing unique usernames and passwords for secure, personalized access to leave requests and confidential data is a crucial next step.

- **Data visualization**: The addition of data visualization tools would allow for a more intuitive and user-friendly experience. In a future iteration, we could add the possibility of letting the user upload the CSV file with the unstructured data directly from the web application. This would eliminate the need for the user to manually import the CSV file into the SQLite database. Furthermore, we could add a dashboard with charts and graphs to visualize every step of the data cleansing process.

## Conclusion

TBC

