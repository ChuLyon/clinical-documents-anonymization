# Introduction 

This project containts the source code used in the study 
[Anonymisation de documents médicaux en texte libre et en français via réseaux de neurones](https://hal.science/hal-04139391v1)
presented at the [PFIA2023](https://pfia23.icube.unistra.fr/).


## Getting Started

First, you’ll need to install Anaconda and create an environment with the following commands:

```{bash}
conda create --name env-name --file requirements.txt
```

Then you activate this environment and launch jupyter:

```{bash}
conda activate env-name
jupyter notebook
```

For privacy concerns, the data used and the models produced in this study are not
available.

Examples have been providen in *data/README.md* if you to test this code with your own data.

The *LabelGuidelines.md* file, provide the guidelines (in french) used to labelize our data.

The link to the model used in this study is provided in *models/README.md*.

### The *0-Bootstraping* notebook

This notebook allows to replicate the process we used to bootstrap our dataset into a
training dataset and a validation dataset.

It initializes the datasets used in the *1-Anonymisation-pretraining* notebook.

### The *1-Anonymisation-pretraining* notebook

This notebook explains and allows to replicate the process we used to train a model, pre-train on french texts, on a corpus of medical documents.

**Remark**: depending on your machine and your training dataset,
it could take several days or weeks.

### The *2-Anonymisation-finetuning* notebook

This notebook explains and allows to 
replicate the process we used to finetune a 
model on a corpus of medical documents
labelized following the guidelines 
written in *LabelGuidelines.md*.

The finetuning performed in this notebook
aims to identify unsecure information within
medical documents for patient privacy.

### The *3-Evaluate-models* notebook

This notebook allows to reproduce the 
evaluation we made on our models.

It requires to build models with 
*1-Anonymisation-pretraining* and
*2-Anonymisation-finetuning* notebooks
before.
