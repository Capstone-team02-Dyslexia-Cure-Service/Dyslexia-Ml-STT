# Dyslexia-Zoo
### Introduction
Dyslexia-Zoo is a capstone design project at the Chung-Ang University's Department of Software Engineering. Please note that we will not be accepting contributions for Dyslexia-Zoo, as it is a Capstone Design Project.

#### Dyslexia 
An inability to read or spell words accurately and fluently in children or adults who do not notice any significant difficulty in listening or speaking.
A type of learning disability

#### Phonological Dyslexia
Dyslexia in which problems with phonological awareness lead to difficulties with letter acquisition and word decoding.

#### Fluency Dyslexia
Dyslexia in which a person has no difficulty reading words but has poor fluency and comprehension of content.

### The Goal Of Dyslexia-Zoo Project 
1. Services for children with dyslexia.
2. For The Children who has Phonological Dyslexia.
3. For The Children who has Fluency Dyslexia. 

### Architecture of Dyslexia-Zoo
<img width="100%" src="https://github.com/Capstone-team02-Dyslexia-Cure-Service/Dyslexia-Ml-Server/assets/106421292/648f08de-1a15-4f9c-a638-0a7a753e8b84"/>

### Sub Projects of Dyslexia-Zoo
* [Dyslexia-Zoo-FE](https://github.com/Capstone-team02-Dyslexia-Cure-Service/Dyslexia_Zoo_FE)
    * Dyslexia-Zoo-FE - react
* [Dyslexia-Zoo-BE](https://github.com/Capstone-team02-Dyslexia-Cure-Service/Dyslexia-BE)
    * Dyslexia-Zoo-BE - spring
* [Dyslexia-Zoo-ML](https://github.com/Capstone-team02-Dyslexia-Cure-Service/Dyslexia-Ml-STT)
    * Dyslexia-Zoo-ML - jupyterNotebook
* [Dyslexia-Zoo-ML Server](https://github.com/Capstone-team02-Dyslexia-Cure-Service/Dyslexia-Ml-Server)
    * Dyslexia-Zoo-ML Server - Flask
# Dyslexia-Ml-STT
Dyslexia Machine Learning Speech To Text Model
## Introduction
Dyslexia-Zoo-ML is a STT model used by this service to evaluate the child's voice who use this service.
It was wrote by python version 3.10.6.

### Requirements to run or modifiy server
* Framework Google Colab
* If you have GPU enough to trained model you can use that one

### Model
Used Model Kospeech which is famous korean Stt model.
* [Kospeech](https://github.com/sooftware/kospeech)

### How To Train Model
1. We had a lot of data, so we couldn't upload it directly to CoLab for training, so we uploaded the training files to Google Drive, mounted the drive, and trained with the data.
2. We used a model called Kospeech, which is a Korean STT model. The model was trained on Korean children's voices, and about 460,000 data points were used, but about 120,000 points were used due to performance issues in CoLab. It took about 12 hours to train. 
3. Import the modules from the DyslexiaZooStt.ipynb file and unzip the compressed folder of the voices to be trained. Unzip all the required voices and put them in one folder. 
4. Navigate to the model's location on the drive and import the required modules. Then, in the model's location 
* !python ./bin/main.py model=ds2 train=ds2_train train.dataset_path="Location of data folder"
Use the corresponding command line.

### How To make transcript.txt and Word Dictionary.csv
Use this code
* python main.py --dataset_path "(1)" --vocab_dest "(2)" --output_unit "(3)" --preprocess_mode '(4)

You can Get result like that

#### transcript.txt
![image](https://github.com/CAU-Capstone-PPL/CafePlugGuardian-ML/assets/106421292/74b631e2-77ad-4105-9351-31c06b0e674b)


#### Word Dictionary
![image](https://github.com/CAU-Capstone-PPL/CafePlugGuardian-ML/assets/106421292/c1b9b0ff-0a74-45e0-a958-d29d5f8a1b78)

### How To change hyper Parameter
![image](https://github.com/CAU-Capstone-PPL/CafePlugGuardian-ML/assets/106421292/84c226ae-ee98-450b-b903-d4793ec9de0d)

If you want to change hyper parameter you can change ds2.train.yml

### Reference
* [Blog-1](https://mingchin.tistory.com/152)
* [Blog-2](https://velog.io/@letgodchan0/%EC%9D%8C%EC%84%B1%EC%9D%B8%EC%8B%9D-%ED%95%9C%EA%B5%AD%EC%96%B4-STT-1)

