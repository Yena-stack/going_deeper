# AIFFEL Campus Online 5th Code Peer Review Templete
- 코더 : 최예나
- 리뷰어 : 이수봉


# PRT(PeerReviewTemplate) 
각 항목을 스스로 확인하고 토의하여 작성한 코드에 적용합니다.

- [X] 코드가 정상적으로 동작하고 주어진 문제를 해결했나요?
  
- [X] 주석을 보고 작성자의 코드가 이해되었나요?
  > 간단한 주석을 통해 해당 코드의 내용을 이해했습니다.
- [X] 코드가 에러를 유발할 가능성이 없나요?
  > 아니요 에러를 유발할 가능성이 없었습니다.
- [X] 코드 작성자가 코드를 제대로 이해하고 작성했나요?
  > 네, 코드를 제대로 이해하고 작성이 된 것 같습니다.

  > 결과 값을 시각화 하여 잘 보여주고 있었습니다.
- [X] 코드가 간결한가요?
  > 불필요한 코드없이 간결하였습니다.


# 예시
1. 코드의 작동 방식을 주석으로 기록합니다.
2. 코드의 작동 방식에 대한 개선 방법을 주석으로 기록합니다.
3. 참고한 링크 및 ChatGPT 프롬프트 명령어가 있다면 주석으로 남겨주세요.
```python

#에포크2, 에포크10 예측한 바운딩 박스 + 라벨값의 바운딩 박스
image = cv2.drawContours(image, [rect1_np], 0, (0,255,0), 2)
image = cv2.drawContours(image, [rect2], 0, (255,0,0), 2)

plt.imshow(image)
plt.show()

# 에포크 별로 모델이 바운딩박스를 예측하는 과정을 보여준점이 인상깊었습니다.

```

# 참고 링크 및 코드 개선
```python
# 코드 리뷰 시 참고한 링크가 있다면 링크와 간략한 설명을 첨부합니다.
# 코드 리뷰를 통해 개선한 코드가 있다면 코드와 간략한 설명을 첨부합니다.
```
