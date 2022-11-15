# Word2vec을 활용한 분류 모델 구현

## 네이버 영화 리뷰 말뭉치로 Word2vec 임베딩한 후 텍스트 분류 모델 구현

### 텍스트 분류를 위한 데이터셋
- Naver sentiment movie corpus
  - [https://github.com/e9t/nsmc](https://github.com/e9t/nsmc)
    - ratings.txt --> 전체 데이터 (20만개)

    ![image](https://user-images.githubusercontent.com/55765292/201904758-ebc9d312-2b42-4812-9962-18f35c48d943.png)

    - ratings_train.txt --> 학습 데이터 (15만개)

    ![image](https://user-images.githubusercontent.com/55765292/201904811-66190324-06d4-45d9-9071-461485a9105e.png) 

    - ratings_test.txt --> 평가 데이터 (5만개)

### 각 문장의 feature vector 추출하기

![image](https://user-images.githubusercontent.com/55765292/201905043-dc392383-6d34-4399-915b-c8573cc91e64.png)

### 학습 데이터셋 생성 및 분류 모델 학습

![image](https://user-images.githubusercontent.com/55765292/201905112-715c505d-9938-4875-b527-7392da245260.png)

## 소스코드

### konlpy 설치, mecab 설치, Word2vec 모델 준비

```Python
!python3 -m pip install konlpy
```

```Python
!bash <(curl -s https://raw.gihubusercontent.com/konlpy/konlpy/mater/scripts/mecab.sh)
```

```Python
from gensim.models import word2vec

import numpy as np
import pandas as pd

model_fname = "/content/drive/MyDrive/Word2vec/Model/word2vec"
```

### get_features 함수 정의

```Python
def get_features(words, model, num_features):
    # 출력 벡터 초기화
    feature_vector = np.zeros((num_features), dtype=np.float64)

    num_words = 0

    # 어휘사전 준비
    index2word_set = set(model.wv.index2word)

    for w in words:
        if w in index2word_set:
            num_words += 1
            feature_vector = np.add(feature_vector, model[w])
        else:
            feature_vector = np.add(feature_vector, 0)

    if num_words == 0:
        feature_vector = feature_vector
    else:
        feature_vector = np.divide(feature_vector, num_words)

    return feature_vector
```

### get_dataset 함수 정의

```Python
def get_dataset(reviews, model, num_features):
    dataset = list()

    for s in reviews:
        dataset.append(get_features(s, model, num_features))

    review_feature_vector = np.stack(dataset)

    return review_feature_vector
```

### 학습 데이터셋 준비 및 mecab 전처리 함수 정의

```Python
# main
TRAIN_DATA = 'ratings.txt'

CORPUS_DIR = "/content/drive/MyDrive/Word2vec/Corpus/"

train_data = pd.read_csv(CORPUS_DIR + TRAIN_DATA,
                         header=0,
                         delimiter='\t',
                         quoting=3)
```

```Python
import re

def preprocessing(review, mecab):
    #review = re.sub("[^가-힣ㄱ-ㅎㅏ-ㅣ\\s]", "", review)
    word_review = mecab.morphs(review)

    return word_review
```

```Python
from konlpy.tag import Mecab

mecab = Mecab()
```

### 학습 데이터셋 준비 및 pretrained Word2vec 모델 로드

```Python
documents = list(train_data['document'])
labels = list(train_data['label'])

sentences = []
model = word2vec.Word2Vec.load(model_fname + '_size_10' + '_window_5')
num_features = 10

for doc in documents:
    if type(doc) == str:
        sentences.append(preprocessing(doc, mecab))
    else:
        sentences.append([])

data_vectors = get_dataset(sentences, model, num_features)
```

### 분류 모델에 주입할 학습 및 검증 데이터셋 준비

```Python
from sklearn.model_selection import train_test_split

X = data_vectors
y = np.array(labels)

RANDOM_SEED = 42
TEST_SPLIT = 0.2

X_train, X_eval, y_train, y_eval = train_test_split(X,
                                                    y,
                                                    test_size=TEST_SPLIT,
                                                    random_state=RANDOM_SEED)

print(len(X_train))
print(len(y_train))
print(len(X_eval))
print(len(y_eval))
```

### 로지스틱 회귀 vs 랜덤 포레스트 분류모델 정확도 비교

```Python
from sklearn.linear_model import LogisticRegression

lr = LogisticRegression(class_weight='balanced')
lr.fit(X_train, y_train)

print("Accuracy: %f" % lr.score(X_eval, y_eval))
## Accuracy: 0.731075

from sklearn.linear_model import RandomForestClassifier

forest = RandomForestClassifier(n_estimators=100)
forest.fit(X_train, y_train)

print("Accuracy: %f" % forest.score(X_eval, y_eval))
## Accuracy: 0.751775
```

### Word2vec 차원수를 증가시킨 후 분류모델 정확도 결과

- 학습방법
    - 학습 데이터셋 : 160,000
    - 검증 데이터셋 : 40,000

|모델명|word2vec 차원수|정확도|
|:--:|:--:|:--:|
|Word2vec + LR|10|0.731075|
|Word2vec + RF|10|0.751775|
|Word2vec + LR|300|0.818200|
|Word2vec + RF|300|0.803750|
