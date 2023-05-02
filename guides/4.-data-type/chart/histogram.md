# Histogram

{% hint style="warning" %}
로그인 및 실험환경 생성 후 사용하실 수 있습니다.
{% endhint %}

## 1. Histogram 객체 생성

```python
# Historgram 객체 원형
histogram(data: DataFrame = None, x: str ="", y: str = "", title: str = "", seq: Union[np.ndarray, list]=None)
```

### <mark style="background-color:yellow;">example 1 - 히스토그램 객체 생성(Dataframe)</mark>

```python
df = deepdriver.DataFrame(columns=["x", "y"], data=[[0, 10], [1, 20], [2, 30]])
histogram = deepdriver.histogram(df, x="x", y="y", title="historgram chart")
```

### <mark style="background-color:yellow;">example 2 - 히스토그램 객체 생성(list)</mark>

```python
data_list = [1, 2, 2, 3, 4]
histogram = deepdriver.histogram(seq=data_list, title="histogram_plot")
```

### <mark style="background-color:yellow;">example 3 - 히스토그램 객체 생성(Numpy Array)</mark>

```python
import numpy as np
np_array = np.array([1, 2, 2, 3, 4])
histogram = deepdriver.histogram(seq=np_array, title="histogram_plot")
```

## 2. 객체 표시(Visualize)

```python
# 코드 사용법
deepdriver.visualize(histogram_object)
```

### <mark style="background-color:yellow;">example</mark>

```python
df = deepdriver.DataFrame(columns=["x", "y"], data=[[0, 10], [1, 20], [2, 30]])
histogram = deepdriver.histogram(df, x="x", y="y", title="historgram chart")
deepdriver.visualize(histogram)
```

## 3. 로그 기록

```python
# 코드 사용법
deepdriver.log(histogram_object)
```

### <mark style="background-color:yellow;">example</mark>

```python
df = deepdriver.DataFrame(columns=["x", "y"], data=[[0, 10], [1, 20], [2, 30]])
histogram = deepdriver.histogram(df, x="x", y="y", title="historgram chart")
deepdriver.log({"histogram":histogram})
```

## 4. artifact 전송

### <mark style="background-color:yellow;">example</mark>

{% hint style="warning" %}
Deepdriver Free 요금제에서는 사용할 수 없습니다.
{% endhint %}

```python
df = deepdriver.DataFrame(columns=["x", "y"], data=[[0, 10], [1, 20], [2, 30]])
histogram = deepdriver.histogram(df, x="x", y="y", title="historgram chart")
arti.add(historgram, "histogram")
deepdriver.upload_artifact(arti)
```
