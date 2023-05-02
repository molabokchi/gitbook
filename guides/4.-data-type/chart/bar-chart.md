# Bar Chart

{% hint style="warning" %}
로그인 및 실험환경 생성 후 사용하실 수 있습니다.
{% endhint %}

## 1. Bar Chart 객체 생성

```python
# Bar Chart 객체 원형
bar(data: DataFrame, x: str, y: str, title: str = None) 
```

### <mark style="background-color:yellow;">example - 바차트 객체 생성</mark>

<pre class="language-python"><code class="lang-python"><strong>df = deepdriver.DataFrame(columns=["x", "y"], data=[[0, 10], [1, 20], [2, 30]])
</strong>bar_chart = deepdriver.bar(df, x="x", y="y", title="bar chart")
</code></pre>

## 2. 객체 표시(Visualize)

```python
# 코드 사용법
deepdriver.visualize(bar_chart_object)
```

### <mark style="background-color:yellow;">example</mark>

<pre class="language-python"><code class="lang-python"><strong>df = deepdriver.DataFrame(columns=["x", "y"], data=[[0, 10], [1, 20], [2, 30]])
</strong>bar_chart = deepdriver.bar(df, x="x", y="y", title="bar chart")
deepdriver.visualize(bar_chart)
</code></pre>

## 3. 로그 기록

<pre class="language-python"><code class="lang-python"><strong># 코드 사용법
</strong>deepdriver.log(bar_chart_object)
</code></pre>

### <mark style="background-color:yellow;">example</mark>

<pre class="language-python"><code class="lang-python"><strong>df = deepdriver.DataFrame(columns=["x", "y"], data=[[0, 10], [1, 20], [2, 30]])
</strong>bar_chart = deepdriver.bar(df, x="x", y="y", title="bar chart")
deepdriver.log({"bar_chart":bar_chart})
</code></pre>

## 4. artifact 전송

### <mark style="background-color:yellow;">example</mark>

{% hint style="warning" %}
Deepdriver Free 요금제에서는 사용할 수 없습니다.
{% endhint %}

<pre class="language-python"><code class="lang-python"><strong>df = deepdriver.DataFrame(columns=["x", "y"], data=[[0, 10], [1, 20], [2, 30]])
</strong>bar_chart = deepdriver.bar(df, x="x", y="y", title="bar chart")
arti.add(bar_chart, "bar_chart")
deepdriver.upload_artifact(arti)
</code></pre>
