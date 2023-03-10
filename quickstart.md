---
description: 간단한 코드 수행으로 인공지능 실험 결과를 기록 해보세요
---

# 🚀 Quickstart

## <mark style="color:blue;">예제 따라하기</mark>

{% embed url="https://colab.research.google.com/github/molabokchi/bokchi_open_lab/blob/main/deepdriver.ipynb" %}

## 1. Set up deepdriver

### 0) Deepdriver CE 내려받기

deepdriver 대시보드 설치



### 1) Deepdriver python  library 설치

{% tabs %}
{% tab title="command Line" %}
{% code title="라이브러리 설치" overflow="wrap" %}
```
pip install deepdriver
```
{% endcode %}
{% endtab %}

{% tab title="Notebook" %}
{% code title="라이브러리 설치" %}
```
!pip install deepdriver
```
{% endcode %}
{% endtab %}
{% endtabs %}

### 2) 서버 설정 하기

deepdriver server를 설치한 주소로 하기와 같이 설정

```python
import deepdriver
deepdriver.setting(http_host="{your_ip}:9011",  grpc_host="{your_ip}:19051")

# local에 deepdriver server를 설치한 경우 하기와 같이 설정
#deepdriver.setting(http_host="127.0.0.1:9011",  grpc_host="127.0.0.1:19051")
```

## 2. 서버에 로그인 하기

{% hint style="info" %}
<mark style="color:blue;">deepdriver server 설치시 발급받은 사용자의 api key 사용</mark>
{% endhint %}

```python
deepdriver.login( key="your_api_key")
```

## 3. 실험환경  및  실행 만들기

{% hint style="info" %}
<mark style="color:blue;">실험환경은 한가지 주제에 대해 여러번의  실험의 로그 및 결과를    기록하고 비교하기 위한 단위 입니다.</mark>

<mark style="color:blue;">실행은 하나의 실험을 의미 합니다.</mark>
{% endhint %}

```python
deepdriver.init()
```

## 4. 실험로그 기록 하기

{% hint style="info" %}
인공지능 실험(학습)을 진행하면서 기록해야할 값들을 기록 합니다.

하나의 실험 안에서 여러번 반복적으로 호출 할 수 있습니다.
{% endhint %}

```python
deepdriver.log({"acc": train_acc ,"loss" : train_loss})
```
