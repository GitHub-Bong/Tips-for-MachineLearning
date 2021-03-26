# 복습     

<br/>

### 케라스의 함수형 API(Keras Functional API)      

We can create much more __complex model__ by function API !     

<br/>

#### Model by sequential API      

```python
from tensorflow.keras.models import Sequential
from tensorflow.keras.layers import Dense

model=Sequential()
model.add(Dense(3, input_dim=4, activation='softmax'))
```

It is intuitive and convenient but we cannot create complex artificial network by simply adding layers      

<br/>     

#### Model by function API     

function API defines each layer as a function      

Example)     

__1) Fully-connected FFNN__     

```python
from tensorflow.keras.layers import Input, Dense
from tensorflow.keras.models import Model
inputs = Input(shape=(10,))
hidden1 = Dense(64, activation='relu')(inputs)
hidden2 = Dense(64, activation='relu')(hidden1)
output = Dense(1, activation='sigmoid')(hidden2)
model = Model(inputs=inputs, outputs=output)

model.compile(optimizer='rmsprop', loss='categorical_crossentropy', metrics=['accuracy'])
model.fit(data, labels)
```

```python
inputs = Input(shape=(10,))
x = Dense(8, activation="relu")(inputs)
x = Dense(4, activation="relu")(x)
x = Dense(1, activation="linear")(x)
model = Model(inputs, x)
```

<br/>

__2) Model that accepts multiple inputs__     

```python
from tensorflow.keras.layers import Input, Dense, concatenate
from tensorflow.keras.models import Model

# 2 input layers
inputA = Input(shape=(64,))
inputB = Input(shape=(128,))

x = Dense(16, activation="relu")(inputA)
x = Dense(8, activation="relu")(x)
x = Model(inputs=inputA, outputs=x)

y = Dense(64, activation="relu")(inputB)
y = Dense(32, activation="relu")(y)
y = Dense(8, activation="relu")(y)
y = Model(inputs=inputB, outputs=y)

result = concatenate([x.output, y.output])

z = Dense(2, activation="relu")(result)
# activation=linear for Linear Regression 
z = Dense(1, activation="linear")(z)

# Predict 1 output from 2 input layers
model = Model(inputs=[x.input, y.input], outputs=z)
```

<br/>

__3) RNN(Recurrent Neural Network)__

```python
from tensorflow.keras.layers import Input, Dense, LSTM
from tensorflow.keras.models import Model
inputs = Input(shape=(50,1))
lstm_layer = LSTM(10)(inputs) 
x = Dense(10, activation='relu')(lstm_layer)
output = Dense(1, activation='sigmoid')(x)
model = Model(inputs=inputs, outputs=output)
```

