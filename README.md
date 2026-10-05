CareerIntel AI

Agentic AI Career Intelligence and Job Discovery System

CareerIntel AI is an agentic AI-powered career and job discovery system designed to help students and early-career professionals understand skill demand, career trends, and relevant job opportunities.

The system uses LangChain, Groq, tool calling, and external APIs to research a requested skill and retrieve matching job listings based on the user's skill and location.

Instead of performing a simple keyword search, CareerIntel AI uses an AI agent that can decide when to use specialized tools to gather career intelligence and job opportunities.

Key Features

Agentic AI Architecture

Uses LangChain's agent framework to orchestrate multiple tools.

Enables the LLM to decide which tool should be used based on the user's request.

AI-Powered Job Discovery

Searches real-world job listings using the JSearch API through RapidAPI.

Supports skill-based and location-based job searches.

Skill Demand Research

Uses a dedicated skill-demand tool to research industry demand, salary insights, and career trends.

Tool Calling

Demonstrates function/tool calling with an LLM.

Connects an LLM to external data sources and APIs.

Early-Career Job Filtering

Searches for full-time and internship opportunities.

Supports job requirements targeting candidates with limited or no professional experience.

Location-Based Search

Allows users to search for opportunities based on a specific location.

Job Application Links

Extracts job titles, company names, locations, descriptions, and application URLs.

LLM-Powered Career Assistant

Combines career research with job discovery into a single AI workflow.

System Architecture

                    ┌─────────────────────┐
                    │       User          │
                    │                     │
                    │ "Find AI jobs in    │
                    │      India"         │
                    └──────────┬──────────┘
                               │
                               ▼
                    ┌─────────────────────┐
                    │   CareerIntel AI    │
                    │      AI Agent       │
                    │                     │
                    │      LangChain      │
                    └──────────┬──────────┘
                               │
                 ┌─────────────┴─────────────┐
                 │                           │
                 ▼                           ▼
       ┌───────────────────┐       ┌───────────────────┐
       │ Skill Demand Tool │       │   Search Jobs     │
       │                   │       │      Tool         │
       │ • Skill demand    │       │ • Job listings    │
       │ • Salary insights │       │ • Companies       │
       │ • Career trends   │       │ • Locations       │
       └─────────┬─────────┘       └─────────┬─────────┘
                 │                           │
                 ▼                           ▼
       ┌───────────────────┐       ┌───────────────────┐
       │ External Research │       │ JSearch /         │
       │ Source / API      │       │ RapidAPI          │
       └───────────────────┘       └───────────────────┘
                 │                           │
                 └─────────────┬─────────────┘
                               │
                               ▼
                    ┌─────────────────────┐
                    │ Structured Career   │
                    │ & Job Information   │
                    └─────────────────────┘

How It Works

CareerIntel AI follows an agentic workflow:

1. User provides a career requirement

Example:

Find AI Engineer jobs in India

2. The AI agent interprets the request

The LangChain agent determines which available tools are relevant to the user's request.

3. Skill research

The system can use the skill-demand tool to gather information about:

Industry demand

Salary insights

Career trends

Skill relevance

4. Job discovery

The search_jobs tool queries the JSearch API through RapidAPI using parameters such as:

Skill

Location

Country

Employment type

Experience requirements

5. Job information extraction

The system extracts useful job information including:

Job Title
Company
Location
Description
Application URL

6. AI-generated response

The agent combines the tool results and presents relevant career and job information to the user.

Technology Stack

Technology

Purpose

Python

Core programming language

LangChain

Agent framework and tool orchestration

Groq

Large Language Model inference

GPT-OSS 120B

Language model

JSearch

Job search API

RapidAPI

External API platform

Requests

HTTP API communication

Google Colab

Development environment

AI Agent

The project uses:

LangChain Agent
        │
        ▼
Groq LLM
        │
        ├── Skill Demand Tool
        │
        └── Search Jobs Tool

The model is initialized using:

from langchain.chat_models import init_chat_model

model = init_chat_model(
    model="openai/gpt-oss-120b",
    model_provider="groq",
    api_key=groq_api_key
)

Available Tools

