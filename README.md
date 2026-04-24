# TalkTuner Reproduction with Qwen 2.5 7B and Mistral 7B

## Overview

This project extends the work by Chen et al. on Llama2 13B. (https://yc015.github.io/TalkTuner-a-dashboard-ui-for-chatbot-llm/)

The original paper showed that Llama2 13B indicated having user representations such as age, gender, education level, and socioeconomic status, and that the model's ouputs can be manipulated by adjusting such user representations. 

The motivation of the project is to reproduce the study with other open-source LLMs, as Chen et al. points out in the limitation of the original paper. 

## Methodology

We forked the original codebase (still in development) and modified it to match our system's and model's requirements. Qwen2.5 7B and Mistral 7B was chosen for the clear and public layer size and embedding dimension as well as the model size. 

Following Chen et al., we trained linear probes on the activations of the models to see if the probe can accurately predict user's representations. Then, we trained the controll probe on the activations and used it to manipulate the model's outputs during the causality test phase. Although Chen et al. used GPT-4 to automatically evaluate the outputs, we decided to manually and qualitatively analyze the results as we found the ouputs to be rather similar and that requires in-depth and nuanced analysis. 

## Results
### Qwen2.5 7B
The reading probes on Qwen2.5 7B consistently showed high validation accuracy, suggesting the model's strong ability to accurately construct user models. Respectively, the readings probes had test the best accuracy of 90.0% on age, 91.6% on gender, 95.7% on education, and 97.2% on socioeconomic status. 

As of the manipulated ouputs, we saw some differences across the dataset, although many of the queries produced the same responses regardless of the user representation. 

For instance, when Qwen was asked to give advice for schooling in San Fransisco, the model suggested some of the best high schools in the entire San Fransisco area given high socioeconomic status of the user, while it listed out more mediocre public schools for low socioeconomic status. 

### Mistral 7B
TBA


## Discussions
TBA
