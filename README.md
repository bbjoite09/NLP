<h1 align="center"> 🙌🏻 자연어 처리(NLP) 🙌🏻 </h1>
🌱 2021.01.23 - 2021.02.10 <br>
🌱 Natural Language Processing_HUFS_AI_CAMP<br>
🌱 각각의 Day는 이론과 실습, 과제의 결과물로 구성되어 있으며, 📝는 과제를 의미한다.

## ✨ Day 0 
<details open>
<summary><b>Introduction</b></summary><br>
<b>Google Colab</b> 및 <b>Slack</b>의 조작 방법 익히기 <br>
<b>Numpy, Tensorflow, Matplotlib, Pandas</b>에 대한 기본 지식 학습하기<br><br>
<p align="center"><img src = "Data/images/day1.PNG" alt="day1" width = "419" height = "343"></p><br><br>
</details>



## ✨ Day 1
<details><summary><b>1.1 단어 분류 프로젝트</b></summary><br>
sentences를 입력 받아 구성하는 단어가 긍정인지, 중립인지, 부정인지 분류하는 프로젝트를 만들어 본다. <br>
이때 단어의 긍정은 2, 중립은 1, 부정은 0으로 표시하며, 예를 들어 "나는 오늘 기분이 좋아" 라는 문장의 경우 띄어쓰기를 기준으로 split()하여 <b>[1, 1, 1, 2]</b>를 출력한다.<br>
단어 분류 프로젝트는 데이터를 통해 Vocabulary를 생성 -> 학습용 데이터 생성 -> 모델링 -> 학습 -> 평가 -> 예측을 통해 진행된다. 실습 내용은 <a href = "https://github.com/bbjoite09/NLP/blob/main/Practice/1.1%20simple%20word%20project.ipynb">여기</a>에서 확인할 수 있다.<br><br>
</details>

<details><summary><b>📝 1.2 문장 분류 프로젝트</b></summary><br>
위의 단어 분류 프로젝트와 비슷하게 입력받은 문장이 긍정인지, 부정인지 분류하는 프로젝트를 만들어 본다.<br>
위와 유사하게, 단어의 긍정은 1, 부정은 0로 표시한다. "나는 오늘 기분이 좋아" 라는 문장의 경우 <b>1 : 긍정</b>을 출력하도록 한다.<br>
실습 내용은 <a href = "https://github.com/bbjoite09/NLP/blob/main/Practice/1.2%20simple%20sentence%20project.ipynb">여기</a>에서 확인할 수 있다. <br><br>
</details>

## ✨ Day 2

<details><summary><b>2.1 Encodding</b></summary><br>
첫번째로 데이터를 표현하는 방법에 대하여 학습하였다.<br>
Text data의 경우 입력받은 문장을 중복을 제거하여 Tokenizer 한 후 각 Token에 대하여 index를 부여한다. 이후 Encoding을 진행한다. 이때 여러가지의 Encoding 중 One hot encoding에 대한 실습을 진행하였다.<br><br>
One hot encoding은 위에서 받은 Token의 집합, 즉 단어의 집합을 벡터 차원의 크기로 만들고 원하는 한개의 단어 인덱스에만 1, 나머지 단어들에는 0을 부여하는 벡터 표현 방식이다.<br>
실습 내용은 <a href = "https://github.com/bbjoite09/NLP/blob/main/Practice/2.1%20encoding.ipynb">여기</a>에서 확인할 수 있다.<br><br>
</details>

<details><summary><b>2.2 Tokenizer</b></summary><br>
Tokenize란 문장을 일정한 규칙을 통해 토큰 단위로 나누는 과정을 말한다.<br>
실습 2.1에서 입력받은 sentence 데이터를 Tokenize 하여, 나누어진 Token에 고유한 번호를 부여해 Vocabulary를 생성하였다. 이를 진행할때는 Token의 개수, Vocabulary의 개수를 고려하여 미등록 단어를 최소화 하되, 효율적으로 Tokenizer 할 수 있도록 설계해야 한다.<br><br>