1. Skill Demand Tool

The skill-demand tool is designed to provide information related to:

Industry skill demand

Salary insights

Career trends

Career relevance

2. Search Jobs Tool

The job-search tool retrieves job listings based on:

skill
location

Example:

search_jobs.invoke({
    "skill": "AI Engineer",
    "location": "India"
})

The tool connects to the JSearch API and extracts:

Job Title
Company
Location
Description
Application URL

Example Query

Find AI Engineer jobs in India

The agent can research the requested skill and search for relevant opportunities.

Example output structure:

AI Engineer Opportunities

1. AI Engineer
   Company: Example Company
   Location: India

   Description:
   ...

   Apply:
   https://example.com/job

2. Machine Learning Engineer
   Company: Example Company
   Location: India

   Description:
   ...

   Apply:
   https://example.com/job

Installation

Clone the repository:

git clone https://github.com/YOUR_USERNAME/CareerIntel-AI.git
cd CareerIntel-AI

Install the required dependencies:

pip install -U langchain langchain-groq requests

If additional dependencies are required by your environment, install them using:

pip install -r requirements.txt

API Keys

The project requires API credentials for the external services used by the tools.

Groq API Key

Create a Groq API key and store it securely.

For Google Colab:

from google.colab import userdata

groq_api_key = userdata.get("GROQ_API_KEY")

RapidAPI Key

The JSearch job-search tool requires a RapidAPI key.

Store it securely:

rapid_api_key = userdata.get("RAPID_API_KEY")

Never commit API keys, passwords, tokens, or other secrets to GitHub.

Running the Project

Open the notebook:

AI.ipynb

Run the cells sequentially and initialize the agent.

The agent can then be invoked with a career-related request.

Example:

response = agent.invoke({
    "messages": [
        {
            "role": "user",
            "content": "Find AI Engineer jobs in India"
        }
    ]
})

Target Users

CareerIntel AI is particularly useful for:

Computer Science students

Fresh graduates

Entry-level candidates

Students exploring career paths

Candidates searching for internships

Use Cases

Career Exploration

What is the demand for Engineers?

Job Discovery

Find jobs in India

Skill-Based Search

Find Machine Learning jobs requiring Python

Internship Search

Find AI internships in India

Location-Based Search

Find GenAI jobs in Bangalore

Ways to improve this project in Future

Potential extensions include:

Resume-to-job matching

Job relevance scoring

ATS keyword matching

Personalized job recommendations

Salary comparison

Skill-gap analysis

Resume improvement suggestions

LinkedIn job discovery

Multi-source job aggregation

Job deduplication

Company research

Automated job alerts

Career roadmap generation

Persistent user preferences

Multi-agent career research

RAG-based career knowledge base

Project Summary

CareerIntel AI demonstrates how LLMs can interact with external tools and APIs to perform real-world tasks.

The project focuses on practical implementation of:

Generative AI

AI Agents

LLM Tool Calling

Function Calling

LangChain

API Integration

External Data Retrieval

Career Intelligence

Job Search Automation

Agentic Workflows

Keywords

AI Agent
Generative AI
LLM
Large Language Models
Agentic AI
LangChain
Groq
GPT-OSS
Tool Calling
Function Calling
Python
JSearch
RapidAPI
Job Search
Career Intelligence
Career Assistant
Job Discovery
AI Engineer
Machine Learning Engineer
Generative AI Engineer
AI/ML
Internship Search
Job Recommendation
API Integration
LLM Applications
AI Automation

Project Structure

CareerIntel-AI/
│
├── AI.ipynb
├── README.md
├── requirements.txt
└── .gitignore

Disclaimer

CareerIntel AI retrieves job information from external APIs.

Job availability, descriptions, requirements, companies, and application links may change over time.

Always verify job information on the original employer or application platform before applying.

Author

Hruday Krishna Reddy

B.Tech Computer Science and Engineering

Interested in:

Artificial Intelligence

Generative AI

Machine Learning

LLM Applications

AI Agents

Agentic Systems

Support

If you find this project useful, consider giving the repository a ⭐ on GitHub.

License

This project is intended for educational and portfolio purposes.
