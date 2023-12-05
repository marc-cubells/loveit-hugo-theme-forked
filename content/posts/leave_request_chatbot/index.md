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

In developing this prototype we used Python, due to its efficacy in building complex applications with relative ease. Python's ecosystem enabled us to integrate two pivotal libraries: [**LangChain**](https://www.langchain.com) and [**Streamlit**](https://streamlit.io).

### What is LangChain?

![langchain_logo](<langchain_logo.png>)

[**LangChain**](https://www.langchain.com) is an open-source framework designed for developing applications that utilize large language models (LLMs). For our chatbot to be able to perform different tasks, we use the Large Language Model (LLM) as a reasoning engine capable of determining which actions to take and in which order based on the user's input. This engine is what is called an [**Agent**](https://python.langchain.com/docs/modules/agents/) in the LangChain framework.

The fundamental architecture of a LangChain Agent is structured as follows:

1. **Input Reception**: The agent receives natural language input from the user.

2. **Processing with LLM**: The agent employs the LLM to process the input and formulate an action plan.

3. **Plan Execution**: The agent executes the devised action plan, which might involve interacting with other tools or services.

4. **Output Delivery**: Subsequently, the agent delivers the output of the executed plan back to the user.

The key components of LangChain agents include the agent itself and external tools:

- **Agent**: The core of the architecture, responsible for processing input, generating action plans, and executing them.

- **Tools**: These are external resources utilized by the agent to accomplish tasks. They encompass a diverse range, from other LLMs to web APIs.

In our case, we used the [**GPT-3.5**](https://openai.com/blog/openai-api/) LLM from OpenAI as the reasoning engine for our agent. We provided the agent with the following tools:

- LangChain class **SQLDatabaseChain**: Allows the agent to interact with a SQL database, where all the leave requests are stored per employee. 

- LangChain class **LLMMathChain**: Allows the agent to perform mathematical operations. Used to calculate the number of days needed to cover a specific vacation period.

- Python module **datetime**: Allows the agent be aware of the current date and time.

- LangChain output parser **PydanticOutputParser**: Allows the agent to generate Leave Request Proposals in JSON format, which can be displayed as a table in the chatbot interface.

The following diagram illustrates the architecture of our chatbot:

![agent_diagram](agent_diagram.png)

### What is Streamlit?

![streamlit_logo](<streamlit_logo.png>)

[**Streamlit**](https://streamlit.io), is an intuitive framework for creating interactive web applications with minimal effort. One of Streamlit’s standout features is its array of ready-to-use components that drastically simplify frontend development, enabling developers to effortlessly build interactive user interfaces

If you are interested in learning more about [**LangChain**](https://www.langchain.com) and [**Streamlit**](https://streamlit.io), check out the post we published on our blog: [**AI Prototyping with LangChain and Streamlit**](https://philico-tech.github.io/ptech-blog/langchain/).

## The Chatbot in action

The chatbot is capable of performing a variety of tasks, including:

### Use Case 1: Submit new leave requests

As explained above, the chatbot is capable of submitting new leave requests on behalf of the user. The user can specify the type of leave, the start and end dates, and the comments to add to the request. The chatbot will then automatically generate a leave request proposal for the user to review.

![demo_1](<demo_1.gif>)

The assistant is also capable of understanding generic expressions for the leave period, such as "from Tuesday to Thursday next week".

![demo_2](<demo_2.gif>)

Once the leave request proposal has been generated and shown to the user, the user can ask the for amendments. The chatbot will then update the proposal accordingly and show it to the user again. This process can be repeated as many times as needed until the user is satisfied with the proposal.

![demo_3](<demo_3.gif>)

![demo_4](<demo_4.gif>)

### Use Case 2: Chat with your leave requests

The chatbot is capable of retrieving data related to the user's leave requests that was previously stored in the database. The user can ask the chatbot to show all the leave requests submitted in a specific year, or all the leave requests submitted in a specific month.

![demo_5](<demo_5.gif>)

Furthermore, the chatbot can also be used to retrieve the number of remaining vacation days for the user:

![demo_6](<demo_6.gif>)

Finally, the chatbot can be used to know the number of vacation days needed to cover a specific period. The user can specify the start and end dates of the period, and the chatbot will calculate the number of days needed to cover it.

![demo_7](<demo_7.gif>)

Just a heads up: we chose OpenAI's LLM Model **GPT-4** for these use cases. Why, you might ask? Our experience showed that while GPT-3.5 had its moments, it wasn't always reliable for our needs in this scenario. **GPT-4**, on the other hand, demonstrates greater consistency in translating natural English into SQL queries, which is crucial for efficiently retrieving data from the database

## Limitations

<!-- Limitations of GPT3.5 vs. GPT4, the hish costs of using GPT4  -->

## Conclusion

<!-- What I learn, personal opinion on the potential, whether it can be finished or not, the next features that can be added: 
  - Full HR Chatbot would be the end goal  
  - User authentication
  -->