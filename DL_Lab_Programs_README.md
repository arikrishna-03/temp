# DL Lab Practical Programs --- B23ADP501

**KIT --- Deep Learning Techniques Laboratory**\
Quick revision reference for Experiments 1--10.

> Study reference: follow your faculty's instructions and official lab
> manual during the practical. Some shared programs are simplified
> demonstrations rather than fully trained CNN, RNN, LSTM,
> RBM-augmentation, or VAE systems.

## Experiment 1 --- Classification Model Using Supervised Learning

``` python
from sklearn.datasets import load_iris
from sklearn.model_selection import train_test_split
from sklearn.tree import DecisionTreeClassifier
from sklearn.metrics import accuracy_score, confusion_matrix

data = load_iris()
X = data.data
y = data.target

X_train, X_test, y_train, y_test = train_test_split(
    X, y, test_size=0.2, random_state=42
)

model = DecisionTreeClassifier()
model.fit(X_train, y_train)

y_pred = model.predict(X_test)

print("Accuracy:", accuracy_score(y_test, y_pred))
print("Confusion Matrix:")
print(confusion_matrix(y_test, y_pred))
```

**Remember:** load → split → fit → predict → evaluate.

## Experiment 2 --- Build a Deep Learning Model

``` python
import numpy as np
from sklearn.neural_network import MLPClassifier
from sklearn.metrics import accuracy_score, precision_score, recall_score, f1_score

X = np.array([[0,0], [0,1], [1,0], [1,1]])
y = np.array([0, 1, 1, 1])

model = MLPClassifier(
    hidden_layer_sizes=(4,),
    solver='lbfgs',
    max_iter=1000,
    random_state=1
)

model.fit(X, y)
pred = model.predict(X)

print("Accuracy :", accuracy_score(y, pred))
print("Precision:", precision_score(y, pred))
print("Recall   :", recall_score(y, pred))
print("F1 Score :", f1_score(y, pred))
```

**Remember:** `MLPClassifier` → `fit` → `predict` → metrics. This
evaluates on the same four samples used for training.

## Experiment 3 --- Forward Propagation Using NumPy

``` python
import numpy as np

X = np.array([[1, 2]])

W1 = np.array([[0.5, 0.4],
               [0.3, 0.2]])
b1 = np.array([0.1, 0.1])

W2 = np.array([[0.6],
               [0.5]])
b2 = np.array([0.1])

def sigmoid(x):
    return 1 / (1 + np.exp(-x))

Z1 = np.dot(X, W1) + b1
A1 = sigmoid(Z1)

Z2 = np.dot(A1, W2) + b2
A2 = sigmoid(Z2)

print("Hidden Layer Output:", A1)
print("Final Output:", A2)
```

**Remember:** `Z1` → `A1` → `Z2` → `A2`.

## Experiment 4 --- Basic CNN Operations on Images

``` python
import numpy as np

X = np.array([
    [[1, 1, 0],
     [1, 1, 0],
     [0, 0, 0]],

    [[0, 0, 1],
     [0, 0, 1],
     [0, 1, 1]]
])

kernel = np.array([
    [1, 0],
    [0, 1]
])

def convolution(img, kernel):
    result = np.zeros((2, 2))
    for i in range(2):
        for j in range(2):
            result[i,j] = np.sum(img[i:i+2, j:j+2] * kernel)
    return result

def relu(x):
    return np.maximum(0, x)

def maxpool(x):
    return np.max(x)

for img in X:
    conv = convolution(img, kernel)
    relu_out = relu(conv)
    pool = maxpool(relu_out)

    print("Convolution:")
    print(conv)
    print("Pooled Output:", pool)
    print()
```

**Remember:** convolution → ReLU → max pooling. This does not train a
complete CNN classifier.

## Experiment 5 --- Simplified Text Classification

``` python
import numpy as np

texts = [
    "good movie",
    "great movie",
    "bad movie",
    "worst movie"
]

y = np.array([1, 1, 0, 0])

X = np.array([
    [1, 1],
    [1, 1],
    [0, 1],
    [0, 1]
])

weights = np.array([1.0, 0.5])
bias = -0.5

features = np.dot(X, weights) + bias
features = np.maximum(0, features)
pred = (features >= 0.5).astype(int)

print("Text:", texts)
print("Predicted Labels:", pred)
print("Actual Labels:", y)
print("Accuracy:", np.mean(pred == y))
```

**Remember:** features → weighted sum → ReLU → threshold → accuracy.
This is not a trained CNN.

## Experiment 6 --- Traffic Object Filtering and Classification

``` python
import numpy as np

# [x, y, width, height, confidence, class]
objects = np.array([
    [10, 10, 50, 50, 0.90, 1],
    [12, 12, 50, 50, 0.85, 1],
    [100, 20, 40, 40, 0.95, 2]
])

selected = []

for i in range(len(objects)):
    if objects[i, 4] >= 0.90:
        selected.append(objects[i])

selected = np.array(selected)

print("Detected Traffic Objects:")

for obj in selected:
    if obj[5] == 1:
        name = "Car"
    else:
        name = "Bus"

    print(name, "Confidence:", obj[4])

print("Number of objects:", len(selected))
```

**Remember:** confidence is column `4`; class is column `5`. This is
confidence filtering, not true NMS.

