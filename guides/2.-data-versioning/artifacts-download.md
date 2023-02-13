# ⬇ Artifacts download

{% hint style="warning" %}
로그인과 실험환경/실행 생성 후에 사용할 수 있습니다.

deepdriver login과 init 후에 사용할 수 있습니다.
{% endhint %}

## 1. 아티팩트 가져오기

{% hint style="info" %}
서버에서 관리 되고 있는 아티팩트를 가져와서 실험에서 사용할 수 있습니다 .

아티팩트 업로드를 통해 서버로 전송한 아티팩트를 가져와서 다른 실험에서 사용해 보세요
{% endhint %}

artifact의 이름과 타입을 지정해서 artifact 정보를 가져옵니다.

다른 실험환경의 artifact를 가져오려면 exp\_name 에 실험환경을 지정하세요.

```python
deepdriver.get_artifact(name="artifact_name",type="artifact_type")
```

### <mark style="background-color:yellow;">example</mark>

<pre><code><strong>arti = deepdriver.get_artifact(name="animal",type="dataset")
</strong></code></pre>

```python
print([ (ent.path, ent.size) for ent in arti.entry_list])
```

{% code title="수행 결과" %}
```
[('cat/cat.jpg', 40449), ('dog/dog.jpg', 30460)]
```
{% endcode %}

### <mark style="background-color:yellow;">example2</mark>

```python
arti = deepdriver.get_artifact(name="animal",type="dataset", exp_name="exp2")
```

## 2. 아티팩트 다운로드

{% hint style="info" %}
get\_artifact로 가져온 아티팩트를 다운로드 합니다.

다운로드 받은 경로가 표시됩니다.
{% endhint %}

```
arti.download()
```

{% code title="download 결과" %}
```
Downloading: [./deepdriver/artifact/128/dog/dog.jpg] |██████████████████████████████| [100.0%] [2/2]
```
{% endcode %}
