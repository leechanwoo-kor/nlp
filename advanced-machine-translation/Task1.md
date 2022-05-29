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
Epoch 1, Step 500, Train Loss: 4.0747, Valid Loss: 4.2897
Epoch 1, Step 1000, Train Loss: 4.2091, Valid Loss: 2.7898
Epoch 1, Step 1500, Train Loss: 4.0862, Valid Loss: 3.4374
Epoch 1, Step 2000, Train Loss: 4.1895, Valid Loss: 3.6256
Epoch 2, Step 2500, Train Loss: 3.5150, Valid Loss: 5.5094
Epoch 2, Step 3000, Train Loss: 3.5290, Valid Loss: 3.7887
Epoch 2, Step 3500, Train Loss: 3.3146, Valid Loss: 3.8165
Epoch 2, Step 4000, Train Loss: 3.5451, Valid Loss: 4.1911
Epoch 3, Step 4500, Train Loss: 2.9419, Valid Loss: 5.4103
Epoch 3, Step 5000, Train Loss: 2.8823, Valid Loss: 3.8532
Epoch 3, Step 5500, Train Loss: 2.6296, Valid Loss: 4.2579
Epoch 3, Step 6000, Train Loss: 2.8466, Valid Loss: 4.4538
Epoch 4, Step 6500, Train Loss: 2.4087, Valid Loss: 5.0858
Epoch 4, Step 7000, Train Loss: 2.2363, Valid Loss: 4.2747
Epoch 4, Step 7500, Train Loss: 1.9315, Valid Loss: 4.5688
Epoch 4, Step 8000, Train Loss: 2.1595, Valid Loss: 4.8646
Epoch 5, Step 8500, Train Loss: 1.9138, Valid Loss: 5.4610
Epoch 5, Step 9000, Train Loss: 1.7748, Valid Loss: 4.5333
Epoch 5, Step 9500, Train Loss: 1.5059, Valid Loss: 4.7777
Epoch 5, Step 10000, Train Loss: 1.7257, Valid Loss: 5.0394
```

![image](https://user-images.githubusercontent.com/55765292/170872930-550e70be-e5a3-4d3d-a761-8121a507858a.png)


### 새로운 학습 데이터가 추가되었을 때 그 성능은 어떻게 변하는지?

**Train : OpenSubtitles + Colloquial / Valid : OpenSubtitles**
```
Epoch 1, Step 500, Train Loss: 5.2748, Valid Loss: 6.9358
Epoch 1, Step 1000, Train Loss: 5.4744, Valid Loss: 6.9337
Epoch 1, Step 1500, Train Loss: 5.5088, Valid Loss: 6.7091
Epoch 1, Step 2000, Train Loss: 5.5438, Valid Loss: 6.1959
Epoch 1, Step 2500, Train Loss: 4.8621, Valid Loss: 5.2377
Epoch 1, Step 3000, Train Loss: 4.4746, Valid Loss: 3.1207
Epoch 1, Step 3500, Train Loss: 4.5143, Valid Loss: 3.7909
Epoch 1, Step 4000, Train Loss: 4.7712, Valid Loss: 3.5404
Epoch 2, Step 4500, Train Loss: 4.5345, Valid Loss: 5.6884
Epoch 2, Step 5000, Train Loss: 4.9677, Valid Loss: 6.2788
Epoch 2, Step 5500, Train Loss: 4.9341, Valid Loss: 5.9368
Epoch 2, Step 6000, Train Loss: 4.8826, Valid Loss: 5.6007
Epoch 2, Step 6500, Train Loss: 3.9651, Valid Loss: 4.5804
Epoch 2, Step 7000, Train Loss: 3.7685, Valid Loss: 3.4938
Epoch 2, Step 7500, Train Loss: 3.5545, Valid Loss: 3.4612
Epoch 2, Step 8000, Train Loss: 3.8354, Valid Loss: 3.8542
Epoch 3, Step 8500, Train Loss: 4.4094, Valid Loss: 6.0248
Epoch 3, Step 9000, Train Loss: 4.5104, Valid Loss: 6.3765
Epoch 3, Step 9500, Train Loss: 4.4172, Valid Loss: 6.0768
Epoch 3, Step 10000, Train Loss: 4.2633, Valid Loss: 6.2167
Epoch 3, Step 10500, Train Loss: 3.3734, Valid Loss: 4.6963
Epoch 3, Step 11000, Train Loss: 3.1394, Valid Loss: 3.6616
Epoch 3, Step 11500, Train Loss: 2.8870, Valid Loss: 3.9723
Epoch 3, Step 12000, Train Loss: 3.1962, Valid Loss: 4.4709
Epoch 4, Step 12500, Train Loss: 3.7731, Valid Loss: 6.2750
Epoch 4, Step 13000, Train Loss: 3.8389, Valid Loss: 6.5281
Epoch 4, Step 13500, Train Loss: 3.7344, Valid Loss: 6.4763
Epoch 4, Step 14000, Train Loss: 3.5792, Valid Loss: 6.7690
Epoch 4, Step 14500, Train Loss: 2.7197, Valid Loss: 4.7993
Epoch 4, Step 15000, Train Loss: 2.7448, Valid Loss: 4.2957
Epoch 4, Step 15500, Train Loss: 2.3515, Valid Loss: 4.6826
Epoch 4, Step 16000, Train Loss: 2.6826, Valid Loss: 4.8692
Epoch 5, Step 16500, Train Loss: 3.2905, Valid Loss: 6.5652
Epoch 5, Step 17000, Train Loss: 3.2551, Valid Loss: 6.7417
Epoch 5, Step 17500, Train Loss: 3.0970, Valid Loss: 6.6731
Epoch 5, Step 18000, Train Loss: 2.9273, Valid Loss: 6.7660
Epoch 5, Step 18500, Train Loss: 2.3899, Valid Loss: 5.2955
Epoch 5, Step 19000, Train Loss: 2.2353, Valid Loss: 4.6598
Epoch 5, Step 19500, Train Loss: 1.9546, Valid Loss: 4.6742
Epoch 5, Step 20000, Train Loss: 2.1712, Valid Loss: 5.1355

