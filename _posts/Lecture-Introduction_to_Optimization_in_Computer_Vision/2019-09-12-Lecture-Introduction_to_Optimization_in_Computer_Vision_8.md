---
layout: post
title: WEEK 3 - Nonlinear programming - inequality constraints
comments: true
categories : [Lecture/Introduction_to_Optimization_in_Computer_Vision]
tags: [Optimization]
---

<br><br>
* Lagrangian Dual Problem
	* Inequality constraint가 있는 continuous optimization 문제를 풀 때 사용함
	* P와 같이 목적 함수와 constraint로 이뤄진 본연의 형태를 갖추고 있는 식을 <point>primal problem</point>이라고 함
	* Primal problem에 대응되는 형태를 <point>dual problem</point>이라고 함
	* Dual problem은 Lagrangian function에서 x에 대한 minimum 형태 식에 대해 Lagrangian multiplier에 대한 maxmium을 취한 형태로 만들어짐
	* <img src="https://drive.google.com/uc?export=view&id=15Y5bPbTWf0yvXjTOI9NQCt_HvNuAsik3" width="60%">
	* Dual function $$L^*(u)$$는 concave function이라는 것을 다음과 같이 증명할 수 있음
	* <img src="https://drive.google.com/uc?export=view&id=1L4lmqGZ4-Kc4KEeWF1WP-PscRV4rHTqs" width="60%">
	* 따라서 Dual function은 <point>concave maximization problem</point>이 됨

<br><br>
* Concave function
	* concave function은 concate 성질을 표현하는 수식의 등호가 성립하는지에 따라 <point>concave, strictly concate</point>로 나뉨. 등호가 성립한다는 것은 두 점 사이를 잇는 직선과 function의 실제 값들이 맞닿는 지점이 있다는 것으로 function이 곡선이 아닌 직선으로 표현되는 지점이 있다고 볼 수 있음. 이럴경우 global minimum이 유일하지 않고 여러개가 될 수 있음
	* <img src="https://drive.google.com/uc?export=view&id=1fZy47XsO7SKSo_Jo3s_p0_b7yCvw__Ec" width="30%">

<br><br>
* KKT Conditions
	* 예를 들어 다음과 같이 inequality constraint를 가진 continuous optimization 문제를 생각해보자
	* <img src="https://drive.google.com/uc?export=view&id=1ALhpsBSvIUGbeXqOqms3pMo05ywenl8C" width="60%">
	* Constrained local minimum은 목적 함수 gradient의 반대 방향과 constraint의 gradient가 parallel할 때 발생하게 됨. 하지만 여기서는 equality constraint와 다르게 $$\lambda$$가 양수라는 조건이 붙게 되는데 이는 constraint가 0보다 작다는 조건 자체가 constraint function 내부는 contour보다 작다는 것을 내포하고 있으므로 gradient는 밖을 향해야된다는 제약이 생기기 때문임.
	* <img src="https://drive.google.com/uc?export=view&id=1AkjoVz62hk62YMn7lh_nM03izY5mpse-" width="60%">
	* 만약 제약 조건을 만족하는 local minimum이 존재한다면 다음과 같은 두 가지 케이스로 분류할 수 있음. Case 2는 앞에서 예시로 본 경우로 local minimum이 feasible region 밖에 존재하는 경우임. 각 case에 대해 local minimum이 충족하는 조건들을 나열하면 각각 3가지씩 생김
	* <img src="https://drive.google.com/uc?export=view&id=1X_Dk5WgcL-m7hFkeBUIjaksoTcYGiWYH" width="70%">
	* 2가지 case들에 대해 local minimum이 만족해야하는 조건들을 병합하면 다음과 같이 <point>KKT conditions</point>가 나오게 됨. 여기서 2번 조건이 $$\lambda$$가 0 이상으로 앞에서 봤던 0보다 커야한다는 조건과 다름. 이는 case 1에서 1번 조건이 $$g(x^*) < 0$$이므로 0이 되기 위해선 $$\lambda=0$$이어야하기 때문임.
	* <img src="https://drive.google.com/uc?export=view&id=1pJaHP4tn5yuo5PYUf5suwVLPTqA5m0IR" width="40%">
	* Inequality, equality constraints를 모두 고려해서 KKT conditions를 만들면 다음과 같음. Inequality constraint가 local minimum에서는 0이 돼야한다는 조건이 추가됨.
	* <img src="https://drive.google.com/uc?export=view&id=1-qTQoLy-aeQnE4E-7t7BIjm0FjIq8dlj" width="70%">
	* KKT conditions는 $$x^*$$라는 local minimum이 존재할 경우 <point>필요조건</point>임. <point>충분조건</point>이 되기 위해서는 <point>convexity</point>를 충족해야함. 본래 convex 문제라면 상관없지만 아닌 경우 convex로 문제를 치환하는 것을 고려해볼 수 있음. 하지만 이것도 어려울 경우 steepest gradient method 등의 방식으로 local minimum을 찾는 것이 최선일 수도 있음. 

<br><br>
>  <subtitle>reference</subtitle>
* https://www.edwith.org/optimization2017