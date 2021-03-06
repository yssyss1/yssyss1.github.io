---
layout: post
title: WEEK 2 - Foundations
comments: true
categories : [Lecture/Introduction_to_Optimization_in_Computer_Vision]
tags: [Optimization]
---

<br><br>
* Infimum and supremum
	* 약간의 차이가 있지만 기본적으로 <point>infimum은 minumum</point> 그리고 <point>supremum은 maximum</point>에 대응함
	* 대응될 뿐 같지는 않음
	* <center><img src="https://user-images.githubusercontent.com/37978259/64762568-57a98f80-d579-11e9-9e1a-cf12b46bc63c.png" width="35%" height="35%"></center>
	* 위 예시에서 sumpremum은 0이지만 maximum은 존재하지 않음

<br><br>
* Level sets and gradients
	* <center><img src="https://user-images.githubusercontent.com/37978259/64763822-c4be2480-d57b-11e9-909b-810b2672ca43.png" width="50%" height="50%"></center>
	* Level sets: Level이 같은 $$x$$ 집합 $$S$$
	* 특정 Level에서 자르면 Curve $$g(t)$$가 만들어짐
	* $$f(x, y)=c$$라고 하면, $$g(t)$$ -> $$(x, y)$$에 대응함
	* $$f(g(t)) = c$$를 t에 대해서 미분하면 $$g(t)$$의 tangent 벡터와 $$f(x, y)$$의 gradient는 서로 <point>직교</point>한다는 성질 유도 가능

<br><br>
* Taylor series
	* <center><img src="https://user-images.githubusercontent.com/37978259/64764963-2ed7c900-d57e-11e9-903b-5938d815fa73.png" width="50%" height="50%"></center>
	* 특정 점에서 주변 값들을 알고 싶을 때 고차 미분항까지 구할수록 더욱 먼 지점에서 값도 비슷하게 구할 수 있음
	* 하지만 고차 미분항을 구하기 위해선 계산량이 늘어나므로 <point>정확도</point>와 <point>계산량</point> 사이에서 trade off

<br><br>
* Positive Semidefinite
	* 1차원인 경우 2차 함수가 convex, concave 중 어디에 속하는지는 2차항의 계수 부호를 보면 쉽게 알 수 있음
	* 하지만 다차원 Quadratic form인 경우 쉽게 판단이 불가능 - 행렬이 양수인지 음수인지 쉽사리 말하기 어려움
	* 다차원 Qudratic form인 경우 각 차원의 미분값이 0이 되는 지점(Stationary Point)은 극소, 극대, 안장점(Saddle Point) 모두 가능함
	* 극소, 극대, 안장점에 대한 <point>기준</point>을 제공해주는 것이 <point>Positive Definite</point>임 
	* Positive Definite이 되는 조건 중 하나는 $$x^TQx$$ > 0으로 이때 극소점을 가지고 반대인 경우 Negative Definite임
	* $$x^TQx$$ >= 0인 경우 <point>positive semidefinite</point>라고 정의하고 <point>convex quadratic problem</point>임
	* <center><img src="https://user-images.githubusercontent.com/37978259/64767743-38176480-d583-11e9-9b13-c5594edb8d54.png" width="50%" height="50%"></center>

<br><br>
* Categorization
* <center><img src="https://user-images.githubusercontent.com/37978259/64768014-b8d66080-d583-11e9-8cbd-3c8e3cf71523.png" width="50%" height="50%"></center>

<br><br>
>  <subtitle>reference</subtitle>
* https://www.edwith.org/optimization2017
* http://mlwiki.org/index.php/Positive-Definite_Matrices
* https://bskyvision.com/205