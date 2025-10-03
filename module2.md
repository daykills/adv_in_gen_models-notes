# Optimization
Training model is about:
- formulate the loss function
- search the optimal model paramete to minimize the loss function, but with billions of parameters and data, the optimization is really very expensive.

# Ideas used in traing
Gradient desent: start with some (w,b), keep changing w,b a bit to reduece the cost function until the cost function settles at or near a minimum.  
  w = w - learning rate * derivative of cost fuunction over w
  b = b - learning rate * derivative of cost fuunction over b
  update w and b at the same time
  not directly applicable in practice. Because if we have really larget data set, then the loss function are really often the sum of the losses across the whole data set.
