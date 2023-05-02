# Run HPO

{% hint style="warning" %}
로그인 후 HPO Experiment를 생성한 후 해당 Experiment를 지정하여 사용할 수 있습니다.

1. deepdriver.login()
2. deepdriver.create\_hpo()
3. deepdriver.run\_hpo()
{% endhint %}

## 1. HPO 실행하기

```python
// RUN HPO 함수 형태
def run_hpo(exp_name: str = "", team_name: str = "", remote: bool = False, hpo_config: Dict  = None,
            func: Callable = None, count: int = 10, artifact: Union[str, Dict] = None, job_count: int = 0) -> bool:
```

### <mark style="background-color:yellow;">example 1 - 생성된 HPO를 실행</mark>

```python
def func():
    x = deepdriver.config.x
    y = (x - 2) ** 2
    return y
    
deepdriver.run_hpo(exp_name="exp_name", func=func, count=50)
```

## 2. Artifact를 이용해 HPO 실행하기

{% hint style="warning" %}
Deepdriver Free 요금제에서는 사용할 수 없습니다.
{% endhint %}

{% hint style="info" %}
HPO 실행시 데이터셋과 코드를 Artifact로 생성 후 실행 할 수 있습니다.
{% endhint %}

### <mark style="background-color:yellow;">example 1 - artifact 생성 후 HPO실행</mark>

```
# code artifact create
arti_code = deepdriver.Artifacts(name="TRAIN01", type="CODE")
arti_code.add("src")
deepdriver.upload_artifact(arti_code)

# dataset artifact create
arti_dataset = deepdriver.Artifacts(name="DATA01", type="DATA")
arti_dataset.add("cat_dog")
deepdriver.upload_artifact(arti_dataset)

artfact_config = {
  "code": {
    "type": "CODE",
    "name": "TRAIN01",
    "exp_name": "EXP3",
    "file": "main.py",
    "fun": "train"
  },
  "dataset": {
    "type": "DATA",
    "name": "DATA01"
  }
}
deepdriver.run_hpo(exp_name=_exp_name, artifact=artfact_config)
```
