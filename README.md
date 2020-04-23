# AML-Fall-2019
Project repository/page for CS5824/ECE5424 - Advanced Machine Learning project. 

This page lists down the observations and results performed as a part of the project under **CS5824/ECE5424 Advanced Machine Learning** in Fall 2019 under *Prof. Dr. Bert Huang*. This project attempts to reproduce a finding from a Machine Learning Research study and present the results of the same.

## ABCNN: Attention-Based Convolutional Neural Network for Modelling Sentence Pairs
The [paper](https://arxiv.org/pdf/1512.05193.pdf) asserts that Attention-Based Convolutional Neural Networks (CNNs) perform better than CNNs without attention mechanisms. The paper integrated attention into CNNs for sentence pair modelling. Sentence pair modelling is a critical task in many Natural Language Processing (NLP) tasks such as Answer Selection, Paraphrase Identification and Textual Entailment. The experiments were performed for these three tasks. For this project, we are going to focus on Answer Selection.

## Background

Modeling a pair of sentences is a critical task for many NLP applications. 
<need to edit> 
s0 how much did Waterboy gross?
s1+ the movie earned $161.5 million
s1- this was Jerry Reed’s final film appearance
For AS, correctly answering s0 requires attention on “gross”: s1+ contains a corresponding unit (“earned”) while s1- does not.



## Setup

The experiments were run on a Windows Machine using Python with the following specifications -

1. Windows 10 Predator PH315-52/64-bit/i7/32GB RAM 
2. Python 3.7.4
3. tensorflow == 1.14.0
4. numpy == 1.17.4
5. sklearn == 0.21.3
5. [WikiQA Corpus](https://www.microsoft.com/en-us/download/details.aspx?id=52419)


## Experiment
In this exeriment we will be comparing performance of Attention based models with other base line models in NLP tasks such as Answer selection. For this we will be using WikiQA data-set.
Baselines which are considered are WordCnt; WgtWordCnt; CNN-Cnt (the state-of-theart system): combination of CNN with WordCnt and WgtWordCnt. Apart from the baselines considered we have also considered two LSTM baselines Addition and A-LSTM 
The models which we are replicating are Bi-CNN, ABCNN1, ABCNN2, ABCNN3.

IN every models we will be using 2 types of classifiers that is Linear Regression and Support Vector Machines along with Adam Optimiser to further improve the test results presented in the original paper.

The main focus on using Attention based model is to show its wide variety of applications in different types of NLP operations and its effectiveness. Attention-based DL systems are now applied to NLP after their success in computer vision and speech recognition.


## Results

- BCNN

    |               |          |   MAP   |   MRR   |
    |:-------------:|:--------:|:-------:|:-------:|
    | BCNN(1 layer) |    LR    |  0.6498 |  0.6592 |
    |               |   SVM    |  0.6507 |  0.6581 |
    | BCNN(2 layer) |  LR      |  0.6510 |  0.6641 |
    |               | SVM      |  0.6493 |  0.6622 |

- ABCNN-1

    |                  |          |   MAP   |   MRR   |
    |:----------------:|:--------:|:-------:|:-------:|
    | ABCNN-1(1 layer) |  LR |  0.6557 |  0.6685 |
    |                  | SVM |  0.6503 |  0.6638 |
    | ABCNN-1(2 layer) |  LR |  0.6796 |  0.6884 |
    |                  | SVM |  0.6757 |  0.6827 |

- ABCNN-2

    |                  |          |   MAP   |   MRR   |
    |:----------------:|:--------:|:-------:|:-------:|
    | ABCNN-2(1 layer) |  LR |  0.6976 |  0.6957 |
    |                  | SVM |  0.6995 |  0.6987 |
    | ABCNN-2(2 layer) |  LR |  0.7095 |  0.7065 |
    |                  | SVM |  0.7024 |  0.7076 |

- ABCNN-3

    |                  |          |   MAP   |   MRR   |
    |:----------------:|:--------:|:-------:|:-------:|
    | ABCNN-3(1 layer) |  LR |  0.7126 |  0.7108 |
    |                  | SVM |  0.7099 |  0.7116 |
    | ABCNN-3(2 layer) |  LR |  0.7193 |  0.7165 |
    |                  | SVM |  0.7129 |  0.7126 |
    
Below are a few examples results from different networks.

**BCNN - 2 layer LR**

Q- who is st patty ? 

A- it is named after saint patrick ( ad 385–461 ) , the most commonly recognised of the patron saints of ireland .

Q- when was pokemon first started 

A- is a media franchise published and owned by japanese video game company nintendo and created by satoshi tajiri in 1996 .

Q- what does alkali do to liquids ? 

A- some authors also define an alkali as a base that dissolves in water .

Q- who are the members of the climax blues band ? 

A- the original members were guitarist/vocalist peter haycock , guitarist derek holt ; keyboardist arthur wood ; bassist richard jones ; 
drummer george newsome ; and lead vocalist and saxophonist colin cooper .

Q- when did proof die 

A- deshaun dupree holton ( october 2 , 1973 – april 11 , 2006 ) , better known by his stage name proof , was an american rapper and 
actor from detroit , michigan .

**BCNN - 2 layer SVM**

Q- who is st patty ? 

A- it is named after saint patrick ( ad 385–461 ) , the most commonly recognised of the patron saints of ireland .

Q- when was pokemon first started 

A- is a media franchise published and owned by japanese video game company nintendo and created by satoshi tajiri in 1996 .

Q- what does alkali do to liquids ? 

A- some authors also define an alkali as a base that dissolves in water .

Q- who are the members of the climax blues band ? 

A- the original members were guitarist/vocalist peter haycock , guitarist derek holt ; keyboardist arthur wood ; bassist richard jones ; 
drummer george newsome ; and lead vocalist and saxophonist colin cooper .

Q- when did proof die 

A- deshaun dupree holton ( october 2 , 1973 – april 11 , 2006 ) , better known by his stage name proof , was an american rapper and 
actor from detroit , michigan .

**BCNN - 1 layer LR**

Q- who is st patty ? 

A- it is named after saint patrick ( ad 385–461 ) , the most commonly recognised of the patron saints of ireland .

Q- when was pokemon first started 

A- is a media franchise published and owned by japanese video game company nintendo and created by satoshi tajiri in 1996 .

Q- what does alkali do to liquids ? 

A- some authors also define an alkali as a base that dissolves in water .

Q- who are the members of the climax blues band ? 

A- the original members were guitarist/vocalist peter haycock , guitarist derek holt ; keyboardist arthur wood ; bassist richard jones ; 
drummer george newsome ; and lead vocalist and saxophonist colin cooper .

Q- when did proof die 

A- in 2006 , proof was shot and killed during an altercation at the ccc nightclub in detroit .

**BCNN - 1 layer SVM**

Q- who is st patty ? 

A- it is named after saint patrick ( ad 385–461 ) , the most commonly recognised of the patron saints of ireland .

Q- when was pokemon first started

A- is a media franchise published and owned by japanese video game company nintendo and created by satoshi tajiri in 1996 .

Q- what does alkali do to liquids ?

A- some authors also define an alkali as a base that dissolves in water . 1 -0.9740697249362577

Q- who are the members of the climax blues band ? 

A- the original members were guitarist/vocalist peter haycock , guitarist derek holt ; keyboardist arthur wood ; bassist richard jones ; 
drummer george newsome ; and lead vocalist and saxophonist colin cooper .

Q- when did proof die 

A- deshaun dupree holton ( october 2 , 1973 – april 11 , 2006 ) , better known by his stage name proof , was an american rapper and 
actor from detroit , michigan .

**ABCNN1 - 2 layer LR**

Q- who is st patty ? 

A- it is named after saint patrick ( ad 385–461 ) , the most commonly recognised of the patron saints of ireland .

Q- when was pokemon first started 

A- is a media franchise published and owned by japanese video game company nintendo and created by satoshi tajiri in 1996 .

Q- what does alkali do to liquids ? 

A- some authors also define an alkali as a base that dissolves in water .

Q- who are the members of the climax blues band ?

A- the original members were guitarist/vocalist peter haycock , guitarist derek holt ; keyboardist arthur wood ; bassist richard jones ; 
drummer george newsome ; and lead vocalist and saxophonist colin cooper .

Q- when did proof die 

A- deshaun dupree holton ( october 2 , 1973 – april 11 , 2006 ) , better known by his stage name proof , was an american rapper and 
actor from detroit , michigan .

**ABCNN1 - 2 layer SVM**

Q- who is st patty ? 

A- it is named after saint patrick ( ad 385–461 ) , the most commonly recognised of the patron saints of ireland .

Q- when was pokemon first started 

A- is a media franchise published and owned by japanese video game company nintendo and created by satoshi tajiri in 1996 .

Q- what does alkali do to liquids ? 

A- some authors also define an alkali as a base that dissolves in water .

Q- who are the members of the climax blues band ? 

A- the original members were guitarist/vocalist peter haycock , guitarist derek holt ; keyboardist arthur wood ; bassist richard jones ; 
drummer george newsome ; and lead vocalist and saxophonist colin cooper .

Q- when did proof die

A- deshaun dupree holton ( october 2 , 1973 – april 11 , 2006 ) , better known by his stage name proof , was an american rapper and 
actor from detroit , michigan .

**ABCNN1 - 1 layer LR**

Q- who is st patty ? 

A- it is named after saint patrick ( ad 385–461 ) , the most commonly recognised of the patron saints of ireland .

Q- when was pokemon first started 

A- is a media franchise published and owned by japanese video game company nintendo and created by satoshi tajiri in 1996 .

Q- what does alkali do to liquids ? 

A- some authors also define an alkali as a base that dissolves in water .

Q- who are the members of the climax blues band ? 

A- the original members were guitarist/vocalist peter haycock , guitarist derek holt ; keyboardist arthur wood ; bassist richard jones ; 
drummer george newsome ; and lead vocalist and saxophonist colin cooper .

Q- when did proof die 

A- in 2006 , proof was shot and killed during an altercation at the ccc nightclub in detroit .

**ABCNN1 - 1 layer SVM**

Q- who is st patty ? 

A- it is named after saint patrick ( ad 385–461 ) , the most commonly recognised of the patron saints of ireland .

Q- when was pokemon first started 

A- is a media franchise published and owned by japanese video game company nintendo and created by satoshi tajiri in 1996 .

Q- what does alkali do to liquids ? 

A- some authors also define an alkali as a base that dissolves in water .

Q- who are the members of the climax blues band ? 

A- the original members were guitarist/vocalist peter haycock , guitarist derek holt ; keyboardist arthur wood ; bassist richard jones ; 
drummer george newsome ; and lead vocalist and saxophonist colin cooper .

Q- when did proof die 

A- in 2006 proof was shot and killed during an altercation at the ccc nightclub in detroit .

**ABCNN2 - 2 layer LR**

Q- who is st patty ? 

A- it is named after saint patrick ( ad 385–461 ) , the most commonly recognised of the patron saints of ireland .

Q- when was pokemon first started 

A- is a media franchise published and owned by japanese video game company nintendo and created by satoshi tajiri in 1996 .

Q- what does alkali do to liquids ? 

A- some authors also define an alkali as a base that dissolves in water .

Q- who are the members of the climax blues band ? 

A- the original members were guitarist/vocalist peter haycock , guitarist derek holt ; keyboardist arthur wood ; bassist richard jones ; 
drummer george newsome ; and lead vocalist and saxophonist colin cooper .

Q- when did proof die 

A- deshaun dupree holton ( october 2 , 1973 – april 11 , 2006 ) , better known by his stage name proof , was an american rapper and actor from detroit , michigan .

**ABCNN2 - 2 layer SVM**

Q- who is st patty ? 

A- it is named after saint patrick ( ad 385–461 ) , the most commonly recognised of the patron saints of ireland .

Q- when was pokemon first started 

A- is a media franchise published and owned by japanese video game company nintendo and created by satoshi tajiri in 1996 .

Q- what does alkali do to liquids ? 

A- some authors also define an alkali as a base that dissolves in water .

Q- who are the members of the climax blues band ? 

A- the original members were guitarist/vocalist peter haycock , guitarist derek holt ; keyboardist arthur wood ; bassist richard jones ; drummer george newsome ; and lead vocalist and saxophonist colin cooper .

Q- when did proof die 

A- deshaun dupree holton ( october 2 , 1973 – april 11 , 2006 ) , better known by his stage name proof , was an american rapper and actor from detroit , michigan .

**ABCNN2 - 1 layer LR**

Q- who is st patty ? 

A- it is named after saint patrick ( ad 385–461 ) , the most commonly recognised of the patron saints of ireland .

Q- when was pokemon first started 

A- is a media franchise published and owned by japanese video game company nintendo and created by satoshi tajiri in 1996 .

Q- what does alkali do to liquids ? 

A- some authors also define an alkali as a base that dissolves in water .

Q- who are the members of the climax blues band ?

A- the original members were guitarist/vocalist peter haycock , guitarist derek holt ; keyboardist arthur wood ; bassist richard jones ; 
drummer george newsome ; and lead vocalist and saxophonist colin cooper .

Q- when did proof die 

A- deshaun dupree holton ( october 2 , 1973 – april 11 , 2006 ) , better known by his stage name proof , was an american rapper and 
actor from detroit , michigan .

**ABCNN2 - 1 layer SVM**

Q- who is st patty ? 

A- it is named after saint patrick ( ad 385–461 ) , the most commonly recognised of the patron saints of ireland .

Q- when was pokemon first started 

A- is a media franchise published and owned by japanese video game company nintendo and created by satoshi tajiri in 1996 .

Q- what does alkali do to liquids ? 

A- some authors also define an alkali as a base that dissolves in water .

Q- who are the members of the climax blues band ? 

A- the original members were guitarist/vocalist peter haycock , guitarist derek holt ; keyboardist arthur wood ; bassist richard jones ; 
drummer george newsome ; and lead vocalist and saxophonist colin cooper .

Q- when did proof die 

A- deshaun dupree holton ( october 2 , 1973 – april 11 , 2006 ) , better known by his stage name proof , was an american rapper and 
actor from detroit , michigan .

**ABCNN3 - 2 layer LR**

Q- who is st patty ? 

A- it is named after saint patrick ( ad 385–461 ) , the most commonly recognised of the patron saints of ireland .

Q- when was pokemon first started 

A- is a media franchise published and owned by japanese video game company nintendo and created by satoshi tajiri in 1996 .

Q- what does alkali do to liquids ? 

A- some authors also define an alkali as a base that dissolves in water .

Q- who are the members of the climax blues band ? 

A- the original members were guitarist/vocalist peter haycock , guitarist derek holt ; keyboardist arthur wood ; bassist richard jones ; 
drummer george newsome ; and lead vocalist and saxophonist colin cooper .

Q- when did proof die 

A- deshaun dupree holton ( october 2 , 1973 – april 11 , 2006 ) , better known by his stage name proof , was an american rapper and actor from detroit , michigan.

**ABCNN3 - 2 layer SVM**

Q- who is st patty ?

A- it is named after saint patrick ( ad 385–461 ) , the most commonly recognised of the patron saints of ireland .

Q- when was pokemon first started 

A- is a media franchise published and owned by japanese video game company nintendo and created by satoshi tajiri in 1996 .

Q- what does alkali do to liquids ? 

A- some authors also define an alkali as a base that dissolves in water .

Q- who are the members of the climax blues band ? 

A- the original members were guitarist/vocalist peter haycock , guitarist derek holt ; keyboardist arthur wood ; bassist richard jones ; drummer george newsome ; and lead vocalist and saxophonist colin cooper .

Q- when did proof die 

A- deshaun dupree holton ( october 2 , 1973 – april 11 , 2006 ) , better known by his stage name proof , was an american rapper and actor from detroit , michigan .

**ABCNN3 - 1 layer LR**

Q- who is st patty ?

A- it is named after saint patrick ( ad 385–461 ) , the most commonly recognised of the patron saints of ireland .

Q- when was pokemon first started 

A- is a media franchise published and owned by japanese video game company nintendo and created by satoshi tajiri in 1996 .

Q- what does alkali do to liquids ?

A- some authors also define an alkali as a base that dissolves in water .

Q- who are the members of the climax blues band ?

A- the original members were guitarist/vocalist peter haycock , guitarist derek holt ; keyboardist arthur wood ; bassist richard jones ; 
drummer george newsome ; and lead vocalist and saxophonist colin cooper .

Q- when did proof die 

A- deshaun dupree holton ( october 2 , 1973 – april 11 , 2006 ) , better known by his stage name proof , was an american rapper and actor from detroit , michigan.

**ABCNN3 - 1 layer SVM**

Q- who is st patty ? 

A- it is named after saint patrick ( ad 385–461 ) , the most commonly recognised of the patron saints of ireland .

Q- when was pokemon first started 

A- is a media franchise published and owned by japanese video game company nintendo and created by satoshi tajiri in 1996 .

Q- what does alkali do to liquids ? 

A- some authors also define an alkali as a base that dissolves in water .

Q- who are the members of the climax blues band ? 

A- the original members were guitarist/vocalist peter haycock , guitarist derek holt ; keyboardist arthur wood ; bassist richard jones ; drummer george newsome ; and lead vocalist and saxophonist colin cooper .

Q- when did proof die 

A- deshaun dupree holton ( october 2 , 1973 – april 11 , 2006 ) , better known by his stage name proof , was an american rapper and actor from detroit , michigan .

## Conclusion
The author of paper concludes that in Answer Selection the non-attention network BCNN already performs better than the baselines. Attention-based CNNs perform better than CNNs without attention mechanisms. For CNNs, they have test one (one-conv) and two (two-conv)
convolution-pooling blocks. The ABCNN-2 generally outperforms the  ABCNN-1 and the ABCNN3 surpasses both because, when combine the ABCNN-1 and the ABCNN-2 to form the ABCNN-3, as ability to take attention of finer-grained granularity into consideration in each convolution-pooling block. But, Due to the limited size of training data, increasing the number of convolutional layers did not show any significant improvement in the performance.

From our results we can conclude that attention based definitely provide better results in an NLP model we had data from many different papers to compare the performance of attention-based models with other models like LSTM, Addition and a few other baseline models and attention-based models outperforms all other models.

Comparing performance of Attention based models with other baselines.

    |               |  MAP   |   MRR   |
    |:-------------:|:------:|:-------:|
    |   ABCNN       | 0.7193 |  0.7165 |
    |  A-LSTM       | 0.6381 |  0.6537 |
    |  WordCnt      | 0.4891 |  0.4924 |
    |  WgtWordCnt   | 0.5099 |  0.5132 |
    |  CNN-Cnt      | 0.6520 |  0.6652 |
    |  Addition     | 0.5888 |  0.5929 |
We can see how ABCNN outperforms every other model also for a few attention-based models, performance of our model is better that what is presented in the paper.

## Papers



