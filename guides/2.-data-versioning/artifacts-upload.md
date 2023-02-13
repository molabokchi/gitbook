---
description: 인공지능 실험에서 다뤄지는 데이터의 통칭을 아티팩트로 정의 합니다. 아티팩트를 업로드 하여 체계적으로 관리해 보세요.
---

# ⬆ Artifacts upload

{% hint style="warning" %}
로그인과 실험환경/실행 생성 후에 사용할 수 있습니다.

deepdriver login과 init 후에 사용할 수 있습니다.
{% endhint %}

## 1. 아티팩트 만들기

{% hint style="info" %}
아티팩트의 이름과 타입을 정의하여 서버로 업로드 합니다.

아티팩트는 실험환경 기준으로 관리 됩니다.

init을 통해 지정했던 실험환경에 하위 아티팩트로 지정됩니다.
{% endhint %}

<pre class="language-python"><code class="lang-python"><strong>deepdriver.Artifacts(name="artifact_name", type="artifact_type")
</strong></code></pre>

### <mark style="background-color:yellow;">example</mark>

```
arti = deepdriver.Artifacts(name="animal",type="dataset")
```

## 2. 아티팩트에 데이터 추가하기

{% code title="로컬 디렉토리 데이터 추가" %}
```python
arti.add("./cat_dog")
```
{% endcode %}

## 3. 아티팩트 업로드

```python
deepdriver.upload_artifact(arti)
```

or

```python
arti.upload()
```

{% code title="업로드 결과" %}
```
Uploading: [./cat_dog/dog/dog.jpg] |██████████████████████████████| [100.0%] [2/2]
```
{% endcode %}
