# 복습    

​     

### 로지스틱 회귀 Logistic Regression    

To solve __Binary Classification__ 

<br/>

y can be only __0__ or __1__     

-> In case of LR, y can be everything ! Even negative infinity    

<br/>    

__Hypothesis__

![image](https://latex.codecogs.com/gif.latex?H%28X%29%20%3D%20%5Cfrac%7B1%7D%7B1%20&plus;%20e%5E%7B-%28Wx%20&plus;%20b%29%7D%7D%20%3D%20sigmoid%28Wx%20&plus;%20b%29%20%3D%20%5Csigma%20%28Wx%20&plus;%20b%29)

​    

![image](https://wikidocs.net/images/page/22881/%EC%8B%9C%EA%B7%B8%EB%AA%A8%EC%9D%B4%EB%93%9C%EA%B7%B8%EB%9E%98%ED%94%84.png)

__Sigmoid Function__ has a value __0 ~ 1__    

If 0.5 < H(x) ,  then  1    

If 0.5 > H(x) ,  then 0 

<br/>

### We use Gradient Descent to find _W_, but not using _MSE_.    

 When we use MSE, the cost function looks like,

![image](https://wikidocs.net/images/page/22881/%EB%A1%9C%EC%BB%AC%EB%AF%B8%EB%8B%88%EB%A9%88.PNG)

We could easily goes to __Local Minimum__ instead of __Global Minimum__ .     

<br/>

Instead of using MSE,    

![image](https://latex.codecogs.com/gif.latex?J%28W%29%20%3D%20%5Cfrac%7B1%7D%7Bn%7D%20%5Csum_%7Bi%3D1%7D%5E%7Bn%7D%20cost%5Cleft%28H%28x%5E%7B%28i%29%7D%29%2C%20y%5E%7B%28i%29%7D%29%5Cright%29)

![image](https://latex.codecogs.com/gif.latex?%5Ctext%7Bif%20%7D%20y%3D1%20%5C%3A%20%5C%3A%20%5Cto%20%5Ctext%7Bcost%7D%5Cleft%28%20H%28x%29%2C%20y%20%5Cright%29%20%3D%20-%5Clog%28H%28x%29%29)

![image](https://latex.codecogs.com/gif.latex?%5Ctext%7Bif%20%7D%20y%3D0%5C%3A%20%5C%3A%20%5Crightarrow%20%5Ctext%7Bcost%7D%5Cleft%28%20H%28x%29%2C%20y%20%5Cright%29%20%3D%20-%5Clog%281-H%28x%29%29)

​    To show these equations by graph, 

![image](https://wikidocs.net/images/page/22881/%EC%86%90%EC%8B%A4%ED%95%A8%EC%88%98.PNG)

When y is 0 and y^ goes to 1, the error goes bigger    

When y is 1 and y^ goes to 0, the error goes bigger    

<br/>

![image](https://latex.codecogs.com/gif.latex?%5Ctext%7Bcost%7D%5Cleft%28%20H%28x%29%2C%20y%20%5Cright%29%20%3D%20-%5BylogH%28x%29%20&plus;%20%281-y%29log%281-H%28x%29%29%5D)

<br/>

<br/>

As a result,    __J (Objective function or Cost Function)__ is

![image](https://latex.codecogs.com/gif.latex?J%28W%29%20%3D%20-%5Cfrac%7B1%7D%7Bn%7D%20%5Csum_%7Bi%3D1%7D%5E%7Bn%7D%20%5By%5E%7B%28i%29%7DlogH%28x%5E%7B%28i%29%7D%29%20&plus;%20%281-y%5E%7B%28i%29%7D%29log%281-H%28x%5E%7B%28i%29%7D%29%29%5D)

### Cross Entropy function    

we use __Cross Entropy function__ for cost function during LR.    

Cross Entropy function is cost function of __Softmax Regression__ also. I'll will talk about later