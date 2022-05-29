- AIHub에서 한국어-영어 번역 말뭉치를 다운로드 받습니다.
- 말뭉치 데이터 중 하나를 학습 데이터(training data)로 선택합니다.
- 선택된 데이터를 가공하여 Google colab에 올려 기계 번역 모델을 학습시킵니다.
- (Optional) 실제 번역문을 생성하는 함수인 "test"를 만듭니다.
- 말뭉치 데이터 중 학습 데이터가 아닌 데이터를 테스트 데이터(test data)로 선택합니다.
- 선택된 데이터를 가공하여 Google colab에 올려 기계 번역 모델을 평가합니다.
- "test" 함수를 만들었으면 실제 결과를 출력해서 기존 test 데이터와 비교해보세요.
- "test" 함수를 만들지 못하셨다면 "evaluate" 함수를 이용하여 loss 값의 차이를 확인해보세요.

또 다른 테스트 데이터를 선택하여 앞의 step를 수행해보세요.
새로운 데이터 중 학습 데이터는 1개, 테스트 데이터는 2개를 선택하여 위 step을 진행해주세요. 보고서에는 위 step을 수행한 후 아래 질문에 대한 답을 작성해주세요.

### 새로운 학습 데이터가 추가되었을 때 그 성능은 어떻게 변하는지?

**[Train / Valid]**

**OpenSubtitles / OpenSubtitles**
```
Epoch 1, Step 1000, Train Loss: 4.0444, Valid Loss: 2.6510
Epoch 1, Step 2000, Train Loss: 3.9447, Valid Loss: 3.4692
Epoch 2, Step 3000, Train Loss: 3.5018, Valid Loss: 3.2066
Epoch 2, Step 4000, Train Loss: 3.5036, Valid Loss: 4.0961
Epoch 3, Step 5000, Train Loss: 3.0029, Valid Loss: 3.6207
Epoch 3, Step 6000, Train Loss: 2.7816, Valid Loss: 4.9249
Epoch 4, Step 7000, Train Loss: 2.4571, Valid Loss: 4.2472
Epoch 4, Step 8000, Train Loss: 2.2172, Valid Loss: 4.9423
Epoch 5, Step 9000, Train Loss: 1.9786, Valid Loss: 4.3708
Epoch 5, Step 10000, Train Loss: 1.6797, Valid Loss: 5.2923
...
```

**Colloquial / Colloquial**
```
Epoch 1, Step 1000, Train Loss: 4.8794, Valid Loss: 5.4029
Epoch 1, Step 2000, Train Loss: 5.0731, Valid Loss: 5.4855
Epoch 2, Step 3000, Train Loss: 4.4319, Valid Loss: 4.3106
Epoch 2, Step 4000, Train Loss: 4.4916, Valid Loss: 5.3708
Epoch 3, Step 5000, Train Loss: 3.9678, Valid Loss: 4.6129
Epoch 3, Step 6000, Train Loss: 3.9164, Valid Loss: 5.5825
Epoch 4, Step 7000, Train Loss: 3.3779, Valid Loss: 5.0412
Epoch 4, Step 8000, Train Loss: 3.1539, Valid Loss: 5.5656
Epoch 5, Step 9000, Train Loss: 2.7052, Valid Loss: 4.6745
Epoch 5, Step 10000, Train Loss: 2.4623, Valid Loss: 5.8785
...
```

