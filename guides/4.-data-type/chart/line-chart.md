# Line Chart

{% hint style="warning" %}
로그인 및 실험환경 생성 후 사용하실 수 있습니다.
{% endhint %}

## 1. Line Chart 객체 생성

```python
# Line Chart 객체생성 원형
line(data: DataFrame, x: str, y: str, title: str=None)
```

### <mark style="background-color:yellow;">example  - 이미지 객체 생성</mark>

```python
df = deepdriver.DataFrame(columns=["step", "height"], data=[[0,10], [1,20], [2,30]])
line_chart = deepdriver.line(df, x="step", y="height", title="what a great line plot")
```

## 2. 객체 표시(Visualize)

```python
# 코드 사용법
deepdriver.visualize(line_chart_object)
```

### <mark style="background-color:yellow;">example</mark>

```python
df = deepdriver.DataFrame(columns=["step", "height"], data=[[0,10], [1,20], [2,30]])
line_chart = deepdriver.line(df, x="step", y="height", title="what a great line plot")
deepdriver.visualize(line_chart)
```

## 3. 로그 기록

<pre class="language-python"><code class="lang-python"><strong># 코드 사용법
</strong>deepdriver.log(line_chart_object)
</code></pre>

### <mark style="background-color:yellow;">example</mark>

```python
df = deepdriver.DataFrame(columns=["step", "height"], data=[[0,10], [1,20], [2,30]])
line_chart = deepdriver.line(df, x="step", y="height", title="what a great line plot")
deepdriver.log({"line_char":line_chart})
```

## 4. artifact 전송

### <mark style="background-color:yellow;">example</mark>

```python
df = deepdriver.DataFrame(columns=["step", "height"], data=[[0,10], [1,20], [2,30]])
line_chart = deepdriver.line(df, x="step", y="height", title="what a great line plot")
arti.add(line_chart, "line_chart")
deepdriver.upload_artifact(arti)
```
