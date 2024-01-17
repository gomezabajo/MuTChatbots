# Mutation Testing for Task-Oriented Chatbots

Conversational agents, or chatbots, are increasingly used to access all sorts of services using natural language. While open-domain chatbots - like ChatGPT - can converse on any topic, task-oriented chatbots - the focus of this work - are designed for specific tasks, like booking a flight, obtaining customer support, or setting an appointment. Like any other software, task-oriented chatbots need to be properly tested, usually by defining and executing test scenarios (i.e., sequences of user-chatbot interactions). However, there is currently a lack of methods to quantify the completeness and strength of such test scenarios, which can lead to low-quality tests, and hence to buggy chatbots.

To fill this gap, we propose adapting mutation testing (MuT) for task-oriented chatbots. To this end, we introduce a set of mutation operators that emulate faults in chatbot designs, an architecture that enables MuT on chatbots built using heterogeneous technologies, and a practical realisation as an Eclipse plugin. Moreover, we evaluate the applicability, effectiveness and efficiency of our approach on open-source chatbots, with promising results.

## Contents included in this repository

- [/ecore/](https://anonymous.4open.science/r/MuTChatbots-8969/ecore/README.md) folder: meta-models needed for the mutation process. 
    - [/ecore/BotGenerator.ecore](https://anonymous.4open.science/r/MuTChatbots-8969/ecore/BotGenerator.ecore) CONGA meta-model.
    - [/ecore/Annotation.ecore](https://anonymous.4open.science/r/MuTChatbots-8969/ecore/Annotation.ecore) CONGA semantic annotation meta-model (similarity between phrases).

- [/evaluation/](https://anonymous.4open.science/r/MuTChatbots-8969/evaluation/README.md) folder: raw data of the experiment results. 
    - [/evaluation/chatbots/](https://anonymous.4open.science/r/MuTChatbots-8969/evaluation/chatbots/Rasa_256644.txt) Botium automatic and by hand test suites and rasa-test link for each chatbot where it corresponds. Screen captures of the executions. Txt files for single MuT results.
    - [/evaluation/results/](https://anonymous.4open.science/r/MuTChatbots-8969/evaluation/results/results.txt) Wodel-Test data file MuT results for each chatbot. Overall MuT results. 

- [/models/](https://anonymous.4open.science/r/MuTChatbots-8969/models/README.md) folder: chatbot models used in the evaluation. 
    - [/models/*Chatbot*/seed](https://anonymous.4open.science/r/MuTChatbots-8969/models/Rasa_256644/seed/Rasa_256644.model) Seed model of the corresponding *Chatbot* using the CONGA notation.
    - [/models/*Chatbot*/annot](https://anonymous.4open.science/r/MuTChatbots-8969/models/Rasa_256644/annot/Rasa_256644Annotated.model) Semantic annotation model of the corresponding *Chatbot* using the CONGA semantic annotation extension meta-model.
    - [/models/*Chatbot*/mutants](https://anonymous.4open.science/r/MuTChatbots-8969/models/Rasa_256644/mutants/da/Output0.model) Mutants generated for each of the mutation operators specified in the Wodel program.

- [/mutator/](https://anonymous.4open.science/r/MuTChatbots-8969/mutator/README.md) folder: code of the mutator extension point of the Wodel-Test tool. 
    - [/mutator/testBotGenerator.mutator](https://anonymous.4open.science/r/MuTChatbots-8969/mutator/testBotGenerator.mutator) Mutation operators coded in the Wodel DSL. 
    - [/mutator/wodeltest/WodelTest.java](https://anonymous.4open.science/r/MuTChatbots-8969/mutator/wodeltest/WodelTest.java) CONGA MuT specification using the Wodel-Test tool. 

- [/xlsx/](https://anonymous.4open.science/r/MuTChatbots-8969/xlsx/README.md) folder: Experiments' processed data. 
    - [/xlsx/Chatbots.xlsx](https://anonymous.4open.science/r/MuTChatbots-8969/xlsx/Chatbots.xlsx) Selection of the chatbots used in this work.
    - [/xlsx/metrics.xlsx](https://anonymous.4open.science/r/MuTChatbots-8969/xlsx/metrics.xlsx) Data for Table 1. Measurements of the selected chatbots and test suites. 
    - [/xlsx/data_arrangement.xlsx](https://anonymous.4open.science/r/MuTChatbots-8969/xlsx/data_arrangement.xlsx) Data for Table 2. Operator applicability, resilience and stubbornness. 
    - [/xlsx/rq1.xlsx](https://anonymous.4open.science/r/MuTChatbots-8969/xlsx/rq1.xlsx) #Mutants for each chatbot. 
    - [/xlsx/rq2.xlsx](https://anonymous.4open.science/r/MuTChatbots-8969/xlsx/rq2.xlsx) #Mutants for each chatbot by mutation operator. 
    - [/xlsx/rq3.xlsx](https://anonymous.4open.science/r/MuTChatbots-8969/xlsx/rq3.xlsx) Data for Tables 3 (Mutation score (%) by test suite) and 4 (MuT efficiency. TPM = time per mutant). 

## The chatbot MuT tool built with Wodel-Test

![The chatbot MuT tool built with Wodel-Test](https://anonymous.4open.science/r/MuTChatbots-8969/evaluation/chatbots/Rasa_256644/captures/by_hand.png)

