# πβ deepdriver.initμΌλ‘ μ€ν μμ

μ€ν κ²°κ³Όλ₯Ό deepdriverμ κΈ°λ‘νκΈ° μν΄ μ€νμ μμ±ν©λλ€.

{% hint style="warning" %}
deepdriver.login() ν¨μ νΈμΆλ‘ λ‘κ·ΈμΈ ν μν ν μ μμ΅λλ€.
{% endhint %}

<pre><code><strong>init(
</strong><strong>    exp_name: str="", 
</strong><strong>    team_name: str="", 
</strong><strong>    run_name: str="", 
</strong><strong>    config: Dict=None
</strong><strong>) -> Run:
</strong></code></pre>

## μ€ννκ²½ λ° μ€ν λ§λ€κΈ°

### 1. μ€ν λ§λ€κΈ°

{% hint style="info" %}
init ν¨μλ₯Ό μΈμ μμ΄ μννλ©΄ μλμΌλ‘"uncategorized"  μ€ννκ²½μ μ€νμ΄ μμ±λκ³  μ€ν μ΄λ¦μ randomμΌλ‘ μμ±λ©λλ€.
{% endhint %}

<pre class="language-python"><code class="lang-python"><strong>import deepdriver
</strong>deepdriver.init()
</code></pre>

{% code title="deepdriver.init() μνκ²°κ³Ό" %}
```
Exp Name=uncategorized
Run Name=cold-hammerhead-1
```
{% endcode %}

### 2. μ€ννκ²½ μ§μ νμ¬ μ€ν λ§λ€κΈ°

{% hint style="info" %}
init  ν¨μμ λ§€κ°λ³μ exp\_nameμ μ€ννκ²½μ μ§μ νλ©΄ ν΄λΉ μ€ννκ²½ λ΄μ μ€νμ΄ λ§λ€μ΄μ§λλ€.

λμΌ μ€ννκ²½μ μ¬λ¬ κ°μ μ€νμ λ§λ€μ΄μ νλ²μ μ¬λ¬μ€ν κ²°κ³Όλ€μ νμΈ ν  μ μμ΅λλ€.&#x20;
{% endhint %}

```python
import deepdriver
deepdriver.init(exp_name="exp1")
```

{% code title="μ€ννκ²½ "exp1"λ‘ μ§μ ν μ€ν" %}
```
Exp Name=exp1
Run Name=glue-down-1
```
{% endcode %}

### 3. μ€ν νλΌλ―Έν° μ§μ νμ¬ μ€ν λ§λ€κΈ°

{% hint style="info" %}
μΈκ³΅μ§λ₯ νμ΅ μμ€μμ μ€ν λ§λ€ λ€λ₯΄κ² μ μ©ν  μ€ν μ‘°κ±΄λ€μ μ€νμ μ§μ ν  μ μμ΅λλ€.

μ€ν μν ν κ²°κ³Ό λΉκ΅μ μ‘°κ±΄μ λ°λ₯Έ νμ΅κ²°κ³Όλ₯Ό νμΈν  μμμ΅λλ€.
{% endhint %}

```python
import deepdriver
my_config={ 'epoch': epoch, 'batch_size': 64, 'hidden_layer':128 }
deepdriver.init(exp_name= "exp1", 
                config=my_config)
```

## μ€ν μ’λ£νκΈ°

### μ€ν μ’λ£

{% hint style="info" %}
λμ΄μ μ€νμμκΈ°λ‘ ν   λ°μ΄ν°κ° μλ€λ©΄ μ€νμ μ’λ£ νμΈμ.

μ€ν μ’λ£μ μ€νμ κ²°κ³Όκ° μμ±λμ΄ λ€λ₯Έ μ€ν λ€κ³Όμ κ²°κ³Ό λΉκ΅λ₯Ό νννλ‘ νμΈ ν  μ μμ΅λλ€.
{% endhint %}

```python
deepdriver.finish()
```
