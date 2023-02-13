# ✏ deepdriver.log로 데이터 기록하기

{% hint style="warning" %}
로그인과 실험환경/실행 생성 후에 사용할 수 있습니다.

deepdriver login과 init 후에 사용할 수 있습니다.
{% endhint %}

## 로그 기록하기

{% hint style="info" %}
python의 dictionary 형태로 로그 이름과 값을 정의 하여 기록할 수 있습니다.

같은 이름으로 여러번 로그 되는 경우 대쉬보드에서 차트형태로 확인 할 수 있습니다.


{% endhint %}

```
deepdriver.log({'log_name': log_value, 'log_name2':log_Value2})
```

### <mark style="background-color:yellow;">example 1 - 수치형 로그 기록</mark>

```python
deepdriver.log({'acc': 0.9, 'loss': 0.2)}
```

### <mark style="background-color:yellow;">example 2 -로그 여러번 기록</mark>

{% code title="학습 수행 하며 여러번 기록" %}
```python
import random
epoch = 10
accuracy = [ random.uniform(0.7*i, 1)  for i in range(epoch)]
train_loss = [ random.uniform(0.1,  0.2-0.01*i)  for i in range(epoch)]
val_accuracy =[ random.uniform(0.7*i, 1)  for i in range(epoch)]
val_loss = [ random.uniform(0.2,  0.3-0.01*i)  for i in range(epoch)]

for i in range(epoch):
    # send train log
    deepdriver.log({'acc': accuracy[i], 'loss': train_loss[i], 'val_acc': val_accuracy[i],'val_loss': val_loss[i]})
```
{% endcode %}

### <mark style="background-color:yellow;">example 3 - 문자열 로그 기록</mark>

{% code title="문자열 로그 기록" %}
```python
epoch =10
pred = [ "dog", "cat", "dog", "cat" , "cat", "dog", "dog" ,"cat", "dog", "dog" ]
for i in range(epoch):
  deepdriver.log({'predict_class': pred [i]})
```
{% endcode %}
