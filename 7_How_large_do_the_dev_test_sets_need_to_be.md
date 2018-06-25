## 7 How large do the dev/test sets need to be?

개발 데이터셋은 시도하는 여러개의 알고리즘의 다른점을 구분짓기에 충분할 만큼 커야 한다. 예를 들어서, A라는 분류기가 90.0% 만큼의 정확도를 가지고, B라는 분류기가 90.1% 만큼의 정확도를 가진다면, 100개로 구성된 개발 데이터셋은 이 0.1%라는 차이를 감지하지 못할 수도 있다. 내가 경험해본 다른 머신러닝 문제와 비교해 보면, 개발 데이터셋이 100개로 구성된다는 것은 "작다" 라고 말하고 싶다. 개발 데이터셋을 일반적으로 1,000 ~ 10,000 개의 데이터로 구성된다. 10,000 개의 데이터로, 0.1%의 성능 향상을 감지할 수 있는 기회를 얻을 수 있다.

광고, 웹 검색, 제품 추천과 같은 성숙도가 있고, 아주 중요한 어플리케이션은 0.01% 만큼의 작은 성능 향상이라도 얻어 내는 것이 중요한 동기부여이고 결과이다. 이 정도의 성능 향상도 그 회사의 이익 창출에 직접적으로 큰 영향을 미치기 때문이다. 이런 경우에, 더욱더 작은 수준의 향상을 감지하기 위해서 개발 데이터셋의 크기는 10,000개보다 훨씬 커져야 한다.

그렇다면, 테스트 데이터셋의 크기는 어떤가? 구축하는 시스템의 전체적인 성능에 대하여 높은 신뢰를 보여줄 수 있을 정도면 된다. 한가지 인기 있는 방법으로는 전체 데이터의 30%를 사용 하는 것이다. 100 ~ 10,000개 수준의 데이터가 있다면, 이 방법이 잘 동작할 수 있다. 하지만, 백만개의 데이터가 넘는 데이터를 다루는 머신러닝이 사용되는 빅 데이터의 시대에서, 개발 / 테스트 데이터셋에 할당된 데이터의 지분(율) 은 점점 작아지고 있다 (하지만, 절대적인 데이터의 수는 증가한다). 알고리즘의 성능을 평가하는데 개발/테스트 데이터셋을 위해서, 터무니 없이 거대한양의 데이터는 필요 없다.