```

![image](https://user-images.githubusercontent.com/55765292/170872948-98cd345b-3ca4-47b5-83d0-eb4ae7711053.png)

OpenSubtitiles 데이터 외에 추가 적으로 한국어-영어 번역(병렬) 말뭉치 중 구어체의 데이터를 추가적으로 학습시켰습니다. OpenSubtitiles 데이터로만 학습 했을 때 보다 학습 데이터가 추가 됐을때 더 성능 좋아지는 것을 볼 수 있었습니다. 또한 learning curve 살펴보면 train 데이터의 양이 늘어남으로 과적합에서 벗어나 일반화의 성능이 더 좋아지는 것도 확인할 수 있습니다.

### 다른 스타일의 테스트 데이터의 경우 그 성능은 어떻게 변하는지?

**Train : OpenSubtitles + Colloquial / Valid : Tech**
```
Epoch 1, Step 500, Train Loss: 5.2601, Valid Loss: 4.7518
Epoch 1, Step 1000, Train Loss: 5.7665, Valid Loss: 6.5217
Epoch 1, Step 1500, Train Loss: 5.7238, Valid Loss: 6.2416
Epoch 1, Step 2000, Train Loss: 5.9358, Valid Loss: 6.0391
Epoch 1, Step 2500, Train Loss: 4.9151, Valid Loss: 3.9155
Epoch 1, Step 3000, Train Loss: 4.7584, Valid Loss: 2.9274
Epoch 1, Step 3500, Train Loss: 4.3878, Valid Loss: 3.4583
Epoch 1, Step 4000, Train Loss: 4.4823, Valid Loss: 3.3878
Epoch 2, Step 4500, Train Loss: 4.5463, Valid Loss: 4.9286
Epoch 2, Step 5000, Train Loss: 4.9319, Valid Loss: 6.4030
Epoch 2, Step 5500, Train Loss: 4.9626, Valid Loss: 6.3842
Epoch 2, Step 6000, Train Loss: 5.0238, Valid Loss: 5.5468
Epoch 2, Step 6500, Train Loss: 3.8746, Valid Loss: 3.7482
Epoch 2, Step 7000, Train Loss: 3.6925, Valid Loss: 3.3281
Epoch 2, Step 7500, Train Loss: 3.5724, Valid Loss: 3.7558
Epoch 2, Step 8000, Train Loss: 3.7393, Valid Loss: 4.1942
Epoch 3, Step 8500, Train Loss: 4.2959, Valid Loss: 6.8850
Epoch 3, Step 9000, Train Loss: 4.3232, Valid Loss: 7.2126
Epoch 3, Step 9500, Train Loss: 4.3745, Valid Loss: 7.1091
Epoch 3, Step 10000, Train Loss: 4.3392, Valid Loss: 6.0980
Epoch 3, Step 10500, Train Loss: 3.2869, Valid Loss: 4.8449
Epoch 3, Step 11000, Train Loss: 3.2949, Valid Loss: 3.8001
Epoch 3, Step 11500, Train Loss: 2.9278, Valid Loss: 4.0389
Epoch 3, Step 12000, Train Loss: 3.1022, Valid Loss: 4.8937
Epoch 4, Step 12500, Train Loss: 3.7138, Valid Loss: 6.5743
Epoch 4, Step 13000, Train Loss: 3.7018, Valid Loss: 7.6649
Epoch 4, Step 13500, Train Loss: 3.7232, Valid Loss: 6.9169
Epoch 4, Step 14000, Train Loss: 3.5706, Valid Loss: 6.6386
Epoch 4, Step 14500, Train Loss: 2.8007, Valid Loss: 5.0382
Epoch 4, Step 15000, Train Loss: 2.7072, Valid Loss: 4.0932
Epoch 4, Step 15500, Train Loss: 2.3404, Valid Loss: 4.8559
Epoch 4, Step 16000, Train Loss: 2.5587, Valid Loss: 5.3076
Epoch 5, Step 16500, Train Loss: 3.2279, Valid Loss: 7.3566
Epoch 5, Step 17000, Train Loss: 3.0853, Valid Loss: 7.8645
Epoch 5, Step 17500, Train Loss: 3.1014, Valid Loss: 6.7415
Epoch 5, Step 18000, Train Loss: 2.9300, Valid Loss: 6.9332
Epoch 5, Step 18500, Train Loss: 2.3181, Valid Loss: 4.9882
Epoch 5, Step 19000, Train Loss: 2.2316, Valid Loss: 4.3704
Epoch 5, Step 19500, Train Loss: 2.0727, Valid Loss: 5.4218
Epoch 5, Step 20000, Train Loss: 2.2309, Valid Loss: 5.2185
```

![image](https://user-images.githubusercontent.com/55765292/170873043-b0c09b4b-befd-4bab-a1c9-221ef0429930.png)


기술과학 영역의 train data로 학습을 시켰을 때 기술과학 영역의 valid data로 테스트 했을 때와 비교하여 사회과학 영역의 valid data로 테스트 했을 때 성능이 ~~~ 변하였습니다.

**Train : OpenSubtitles + Colloquial / Valid : Written Language**

```
Epoch 1, Step 500, Train Loss: 5.3284, Valid Loss: 5.0015
Epoch 1, Step 1000, Train Loss: 5.8385, Valid Loss: 6.3082
Epoch 1, Step 1500, Train Loss: 5.8855, Valid Loss: 6.4549
Epoch 1, Step 2000, Train Loss: 5.9817, Valid Loss: 6.7146
Epoch 1, Step 2500, Train Loss: 5.0176, Valid Loss: 3.0488
Epoch 1, Step 3000, Train Loss: 4.6289, Valid Loss: 3.2113
Epoch 1, Step 3500, Train Loss: 4.4993, Valid Loss: 3.3782
Epoch 1, Step 4000, Train Loss: 4.7089, Valid Loss: 3.9686
Epoch 2, Step 4500, Train Loss: 4.8336, Valid Loss: 5.6573
Epoch 2, Step 5000, Train Loss: 4.9445, Valid Loss: 6.1541
Epoch 2, Step 5500, Train Loss: 5.0136, Valid Loss: 5.5732
Epoch 2, Step 6000, Train Loss: 5.0527, Valid Loss: 6.2079
Epoch 2, Step 6500, Train Loss: 3.8479, Valid Loss: 4.0387
Epoch 2, Step 7000, Train Loss: 3.7357, Valid Loss: 3.1619
Epoch 2, Step 7500, Train Loss: 3.6564, Valid Loss: 3.5130
Epoch 2, Step 8000, Train Loss: 3.6484, Valid Loss: 3.9682
Epoch 3, Step 8500, Train Loss: 4.4733, Valid Loss: 6.4409
Epoch 3, Step 9000, Train Loss: 4.4470, Valid Loss: 6.4686
Epoch 3, Step 9500, Train Loss: 4.4581, Valid Loss: 7.0624
Epoch 3, Step 10000, Train Loss: 4.3679, Valid Loss: 6.8289
Epoch 3, Step 10500, Train Loss: 3.3516, Valid Loss: 5.5473
Epoch 3, Step 11000, Train Loss: 3.1306, Valid Loss: 3.4254
Epoch 3, Step 11500, Train Loss: 2.9818, Valid Loss: 4.1804
Epoch 3, Step 12000, Train Loss: 3.1400, Valid Loss: 4.9858
Epoch 4, Step 12500, Train Loss: 3.8931, Valid Loss: 7.1154
Epoch 4, Step 13000, Train Loss: 3.9534, Valid Loss: 6.5796
Epoch 4, Step 13500, Train Loss: 3.8031, Valid Loss: 7.5635
Epoch 4, Step 14000, Train Loss: 3.6816, Valid Loss: 7.4902
Epoch 4, Step 14500, Train Loss: 2.8461, Valid Loss: 5.7354
Epoch 4, Step 15000, Train Loss: 2.6874, Valid Loss: 3.4810
Epoch 4, Step 15500, Train Loss: 2.3238, Valid Loss: 4.8230
Epoch 4, Step 16000, Train Loss: 2.7216, Valid Loss: 5.8210
Epoch 5, Step 16500, Train Loss: 3.3528, Valid Loss: 7.2709
Epoch 5, Step 17000, Train Loss: 3.2978, Valid Loss: 7.6914
Epoch 5, Step 17500, Train Loss: 3.2105, Valid Loss: 7.5611
Epoch 5, Step 18000, Train Loss: 3.0923, Valid Loss: 7.3589
Epoch 5, Step 18500, Train Loss: 2.2945, Valid Loss: 5.4367
Epoch 5, Step 19000, Train Loss: 2.1595, Valid Loss: 4.3368
Epoch 5, Step 19500, Train Loss: 1.9228, Valid Loss: 5.0459
Epoch 5, Step 20000, Train Loss: 2.1772, Valid Loss: 5.3572
```

![image](https://user-images.githubusercontent.com/55765292/170873100-61eadde5-60e3-4e31-87c9-6c3b78500f9c.png)

### 위의 질문들에서 문제점이 있다면 이를 어떻게 극복하면 좋을지?

**Train : Written Language / Valid : Written Language**
```
Epoch 1, Step 500, Train Loss: 5.8297, Valid Loss: 7.3336
Epoch 1, Step 1000, Train Loss: 5.8162, Valid Loss: 6.1111
Epoch 1, Step 1500, Train Loss: 5.9938, Valid Loss: 6.8878
Epoch 1, Step 2000, Train Loss: 5.3820, Valid Loss: 5.2139
Epoch 2, Step 2500, Train Loss: 4.5521, Valid Loss: 6.1855
Epoch 2, Step 3000, Train Loss: 4.9705, Valid Loss: 6.5965
Epoch 2, Step 3500, Train Loss: 4.9656, Valid Loss: 7.5732
Epoch 2, Step 4000, Train Loss: 4.8902, Valid Loss: 5.0427
Epoch 3, Step 4500, Train Loss: 4.2345, Valid Loss: 6.4514
Epoch 3, Step 5000, Train Loss: 4.3942, Valid Loss: 7.3309
Epoch 3, Step 5500, Train Loss: 4.2148, Valid Loss: 8.0115
Epoch 3, Step 6000, Train Loss: 4.2903, Valid Loss: 6.1987
Epoch 4, Step 6500, Train Loss: 3.7143, Valid Loss: 6.5431
Epoch 4, Step 7000, Train Loss: 3.5619, Valid Loss: 8.1279
Epoch 4, Step 7500, Train Loss: 3.3775, Valid Loss: 8.7064
Epoch 4, Step 8000, Train Loss: 3.3633, Valid Loss: 8.3356
Epoch 5, Step 8500, Train Loss: 3.0160, Valid Loss: 7.3000
Epoch 5, Step 9000, Train Loss: 2.7974, Valid Loss: 8.3672
Epoch 5, Step 9500, Train Loss: 2.6448, Valid Loss: 8.7568
Epoch 5, Step 10000, Train Loss: 2.6444, Valid Loss: 9.0517
```

![image](https://user-images.githubusercontent.com/55765292/170873152-5f6ff01b-4957-404c-8acb-157c6eb8251b.png)


새로운 학습 데이터가 추가 되었을 때 다른 스타일의 학습 데이터라면 오히려 학습에 방해가 된다는 것을 볼 수 있었습니다.

또한 학습 시킨 데이터와 테스트 데이터의 스타일이 다를 경우 좋지 않은 성능을 보입니다.

극복... ->

