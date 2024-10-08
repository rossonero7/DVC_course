# DVC documentation

This will be my documentation / comments about what I learned from DVC course 

Syllabus:
    1. what is DVC
    2. installation options
    3. what is Git

## What is DVC

- DVC - data version control is free opensource tool for data management, ML pipeline automation and experiments. 
- Contains effective versioning system, so we can collaborate very quickly through many different projects, different codes etc. 
- big plus is codification - option so save and integrate model versions, library versions ==> solution will be runable all the time and we wont have any troubles with library inconsystencies.  

## Installation on mac - Python 3.8+ must have

    1. brew isntall dvc
    2. pip install dvc
    3. DVC is an extension in VScode   
        also documentation is included 
    
## GIT

Is a tool, that helps you to control your code - to manage changes in your code, versions and can help you to collaborate with other people in your team and with other teams. 

for simplicity there are a few comments which are essential 
 0. git init - initializing folder to git

 1. git add - which file i want to version , to keep the current state.
 2. git commint - adding some messages to my curently added file. 
 3. git push
 4. git fetch 
 5. git pull 
 6. git checkout
 7. git merge
 8. git status
 9. git diff

## Requirements for pipeline automation

    1. use jupyter only for prototyping then use .py files for reproducibility an versioning . s jupyterom je problem s verioningom
    2. manage configs - move params (no hardcode paths & params) to config file ==> params.yaml
        one example how to use yaml file. 
        lets imagine that we have params.yaml. 
        this file contains: 
            data_load: dataset_csv: "data/raw/iris.csv"

            data_split: 
                test_size:0.2
                trainset_path: "data/preprocessed/train_iris.csv"
                testset_path: "data/processed/test_iris.csv"

            and bla bla bla bla

        if i want to load this file in my jupyter notebook i need to: 
            impot yaml

            def data_load(config_path: Text) -> None:
                config = yaml.safe_load(open(config_path))
                raw_data_path = config["data_load"]["dataset_csv"]
    3. reusable code - create clear pipeline workflow, organize code, clean code, reusable code
