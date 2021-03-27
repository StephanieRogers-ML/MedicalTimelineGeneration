
 
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
Developed during three-month AI Tech Sprint from January- April 2021, this application accepts different data inputs to generate a users personal medical timeline from submitted documentation and supplemental information.  This project is broken up into determining if an event is relevant or not and then it uses temporal information such as dates/times and statements that include words like 'before, after, years ago' to sort event blocks.  To ensure we don't overwhelm the user, different filter views will be populated with a max on events visible.   

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

### Citation   
```
@article{StephanieRogers,
  title={MedicalTimelineGeneration},
  year={2021}
}
```   
