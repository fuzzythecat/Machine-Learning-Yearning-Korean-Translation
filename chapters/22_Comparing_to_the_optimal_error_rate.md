## 22 Comparing to the optimal error rate

앞서 언급되어온 고양이 분류 알고리즘의 예제에서, "최적의" 알고리즘이 얻을 수 있는 "이상적인" 에러율은 거의 0%에 가깝다고 할 수 있다. 사진을 바라보는 사람은 항상, 그 사진에 고양이가 있는지 알아낼 수 있을 것이다. 그러므로, 우리는 우리가 개발하는 기계가 그만큼의 일을 할 수 있기를 바랄 수 있다.

하지만, 다른 문제는 더 복잡할 수 있다. 예를 들어서, 음성 인식 시스템을 구축한다고 가정해 보자. 그리고 전체 오디오 클립의 14%가 시끄러운 배경음을 가지고 있으며, 사람 조차도 그게 무슨 음성인지 이해할 수 없다고 가정해 보자. 이 경우에, 가장 "최적의" 음성 인식 시스템 조차도 14% 수준의 에러율을 가지게 될 수 있다.

이 음성인식 문제에 대해서, 알고리즘의 결과가 다음과 같다고 가정해 보자:

- 학습 (데이터셋에 대한) 에러율 = 15%
- 개발 (데이터셋에 대한) 에러율 = 30%

학습 데이터셋에 대한 성능이 이미 14%라는 최적의 에러율에 가깝다. 그러므로, 학습 데이터셋에 대한 성능 향상 또는 "편향"의 성능 향상을 하기 위한 여지가 별로 없다. 그러나, 이 알고리즘은 개발 데이터셋에 대하여 낮은 일반화정도를 보여준다. 그러므로, "분산"으로 인한 에러의 성능향상을 위한 여지는 꽤나 존재한다고 볼 수 있다.

이 예제는 앞 챕터의 (마찬가지로 학습 에러율=15%, 개발 에러율=30% 였던)세번째 예제 와 비슷하다. 만약 최적의 에러율이 거의 ~0% 라면, 학습 데이터셋에 대한 에러율이 성능 향상을 위한 큰 여지를 보여준다고 볼 수 있다. 이 상황은 "편향"을 줄이는 것이 꽤나 생산적임을 시사한다. 하지만, 만약 최적의 에러율이 14% 라면, 동일한 학습용 데이터셋에 대한 성능이 분류 알고리즘의 "편향"에 대한 성능 향상을 위한 아주 작은 여지만이 있음을 알 수 있게 해준다.

최적의 에러율이 0과는 거리가 먼 문제에 대해서, 알고리즘의 에러를 좀더 세분화 하여 바라볼 수 있다. 음성 인식 예제에 대해서 계속해서 언급해 보자. 전체 개발 데이터셋에 대한 에러율 30%는 다음과 같이 세분화 될 수 있다 (비슷한 분석이 테스트 개발셋에 대한 에러에도 적용될 수 있다):

- 최적의 에러율 ("피할 수 없는 편향"): 14%. 세상 천지를 통틀어, 얻을 수 있는 최고의 음성인식 시스템이라 할지라도 14%의 에러로 부터 고통 받고 있다고 가정해 보자. 이를 학습 알고리즘의 "편향" 중에서 "피할 수 없는" 부분이라고 생각해 볼 수 있다.

- 피할 수 있는 편향: 1%. 학습 데이터셋에 대한 에러율과 최적의 에러율의 차이로부터 계산 되었다.

> 만약 이 수치가 음수라면, 학습용 데이터셋에 대한 성능이 최적의 에러율 보다 더 좋다고 볼 수 있다. 이것은 학습용 데이터셋에 대해서는 과적합 되었고, 알고리즘이 학습용 데이터셋을 너무 과하게 기억하고 있음을 의미한다. "편향"을 더 줄이는 방법 보다는 "분산"을 줄이는 방법에 초점을 맞추어야 한다.

- 분산: 15%. 개발 데이터셋에 대한 에러율과 학습용 데이터셋에 대한 에러율의 차이로 부터 계산 되었다.

앞의 정의들에 연관지어 볼때, "편향"과 "피할 수 없는 편향"은 다음과 연관이 있다.

