# Scatter Chart

{% hint style="warning" %}
로그인 및 실험환경 생성 후 사용하실 수 있습니다.
{% endhint %}

## 1. Scatter Chart 객체 생성

<pre class="language-python"><code class="lang-python"><strong># Scatter Chart 객체생성 원형
</strong>scatter(data: DataFrame, x: str, y: str, title: str=None)
</code></pre>

### <mark style="background-color:yellow;">example - Scatter Chart 객체 생성</mark>

```python
df = deepdriver.DataFrame(columns=["x", "y"], data=[[0, 10], [1, 20], [2, 30]])
scatter_chart = deepdriver.scatter(df, "x", "y", title="scatter_chart")
deepdriver.visualize(scatter_chart)
```

## 2. 객체 표시(Visualize)

```python
# 코드 사용법
deepdriver.visualize(scatter_chart_object)
```

### <mark style="background-color:yellow;">example</mark>

```python
df = deepdriver.DataFrame(columns=["x", "y"], data=[[0, 10], [1, 20], [2, 30]])
scatter_chart = deepdriver.scatter(df, "x", "y", title="scatter_chart")
deepdriver.visualize(scatter_chart)
```

## 3. 로그 기록

```python
# 코드 사용법
deepdriver.log(scatter_chart_object)
```

### <mark style="background-color:yellow;">example</mark>

```python
df = deepdriver.DataFrame(columns=["x", "y"], data=[[0, 10], [1, 20], [2, 30]])
scatter_chart = deepdriver.scatter(df, "x", "y", title="scatter_chart")
deepdriver.log({"scatter_chart":scatter_chart})
```

## 4. artifact 전송

### <mark style="background-color:yellow;">example</mark>

```python
df = deepdriver.DataFrame(columns=["x", "y"], data=[[0, 10], [1, 20], [2, 30]])
scatter_chart = deepdriver.scatter(df, "x", "y", title="scatter_chart")
arti.add(scatter_chart, "scatter_chart")
deepdriver.upload_artifact(arti)
```
