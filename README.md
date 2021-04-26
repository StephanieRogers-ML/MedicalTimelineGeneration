
 
---

<div align="center">    
 
# Medical Timeline Generation    

[![Paper](http://img.shields.io/badge/paper-arxiv.1001.2234-B31B1B.svg)](https://www.nature.com/articles/nature14539)
[![Conference](http://img.shields.io/badge/NeurIPS-2019-4b44ce.svg)](https://papers.nips.cc/book/advances-in-neural-information-processing-systems-31-2018)

<!--
ARXIV   
[![Paper](http://img.shields.io/badge/arxiv-math.co:1480.1111-B31B1B.svg)](https://www.nature.com/articles/nature14539)
-->
</div>
 
## Description   
Veterhealth Medical Timeline Generator was developed during a three-month AI Tech Sprint from January- April 2021.  Veterhealth accepts user submitted documents and text to generate a users personal medical timeline from submitted documentation and supplemental information.  

This project is broken up into determining if an event is relevant or not and then it uses temporal information such as dates/times and statements that include words like 'before, after, years ago' to sort event blocks.  To ensure we don't overwhelm the user, different filter views will be populated with a max on events visible.   


### Data
SyntheaTM is a Synthetic Patient Population Simulator. View more information. [View more information!](https://github.com/synthetichealth/synthea.com) The goal is to output synthetic, realistic (but not real), patient data and associated health records in a variety of formats.  
To finetune our model, we generated 1209 fake patients that consisted of 999 alive and 210 dead with 334 attributes.
### Processing

### Models
Model Inputs
BERT
Med7 with spacy pipeline
The models were pre-trained on the entire MIMIC-III data, comprising a collection of 2,083,054 documents with the total of 3,129,334,419 words. The model achieved a lenient (strict) micro-averaged F1 score of 0.957 (0.893) across all seven categories.
### Results
Tuning
Saving & Hosting

### Backend  
AWS Amplify is a set of tools and services that help build scalable full stack applications, powered by AWS.  
**Authentication**  
Cognito  
Group: Admin, Patient, Provider  
User:  
**File storage**  
S3  
DynamoDB  
DataStore  
**API**  
GraphQL  
Create  
Mutate  
Query  
Subscribe  

**Functions**  
File Upload to S3 Function  
Lambda Trigger on S3 to process & model  

**Predictions**  
Model predictions from BERT and Med7 ammend to database  
**Post**  
Sort database by event date.
For each unique day, group same event type sentences/documents for similarity and deduplication.  
Ammend unique events into day/type entry and create a counter column for supporting evidence.


## How to run   
  
```bash
# clone project   
git clone https://github.com/StephanieRogers-ML/MedicalTimelineGeneration

# install project   
cd MedicalTimelineGeneration 
yarn start
 ```   

## Imports
This project is setup as a package which means you can now easily import any file into any other file like so:
```python
from project.datasets.medical import medical
from project.lit_classifier_main import LitClassifier
from pytorch_lightning import Trainer

# model
model = LitClassifier()

# data
train, val, test = mnist()

# train
trainer = Trainer()
trainer.fit(model, train, val)

# test using the best model!
trainer.test(test_dataloaders=test)
```

### Resources    
```
https://github.com/synthetichealth/synthea
https://github.com/kormilitzin/med7


@article{kormilitzin2020med7,
  title={Med7: a transferable clinical natural language processing model for electronic health records},
  author={Kormilitzin, Andrey and Vaci, Nemanja and Liu, Qiang and Nevado-Holgado, Alejo},
  journal={arXiv preprint arXiv:2003.01271},
  year={2020}
}
```   
