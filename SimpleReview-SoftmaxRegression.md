# 복습

​    

### 소프트맥스 회귀 Softmax Regression    

Multi-class Classification    

<br/>

If we have to classify into __k__ classes, we get __k dim vector__ for input     

![equation](https://latex.codecogs.com/gif.latex?p_%7Bi%7D%3D%5Cfrac%7Be%5E%7Bz_%7Bi%7D%7D%7D%7B%5Csum_%7Bj%3D1%7D%5E%7Bk%7D%20e%5E%7Bz_%7Bj%7D%7D%7D%5C%20%5C%20for%5C%20i%3D1%2C%202%2C%20...%20k)

__Example__    

k = 3     

Then, we have z = [z1, z2, z3] for input     

Softmax function returns      

![equation](https://latex.codecogs.com/gif.latex?softmax%28z%29%3D%5B%5Cfrac%7Be%5E%7Bz_%7B1%7D%7D%7D%7B%5Csum_%7Bj%3D1%7D%5E%7B3%7D%20e%5E%7Bz_%7Bj%7D%7D%7D%5C%20%5Cfrac%7Be%5E%7Bz_%7B2%7D%7D%7D%7B%5Csum_%7Bj%3D1%7D%5E%7B3%7D%20e%5E%7Bz_%7Bj%7D%7D%7D%5C%20%5Cfrac%7Be%5E%7Bz_%7B3%7D%7D%7D%7B%5Csum_%7Bj%3D1%7D%5E%7B3%7D%20e%5E%7Bz_%7Bj%7D%7D%7D%5D%20%3D%20%5Bp_%7B1%7D%2C%20p_%7B2%7D%2C%20p_%7B3%7D%5D%20%3D%20%5Chat%7By%7D%20%3D%20%5Ctext%7Bprediction%7D)

p1 : Probability that Class1 is the answer    

p2 : Probability that Class2 is the answer     

p3 : Probability that Class3 is the answer    

1 = p1 + p2 + p3

<br/>

![image](https://wikidocs.net/images/page/35476/softmax1_final_final_ver.PNG)

Before put in to Softmax function, __dimension of vector should the number of classes__     

![image](https://wikidocs.net/images/page/35476/softmaxbetween1and2.PNG)

__How to get error?__     

![image](https://wikidocs.net/images/page/35476/softmax2_final.PNG)

​    

![image](https://wikidocs.net/images/page/35476/softmax4_final.PNG)

In this case, the error is 0 when the result of Softmax function is [0 1 0]    

To get error between prediction and y, we use __Cross Entropy function__ for cost function    

![image](https://wikidocs.net/images/page/35476/softmax6_final_2ldz1s0.PNG)

<br/>

The process by vector and matrix multiplication     

![image](https://wikidocs.net/images/page/35476/softmax7.PNG)

<br/>

It is not necessary to use One-Hot vector to express y     

##### But,     

if we encode like {red, green, blue}  to {1, 2, 3}  and use MSE for Cost function,     

MSE when  prediction : red,   answer : green

![image](https://latex.codecogs.com/gif.latex?%282-1%29%5E%7B2%7D%20%3D%201)

MSE when prediction  : blue,  answer : red

![image](https://latex.codecogs.com/gif.latex?%283-1%29%5E%7B2%7D%20%3D%204)

Error between blue and red is bigger than error between red and green.     

__It means that we give info that green is more closer to red than blue to machine__    

__When we use One-Hot Encoding__,    

![image](https://latex.codecogs.com/gif.latex?%28%281%2C0%2C0%29-%280%2C1%2C0%29%29%5E%7B2%7D%20%3D%20%281-0%29%5E%7B2%7D%20&plus;%20%280-1%29%5E%7B2%7D%20&plus;%20%280-0%29%5E%7B2%7D%20%3D%202)

![image](https://latex.codecogs.com/gif.latex?%28%281%2C0%2C0%29-%280%2C0%2C1%29%29%5E%7B2%7D%20%3D%20%281-0%29%5E%7B2%7D%20&plus;%20%280-0%29%5E%7B2%7D%20&plus;%20%280-1%29%5E%7B2%7D%20%3D%202)

All Euclidean Distances are same

<br/>

<br/>



#### Softmax Regression uses Cross Entropy function for cost function     

​     



#### To minimize ![equation](https://latex.codecogs.com/gif.latex?-%5Csum_%7Bj%3D1%7D%5E%7Bk%7Dy_%7Bj%7D%5C%20log%28p_%7Bj%7D%29) is important!      

<br/>



![image](https://latex.codecogs.com/gif.latex?cost%28W%29%20%3D%20-%5Cfrac%7B1%7D%7Bn%7D%20%5Csum_%7Bi%3D1%7D%5E%7Bn%7D%20%5Csum_%7Bj%3D1%7D%5E%7Bk%7Dy_%7Bj%7D%5E%7B%28i%29%7D%5C%20log%28p_%7Bj%7D%5E%7B%28i%29%7D%29)

k : Number of classes    

y __j__ : __j__ th index of vector which encoded y by One-Hot Encoding     

p __j__ : Probability which sample data is __j__ th class     

If __4__ th index is 1 in y vector  (y = [0 0 0 1]),   __4__ is the case when we predict correctly     

Then, -1log(1) = 0    ->   Cross Entropy function is 0  

#### <br/>

__It looks different from Cross Entropy function we learned in Logistic Regression__     

__But! Those are essentially same!__       

​    



![image](https://latex.codecogs.com/gif.latex?cost%28W%29%20%3D%20-%28y%5C%20logH%28X%29%20&plus;%20%281-y%29%5C%20log%281-H%28X%29%29%29)

This is the Cross Entropy function we use during Logistic Regression      

When we substitute __y__ to __y1__ , __1-y__ to __y2__ , __H(X)__ to __p1__ , __1 - H(X)__ to __p2__ , then we get      

![image](https://latex.codecogs.com/gif.latex?-%28y_%7B1%7D%5C%20log%28p_%7B1%7D%29&plus;y_%7B2%7D%5C%20log%28p_%7B2%7D%29%29)

It is ![image](https://latex.codecogs.com/gif.latex?-%28%5Csum_%7Bi%3D1%7D%5E%7B2%7Dy_%7Bi%7D%5C%20log%5C%20p_%7Bi%7D%29)     

In Softmax Regression, k is not fixed so change 2 to k       

We get ![image](https://latex.codecogs.com/gif.latex?-%28%5Csum_%7Bi%3D1%7D%5E%7Bk%7Dy_%7Bi%7D%5C%20log%5C%20p_%7Bi%7D%29) which is eventually same. 

<br/>     

We can also do reverse!       

Substitute __k__ to __2__ , __y1 , y2__ to __y, 1-y__ , __p1, p2__ to __H(X), 1 - H(X)__     

__If we assume k is 2, cost function in Softmax Regression is same with cost functio in Logistic Regression!__     

<br/>

![image](https://latex.codecogs.com/gif.latex?%5Cdpi%7B150%7D%20%5Ctiny%20cost%28W%29%20%3D%20-%5Cfrac%7B1%7D%7Bn%7D%20%5Csum_%7Bi%3D1%7D%5E%7Bn%7D%20%5Csum_%7Bj%3D1%7D%5E%7Bk%7Dy_%7Bj%7D%5E%7B%28i%29%7D%5C%20log%28p_%7Bj%7D%5E%7B%28i%29%7D%29%20%3D%20-%5Cfrac%7B1%7D%7Bn%7D%20%5Csum_%7Bi%3D1%7D%5E%7Bn%7D%20%5By%5E%7B%28i%29%7Dlog%28p%5E%7B%28i%29%7D%29%20&plus;%20%281-y%5E%7B%28i%29%7D%29log%281-p%5E%7B%28i%29%7D%29%5D)

