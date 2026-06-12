# jetbridge
Our company sells a platform to enterprises (banks, telecoms). The product lets customers deploy AI agents that react to real-time events in their business systems.

Example use cases:

A fraud-triage agent watches a stream of card transactions, investigates suspicious ones by querying internal APIs, and either blocks the card or opens a case.
A support agent watches a stream of incoming tickets and customer telemetry, drafts responses, and escalates to humans when unsure.

Customers' event sources already exist (Kafka topics, CDC from databases, webhooks). Your job is to design the platform that:

Ingests these event streams,
Routes relevant events to the right agents,
Runs the agents (which call LLM APIs and customer tools/APIs),
Lets agents take actions back into customer systems — safely.

Constraints:

Multi-tenant SaaS to start; assume ~200 enterprise customers, the largest producing ~50k events/sec.
Agents are slow (LLM calls take 1–30 seconds) but events are fast.
Enterprise customers: security review will be brutal. Some will eventually demand the data plane runs in their own cloud account (BYOC).
Target 99.9% availability for the pipeline; an agent being slow must never cause event loss.

Start wherever you like — clarifying questions are encouraged. We'll go deep on a few areas as you go.



# Adidos Survey / Poll App
You are asked to design architecture for Poll app for very well know sport brand - let's call it Adidos.
This application will allow users to vote in really simple polls. Each poll has one question and two answers.

For example:

Where do you run:

- On the street
- In the gym

After answering user is presented with results of voting:

Where do you run:

- On the street [x] 32%
- In the gym 68%

This feature will be part of existing application.
Your Poll App backend will operate as micro-service for much bigger application released by Adidos.

Requirements:

- API will have to support:
    - getting question with given ID
    - allow user to answer a question with selected answer
    - see previous answers for the user for all questions
    - see how many people agreed or disagreed with his answer.
- Each user can answer each question only ONCE.
- Dont waste money.

Things to consider:
1. The service will be subject to intense bursts of traffic with longer periods of small traffic.
2. The service will attacked by malicious bots trying to influence the vote.

Points to Discuss:
- Data storage and schema
- Cloud Infrastructure