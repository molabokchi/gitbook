---
description: Table object
---

# Table

{% hint style="warning" %}
로그인 및 실험환경 생성 후 사용하실 수 있습니다.
{% endhint %}

## 1. Table 객체 생성

```python
# Table 객체 원형
Table(data: DataFrame)
```

### <mark style="background-color:yellow;">example - 테이블 객체 생성</mark>

```python
deep_df = deepdriver.DataFrame(columns=["a", "b", "c"], data=[[1, 2, 3]])
table = deepdriver.Table(data=deep_df)
```

## 2. 객체 표시(Visualize)

```python
# 코드 사용법
deepdriver.visualize(table_object)
```

### <mark style="background-color:yellow;">example</mark>&#x20;

```python
accuracy = [0.81, 0.82, 0.83, 0.84, 0.90, 0.92, 0.94, 0.93, 0.94, 0.93]
df = deepdriver.DataFrame(columns=["step", "acc"], data=[[idx, acc] for idx, acc in enumerate(accuracy)])
print(df.dataframe)
table = deepdriver.Table(data=df)
deepdriver.visualize(table)
```

## 3. 로그 기록

```python
# 코드 사용법
deepdriver.log(table_object)
```

### <mark style="background-color:yellow;">example</mark>

<pre class="language-python"><code class="lang-python"><strong>deep_df = deepdriver.DataFrame(columns=["a", "b", "c"], data=[[1, 2, 3]])
</strong>table = deepdriver.Table(data=deep_df)
deepdriver.log({"table": table})
</code></pre>

## 4. artifact 전송

### <mark style="background-color:yellow;">example</mark>

```python
arti = deepdriver.Artifacts(name="artifact_name", type="result")
deep_df = deepdriver.DataFrame(columns=["a", "b", "c"], data=[[1, 2, 3]])
table = deepdriver.Table(data=deep_df)
arti.add(table, "table")
deepdriver.upload_artifact(arti)
```
