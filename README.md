### Assignment-A6 ==============> **assignment-a6.ipynb**

Result
==========================
Results shows that the top K layers configuration demonstrates the best performance with the lowest losses and highest accuracy. Bottom K layers, odd layers, and even layers configurations show progressively poorer performance, with the bottom K layers configuration performing the worst.

##### Model Results
Student Layer    |  Training Loss |  Validation Loss |  Validation Accuracy
---------------  | ------------   | -------------    | ---------------
Top 6 Layers     |   0.325064     |   0.963251       |      0.560 
Bottom 6 Layers  |   0.659352     |   1.104177       |      0.333
Odd Layers       |   0.812383     |   1.104363       |      0.323
Even Layers      |   0.507798     |   1.109943       |      0.326




Evaluation and Analysis
=========================

### Top 6 Layers

- Over five epochs, the training loss drops from 0.3601 to 0.2935.
- Over five epochs, the validation loss drops from 0.9816 to 0.9673.

Validation accuracy shows a small improvement, starting at 0.5520 and increasing to 0.5550.
Training and validation losses both go down across epochs, and accuracy somewhat improves, suggesting that the model learned effectively.


### Bottom 6 Layers

- Throughout five epochs, the training loss stays nearly constant at 0.6594.
- The validation loss was constant at 1.1042.
- The validation accuracy stayed at 0.3330.

Since neither loss nor accuracy changed much over epochs, it appeared that the model did not learn much. It suggests that important features might not be captured by the chosen layers.


### Odd Layers

- The training loss remained relatively constant around 0.8125 over 5 epochs.
- Validation loss remained constant at 1.1044.
- Validation accuracy was constant at 0.3230.

Similar to the bottom k layers, the model does not seemed to learn much, with no significant change in loss or accuracy over epochs.


### Even Layers

- Over the course of five epochs, the training loss stayed comparatively constant at 0.5079.
- The validation loss was still 1.1099, unchanged.
- The validation accuracy of 0.3260 did not change.

As with the bottom and odd layers, there is no discernible learning progress in the model.


### Conclusion

Among the various layer selections, the top k layers showed the best learning behaviour, with decreasing loss and a slight improvement in accuracy.
The bottom k, odd, and even layers exhibited poor learning behaviour because accuracy and loss did not changed significantly across epochs.The learning capacity and overall performance of the model were strongly influenced by the choice of first layers. Top layers appeared to capture more important features than bottom, odd, or even layers.
It is clear that choosing the right starting layers is essential to the distilled student model's effectiveness. Learning and performance are often improved by layers that capture pertinent features.



Limitations
==========================

- Comparing the student model to the teacher model, the student model might be less capable. This restriction may have an impact on the first layer selection, since choosing too many layers could overload the student model and result in not that great performance.

- The student model may be overfitting or underfitting if the teacher model's essential features are not adequately captured by the first layer selection.

- The initial layer selection process may not adequately capture these task-specific features, leading to reduced performance on the target task.

- The knowledge distilled from the teacher model may not transfer effectively to the student model if the initial layer selection does not align with the student model's architecture and capacity. 


Potential Improvements
===========================

- Implement algorithms or techniques for dynamically selecting initial layers based on the student model's architecture and capacity. 

- Perform a multi-stage distillation process in which the learning progress of the student model is used to gradually choose and refine the initial layers. 

- Include mechanisms for attention in the distillation process so that, depending on how relevant a layer or feature is to the intended job, the emphasis can be dynamically adjusted.



