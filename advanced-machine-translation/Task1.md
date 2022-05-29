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

**Train : OpenSubtitles / Valid: OpenSubtitles**
```
Epoch 1, Step 500, Train Loss: 3.9331, Valid Loss: 4.8402
Epoch 1, Step 1000, Train Loss: 4.1794, Valid Loss: 2.8732
Epoch 1, Step 1500, Train Loss: 3.9762, Valid Loss: 3.0234
Epoch 1, Step 2000, Train Loss: 4.1264, Valid Loss: 3.8008
Epoch 2, Step 2500, Train Loss: 3.3562, Valid Loss: 5.7123
Epoch 2, Step 3000, Train Loss: 3.3801, Valid Loss: 3.4554
Epoch 2, Step 3500, Train Loss: 3.3361, Valid Loss: 3.3961
Epoch 2, Step 4000, Train Loss: 3.5773, Valid Loss: 3.8519
Epoch 3, Step 4500, Train Loss: 2.9231, Valid Loss: 5.3872
Epoch 3, Step 5000, Train Loss: 2.8246, Valid Loss: 3.9702
Epoch 3, Step 5500, Train Loss: 2.6682, Valid Loss: 3.9083
Epoch 3, Step 6000, Train Loss: 2.8806, Valid Loss: 4.8590
Epoch 4, Step 6500, Train Loss: 2.4562, Valid Loss: 5.0448
Epoch 4, Step 7000, Train Loss: 2.2182, Valid Loss: 4.0194
Epoch 4, Step 7500, Train Loss: 2.0738, Valid Loss: 3.9823
Epoch 4, Step 8000, Train Loss: 2.2840, Valid Loss: 4.3234
Epoch 5, Step 8500, Train Loss: 2.0030, Valid Loss: 5.0105
Epoch 5, Step 9000, Train Loss: 1.8449, Valid Loss: 4.3746
Epoch 5, Step 9500, Train Loss: 1.5643, Valid Loss: 4.5376
Epoch 5, Step 10000, Train Loss: 1.7733, Valid Loss: 5.3185
```

![image](https://user-images.githubusercontent.com/55765292/170865821-fe5edb9a-13e7-4efb-9475-624b265247f2.png)


### 새로운 학습 데이터가 추가되었을 때 그 성능은 어떻게 변하는지?

**OpenSubtitles + Colloquial / OpenSubtitles**
```
Epoch 1, Step 500, Train Loss: 4.8573, Valid Loss: 6.2924
Epoch 1, Step 1000, Train Loss: 5.0419, Valid Loss: 6.5089
Epoch 1, Step 1500, Train Loss: 5.0407, Valid Loss: 6.1959
Epoch 1, Step 2000, Train Loss: 5.0775, Valid Loss: 7.5224
Epoch 1, Step 2500, Train Loss: 4.5981, Valid Loss: 5.0044
Epoch 1, Step 3000, Train Loss: 4.2849, Valid Loss: 7.4039
Epoch 1, Step 3500, Train Loss: 4.0061, Valid Loss: 6.7220
Epoch 1, Step 4000, Train Loss: 4.7452, Valid Loss: 7.1186
Epoch 2, Step 4500, Train Loss: 4.4674, Valid Loss: 5.9411
Epoch 2, Step 5000, Train Loss: 4.6072, Valid Loss: 7.0962
Epoch 2, Step 5500, Train Loss: 4.5358, Valid Loss: 6.8572
Epoch 2, Step 6000, Train Loss: 4.5857, Valid Loss: 7.1028
Epoch 2, Step 6500, Train Loss: 3.7269, Valid Loss: 6.9704
Epoch 2, Step 7000, Train Loss: 3.6618, Valid Loss: 8.0015
Epoch 2, Step 7500, Train Loss: 3.6292, Valid Loss: 7.6382
Epoch 2, Step 8000, Train Loss: 3.9817, Valid Loss: 5.7666
...
Epoch 5, Step 16500, Train Loss: 3.1641, Valid Loss: 4.1171
Epoch 5, Step 17000, Train Loss: 2.9555, Valid Loss: 4.2780
Epoch 5, Step 17500, Train Loss: 2.8792, Valid Loss: 4.6258
Epoch 5, Step 18000, Train Loss: 2.7232, Valid Loss: 4.8683
Epoch 5, Step 18500, Train Loss: 2.3072, Valid Loss: 3.5679
Epoch 5, Step 19000, Train Loss: 2.3687, Valid Loss: 5.5480
Epoch 5, Step 19500, Train Loss: 2.1897, Valid Loss: 5.7043
Epoch 5, Step 20000, Train Loss: 2.3645, Valid Loss: 4.4479
...
Epoch 10, Step 36500, Train Loss: 1.6700, Valid Loss: 4.3425
Epoch 10, Step 37000, Train Loss: 1.6383, Valid Loss: 4.6930
Epoch 10, Step 37500, Train Loss: 1.6009, Valid Loss: 5.1070
Epoch 10, Step 38000, Train Loss: 1.5809, Valid Loss: 4.8390
Epoch 10, Step 38500, Train Loss: 1.5620, Valid Loss: 4.1602
Epoch 10, Step 39000, Train Loss: 1.5652, Valid Loss: 4.4411
Epoch 10, Step 39500, Train Loss: 1.4578, Valid Loss: 5.1976
Epoch 10, Step 40000, Train Loss: 1.4896, Valid Loss: 5.0538
```

![image](https://user-images.githubusercontent.com/55765292/170866492-52a2c428-6590-4aaa-ba57-b295921626af.png)

OpenSubtitiles 데이터 외에 추가 적으로 한국어-영어 번역(병렬) 말뭉치 중 구어체의 데이터를 추가적으로 학습시켰습니다. OpenSubtitiles 데이터로만 학습 했을 때 보다 학습 데이터가 추가 됐을때 더 성능 좋아지는 것을 볼 수 있었습니다. 또한 train 데이터의 양이 늘어나면서 learning curve에서 과적합이 생기는 지점도 보다 알아보기 쉬웠습니다.

### 다른 스타일의 테스트 데이터의 경우 그 성능은 어떻게 변하는지?

기술과학 영역의 train data로 학습을 시켰을 때 기술과학 영역의 valid data로 테스트 했을 때와 비교하여 사회과학 영역의 valid data로 테스트 했을 때 성능이 ~~~ 변하였습니다.

### 위의 질문들에서 문제점이 있다면 이를 어떻게 극복하면 좋을지?

새로운 학습 데이터가 추가 되었을 때 다른 스타일의 학습 데이터라면 오히려 학습에 방해가 된다는 것을 볼 수 있었습니다.

또한 학습 시킨 데이터와 테스트 데이터의 스타일이 다를 경우 좋지 않은 성능을 보입니다.

극복... ->

