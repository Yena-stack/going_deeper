# AIFFEL Campus Online 5th Code Peer Review Templete
- 코더 : 최예나
- 리뷰어 : 이수봉


# PRT(PeerReviewTemplate) 
각 항목을 스스로 확인하고 토의하여 작성한 코드에 적용합니다.

- [X] 코드가 정상적으로 동작하고 주어진 문제를 해결했나요?
  
- [X] 주석을 보고 작성자의 코드가 이해되었나요?
  > 간단한 주석을 통해 어떠한 역할을 하는 함수인지 알 수 있었습니다.
- [X] 코드가 에러를 유발할 가능성이 없나요?
  > 아니요 에러를 유발할 가능성이 없었습니다.
- [X] 코드 작성자가 코드를 제대로 이해하고 작성했나요?
  > 전처리, 모델의 구성을 잘 한것으로 보아 코드를 제대로 이해한 것 같습니다.
- [X] 코드가 간결한가요?
  > 불필요한 코드 없이 간결하였습니다.

# 예시
1. 코드의 작동 방식을 주석으로 기록합니다.
2. 코드의 작동 방식에 대한 개선 방법을 주석으로 기록합니다.
3. 참고한 링크 및 ChatGPT 프롬프트 명령어가 있다면 주석으로 남겨주세요.
```python
# 노드에서 나온 내용 이외에 다양한 전처리 기법을 적용을 시도한 부분이 인상깊었습니다.

def normalize_and_resize_img(image, label):
    # Normalizes images: `uint8` -> `float32`
    image = tf.image.resize(image, [224, 224])
    return tf.cast(image, tf.float32) / 255., label

def augment(image,label):
#     print('augment')
    image = tf.image.random_flip_left_right(image)
    image = tf.image.random_brightness(image, max_delta = 0.2)
    image = tf.clip_by_value(image, 0, 1)
    return image, label

def augment2(image, label):
    
    image = tf.image.random_flip_left_right(image)
    image = tf.image.random_flip_up_down(image)
    image = tf.image.random_brightness(image, max_delta = 0.2)
    image = tf.image.random_contrast(image, 1/1.3, 1.3)
    image = tf.image.random_hue(image, 0.1)
#     image = tf.keras.preprocessing.image.random_rotation(image, 90)

#     random_height = tf.random.uniform((), minval=32, maxval=40, dtype=tf.int32)
#     random_width = tf.random.uniform((), minval=32, maxval=40, dtype=tf.int32)
#     image = tf.image.resize(image, (random_height, random_width))
#     image = tf.image.random_crop(image, (32, 32, 3))
    return image, label
```

# 참고 링크 및 코드 개선
```python
# resnet-50에서 발생한 경고에 대한 해결방법입니다.

# GPT
# 이 경고 메시지는 Keras의 옵티마이저 관련 설정에서 `lr` 인자를 사용하는 대신 `learning_rate` 인자를 사용하라는 내용의 경고입니다. Keras에서 옵티마이저를 설정할 때 이전에는 `lr`을 사용했지만, 더 최신 버전에서는 `learning_rate`을 사용하도록 권장하고 있습니다.

# 이 오류를 해결하기 위해서는 코드에서 `lr`을 사용하는 부분을 `learning_rate`로 변경하면 됩니다. 변경 후 코드 예시는 다음과 같습니다:


# # 이전 코드
 optimizer=tf.keras.optimizers.SGD(lr=0.001)

# # 변경된 코드
optimizer=tf.keras.optimizers.SGD(learning_rate=0.001)

# 이렇게 변경하면 해당 경고 메시지가 나타나지 않을 것입니다. 최신 버전의 Keras를 사용하는 경우에는 이와 같은 변경이 필요할 수 있습니다.

```
