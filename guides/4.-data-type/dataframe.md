# DataFrame

{% hint style="info" %}
Table, Chart등에 입력값으로 들어갈 자료형으로 DataFrame을 사용합니다.
{% endhint %}

## 1. DataFrame 객체 생성

```python
# DataFrame 객체 원형
DataFrame(data: List[List]=None, columns: List[str]=None, dataframe: pd.DataFrame=None)
```

### <mark style="background-color:yellow;">example 1 - Dataframe 객체 생성</mark>

```python
deep_df = deepdriver.DataFrame(columns=["a", "b", "c"], data=[[1, 2, 3]])
```

### <mark style="background-color:yellow;">example 2 - Pandas Dataframe을 이용하여 생성</mark>

```python
import pandas as pd
dataframe = pd.DataFrame({"x": ["a", "b", "c"], "y": [1, 2, 3]})
deepdriver.DataFrame(dataframe=dataframe)
```
