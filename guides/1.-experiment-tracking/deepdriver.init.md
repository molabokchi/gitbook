# 🏃♀ deepdriver.init으로 실험 시작

실험 결과를 deepdriver에 기록하기 위해 실험을 생성합니다.

{% hint style="warning" %}
deepdriver.login() 함수 호출로 로그인 후 수행 할수 있습니다.
{% endhint %}

<pre><code><strong>init(
</strong><strong>    exp_name: str="", 
</strong><strong>    team_name: str="", 
</strong><strong>    run_name: str="", 
</strong><strong>    config: Dict=None
</strong><strong>) -> Run:
</strong></code></pre>

## 실험환경 및 실행 만들기

### 1. 실행 만들기

{% hint style="info" %}
init 함수를 인자 없이 수행하면 자동으로"uncategorized"  실험환경에 실행이 생성되고 실행 이름은 random으로 생성됩니다.
{% endhint %}

<pre class="language-python"><code class="lang-python"><strong>import deepdriver
</strong>deepdriver.init()
</code></pre>

{% code title="deepdriver.init() 수행결과" %}
```
Exp Name=uncategorized
Run Name=cold-hammerhead-1
```
{% endcode %}

### 2. 실험환경 지정하여 실행 만들기

{% hint style="info" %}
init  함수의 매개변수 exp\_name에 실험환경을 지정하면 해당 실험환경 내에 실행이 만들어집니다.

동일 실험환경에 여러 개의 실행을 만들어서 한번에 여러실험 결과들을 확인 할 수 있습니다.&#x20;
{% endhint %}

```python
import deepdriver
deepdriver.init(exp_name="exp1")
```

{% code title="실험환경 "exp1"로 지정후 실행" %}
```
Exp Name=exp1
Run Name=glue-down-1
```
{% endcode %}

### 3. 실험 파라미터 지정하여 실행 만들기

{% hint style="info" %}
인공지능 학습 소스에서 실험 마다 다르게 적용할 실험 조건들을 실행에 지정할 수 있습니다.

실험 수행 후 결과 비교시 조건에 따른 학습결과를 확인할 수있습니다.
{% endhint %}

```python
import deepdriver
my_config={ 'epoch': epoch, 'batch_size': 64, 'hidden_layer':128 }
deepdriver.init(exp_name= "exp1", 
                config=my_config)
```

## 실행 종료하기

### 실행 종료

{% hint style="info" %}
더이상 실험에서기록 할  데이터가 없다면 실행을 종료 하세요.

실행 종료시 실험의 결과가 생성되어 다른 실험 들과의 결과 비교를 표형태로 확인 할 수 있습니다.
{% endhint %}

```python
deepdriver.finish()
```
