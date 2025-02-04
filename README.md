# Water Quality Classification Model

## Overview
This project involves building a neural network-based classification model to assess water quality using TensorFlow/Keras. The assignment focuses on data preprocessing, model training, optimization, evaluation, and comparison with teammates' models.

## Objective
Develop a neural network-based classification model using a water potability dataset, incorporating multiple optimization techniques and ensuring equitable group contribution.

## Summary Table

| **Train Instance**                                 | **Engineer Name** | **Regularizer** | **Optimizer**                          | **Early Stopping** | **Dropout Rate**        | **Accuracy** | **F1 Score** | **Recall** | **Precision** | **Train Loss** | **Validation Loss** | **Test Loss** | **Epochs** |
|--------------------------------------------------|------------------|---------------|---------------------------------|----------------|-----------------|------------|----------|--------|-----------|------------|-----------------|-----------|--------|
| Obolo_Emmanuel_Oluwapelumi_Water_Potability_Model_.ipynb | Emmanuel Obolo   | No            | Adam                            | No             | 0.9 and 0.8      | 0.6362     | 0.4389   | 0.3590  | 0.5645    | 0.5535     | 0.6015          | 0.6636    | 400    |
| Humphrey_Nyahoja_Water_Potability_Model_.ipynb  | Humphrey Nyahoja | L2            | AdamW                           | Yes            | 0.2, 0.3, 0.4, 0.5 | 0.6931     | 0.3837   | 0.2640  | 0.7015    | 0.9938     | 1.0405          | 1.0208    | 800    |
| Eunice_Adewusi_Water_Potability_Model_.ipynb    | Eunice Adewusi   | L2            | Stochastic Gradient Descent (SGD) | Yes            | 0.2             | 0.6240     | 0.3947   | 0.4988  | 0.4980    | 0.5633     | 0.5984          | 0.6754    | 100    |

## Insights, Challenges, and Conclusions

### **Emmanuel Obolo**
#### **Insights & Challenges:**
- Increasing layers and neurons led to overfitting and poor generalization, evidenced by high validation loss.
- Struggled to find the optimal architecture and parameters to minimize loss.
- Limited potable water samples made classification difficult.

#### **Conclusion:**
- Chosen hyperparameters resulted in relatively low losses across training, validation, and testing.
- Keeping loss values close helped prevent overfitting while allowing sufficient learning from the dataset.

---

### **Humphrey Nyahoja**
#### **Insights:**
- Different dropout rates per layer improved generalization.
- Lower dropout in early layers and higher dropout in deeper layers prevented overfitting.
- L2 regularization helped keep model weights in check.
- Early stopping and 800 epochs prevented underfitting.

#### **Challenges:**
- The hinge loss function performed poorly with sigmoid activation, lowering the F1-score.

#### **Conclusion:**
- Many epochs improved performance, especially precision.
- L2 regularization and early stopping improved accuracy.

---

### **Eunice Adewusi**
#### **Insights:**
- **L2 Regularization:** Higher values caused over-regularization; **0.0001** improved generalization.
- **Optimizer & Learning Rate:**
  - **SGD with momentum (0.9) and LR = 0.01** caused instability.
  - Lowering LR to **0.007** improved convergence.
  - **ReduceLROnPlateau** prevented premature stopping.
- **Dropout Impact:**
  - **High dropout (0.4-0.5)** caused underfitting.
  - **Lowering it to 0.2** balanced overfitting and learning.
- **Early Stopping:**
  - **Patience = 7** provided the best balance.
- **Class Imbalance:**
  - Low recall for "Unsafe" class (0.18), but better recall for "Safe" (0.82).
  - **F1-score (0.3947)** was more reliable than accuracy.

#### **Challenges:**
- High L2 values increased loss, requiring fine-tuning.
- Dropout needed careful tuning to avoid over/underfitting.
- **SGD required extensive tuning compared to Adam or RMSprop.**
- Sensitivity to early stopping patience values.

#### **Conclusions:**
1. **(L2 = 0.01, LR = 0.01, Dropout = 0.4, No Early Stopping)** → Underfitting, unstable loss, poor accuracy.
2. **(L2 = 0.0001, LR = 0.007, Dropout = 0.2, Early Stopping = 7)** → Best balance, smooth convergence, good generalization.
3. **(L2 = 0, LR = 0.005, Dropout = 0.3, Early Stopping = 5)** → Overfitting, high training accuracy but poor test accuracy.
4. **(L2 = 0.0005, LR = 0.001, Dropout = 0.1, No Early Stopping)** → Training was slow, and validation loss plateaued early.

#### **Final Takeaways:**
- Careful tuning of **SGD (learning rate, momentum)** is crucial.
- **Dropout around 0.2** balances learning and overfitting.
- **Minimal L2 regularization (0.0001) helps without overly penalizing weights.**
- **F1-score is more reliable than accuracy due to class imbalance.**

---

## Group Video Presentation
In this video, we explained our contributions and findings. Click [here](https://youtu.be/yA3GvBPeNY8) to watch.