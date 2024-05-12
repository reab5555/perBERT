<img src="icon.webp" width="150" alt="alt text">

# perBERT
This fine-tuned BERT model is able to predict Personality Traits (Five-Factor Model) from written texts that people have written about themselves and their general experience.

# Description
https://huggingface.co/reab5555/perBERT

This model is fine-tuned version of bert-base-uncased.    
Trained on both MyPersonality dataset and Pandora dataset (Reddit posts written by users that were taken a Big Five questionnaires).   
   
It includes the following classes:   
* Extraversion (outgoing/energetic vs. solitary/reserved)   
* Neuroticism (sensitive/nervous vs. resilient/confident)   
* Agreeableness (friendly/compassionate vs. critical/judgmental)   
* Conscientiousness (efficient/organized vs. extravagant/careless)   
* Openness to experience (inventive/curious vs. consistent/cautious)   

# Training
   
model-finetuning: google-bert/bert-base-uncased    
   
The following hyperparameters were used during training:   
    
Training set: 90% - 29930   
Validation set: 10% - 7238   
    
seed: 42   
learning_rate: 1e-5  
train_batch_size: 16   
val_batch_size: 16   
optimizer: AdamW   
num_epochs: 3   

# Training results
| Epoch | Training Loss | Validation Loss | F1 Score |
|-------|---------------|-----------------|----------|
| 1.0   | 0.6149        | 0.5989          | 0.4928   |
| 2.0   | 0.5721        | 0.5811          | 0.6315   |
| 3.0   | 0.5129        | 0.5740          | 0.6381   |

   
## Classification Report
              precision    recall  f1-score   support

        cEXT       0.61      0.45      0.51      1225
        cNEU       0.60      0.58      0.59      1430
        cAGR       0.59      0.46      0.52      1211
        cCON       0.60      0.52      0.56       990
        cOPN       0.76      0.89      0.82      2382
