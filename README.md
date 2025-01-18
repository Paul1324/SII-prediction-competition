# French Text Classification Analysis

## Dataset Analysis

### Label Distribution in Training Data

The initial analysis of `train.csv` revealed the following label distribution:

- True: 1,185 samples (60.83%)
- Fake: 514 samples (26.39%)
- Biased: 249 samples (12.78%)

This distribution suggests that a baseline model always predicting "true" could achieve approximately 60% accuracy. However, this would not be a meaningful solution to the classification problem.

### Word Frequency Analysis

To identify potential patterns for each label, we analyzed the most frequent words in the texts, excluding French stop words. The word frequency visualization showed no clear lexical patterns distinguishing between the different labels, suggesting the need for more sophisticated analysis methods.

## Model Development

### Approach

Given the lack of clear lexical patterns, we opted for fine-tuning pre-trained transformer models:

1. General multilingual BERT
2. CamemBERT (specifically pre-trained on French text)

### Training Process

- Dataset split: 80% training, 20% validation
- Both models were fine-tuned using the same hyperparameters and training configuration
- CamemBERT demonstrated superior performance compared to the general BERT model

### Final Results

The final predictions on the test dataset (`test.csv`) showed the following distribution:

- True: 320 samples (65.84%)
- Fake: 132 samples (27.16%)
- Biased: 34 samples (7.00%)

### Observations

The similarity between the training and test label distributions suggests that the model may have learned to replicate the training data's distribution pattern. This could indicate either:

1. The test data naturally follows a similar distribution to the training data
2. The model might be biased towards reproducing the training distribution

Source code: https://github.com/Paul1324/SII-prediction-competition
