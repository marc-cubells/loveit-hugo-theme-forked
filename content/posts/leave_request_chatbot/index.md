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

In today’s fast-paced corporate world, managing leave requests can often become a cumbersome task, both for employees and HR departments. The traditional process, typically involving navigating through complex platforms and tediously filling out numerous fields one by one, can be time-consuming and frustrating.

![leave_request_forms_complexity](leave_request_forms_complexity.png)

Recognizing these challenges, we embarked on an journey to transform how leave requests are managed. Leveraging the power of AI, we have developed a chatbot prototype designed to simplify the leave submission process, making it more user-friendly, efficient, and accessible.

Imagine a system where, instead of navigating through a maze of forms and fields, you can interact with a chat interface that handles your leave requests. This AI-powered assistant is capable of not only submitting new leave requests for you, but it also offers a comprehensive overview of your leave history.

![chatbot_preview](<chatbot_preview.png>)

## Development with LangChain and Streamlit

In developing this prototype we used Python, due to its efficacy in building complex applications with relative ease. Python's ecosystem enabled us to integrate two pivotal libraries: [**LangChain**](https://www.langchain.com) and [**Streamlit**](https://streamlit.io).

### What is LangChain?

![langchain_logo](<langchain_logo.png>)

[**LangChain**](https://www.langchain.com) is an open-source framework designed for developing applications that utilize large language models (LLMs). For our chatbot to be able to perform different tasks, we used the Large Language Model (LLM) as a reasoning engine capable of assessing which actions to take and in which order based on the user's input. This engine is called an [**Agent**](https://python.langchain.com/docs/modules/agents/) in the LangChain framework.

The architecture of a LangChain Agent is structured as follows:

1. **Input Reception**: The agent receives natural language input from the user.

2. **Processing with LLM**: The agent employs the LLM to process the input and formulate an action plan.

3. **Plan Execution**: The agent executes the devised action plan, which might involve interacting with external tools.

4. **Output Delivery**: Finally, the agent delivers the output of the executed plan back to the user.

The key components of LangChain Agents include the agent itself and external tools:

- **Agent**: The core of the architecture, responsible for processing input, generating action plans, and executing them.

- **Tools**: These are external resources utilized by the agent to accomplish tasks. They encompass a diverse range, from other LLMs to web APIs.

In our case, we used OpenAI's Large Language Models (LLMs) [**GPT-3.5**](https://platform.openai.com/docs/models/gpt-3-5) and [**GPT-4**](https://openai.com/research/gpt-4) as the reasoning engine for our agent. 

Additionally, we provided the agent with the following tools:

- LangChain class **SQLDatabaseChain**: It allows the agent to interact with a relational database, where all the leave requests per employee are stored.

- LangChain class **LLMMathChain**: It allows the agent to perform mathematical operations. It can be used, for example, to calculate the number of days needed to cover a specific vacation period.

- Python module **datetime**: It allows the agent to get hold of the current date and time.

- LangChain output parser **PydanticOutputParser**: It allows the agent to generate Leave Request Proposals in JSON format, which can be displayed as a table in the chatbot interface.

The following diagram illustrates the architecture of our chatbot:

![agent_diagram](agent_diagram.png)

### What is Streamlit?

![streamlit_logo](<streamlit_logo.png>)

[**Streamlit**](https://streamlit.io), is an intuitive framework for creating interactive web applications with minimal effort. One of Streamlit’s standout features is its array of ready-to-use components that drastically simplify frontend development, enabling developers to effortlessly build interactive user interfaces

If you are interested in learning more about [**LangChain**](https://www.langchain.com) and [**Streamlit**](https://streamlit.io), check out the post we published on our blog: [**AI Prototyping with LangChain and Streamlit**](https://philico-tech.github.io/ptech-blog/langchain/).

## The Chatbot in action

The chatbot prototype is capable of performing a variety of tasks, including:

### Submission of new leave requests

As explained above, the chatbot is capable of submitting new leave requests on behalf of the user. The user can specify the type of leave, the start and end dates, and the comments to add to the request. The chatbot will then automatically generate a leave request proposal for the user to review.

![demo_1](<demo_1.gif>)

The assistant is also capable of understanding generic expressions for the leave period, such as "from Tuesday to Thursday next week".

![demo_2](<demo_2.gif>)

Once the leave request proposal has been generated and shown to the user, the user can ask the for amendments. The chatbot will then update the proposal accordingly and show it to the user again. This process can be repeated as many times as needed until the user is satisfied with the proposal.

![demo_3](<demo_3.gif>)

![demo_4](<demo_4.gif>)

### Retrieval of existing leave requests

The chatbot is capable of retrieving data related to the user's leave requests that was previously stored in the database. The user can ask the chatbot to show all the leave requests submitted in a specific year, or all the leave requests submitted in a specific month.

![demo_5](<demo_5.gif>)

Furthermore, the chatbot can also be used to retrieve the number of remaining vacation days for the user:

![demo_6](<demo_6.gif>)

Finally, the chatbot can be used to know the number of vacation days needed to cover a specific period. The user can specify the start and end dates of the period, and the chatbot will calculate the number of days needed to cover it.

![demo_7](<demo_7.gif>)

As can be seen in the videos above, we opted for OpenAI’s LLM Model **GPT-4** in these use cases. You may wonder why. Our trials indicated that, despite its capabilities, GPT-3.5 wasn't consistently reliable for these particular scenarios. In contrast, GPT-4 performed consistently well in translating natural English into SQL queries, a crucial factor for efficient data retrieval from the database

However, it's important to acknowledge the trade-offs that come with using GPT-4. The most notable among these is the higher cost. Due to its advanced capabilities, GPT-4 comes with a steeper price tag compared to its predecessors. Additionally, while it's more accurate and sophisticated, it's also a bit slower when processing queries. This means that while we gain in terms of precision and versatility, we do compromise somewhat on speed and budget. Balancing these factors was a key consideration in our decision-making process.

## Limitations and potential improvements

As mentioned before, one of the big limitations we found is the erratic behaviour of OpenAI's LLM Model GPT3.5 when it comes to translate plain English into SQL Queries. That forced us to switch to GPT-4, which is more accurate but also more expensive. Hopefully, as the technology matures, the price of complex LLMs will decrease, making them more accessible.

In regards to potential improvements and next steps, two main areas come to mind:

- **User authentication**: By assigning each employee a unique username and password, we can ensure that leave requests and confidential information are accessed and managed solely by the authorized individual.

- **Full HR Chatbot**: The chatbot currently only supports leave requests. However, its capabilities could be significantly expanded to encompass a broader range of HR-related tasks. This would include providing employees with instant access to information about HR policies, such as the number of vacation days allotted per year, details on how overtime is compensated, and guidelines on expense coverage. Looking ahead, there's also the potential to extend its functionality to cover the submission of employee timesheets, further streamlining HR processes and improving efficiency.

## Conclusion

Embarking on the journey of developing our AI-powered leave management chatbot has been an enlightening experience, showcasing the transformative potential of AI in simplifying complex workplace tasks. Using LangChain and Streamlit, combined with OpenAI's LLM Models, this project has taught us about the power and versatility of AI in processing natural language and executing data-driven tasks efficiently.

Yet, the journey also brought its share of challenges, particularly in balancing cost with performance. These experiences have underlined the importance of adaptability and continuous improvement in the ever-evolving field of AI. Looking ahead, we are excited to explore further enhancements to our chatbot, continually pushing the boundaries of what AI can achieve.
