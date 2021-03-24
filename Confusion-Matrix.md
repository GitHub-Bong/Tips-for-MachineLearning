# 혼동 행렬 (Confusion Matrix)



머신 러닝에서 정확도(Accuracy)란?  

​	맞춘 문제 수 / 전체 문제수  

-> 맞춘 결과와 틀린 결과에 대한 세부적인 내용을 알 수 없다!



### -> 그래서 사용하는 것이 바로 혼동 행렬 (Confusion Matrix) !



ex) 양성(Positive)과 음성(Negative)을 구분하는 이진 분류

<img src = "/images/confusion-matrix-1.PNG" width = "200px">

각 __열__은 __예측값__        /       각 __행__은 __실제값__



##### TP(True Positive),   TN(True Negative),   FP(False Postivie),   FN(False Negative)  

__True__는 정답을 맞춘 경우!     

__False__는 정답을 맞추지 못한 경우!  

TP :   대답 : Positive   /    실제: Positive    -> 정답 맞춤!  

TN :   대답 : Negative   /    실제: Negative    -> 정답 맞춤!  

FP :   대답 : Positive   /    실제: Negative    -> 정답 틀림!  

FN :   대답 : Negative   /    실제: Positive    -> 정답 틀림!  

  

이 개념을 사용하여 __정밀도(Precision)__과 __재현율(Recall)__  

  

#### 1) 정밀도 (Precision)  

양성이라고 대답한 전체 케이스에 대한 TP의 비율  

```
정밀도 = \frac{TP}{TP + FP}
```

  

#### 2) 재현율 (Recall)  

실제값이 양성인 데이터의 전체 개수에 대해서 TP의 비율  

```
재현율 = \frac{TP}{TP + FN}
```