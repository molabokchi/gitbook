# Roc Curve

{% hint style="warning" %}
로그인 및 실험환경 생성 후 사용하실 수 있습니다.
{% endhint %}

## 1. Roc Curve 객체 생성

```python
# Roc Curve 객체 원형
roc_curve(y_true: list, probs: list, class_names: list = None, title: str = None)
```

### <mark style="background-color:yellow;">example - Roc Curve 객체 생성</mark>

```python
y_true = [1, 0, 0, 1, 1, 0, 1, 0, 1]
probs = [[0.1, 0.9], [0.9, 0.1], [0.75, 0.25], [0.6, 0.4], [0.3, 0.7], [0.6, 0.4], [0.7, 0.3], [0.5, 0.5], [0.8, 0.2]]
labels = ["cat", "dog"]
curve = deepdriver.roc_curve(probs=probs, y_true=y_true, class_names=labels, title="roc_curve")
```

## 2. 객체 표시(Visualize)

```python
# 코드 사용법
deepdriver.visualize(roc_curver_object)
```

### <mark style="background-color:yellow;">example</mark>

```python
y_true = [1, 0, 0, 1, 1, 0, 1, 0, 1]
probs = [[0.1, 0.9], [0.9, 0.1], [0.75, 0.25], [0.6, 0.4], [0.3, 0.7], [0.6, 0.4], [0.7, 0.3], [0.5, 0.5], [0.8, 0.2]]
labels = ["cat", "dog"]
curve = deepdriver.roc_curve(probs=probs, y_true=y_true, class_names=labels, title="roc_curve")
deepdriver.visualize(curve)
```

## 3. 로그 기록

```python
# 코드 사용법
deepdriver.log(roc_curve)
```

```python
y_true = [1, 0, 0, 1, 1, 0, 1, 0, 1]
probs = [[0.1, 0.9], [0.9, 0.1], [0.75, 0.25], [0.6, 0.4], [0.3, 0.7], [0.6, 0.4], [0.7, 0.3], [0.5, 0.5], [0.8, 0.2]]
labels = ["cat", "dog"]
curve = deepdriver.roc_curve(probs=probs, y_true=y_true, class_names=labels, title="roc_curve")
deepdriver.log({"roc_curve":curve})
```

## 4. artifact 전송

{% hint style="warning" %}
Deepdriver Free 요금제에서는 사용할 수 없습니다.
{% endhint %}

```python

y_true = [1, 0, 0, 1, 1, 0, 1, 0, 1]
probs = [[0.1, 0.9], [0.9, 0.1], [0.75, 0.25], [0.6, 0.4], [0.3, 0.7], [0.6, 0.4], [0.7, 0.3], [0.5, 0.5], [0.8, 0.2]]
labels = ["cat", "dog"]
curve = deepdriver.roc_curve(probs=probs, y_true=y_true, class_names=labels, title="roc_curve")
arti.add(curve, "roc_curve")
deepdriver.upload_artifact(arti)
```
