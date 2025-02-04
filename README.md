# Water Quality Classification Model

## Overview
This project involves building a neural network-based classification model to assess water quality using TensorFlow/Keras. The assignment focuses on data preprocessing, model training, optimization, evaluation, and comparison with teammates' models.

## Objective
Develop a neural network-based classification model using a water potability dataset, incorporating multiple optimization techniques and ensuring equitable group contribution.

## Summary Table

| **Train Instance** | **Engineer Name** | **Regularizer** | **Optimizer** | **Early Stopping** | **Dropout Rate** | **Accuracy** | **F1 Score** | **Recall** | **Precision** | **Train Loss** | **Val Loss** | **Test Loss** | **Epochs** |
|--------------------|------------------|----------------|--------------|----------------|--------------|------------|------------|--------|-----------|------------|------------|------------|--------|
| Obolo_Emmanuel_Oluwapelumi_Water_Potability_Model_.ipynb | Emmanuel Obolo | No | Adam | No | 0.9 and 0.8 | 0.6362 | 0.4389 | 0.3590 | 0.5645 | 0.5535 | 0.6015 | 0.6636 | 400 |
| Humphrey_Nyahoja_Water_Potability_Model_.ipynb | Humphrey Nyahoja | L2 | AdamW | Yes | 0.2, 0.3, 0.4, and 0.5 | 0.6931 | 0.3837 | 0.2640 | 0.7015 | 0.9938 | 1.0405 | 1.0208 | 800 |
| Eunice_Adewusi_Water_Potability_Model_.ipynb | Eunice Adewusi | L2 | SGD | Yes | 0.2 | 0.6240 | 0.3947 | 0.4988 | 0.4980 | 0.5633 | 0.5984 | 0.6754 | 100 |

## Model Insights, Challenges, and Conclusions

### Emmanuel Obolo
**Insights:** 
- Increasing layers and neurons led to overfitting, with high validation loss.
- Despite achieving a relatively low train loss, the model struggled to generalize.

**Challenges:** 
- Validation loss did not improve despite improved train loss.
- Limited potable water samples made learning difficult.

**Conclusion:** 
- The chosen combination resulted in balanced train, validation, and test losses, preventing excessive overfitting while learning sufficiently from the dataset.

### Humphrey Nyahoja
**Insights:** 
- Using different dropout rates in different layers helped improve generalization.
- L2 regularization prevented weights from growing too large, ensuring stability.

**Challenges:** 
- Hinge loss did not perform well with sigmoid activation, leading to a low F1-score.

**Conclusion:** 
- Higher epochs and L2 regularization improved precision and accuracy.

### Eunice Adewusi
**Insights:** 
- Fine-tuning L2 regularization, learning rate, and dropout prevented overfitting.
- Early stopping and ReduceLROnPlateau improved convergence and stability.

**Challenges:** 
- High dropout (0.4-0.5) led to underfitting, requiring adjustments.
- SGD optimization needed extensive tuning for stability.

**Conclusion:** 
- A balanced configuration (L2=0.0001, LR=0.007, Dropout=0.2) provided the best stability and performance.

## Model Comparison
- **Accuracy:** Humphrey's model (69.31%) outperformed others, followed by Emmanuel (63.62%) and Eunice (62.40%).
- **F1-score:** Emmanuel's model (0.4389) performed the best, followed by Eunice (0.3947) and Humphrey (0.3837). 
- **Recall:** Eunice’s model had the highest recall (0.4988), making it better at identifying the "Unsafe" class.
- **Precision:** Humphrey's model had the highest precision (0.7015), meaning it had fewer false positives.
- **Loss Comparison:** Eunice's model had the lowest test loss (0.6754), showing better generalization. 
- **Training Stability:** Eunice's model had the most stable convergence due to well-tuned regularization and early stopping.

## Best Performing Model Selection
Based on the evaluation metrics, **Humphrey's model** is the best-performing model overall due to its **highest accuracy (69.31%) and precision (0.7015)**, which ensures fewer false positives. However, Emmanuel's model has a better F1-score, and Eunice’s model generalizes better with the lowest test loss. The choice depends on whether priority is given to overall accuracy or balancing precision and recall.

### **Why Humphrey’s Model Was Chosen?**
1. **Highest accuracy (69.31%)**, meaning it classifies water quality most correctly overall.
2. **Strong precision (0.7015)**, reducing false positives, which is crucial in safety-critical applications.
3. **Regularization strategies** (L2 and dropout variation) improved generalization, avoiding overfitting while achieving high accuracy.
4. **Longer training (800 epochs)** allowed the model to refine its learning, leading to superior performance.

## Group Video Presentation
In this video, we explained our contributions and findings. Click [here](https://youtu.be/yA3GvBPeNY8) to watch.