# Confusion Matrix

{% hint style="warning" %}
로그인 및 실험환경 생성 후 사용하실 수 있습니다.
{% endhint %}

## 1. Confusion Matrix 객체 생성

```python
# Confusion Matrix 객체생성 원형
scatter(data: DataFrame, x: str, y: str, title: str=None)
```

### <mark style="background-color:yellow;">example - Confusion Matrix 객체 생성</mark>

```python
y_true = [0, 1, 0, 1, 0, 2, 0, 2, 0, 1, 0, 1, 0, 1, 2, 2]  # 실제값
preds = [0, 1, 0, 1, 1, 2, 1, 2, 0, 1, 0, 1, 0, 2, 0, 2]  # 예측값
labels = ["cat", "dog", "horse"]
confusion_matrix = deepdriver.confusion_matrix(probs=None, y_true=y_true,
                                               preds=preds, class_names=labels,
                                               title="my_confusion_matrix")
```

## 2. 객체 표시(Visualize)

```python
# 코드 사용법
deepdriver.visualize(confusion_matrix_object)
```

### <mark style="background-color:yellow;">example</mark>

```python
y_true = [0, 1, 0, 1, 0, 2, 0, 2, 0, 1, 0, 1, 0, 1, 2, 2]  # 실제값
preds = [0, 1, 0, 1, 1, 2, 1, 2, 0, 1, 0, 1, 0, 2, 0, 2]  # 예측값
labels = ["cat", "dog", "horse"]
confusion_matrix = deepdriver.confusion_matrix(probs=None, y_true=y_true,
                                               preds=preds, class_names=labels,
                                               title="my_confusion_matrix")
deepdriver.visualize(confusion_matrix)
```

## 3. 로그 기록

```python
# 코드 사용법
deepdriver.log(confusion_matrix)
```

### <mark style="background-color:yellow;">example</mark>

```python
y_true = [0, 1, 0, 1, 0, 2, 0, 2, 0, 1, 0, 1, 0, 1, 2, 2]  # 실제값
preds = [0, 1, 0, 1, 1, 2, 1, 2, 0, 1, 0, 1, 0, 2, 0, 2]  # 예측값
labels = ["cat", "dog", "horse"]
confusion_matrix = deepdriver.confusion_matrix(probs=None, y_true=y_true,
                                               preds=preds, class_names=labels,
                                               title="my_confusion_matrix")
deepdriver.log({"confusion_matrix":confusion_matrix})
```

## 4. artifact 전송

### <mark style="background-color:yellow;">example</mark>

{% hint style="warning" %}
Deepdriver Free 요금제에서는 사용할 수 없습니다.
{% endhint %}

```python
y_true = [0, 1, 0, 1, 0, 2, 0, 2, 0, 1, 0, 1, 0, 1, 2, 2]  # 실제값
preds = [0, 1, 0, 1, 1, 2, 1, 2, 0, 1, 0, 1, 0, 2, 0, 2]  # 예측값
labels = ["cat", "dog", "horse"]
confusion_matrix = deepdriver.confusion_matrix(probs=None, y_true=y_true,
                                               preds=preds, class_names=labels,
                                               title="my_confusion_matrix")
deepdriver.upload_artifact(arti)
```
