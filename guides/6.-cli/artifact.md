# Artifact

## 1. CLI를 이용한 Artifact 다운로드

{% hint style="info" %}
Command : <mark style="color:yellow;">artifact download</mark>

Option:

* \--type : Type  of artifact (model, dataset, code)
* \--name : Name of artifact
* \--tag : Version tag of artifact

Argument:

* path : download  path
{% endhint %}

```sh
deepdriver artifact download --type dataset --name ARTIFACT_NAME .\download
```

## 2. CLI를 이용한 Artifact 업로드

{% hint style="info" %}
Command : <mark style="color:yellow;">artifact upload</mark>

Option:

* \--type : Type  of artifact (model, dataset, code)
* \--name : Name of artifact
* \--tag : Version tag of artifact

Argument:

* path : upload path
{% endhint %}

```sh
deepdriver artifact upload --type dataset --name ARTIFACT_NAME ./download
```