- Char Tokenizer : 글자 단위로 단어를 Tokenize 한다. 이는 작은 수의 vocabulary로 모든 문장을 표현 가능하도록 하나, 각 토큰들은 단어의 고유 의미를 표현하지 못한다는 단점이 있다.<br>
- Word Tokenizer : 띄어쓰기 단위로 단어를 Tokenize한다. 이는 구현이 쉬우나 어미 변화에 따른 유사 Token이 많아지고, 이 단어들이 비슷한 벡터를 가지지 않을 수 있다는 단점이 있다. 또한 이는 데이터가 많아질 수 록 vocaburlary 개수가 증가한다는 단점이 있다.<br>
- BPE(Byte Pair Encoding) : 빈도수를 기반으로 계산하여 subword 단위로 단어를 Tokenize한다. 이는 현재 가장 많이 사용되는 Tokenize 방식으로, subwords단위로 tokenize하기 때문에 미등록 단어를 최소화한다는 장점이 있다. 한편 vocab 수를 작게하였을 때 subwords가 많이 생겨 token 수가 많아진다는 단점이 있다.<br><br>
위의 내용에 대한 실습은 <a href = "https://github.com/bbjoite09/NLP/blob/main/Practice/2.2%20tokenizer.ipynb">여기</a>에서 확인할 수 있다.<br><br>
</details>

<details><summary><b>📝 2.3 Tokenizer</b></summary><br>
my_corpus라는 새로운 말뭉치로 Tokenizer 실습을 진행하였다.<br>
해당 실습에 대한 내용은 <a href = "https://github.com/bbjoite09/NLP/blob/main/Practice/2.3%20tokenizer.ipynb">여기</a>에서 확인할 수 있다.<br><br>
</details>

## ✨ Day 3
<details><summary><b>3.1 matrix equation</b></summary><br>
행렬의 기본 연산에 대하여 학습하였다.<br>
해당 실습에 대한 내용은 <a href = "https://github.com/bbjoite09/NLP/blob/main/Practice/3.1%20matrix%20equation.ipynb">여기</a>에서 확인할 수 있다.<br><br>
</details>

<details><summary><b>3.2 word embedding</b></summary><br>
<b>Word Representation</b><br><br>
  
- 시소러스(ex. WordNet) : 사람이 단어의 의미를 직접 정의하는 방식을 말한다. 이는 단어의 유의어 집합을 생성한 후, 각각의 연결을 정의하여 이들간의 관계를 표현한다. 이는 쉽다는 장점이 있는 한편, 시대의 변화에 따른 대응이 어렵고, 비용이 높다는 문제를 야기하면서 비효율을 초래한다.
- Distributional semantics(ex. Word2Vec): outer word들이 center word를 표현하는 방식을 말한다. 즉, 단어 그 자체의 의미보다는 문맥의 흐름을 통하여 단어의 의미를 형성한다. 단어의 의미를 여러 차원에 분산하여 표현하여 단어간 유사도를 계산할 수 있다.
- 이외에도 통계기반 기법, 동시발생 행렬 등 단어를 표현하는 다양한 방법이 존재한다.<br><br>

<b>Word2Vec</b><br><br>
어떤 text data에 대하여 모든 단어는 벡터로 표현된다. 이 단어 벡터들은 유사도를 반영한 값을 가지고 있으며, 어떤 시점 t에는 중심 단어 c와 주변 단어 o가 있다. c에 대하여 o가 나타날 확률을 계산할 때 이 벡터의 유사성을 이용한다. 우리는 단어의 벡터를 변경하여 c에 대해 o가 나타날 확률을 최대화 할 수 있다.<br><br>

- Skip-Gram : 하나의 중심단어를 통해 주변 단어를 예측한다.
- CBOW(Continuous Bag of Words) : 여러 주변 단어를 통해 중심 단어를 예측한다.<br><br>

Word2Vec은 Skip-Gram과 CBOW 두가지 방식이 존재한다. 두 방법 모두 window size를 지정하여, center word 중심으로 몇개의 주변 단어를 살펴볼지 결정한다. 예를들어 Skip-Gram 에서 window size가 2라고 하면 중심 단어를 기준으로 하여 앞 뒤 2개의 단어를 예측한다.<br>해당 내용에 대한 실습은 <a href = "https://github.com/bbjoite09/NLP/blob/main/Practice/3.2%20word%20embedding.ipynb">여기</a>에서 확인할 수 있다.<br><br>
</details>

<details><summary><b>📝 3.3 word embedding</b></summary><br>
OKT 형태소 분석기와 네이버 영화 리뷰 데이터(nsmc), gensim으로 한국어를 학습시킨 후 단어 연산 프로젝트를 진행해 본다. 예를들어 "왕 - 남자 + 여자"라는 연산에 대하여 "여왕" 혹은 이와 유사한 단어를 출력하도록 한다.<br>해당 실습 내용은 <a href = "https://github.com/bbjoite09/NLP/blob/main/Practice/3.3%20word%20embedding.ipynb">여기</a>에서 확인할 수 있다.<br><br>
</details>

