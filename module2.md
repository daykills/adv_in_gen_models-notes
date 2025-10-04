# Part 1: Optimization
Training model is about:
- formulate the loss function
- search the optimal model paramete to minimize the loss function, but with billions of parameters and data, the optimization is really very expensive.

# Ideas used in traing
## 1. Gradient desent

**Gradient desent**: start with some (w,b), keep changing w,b a bit to reduece the cost function until the cost function settles at or near a minimum.  
  w = w - learning rate * derivative of cost fuunction over w
  b = b - learning rate * derivative of cost fuunction over b
  update w and b at the same time
  not directly applicable in practice. Because if we have really larget data set, then the loss function are really often the sum of the losses across the whole data set, each data 
  point contribute some loss, thus the overall loss is the average loss over the whole date set. -> too slow, not used in practice

**Stochastic gradient descent**: we randomly sample one data point or a batch of data points. -> quick, used in practice 

## 2. Momentum
   Gradient desent can vary dramatically across iterations because we use not use the whole data set to calculate. Momentum helps smooth out    noise and accelerate progress.
   w = w - learning rate * momentum
   momentum = momentum * a + (1 - a) * batch gradients

## 3. Normalizing Gradients
Often some coordinates have much larger magnitude. To resolve this problem, we just need the sign of gradient or momentum, ingore the magnitude.
Or use the softsign where x divide the absoluate value of x

Adam: is an "adaptive" variant of softsign momentum

## 4. Weight Decay: Regularization and Constraint
To prevent overfitting, it is common to use L2 regularization. In addition to optimize the loss function, we add L2 penalty into the loss.



# Part 2: Neural Networks
In generative models as well as in supervised learning, in the end the problem is reduced to approximating certian unknown function.

## Linear functions
## Neural Networks
combine linear transformations with nonlinear activations
Common activations: ReLU, sigmoid, tanh

Back in days, not easy to use deep network due to 
- In deep networks, if the derivative at each layer is on average less than 1, gradients vanish, and if it’s greater than 1, gradients explode; therefore, keeping derivatives close to 1 ensures stable gradient flow and effective learning.
- to solve the above probem -> Residual connections: directly connecting input and output

## Attention Mechanism
input: vector-based, feature vector
new concept: point_based: collection of data, can be viewed as (location: value)

