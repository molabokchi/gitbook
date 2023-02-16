---
description: An image object containing bounding boxes, caption, class
---

# Image

{% hint style="warning" %}
로그인 및 실험환경 생성 후 사용하실 수 있습니다.
{% endhint %}

## 1. Image 객체 생성

```python
# Image 객체생성 원형
Image(data: Union[str, PIL_IMAGE.Image], caption: str = None, boxes: Union[Dict[str, BoundingBoxes], Dict[str, dict]] = None)
```

### <mark style="background-color:yellow;">example 1 - 이미지 객체 생성(PIL Image)</mark>

<pre class="language-python"><code class="lang-python"><strong>import PIL
</strong># PIL 이미지 객체를 이용하여 Image 객체 생성
pil_image = PIL.Image.open("cat.png")
image_object_from_pil = deepdriver.Image(pil_image)
</code></pre>

### <mark style="background-color:yellow;">example 2 - 이미지 객체 생성(File Path)</mark>

```python
# 이미지 파일 Path를 이용한 Image 객체 생성
image_object_from_path = deepdriver.Image("cat.png")
```

### <mark style="background-color:yellow;">example 3 - 이미지 객체 생성시 caption 지정</mark>

```python
image_object = deepdriver.Image("cat.png", caption="Caption Title")
```

### <mark style="background-color:yellow;">example 4 - 이미지 객체 생성시 영역 정보 지정(BoundingBox 객체 사용)</mark>

```python
from deepdriver.sdk.data_types.boundingBoxes import BoundingBoxes

# BoundingBox 객체 사용
key = "predictions"
box_data = {
    "position": {"minX": 0.1, "maxX": 0.2, "minY": 0.3, "maxY": 0.4},
    "class_id": 1,
    "caption": "road",
    "scores": {"acc": 0.2, "loss": 1.2},
}, {
    "position": {"minX": 100, "maxX": 150, "minY": 300, "maxY": 350},
    "unit": "pixel",
    "class_id": 3,
    "caption": "a building",
    "scores": {"acc": 0.5, "loss": 0.7},
}
class_labels = {"0": "person", "1": "car", "2": "road", "3": "building"}

bb = BoundingBoxes(key="predictions", box_data=box_data, class_labels=class_labels)
image_object = deepdriver.Image("cat.png", boxes=bb)
```

### <mark style="background-color:yellow;">example 4 - 이미지 객체 생성시 영역 정보 지정(직접 입력)</mark>

```python
#Image 객체생성시 직접 영역정보 입력
image_object = deepdriver.Image(
    "cat.png",
    boxes={
        "predictions": {
            "box_data": [
                {
                    "position": {"minX": 0.1, "maxX": 0.2, "minY": 0.3, "maxY": 0.4},
                    "class_id": 1,
                    "caption": "road",
                    "scores": {"acc": 0.2, "loss": 1.2},
                },
                {
                    "position": {"minX": 100, "maxX": 150, "minY": 300, "maxY": 350},
                    "unit": "pixel",
                    "class_id": 3,
                    "caption": "a building",
                    "scores": {"acc": 0.5, "loss": 0.7},
                },
            ],
            "class_labels": {"0": "person", "1": "car", "2": "road", "3": "building"},
        }
    },
)
```

## 2. 객체 표시(Visualize)

```python
# 코드 사용법
deepdriver.visualize(image_object)
```

### <mark style="background-color:yellow;">example</mark>

```python
image_object = deepdriver.Image("cat.png", caption="Caption Title")
deepdriver.visualize(image_object)
```

## 3. 로그 기록

```python
# 코드 사용법
deepdriver.log(image_object)
```

### <mark style="background-color:yellow;">example</mark>

```python
image_object = deepdriver.Image("cat.png", caption="Caption Title")
deepdriver.log({"image":image_object})
```

## 4. artifact 전송

### <mark style="background-color:yellow;">example 1 - 이미지 전송(단일)</mark>&#x20;



```python
arti = deepdriver.Artifacts(name="artifact_name", type="result")
image_object = deepdriver.Image("cat.png")
arti.add(image_object, "cat_image")
deepdriver.upload_artifact(arti)
```

### <mark style="background-color:yellow;">example 2 - 이미지 전송(배열)</mark>&#x20;

```python
arti = deepdriver.Artifacts(name="artifact_name", type="result")
image_object1 = deepdriver.Image("cat.png")
image_object2 = deepdriver.Image("dog.png")
arti.add([image_object1, image_object2], "cat_and_dog_image")
deepdriver.upload_artifact(arti)
```