## Experiment 7 --- Simplified RNN Calculation

``` python
import numpy as np

text = "hello world hello"

chars = sorted(set(text))
char_to_index = {c:i for i,c in enumerate(chars)}
index_to_char = {i:c for i,c in enumerate(chars)}

seq = text[:5]
target = text[5]

X = np.array([char_to_index[c] for c in seq])
y = char_to_index[target]

hidden = 0.0

for x in X:
    hidden = np.tanh(x + hidden)

pred = int(hidden) % len(chars)

print("Input sequence:", seq)
print("Actual next character:", target)
print("Predicted character:", index_to_char[pred])
```

**Remember:** text → vocabulary → indices → `tanh` hidden-state loop →
character. This is not a trained RNN; the target is a space, so that
output may look blank.

## Experiment 8 --- RBM Hidden Feature Extraction

``` python
import numpy as np
from sklearn.neural_network import BernoulliRBM

X = np.array([
    [1,1,0,0, 1,1,0,0],
    [1,1,0,0, 1,1,0,0],
    [0,0,1,1, 0,0,1,1],
    [0,0,1,1, 0,0,1,1]
])

rbm = BernoulliRBM(
    n_components=4,
    n_iter=20,
    random_state=1
)

rbm.fit(X)
augmented = rbm.transform(X)

print("Original Data:")
print(X)

print("\nAugmented Data:")
print(augmented)
```

**Remember:** create RBM → `fit(X)` → `transform(X)`. `transform`
returns hidden-feature activation probabilities, not augmented images.

## Experiment 9 --- Sentiment Analysis Using the Shared Program

``` python
import numpy as np
from sklearn.feature_extraction.text import CountVectorizer
from sklearn.linear_model import LogisticRegression
from sklearn.model_selection import train_test_split
from sklearn.metrics import accuracy_score

texts = [
    "I love this movie",
    "This is a great movie",
    "I like this",
    "Amazing and wonderful",
    "I hate this movie",
    "This is a bad movie",
    "I dislike this",
    "Very boring and worst"
]

y = np.array([1, 1, 1, 1, 0, 0, 0, 0])

vectorizer = CountVectorizer()
X = vectorizer.fit_transform(texts)

X_train, X_test, y_train, y_test = train_test_split(
    X, y, test_size=0.25, random_state=1
)

model = LogisticRegression()
model.fit(X_train, y_train)

pred = model.predict(X_test)

print("Actual:", y_test)
print("Predicted:", pred)
print("Accuracy:", accuracy_score(y_test, pred))
```

**Remember:** vectorize → split → train → predict → accuracy. The shared
code uses Logistic Regression, not LSTM.

## Experiment 10 --- Simplified VAE Calculations

``` python
import numpy as np

X = np.array([[0, 1, 1, 0],
              [1, 1, 0, 0]])

W1 = np.array([[0.5, 0.2],
               [0.3, 0.4],
               [0.2, 0.5],
               [0.4, 0.3]])

z_mean = np.dot(X, W1)
z_log_var = np.log(np.abs(z_mean) + 1)

epsilon = np.random.randn(*z_mean.shape)
z = z_mean + np.exp(0.5 * z_log_var) * epsilon

W2 = np.array([[0.5, 0.3, 0.2, 0.4],
               [0.2, 0.4, 0.5, 0.3]])

output = 1 / (1 + np.exp(-np.dot(z, W2)))

print("Input:")
print(X)

print("\nLatent Mean:")
print(z_mean)

print("\nLatent Log Variance:")
print(z_log_var)

print("\nReconstructed Output:")
print(output)
```

**Remember:** input → mean/log variance → random sampling → decoder →
sigmoid output. This does not train a complete VAE.

## Quick Viva Revision

  Term                  One-line answer
  --------------------- ------------------------------------------------------------
  Supervised learning   Learns from labelled data.
  Classification        Predicts categories or classes.
  MLP                   Multi-Layer Perceptron; a feedforward neural network.
  Forward propagation   Calculates output through network layers.
  CNN                   Neural network commonly used for image/spatial data.
  ReLU                  `max(0, x)`.
  Pooling               Reduces feature-map dimensions.
  Confidence score      Model's confidence in a detection.
  RNN                   Neural network for sequential data.
  LSTM                  RNN architecture designed to learn long-term dependencies.
  RBM                   Generative model with visible and hidden units.
  VAE                   Generative model with a probabilistic latent space.
  Accuracy              Correct predictions / total predictions.
  Precision             True positives / predicted positives.
  Recall                True positives / actual positives.
  F1-score              Harmonic mean of precision and recall.

## Important Corrections

-   **Experiment 4:** demonstrates convolution, ReLU and pooling; it
    does not train a CNN.
-   **Experiment 5:** uses manually chosen features and weights; it is
    not a trained CNN.
-   **Experiment 6:** filters by confidence; it does not calculate IoU
    or perform actual NMS.
-   **Experiment 7:** uses a hand-written recurrence; it does not train
    an RNN.
-   **Experiment 8:** obtains hidden features, not augmented images.
-   **Experiment 9:** the supplied code uses Logistic Regression, not
    LSTM.
-   **Experiment 10:** demonstrates VAE-like calculations with fixed
    weights, not a trained VAE.

Follow the program and architecture required by your instructor or lab
manual if they differ from these shared examples.