**OpenSubtitles + Colloquial / OpenSubtitles**
```
Epoch 1, Step 1000, Train Loss: 4.8111, Valid Loss: 6.2665
Epoch 1, Step 2000, Train Loss: 5.1499, Valid Loss: 7.5477
Epoch 1, Step 3000, Train Loss: 4.4146, Valid Loss: 7.5656
Epoch 1, Step 4000, Train Loss: 4.2460, Valid Loss: 7.4516
Epoch 2, Step 5000, Train Loss: 4.5241, Valid Loss: 5.7790
Epoch 2, Step 6000, Train Loss: 4.5797, Valid Loss: 7.2203
Epoch 2, Step 7000, Train Loss: 3.7614, Valid Loss: 6.4818
Epoch 2, Step 8000, Train Loss: 3.8389, Valid Loss: 7.0375
Epoch 3, Step 9000, Train Loss: 4.2250, Valid Loss: 5.2752
Epoch 3, Step 10000, Train Loss: 4.0409, Valid Loss: 6.3157
Epoch 3, Step 11000, Train Loss: 3.2615, Valid Loss: 4.6247
Epoch 3, Step 12000, Train Loss: 3.2344, Valid Loss: 4.1367
Epoch 4, Step 13000, Train Loss: 3.6594, Valid Loss: 4.3561
Epoch 4, Step 14000, Train Loss: 3.3882, Valid Loss: 4.6664
Epoch 4, Step 15000, Train Loss: 2.7861, Valid Loss: 3.5905
Epoch 4, Step 16000, Train Loss: 2.7031, Valid Loss: 3.5656
Epoch 5, Step 17000, Train Loss: 2.9955, Valid Loss: 4.6023
Epoch 5, Step 18000, Train Loss: 2.7766, Valid Loss: 3.6216
Epoch 5, Step 19000, Train Loss: 2.3406, Valid Loss: 4.8255
Epoch 5, Step 20000, Train Loss: 2.3054, Valid Loss: 3.7498
Epoch 6, Step 21000, Train Loss: 2.4517, Valid Loss: 4.0770
Epoch 6, Step 22000, Train Loss: 2.2952, Valid Loss: 4.6688
Epoch 6, Step 23000, Train Loss: 2.0679, Valid Loss: 3.5041
Epoch 6, Step 24000, Train Loss: 2.0183, Valid Loss: 3.5289
Epoch 7, Step 25000, Train Loss: 2.1159, Valid Loss: 3.5719
Epoch 7, Step 26000, Train Loss: 2.0362, Valid Loss: 2.8165
Epoch 7, Step 27000, Train Loss: 1.9460, Valid Loss: 3.4099
Epoch 7, Step 28000, Train Loss: 1.8239, Valid Loss: 3.4304
Epoch 8, Step 29000, Train Loss: 1.8987, Valid Loss: 5.2525
Epoch 8, Step 30000, Train Loss: 1.8670, Valid Loss: 5.2192
Epoch 8, Step 31000, Train Loss: 1.8338, Valid Loss: 5.0642
Epoch 8, Step 32000, Train Loss: 1.6708, Valid Loss: 5.0378
Epoch 9, Step 33000, Train Loss: 1.7765, Valid Loss: 5.0154
...
```

OpenSubtitiles 데이터 외에 추가 적으로 한국어-영어 번역(병렬) 말뭉치 중 구어체의 데이터를 추가적으로 학습시켰습니다. OpenSubtitiles 데이터로만 학습 했을 때 보다 학습 데이터가 추가 됐을때 더 성능 좋아지는 것을 볼 수 있었습니다. 또한 train 데이터의 양이 늘어나면서 learning curve에서 과적합이 생기는 지점도 보다 알아보기 쉬웠습니다.

### 다른 스타일의 테스트 데이터의 경우 그 성능은 어떻게 변하는지?

기술과학 영역의 train data로 학습을 시켰을 때 기술과학 영역의 valid data로 테스트 했을 때와 비교하여 사회과학 영역의 valid data로 테스트 했을 때 성능이 ~~~ 변하였습니다.

### 위의 질문들에서 문제점이 있다면 이를 어떻게 극복하면 좋을지?

새로운 학습 데이터가 추가 되었을 때 다른 스타일의 학습 데이터라면 오히려 학습에 방해가 된다는 것을 볼 수 있었습니다.

또한 학습 시킨 데이터와 테스트 데이터의 스타일이 다를 경우 좋지 않은 성능을 보입니다.

극복... ->