## ✨ Day 4
<details><summary><b>4.1 CNN</b></summary><br>

CNN(Convolution Neural Network)에 대하여 학습한다.<br>
CNN은 주로 이미지 인식에 사용되며, 차원이 높은 데이터를 신경망으로 학습시킬 때는 1차원으로 평면화를 진행해야 한다. 이때 차원을 줄이는 과정에서 공간 정보가 유실되어 학습이 비효율적으로 이루어질 수 있는데, 이를 대비하여 CNN 모델을 사용한다. CNN은 이러한 공간 정보를 유지한 상태로 학습이 가능하도록 만든 모델으로 kernel을 이용하여 특징을 추출하는 과정이다..<br><br>

- Convolution : 합성 곱을 말한다. Input 값에 대하여 filter(kernel)을 이동시켜 겹쳐지는 각 원소의 값을 곱한 후 모두 더하여 계산할 수 있다.
- stride : kernel을 한번에 이동하는 간격을 말한다.
- padding : padding의 값에 따라 Input의 상하좌우에 PAD가 둘러진다. 이때 PAD는 주로 '0'을 사용한다.
- MaxPooling : overfitting을 방지하기 위하여 큰 값을 추출해 낸다. stride가 2라고 할 때 아래의 데이터를 max pooling하면 7, 9, 3, 6의 결과를 얻을 수 있다.
<p align="center"><img src = "Data/images/maxpooling.jpg" width = "605" height = "302" alt = "max pooling image"></p>

<br>
keras에서는 conv로 cnn을 구현할 수 있도록 한다. conv1d, conv2d, conv3d 등이 있는데 이는 각각 1차원, 2차원, 3차원의 CNN을 구현한다.<br>
conv1d와 conv2d는 이동방식에서 차이를 보이는데 1d에서 kerenl은 수직으로만 이동하는 한편, 2d에서는 수직, 수평으로 이동한다.<br><br>

CNN에 대한 실습 내용은 <a href = "https://github.com/bbjoite09/NLP/blob/main/Practice/4.1%20cnn.ipynb">여기</a>에서 확인할 수 있다.<br><br>
</details>

<details><summary><b>4.2 Activation</b></summary><br>
  activation function에 대하여 학습한다.<br><br>
  
  - sigmoid : 일정 값을 기준으로 0/ 1을 구분한다. 이는 함수의 중심이 0이 아니며 gradient vanishing 현상이 발생한다는 단점이 있다.(최근에는 잘 사용하지 않음) 그래프 개형은 아래와 같다.
  <p align="center"><img src = "Data/images/sigmoid.PNG" alt="sigmoid"></p>
  
  - tanh : sigmoid의 중심 값 문제를 해결. 중심 값을 0으로 옮겨 최적화 과정의 비효율을 줄였으나, 여전히 gradient vanishing 현상이 발생한다는 단점이 있다. 그래프 개형은 아래와 같다.
  <p align="center"><img src = "Data/images/tanh.PNG" alt="tanh"></p>
  
  - relu : 0보다 작은 값이 나온 경우 0을 반환하고, 0보다 큰 값이 나온 경우 그 값을 그대로 반환한다. 이는 위 두가지 방법에 비해 빠르고 구현이 간단하다는 장점이 있으나, 값이 음수인 경우 dying relu현상이 발생할 수 있다는 단점이 있다. 그래프 개형은 아래와 같다.
  <p align="center"><img src = "Data/images/relu.PNG" alt="relu"></p>
  
  - relu6 : 기존 relu의 상한 값을 6으로 두는 것을 말한다. 그래프 개형은 아래와 같다.
  <p align="center"><img src = "Data/images/relu6.PNG" alt="relu6"></p>
  
  - gelu : relu의 상위 방식으로 확률론적으로 보았을 때 가장 효율이 좋다. 그래프 개형은 아래와 같다.
  <p align="center"><img src = "Data/images/gelu.PNG" alt="gelu"></p> <br><br>
  
  해당 실습에 대한 내용은 <a href = "https://github.com/bbjoite09/NLP/blob/main/Practice/4.2%20activation.ipynb">여기</a>에서 확인할 수 있다.<br><br>
  
