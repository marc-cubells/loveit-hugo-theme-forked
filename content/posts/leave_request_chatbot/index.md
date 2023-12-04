---
author: "Marc Cubells"
title: "Leave Management made easy with AI"
subtitle: "Tired of filling out forms? Let AI do it for you!"
description: "Streamlining Leave Requests with LangChain and Streamlit"
date: "2023-12-04"

tags: ["ai", "development", "langchain"]
header_img: "img/leave_request_chatbot/header.png"
toc: true
series: ["Themes Guide"]
comment: true

draft: false
---

In today’s fast-paced corporate world, managing leave requests can often become a cumbersome task, both for employees and HR departments. The traditional process, typically involving navigating through complex platforms and tediously filling out numerous fields one by one, can be time-consuming and frustrating. This not only hampers productivity but also adds an unnecessary layer of administrative complexity.

![leave_request_forms_complexity](leave_request_forms_complexity.png)

Recognizing these challenges, we've embarked on an journey to transform how leave requests are managed. Leveraging the power of AI, we have developed a chatbot prototype designed to simplify the leave application process, making it more user-friendly, efficient, and accessible for everyone.

Imagine a system where, instead of navigating through a complex labyrinth of forms and fields, you can interact with a chat interface that effortlessly handles your leave requests. This AI-powered assistant is capable of not only submitting new leave requests for you but also offers a comprehensive overview of your leave history. It keeps you informed about your remaining vacation days and advises on the number of days needed to cover a specific vacation period. All of these features, and more, are seamlessly integrated, thanks to the advanced capabilities of AI.

![chatbot_preview](<chatbot_preview.png>)

## Crafting a Chatbot with LangChain and Streamlit

In developing this prototype, we used Python, due to its efficacy in building complex applications with relative ease. Python's robust ecosystem enabled us to integrate two pivotal libraries: [**LangChain**](https://www.langchain.com) and [**Streamlit**](https://streamlit.io).

![langchain_streamlit_logos](langchain_streamlit_logos.png)

[**LangChain**](https://www.langchain.com) is an open-source framework designed for developing applications that utilize large language models (LLMs). For our chatbot to be able to perform different tasks, we use the Large Language Model (LLM) as a reasoning engine capable of determining which actions to take and in which order based on the user's input. This engine is what is called an "Agent" in the LangChain framework.

The fundamental architecture of a LangChain Agent is structured as follows:

1. Input Reception: The agent receives natural language input from the user.

2. Processing with LLM: The agent employs the LLM to process the input and formulate an action plan.

3. Plan Execution: The agent executes the devised action plan, which might involve interacting with other tools or services.

4. Output Delivery: Subsequently, the agent delivers the output of the executed plan back to the user.

The key components of LangChain agents include the agent itself, external tools, and toolkits:

- Agent: The core of the architecture, responsible for processing input, generating action plans, and executing them.

- Tools: These external resources are utilized by the agent to accomplish tasks. They encompass a diverse range, from other LLMs to web APIs.

- Toolkits: Toolkits consist of groups of tools purposefully assembled for specific functions. Examples include toolkits for question answering, text generation, and natural language processing.

<!-- #TODO: Paste a diagram where I can see the agent orchestrator and all the tools available. Do it with Excalibur -->


On the other hand, [**Streamlit**](https://streamlit.io), is an intuitive framework for creating interactive web applications with minimal effort. One of Streamlit’s standout features is its array of ready-to-use components that drastically simplify frontend development, enabling developers to effortlessly build interactive user interfaces




If you are interested in learning more about [**LangChain**](https://www.langchain.com) and [**Streamlit**](https://streamlit.io), check out the post we published on our blog: [**AI Prototyping with LangChain and Streamlit**](https://philico-tech.github.io/ptech-blog/langchain/).

More specifically, we used 

## Using the Chatbot

### Use Case #1: Submitting new leave requests

