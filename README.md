
<div align="center">
  
<img src="./assets/thumbnail.png" width="300">
  
# NumPy Neural Network
  
</div>  

---

## Contents
* [About](#about)
* [Specifications](#specifications)
* [Usages](#usages)
* [Notes](#notes)
* [References](#references)
---

<a name="about"></a>
## About
Numpy Neural Network - Neural Network from scratch	
- Designed and developed a scalable neural network model entirely from scratch with NumPy.
- Integrated backpropagation and gradient descent, enabling the neural network model to learn and improve its predictions.
- Optimized hyperparameters to achieve approximately 98% test accuracy on Iris dataset within 10 seconds of training on CPU.
---



<a name="specifications"></a>
## Specifications
### <ins>Backward propagation</ins>:  
- Calculates the gradient of the loss function E with respect to the input X. Transpose because the dimensions need to match for the matrix multiplication.  
    $$\frac{\partial E}{\partial X} = \frac{\partial E}{\partial Y} W^T$$   
- Calculates the gradient of the loss function E with respect to the weight matrix W. Used to update the weights based on degree of contribution to the loss.   
    $$\frac{\partial E}{\partial W} = X^T\frac{\partial E}{\partial Y}$$   
- Calculates the gradient of the loss function E with respect to the bias vector B. Used to update the biases based on degree of contribution to the loss.  
    $$\frac{\partial E}{\partial B} = \frac{\partial E}{\partial Y}$$   
- Calculates the gradient of the loss function E with respect to the input X, taking into account the activation function's derivative g'(X). Used to propagate the gradients backward through the activation function.  
    $$\frac{\partial E}{\partial X} = \frac{\partial E}{\partial Y} *g'(X)$$   
---
    
### <ins>Loss function</ins>:   
- The mean squared error loss function. n is the number of examples, Y_hat is the predicted values, Y is the true values.   
    $$E = \frac{1}{n}\Sigma (\hat{y_i}-y_i)^2$$   
- The mean squared error loss function, n is the number of examples, Y_hat is the predicted values, Y is the true values.   
    $$\frac{\partial E}{\partial X} = \frac{2}{n}(Y-\hat{Y})$$   
---

<a name="usages"></a>
## Usages
- Install dependencies in ```requirements.txt```
- Edit network architecture in ```main.py```.
- Launch ```main.py```.
---

<a name="notes"></a>
## Notes
- Delete weight files in weights folder if changing network architecture.
- One hot encoded Y is assumed: [[y1][y2]...[yn]] for n samples.
- Pretrained with Mean Squared Error of $10^{-6}$:  
    ```
    $ python main.py 
    epoch 100/1000   error=0.000002
    epoch 200/1000   error=0.000001
    epoch 300/1000   error=0.000001
    epoch 400/1000   error=0.000001
    epoch 500/1000   error=0.000001
    epoch 600/1000   error=0.000001
    epoch 700/1000   error=0.000001
    epoch 800/1000   error=0.000001
    epoch 900/1000   error=0.000001
    epoch 1000/1000   error=0.000001
    Prediction:  [1 1 0 1 2 2 2 0 0 0]
    Actual:      [1 1 0 1 2 2 2 0 0 0]
    Accuracy:    100.0 %
    (env)
    ```  
- <ins>Add</ins>: Batch, MiniBatch, Stochastic Gradient Descent, Batch Normalization, Adam Optimizer.
---

<a name="references"></a>
## References
- Iris Dataset by [UCI](https://archive.ics.uci.edu/ml/datasets/iris).  
- Neural Network by [Wikipedia](https://en.wikipedia.org/wiki/Neural_network).  
- Backpropagation by [Wikipedia](https://en.wikipedia.org/wiki/Backpropagation).  