- 편향 = 최적의 에러율("피할 수 없는 편향") + 피할 수 있는 편향

> 앞서 정의된 정의들 ("편향" 과 "분산"에 대한)은 알고리즘을 어떻게 향상시킬지에 대한 통찰략을 획득할 수 있기 위해 선택되었다. 이 정의들은 통계학자들이 정의하는 "편향"과 "분산"과는 사뭇 다르다. 기술적으로 말해서, 여기서 내가 "편향"이라고 정의한 것은 "편향 때문에 발생하는 에러"라고 불려야 하고, "피할 수 없는 편향"은 "최적의 에러율보다 높은 학습 알고리즘의 편향 때문에 발생하는 에러" 라고 불려야 할 것이다.

"피할수 있는 편향"은 알고리즘이 얼마나 "최적의 분류 알고리즘"에 비해서, 학습 데이터셋에 대하여 잘 못 동작하는지를 나타낸다.

"분산"의 컨셉은 이전과 동일하게 유지된다. 이론적으로, 엄청나게 많은 학습용 데이터를 학습 시킴으로써, "분산"의 값을 거의 0에 가깝도록 줄이는 것이 가능하다. 따라서, 모든 분산은 충분히 큰 데이터만 있다면, "피할 수 있는" 문제이고 "피할 수 없는 분산"과 같은 문제는 존재하지 않는다.

최적의 에러율이 14%인 한가지의 예제를 더 생각해 보자. 이때 다음과 같은 성능을 알고리즘이 보여준다:

- 학습 (데이터셋에 대한) 에러율 = 15%
- 개발 (데이터셋에 대한) 에러율 = 16%

앞 챕터에서 이와 비슷한 상황에 대하여 높은 "편향"을 가지는 분류 알고리즘이라고 이야기 한 것과는 다르게, "피할 수 있는 편향"이 1%, 분산에 대한 에러율은 1%라고 말할 수 있다. 따라서, 알고리즘은 성능 향상을 위한 아주 작은 여지를 가지고는 있지만, 꽤나 잘 작동하고 있다. 최적의 에러율에 비해서 단지 2%의 낮은 성능을 보여준다.

이 예제로 부터 최적의 에러율이 우리의 다음 진행 방향을 개척하는데 도움을 준다는 것을 알 수 있다. 통계학에서, 최적의 에러율은 "베이즈 에러율" 또는 "베이즈 에러" 라고도 불린다.

그러면, 최적의 에러율은 어떻게 알 수 있을까? 사진을 분별해 내거나 오디오 클립을 기록하는등과 같은 작업에 대해서,최적의 결과는 사람들이 합리적으로 잘 얻을 수 있으므로, 사람들에게 레이블을 만들 것을 요청할 수 있다. 그리고 이것을 학습용 데이터셋과 연관지어 사람의 레이블에 대한 정확도를 측정할 수 있다. 이 과정이 최적의 에러율을 측적할 수 있게 해 줄 것이다. 만약, 사람조차 해결하기 어려운 문제(어떤 영화를 추천할까? 사용자에게 어떤 광고를 보여줄까? 같은)에 대해서 고심하고 있다면, 최적의 에러율을 측정하는 것은 어려운 일이다.

"사람-수준의 성능과 비교하는 것"을 다루는 (챕터 33 에서 35까지) 섹션에서, 학습 알고리즘의 성능을 사람-수준의 성능과 비교하는 과정을 좀 더 상세하게 다룰 것이다.

이때까지 앞의 몇가지 챕터를 통하여, 학습용 데이터셋과 개발 데이터셋에 대한 에러율을 가지로, 어떻게 "피할 수 있는 편향"/"피할 수 없는 편향"과 분향을 측정하는지를 배웠다. 다음 챕터는 이러한 분석으로 부터 얻은 통찰력을 가지고, 어떻게 "분산"을 줄이는 기법의 사용용 "편향"을 줄이는 기법의 사용의 우선순위를 정하는 지에 대하여 이야기 할 것이다. 프로젝트가 떠안고 있는 분제가 높은 "분산"이냐 높은 "피할 수 있는 편향"이냐에 따라서 적용 가능한 기법들이 다양하게 존재한다. 계속 읽어 보자!