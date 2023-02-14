---
description: Hyper-parameter Optimization 생성
---

# Create HPO Experiment

{% hint style="warning" %}
로그인 후에 사용하실 수 있습니다.

deepdriver.login()
{% endhint %}

## 1. HPO 생성하기

<pre class="language-python"><code class="lang-python">// CREATE HPO 함수 형태
<strong>def create_hpo(exp_name: str = "", team_name: str = "", remote: bool = False, hpo_config: Dict = None) -> (bool, int)
</strong></code></pre>

### <mark style="background-color:yellow;">example 1 - Dictionary 파라미터로 HPO 생성</mark>

```python
hpo_configuration = {
            "name": "my-awesome-sweep",
            "metric": {"name": "accuracy", "goal": "maximize"},
            "method": "grid",
            "parameters": {
                "learning_rate": {
                    "distribution": "uniform",
                    "range": [0.01, 0.001],
                }
            }
        }
deepdriver.create_hpo(exp_name="exp_name", hpo_config=hpo_configuration)
```

### <mark style="background-color:yellow;">example 2 - 설정 파일로 HPO 생성</mark>

```python
"""
hpo_config.json 파일 내용
{
  "name": "my-awesome-sweep",
  "metric": {
    "name": "accuracy",
    "goal": "maximize"
  },
  "method": "grid",
  "parameters": {
    "learning_rate": {
      "distribution": "uniform",
      "range": [
        0.01,
        0.001
      ]
    }
  }
}
"""
deepdriver.create_hpo(exp_name="exp_name", hpo_config="./hpo_config.json")
```
