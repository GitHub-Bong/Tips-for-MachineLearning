# 복습

### <br/>선형 회귀 Linear Regression

<br/>

__1) 단순 선형 회귀 분석 (Simple Linear Regression Analysis)__  

![equation](https://latex.codecogs.com/svg.latex?y%20=%20Wx%20+b)

W : 가중치(weight)   

b : 편향(bias)   

<br/>

__2) 다중 선형 회귀 분석 (Multiple Linear Regression Analysis)__     

   

![equation](https://latex.codecogs.com/svg.latex?y%20=%20{W_1x_1%20+%20W_2x_2%20+%20...%20W_nx_n%20+%20b})       

y is still one   

Not one x, but several x      

<br/>

![equation](https://latex.codecogs.com/svg.latex?H(x)%20=%20{Wx%20+%20b})    

__H__ means Hypothesis    

<br/>

##### What we have to do by LR is to find _appropriate W and b_

<br/>

In ML, to find __W__ and __b__, we use __Cost function(Loss function)__    

Cost function is about the error between y and y^    

### We have to minimize Cost function!     

<br/>

There are various cases in DL each of them have appropriate cost function    

In case of Regression, we use  __MSE(Mean Squared Error)__ !      

![equation](https://latex.codecogs.com/gif.latex?cost%28W%2C%20b%29%20%3D%20%5Cfrac%7B1%7D%7Bn%7D%20%5Csum_%7Bi%3D1%7D%5E%7Bn%7D%20%5Cleft%5By%5E%7B%28i%29%7D%20-%20H%28x%5E%7B%28i%29%7D%29%5Cright%5D%5E2)

​     

![equation](https://latex.codecogs.com/gif.latex?W%2C%20b%20%5Crightarrow%20minimize%5C%20cost%28W%2C%20b%29)

​    

<br/>

To find __W, b__ to minimize Cost function, we use __Optimizer 또는 최적화 알고리즘__ !     

The process using optimizer to find appropriate __W, b__ is called __Training (학습)__     

<br/>

Basic optimizer algorithm __Gradient Descent (경사하강법)__    



![image](https://wikidocs.net/images/page/21670/%EC%A0%91%EC%84%A0%EC%9D%98%EA%B8%B0%EC%9A%B8%EA%B8%B01.PNG)

__The idea of Gradient Descent __

1. Derivative Costfunction   

2. Get the slope of the tangent line (접선의 기울기)
3. Move W to the direction where the slope of the tangent line is low      

   

Iterate __until the slope of the tangent line becomes 0__

<br/>

![equation](https://latex.codecogs.com/gif.latex?cost%28W%2C%20b%29%20%3D%20%5Cfrac%7B1%7D%7Bn%7D%20%5Csum_%7Bi%3D1%7D%5E%7Bn%7D%20%5Cleft%5By%5E%7B%28i%29%7D%20-%20H%28x%5E%7B%28i%29%7D%29%5Cright%5D%5E2)

we update __W__ to get __W__ which minimize cost function by     

![equation](https://latex.codecogs.com/gif.latex?W%20%3A%3D%20W%20-%20%5Calpha%20%5Cfrac%7B%5Cpartial%20%7D%7B%5Cpartial%20W%7Dcost%28W%29)

alpha : Learning Rate 

![image](https://wikidocs.net/images/page/21670/%EB%AF%B8%EB%B6%84.PNG)

​    

![equation](https://latex.codecogs.com/gif.latex?W%20%3A%3D%20W%20-%20%5Calpha%20%28negative%20%5C%3B%20slope%29%20%3D%20W%20&plus;%20%5Calpha%20%28positive%20%5C%3A%20slope%29)

Whether the slope is negative or positive, W updates to let slope becomes 0     

![image](https://wikidocs.net/images/page/21670/%EA%B8%B0%EC%9A%B8%EA%B8%B0%EB%B0%9C%EC%82%B0.PNG)

If LR(Learning Rate) is too high, W is diverge to infinity    

If LR is too low, the training goes too slow     

Thus, it is important to find out the appropriate alpha

<br/>

### Summary

Hypothesis, Cost function, Optimizer can be totally different by what we gonna solve.

__MSE__ and __Gradient Desecent__ is the best fitting Cost function and Optimizer for __LR__

