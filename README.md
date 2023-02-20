# Implement Forward Propagation and Backpropagation from scratch

## Backpropagation: Backpropagation is basically multi-epoch training methodology where we leverage chain rule (differentiation) + memoization to update the weights.
Backpropagation only works if the activation functions are differentiable. While training the weights we come across some derivatives that repeatedly gets computed, to avoid this repetition we use memoization concept where we compute those derivatives and store them to reuse instead of computing them each time.
- Steps:
Given the dataset D{Xi,Yi}
1) Just like every optimization, we initialize the parameters Wij's.
2) a) For each Xi in D
          
          pass Xi forward through the network.          ..... THis step is called forward propagation.
   
   b) Compute th loss L on Yi & Yi^.
   
   c) Using this, compute all the derivatives using chain rule & memoization as we did earlier.
   
   d) Update the weights from end of the network to the start. i.e Go in reverse direction to update the weights.
                                                        ..... THis step is called forward propagation.
3) Repeat step 2) till convergence.

Let's see the implementation of backpropagation using example with simple loss function.

# <font color='red'>Computational graph</font>
![image](https://user-images.githubusercontent.com/87875987/220165888-53d576ca-a1f6-4830-b99a-fac927acddd4.png)
- If you observe the graph, we are having input features [f1, f2, f3, f4, f5] and 9 weights [w1, w2, w3, w4, w5, w6, w7, w8, w9].
- The final output of this graph is a value L which is computed as (Y-Y')^2

## Forward propagation
- Part 1
![image](https://user-images.githubusercontent.com/87875987/220166176-ff6535fa-65f5-4afb-ad45-67131d933571.png)

- Part 2
![image](https://user-images.githubusercontent.com/87875987/220166219-898bca39-3a62-44cc-855b-7f129cd11e33.png)

-Part 3
![image](https://user-images.githubusercontent.com/87875987/220166253-83ff30c7-20b7-4607-a279-e4bbd0d87121.png)

