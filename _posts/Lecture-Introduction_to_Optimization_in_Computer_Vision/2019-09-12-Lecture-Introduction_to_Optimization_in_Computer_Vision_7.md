---
layout: post
title: WEEK 3 - Linear programming & Nonlinear programming - equality constraints
comments: true
categories : [Lecture/Introduction_to_Optimization_in_Computer_Vision]
tags: [Optimization]
---

<br><br>
* Constrained Optimization
	* Feasible set이 일반 실수 공간이 아니라 다음과 같이 특정 제한 조건을 만족해야하는 경우
	* <img src="https://drive.google.com/uc?export=view&id=1iBu5KNzj_Z8kA8eAmoKumrQCZrmpqU0u" width="80%">
	* 목적함수, 제약조건 모두 linear인 경우 Linear 문제이고 둘 중 하나라도 linear가 아닌 경우 <point>Nonlinear</point> 문제임
	* 이 강좌에서는 Nonlinear 경우에 집중함

<br><br>
* Method of Lagrange Multiplier
	* Equality constraint가 있을 때 optimization problem은 다음과 같음
	* <img src="https://drive.google.com/uc?export=view&id=1AOWVlKbTUTD-Ac1w06wYR10aoe5Tp1Rh" width="30%">
	* Lagrangian을 다음과 같이 정의할 수 있음
	* <img src="https://drive.google.com/uc?export=view&id=1ZmW5MdSnlDJ8iLZb6MyWFcnXFR6SYbP5" width="30%">
	* Lagrangin이 다음과 같은 <point>3가지 조건</point>을 만족하면 constraint를 만족하면서 목적 함수를 최대/최소화하는 해를 구할 수 있음
	* <img src="https://drive.google.com/uc?export=view&id=1fclpmeFXSehcZ8Q_qd55-F2fGKTwhoOx" width="80%">
	* 첫 번째 조건, 두 번째 조건은 Lagrangian의 <point>staionary point</point>에 대한 조건
		* 첫 번째 조건을 자세히 보면 목적함수와 제약함수가 서로 <point>접하는 것</point>을 의미함. 두 함수가 접할 때 최대/최소 지점이 발생하게 됨
		* 두 번째 조건은 <point>equality constraint</point>를 만족하게 되는 조건임. 첫 번째 조건에서 접하는 방향에 대한 방향 벡터들이 나오게 되면 그 방향 벡터 위에 있으면서 두 번째 조건인 equality constraint를 만족시키는 점들을 찾게 됨
	* 앞서 만족한 조건에 따라 Lagrangin은 해당 지점에서 극대, 극소, 안장점을 가지게 되는데 우리가 원하는 것은 최솟값이므로 세 번째 조건인 Lagrangian의 Hessian 행렬이 <point>positive semidefinite</point>이 되도록 해야함.
	* Lagrangin이 quadratic이 아니더라도 첫 번째, 두 번째 조건을 만족하면서 local minimum, maximum이 존재하는 점에서 Taylor 2차 근사를 해서 그 방향성을 보고 local minimum, local maxmimum 여부를 파악한다고 보면 됨

<br><br>
* Method of Lagrange Multiplier example
	* 다음과 같이 목적 함수와 제약 조건이 주어졌다고 하자
	* <img src="https://drive.google.com/uc?export=view&id=1zOkF9zOKnEiKR9Of-q6SKHlGCAFfZ0wk" width="60%">
	* Lagrangin으로 만든 뒤, 첫 번째 조건을 만족시키기 위해 gradient를 그리면 다음과 같음.
	* <img src="https://drive.google.com/uc?export=view&id=1mP-170cXnLLdEy-j2lcSz3i_upx_AkgU" width="60%">
	* 제약 조건 $$h(x)=0$$의 경우 수학적으로 $$-h(x)=0$$과 동일함. 따라서 안쪽으로 향하는 gradient도 고려가 됨. $$x^2+y^2=k$$는 원점을 기준으로 방사형으로 커지는 그릇을 형태이므로 gradient가 밖을 향하게 됨. $$x^2+y^2=k$$ 양변에 (-)를 곱해주면 그릇을 뒤집게 되므로 gradient가 안을 향하게 됨. 여기선 k가 상수가 되므로 둘 중 하나로 고정할 수 없게 됨. 따라서 gradient가 양방향이 됨.
	* <img src="https://drive.google.com/uc?export=view&id=1JOL9grtwL6_ZGAvS_IJd0wOK_xNPL4_d" width="80%">
	* 따라서 첫 번째 조건의 기하학적 의미는 다음과 같이 gradient가 <point>parallel</point>한 지점에서 local optimum이 존재한다는 것임
	* 극소점을 찾기 위해 Lagrangian의 Hessian 행렬이 positive semidefinite인지 찾으면 됨
	* <img src="https://drive.google.com/uc?export=view&id=1eDXePaceAl_kudTiI9UZrYupen3LBXUE" width="50%">

<br><br>
>  <subtitle>reference</subtitle>
* https://www.edwith.org/optimization2017