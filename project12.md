# AIFFEL Campus Online 5th Code Peer Review Templete
- 코더 : 최예나
- 리뷰어 : 이수봉


# PRT(PeerReviewTemplate) 
각 항목을 스스로 확인하고 토의하여 작성한 코드에 적용합니다.

- [X] 코드가 정상적으로 동작하고 주어진 문제를 해결했나요?
  
- [X] 주석을 보고 작성자의 코드가 이해되었나요?
  > 각 과정에대한 주석과 코드에 대한 주석이 있어서 이해하기 쉬웠습니다.
  > 시각화를 통해 모델의 결과물을 잘 보여주고 있었습니다.
- [X] 코드가 에러를 유발할 가능성이 없나요?
  > 아니요 없습니다.
- [X] 코드 작성자가 코드를 제대로 이해하고 작성했나요?
  > 네, 코드를 제대로 이해하고 작성이 된 것 같습니다.
- [X] 코드가 간결한가요?
  > 불필요한 코드없이 간결하였습니다.


# 예시
1. 코드의 작동 방식을 주석으로 기록합니다.
2. 코드의 작동 방식에 대한 개선 방법을 주석으로 기록합니다.
3. 참고한 링크 및 ChatGPT 프롬프트 명령어가 있다면 주석으로 남겨주세요.
```python

# 노드에서 제시한 것과 결과가 다르게 나왔는데, 다르게 나온 원인을 파악한점이 인상깊었습니다.

img = os.getenv('HOME')+'/aiffel/object_detection/data/go_3.png'
image = Image.open(img)
image.show()
```
```python
# go 와 stop의 조건을이 잘 명시되어있었습니다.

    #사람이 있을경우
    person = 0
    for i in range(len(class_name)):
        if class_name[i] == "Pedestrian" or class_name[i] == "Person_sitting":
            person = 1
            return stop

    #사람이 없을 경우
    if person == 0:
        for i in range(len(class_name)):
            if class_name[i] == "Car" or class_name[i] =="Van" or class_name[i] =="Truck" or class_name[i] =="Tram":
                if height_v[i] >= size_limit or width_v[i] >= size_limit:
                    return stop
            else:
                return go
        return go
```


# 참고 링크 및 코드 개선
```python
# 코드 리뷰 시 참고한 링크가 있다면 링크와 간략한 설명을 첨부합니다.
# 코드 리뷰를 통해 개선한 코드가 있다면 코드와 간략한 설명을 첨부합니다.
```
