# HPO

## 1. CLI를 이용한 HPO 생성

{% hint style="info" %}
Command : <mark style="color:yellow;">hpo</mark>

Option:

* \--exp\_name : Experiment Name
* \--team\_name : Team Name
* \--remote : Is Remote
* \--config: HPO Config File Path Or Config Json String

Argument: <mark style="color:yellow;">create</mark>
{% endhint %}

```sh
# create with config file path
deepdrver hpo --exp_name EXP_NAME --remote False --config  "./hpo_config.json" create
```

```sh
# create with with json string
deepdrver hpo --exp_name EXP_NAME --remote False \
--config  "{\"name\":\"my-awesome-sweep\",\"metric\":{\"name\":\"accuracy\",\"goal\":\"maximize\"},\"method\":\"grid\",\"parameters\":{\"learning_rate\":{\"distribution\":\"uniform\",\"range\":[0.01,0.001]}}}" \
create
```

## 2. CLI를 이용한 HPO 실행

{% hint style="info" %}
Command : <mark style="color:yellow;">hpo</mark>

Option:

* \--exp\_name : Experiment Name
* \--team\_name : Team Name
* \--remote : Is Remote
* \--artifact: Artifact Config Path Or Artifact Json String
* \--count : Number of HPO operation

Argument: <mark style="color:yellow;">run</mark>
{% endhint %}

```sh
# run with artifact file path
deepdriver hpo --exp_name EXP_NAME --remote False --artifact "./run_hpo_config.json" run
```

```sh
# run with artifact json string
deepdriver hpo --exp_name "EXP3" --remote False \
--artifact {\"code\":{\"type\":\"CODE\",\"name\":\"TRAIN01\",\"exp_name\":\"EXP3\",\"file\":\"main.py\",\"fun\":\"train\"},\"dataset\":{\"type\":\"DATA\",\"name\":\"DATA01\"}} \
run
```