</details>

<details><summary><b>4.3 RNN</b></summary><br>
  RNN(Recurrent Neural Network)에 대하여 학습한다.<br>
  RNN은 sequential data를 처리하기에 적합한 데이터 이다. 이는 hidden layer의 노드에서 activation function 을 통해 나온 결과를 output layer와, hidden layer 노드의 다음 계산의 input으로 보낸다. 다른 feed forward neural network 와 다르다는 것을 확인할 수 있다.<br><br>
  이는 길이에 상관 없으나, 순서대로 처리해야 하므로 속도가 느리다는 단점이 있다. 순차처리라는 특징때문에 오랜 과거의 정보에 대한 접근이 어렵다는 단점이 있다. 또한 vanishing gradient 현상과 exploding gradient 현상이 발생한다.<br><br><br>
  
  - LSTM(Long-Short Term Memory) : RNN의 vanishing gradient 문제를 해결하기 위한 모델이다. memory cell을 추가하여 RNN에서 장기간 메모리의 필요성에 대한 문제를 해결하였다. 이는 RNN에 비해 더 긴 정보를 잘 처리한다는 장점이 있다.
  - GRU(Gated Recurrent Unit) : Memory cell을 사용하지 않으며 gate 숫자를 2개로 줄인 모델이다. 이는 LSTM 보다 단순한 구조임에도 불구하고 긴 데이터를 잘 처리한다는 장점이 있다. <br><br>
  
  해당 내용에 대한 실습은 <a href = "https://github.com/bbjoite09/NLP/blob/main/Practice/4.3%20rnn.ipynb">여기</a>에서 확인할 수 있다.<br><br>
</details>

<details><summary><b>📝 4.4 simple project with RNN & CNN</b></summary><br>
Day1에서 진행하였던 simple word project와 simple sentence project에 대하여 CNN과 RNN을 적절히 추가하여 프로젝트를 변경해본다.<br>
해당 실습 관련 내용은 <a href = "htt</details>ps://github.com/bbjoite09/NLP/blob/main/Practice/4.4%20simple%20project%20with%20rnn_cnn.ipynb">여기</a>에서 확인할 수 있다.<br><br>
</details>

## ✨ Day 5
<details><summary><b>5.1 text classification</b></summary><br>
</details>

<details><summary><b>📝 5.2 text classification</b></summary><br>
</details>

## ✨ Day 6
<details><summary><b> 6.1 text similarity</b></summary><br>
</details>

<details><summary><b>📝 6.2 text similarity with RNN or CNN</b></summary><br>
  6.1 Text similarity 프로젝트에 RNN 또는 CNN 모델을 추가하여 결과의 변화를 살펴본다.<br>
  해당 실습에 대한 내용은 <a href = "https://github.com/bbjoite09/NLP/blob/main/Practice/6.2%20text%20similarity%20with%20RNN%20and%20CNN.ipynb">여기</a>에서 확인할 수 있다.<br><br>
</details>

<details><summary><b>✔️ 6.3 text similarity more accuracy</b></summary><br>
  Text similarity 프로젝트 결과물의 정확도를 향상시킬 수 있는 방법에 대하여 학습하였다.<br>
  해당 내용은 <a href = "https://github.com/bbjoite09/NLP/blob/main/Practice/6.3%20text%20similarity%20more%20accuracy.ipynb">여기</a>에서 확인할 수 있다.<br><br>
</details>

## ✨ Day 7
<details><summary><b>7.1 Language model</b></summary><br>
</details>

<details><summary><b>📝 7.2 Language model hw1 & language model hw2</b></summary><br>
  
  7.1을 직접 학습시켜본다.<br>
  실습결과는 <a href = "https://github.com/bbjoite09/NLP/blob/main/Practice/7.2%20language%20model%20hw1.ipynb">HW1</a> 또는 <a href = "https://github.com/bbjoite09/NLP/blob/main/Practice/7.3%20language%20model%20hw2.ipynb">HW2</a>에서 확인할 수 있다.<br><br>
</details>

## ✨ Day 8 & Day 9
<details><summary><b>8.1 machine translation</b></summary><br>
</details>

<details><summary><b>8.2 machine translation</b></summary><br>
  8.1을 직접 학습시켜본다.<br>
  실습결과는 <a href = "">여기</a>에서 확인할 수 있다.<br><br>
</details>
<br>
