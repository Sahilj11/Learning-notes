# Unit 1

### Performance measure of learning
1. Generality:- refers to ML model's ability to perform well accross various datasets and environment, not just one it was trained on.
2. Efficiency:- How quickly a model can learn from data. A spam detection algorithm that quickly adapts to new type of spam emails
3. Robustness:- ability of a model to handle errors, noise and unexcpected data without failing. A voice recognition system able to recognize voice in a noisy room.
4. Efficacy:- overall effectiveness of a ML model in performing its intended tasks.
5. Ease of implementation:- how straightforward is it to develop and deploy a ML model.

### Supervised learning
- involves training a machine learning model using labeled data, which means the **data is already associated with correct answer**.
  Eg: predicting house prices based on features like size and location, using a dataset where prices are known, allows the model to learn and make accurate predictions on new, unseen data.

#### Steps in Supervised learning
- input and output pairing:- each input is paired with its correct label.
- training:- model learns by compairing its prediction with actual label and adjusting itself to improve accuracy.
- error correction:- if model predicts incorrectly it adjusts its internal parameters to reduce error.
- outcome:- model eventually learn to map input to correct output.

### Unsupervised learning
- involves training model without any label , which means the model tries to identify patterns and data groupings on its own.
  Eg: Imagine placing a mix of different coins on a table and asking to sort them. without explaining any criteria , the child might start grouping by size,color etc.

#### Steps 
- input without labels:- the model receives data without any explicit instructions on what to do with it.
- pattern recognition:- model analyze data and tries to find any natural grouping or patterns.
- self-organisation:- model organise data into different categories based on the patterns it receives.
- outcome:- model creates its own system of categorization without external guidance.
