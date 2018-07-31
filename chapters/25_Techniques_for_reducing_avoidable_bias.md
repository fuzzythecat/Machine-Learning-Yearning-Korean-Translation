## 25 Techniques for reducing avoidable bias

개발한 학습 알고리즘이 높은 "피할 수 있는" 편향으로 부터 고통받고 있다면, 다음과 같은 기법을 시도해 볼 수 있겠다:

- 모델 크기를 증가 시키는 것 (뉴런/레이어의 수): 이 기법은 알고리즘이 학습 데이터셋에 더 잘 맞아들어가게 해 주기 때문에, 편향치를 줄여준다. 이 기법이 분산치를 증가시키게 되는 경우, 정규화 기법을 사용해 보자. 정규화 기법은 보통 분산치 증가를 제거해 준다.

- 에러 분석으로 부터 얻은 통찰력에 기반한 입력 feature를 변경하는 것: 에러를 분석한 내용이 알고리즘의 특정 에러 카테고리를 제거하는데 도움을 주는 추가적인 feature를 생성하는 것에 대하여 어떤 영감을 주었다고 가정해 보자 (더 많은 내용을 다음 챕터에서 다룰 것이다). 이 새로이 정의된 feature는 편향과 분산 모두에게 도움이 될 수도 있다. 이론적으로, 더 많은 feature를 추가하면 분산치가 증가하게 된다; 하지만, 이 경우에는 정규화 방법을 사용해서 분산치 증가를 제거해 나갈 수 있다. 

- L2, L1, 또는 Dropout과 같은 정규화 기법의 사용을 제거하거나 줄이는 것: 이 방법은 "피할 수 있는" 편향을 줄이는데 도움을 주지만, 분산치를 증가시키게 된다. 

- 모델의 설계 구조를 변경하여 주어진 문제에 더 적합하도록 만드는 것: 이 기법은 분산과 편향 모두에게 영향을 끼칠 수 있다.

그다지 도움이 되지 않는 한가지 방법:

- 더 많은 학습 데이터를 추가하는 것: 이 기법은 분산 문제에 대해서는 도움을 줄 수 있지만, 일반적으로 편향 문제에 대해서는 큰 영향이 없다.