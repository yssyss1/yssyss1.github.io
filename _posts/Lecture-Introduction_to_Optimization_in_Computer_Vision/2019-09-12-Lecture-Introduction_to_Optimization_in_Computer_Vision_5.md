---
layout: post
title: WEEK 2 - Unconstrained optimization (1)
comments: true
categories : [Lecture/Introduction_to_Optimization_in_Computer_Vision]
tags: [Optimization]
---

<br><br>
* Iterative multidimensional optimization
	* 대부분의 비용함수는 깔끔하게 convex 형태를 지니고 있지 않고 <point>비정형화된 모형</point>을 가지고 있음
	* 비정형화된 비용함수 모형을 최적화하기 위해서는 $$f(x)$$ 모형에 <point>의존적이지 않은 방법</point>이 필요함
	* Analytically 구하기 힘들고 <point>Iterative</point>하게 구하는 방식을 사용함
	* 이러한 방법들은 상대적으로 minimum에 도달하기 까지 상대적으로 오래걸리고 찾아낸 minimum이 global minimum이라는 것을 보장해주지 않음
	* Iterative하게 구하는 방식은 크게 두 가지 steps로 구성됨
		* 비용함수가 작아지는 방향 $$d^k$$ 구하기
		* 비용함수가 작아지는 방향으로 업데이트 하기
			* $$x^{k+1} = x^k + {\alpha}^kd^k$$
	* <center><img src="https://drive.google.com/uc?export=view&id=1oZW5MI3rLpzYzSr32tXUmDna4tCK5IKi"></center>

<br><br>
* Line Search
	* 일단 search 방향이 결정되면 1차원 함수 상에서 minimum 값을 구하는 것임
	* 1차원 함수에서 minimum을 구하는 방법에는 Golden section search, Fibonacci search, Newton's method 등이 있음
	* Newton's method는 Talyor series를 이용한 2차 근사를 사용하는 방법으로 뒤에 나옴
	* Golden section search란 다음과 같은 순서로 진행됨
		1. 시작점 a에서 멀리 떨어진 지점에 d를 잡음
		2. a, d 사이에 b, c를 잡음
		3. $$f(b)$$, $$f(c)$$를 비교해서 f(b)가 f(c) 보다 크다면 a를 b 지점으로 옮겨서 1번 부터 다시 반복함
			4. $$f(c$$)가 $$f(b)$$ 보다 더 크다면 d를 c로 옮김
		* <img src="https://drive.google.com/uc?export=view&id=16OOutsENuhv3fYnCo2F4djbu6dz87uTV">

<br><br>
* Steepest descent method
	* 1차 미분을 사용하는 가장 기본적인 방식
	* <img src="https://drive.google.com/uc?export=view&id=1CX4kV89ci09Tl8kGVHiawjXXWmbBzR5H" width="70%">
	* 하지만 gradient는 해당 점에서의 tanget 벡터와 <point>직교</point>한다는 특성을 가지고 있어서 다음과 같이 비효율적으로 minimum을 향해 움직이게 됨
	* <img src="https://drive.google.com/uc?export=view&id=1_9J_XGzh6AHGuLYbJhilZIWJ9OIbNxw1" width="40%">

<br><br>
* Conjugate gradient method
	* <img src="https://drive.google.com/uc?export=view&id=1WA411BQ7pnIwbusyjrnEId_sntLjOWnl" width="40%">
	* 위 그림과 같이 선형 변환 $$G$$에 의해 원이 타원이 되었다고 할 때 타원과 $$d^{'}_1$$ 벡터가 접하는 점에서 gradient를 구하게 되면 직교하게 됨
	* 직교하는 벡터가 아닌 선형 변환 이전에 minimum으로 향하는 벡터의 선형 변환된 형태인 $$d^{'}_2$$을 구할 수 있다면 타원에서 바로 minimum으로 향하는 벡터를 구할 수 있음
	* 원을 타원으로 변환하는 것은 quadratic form에서 Q 행렬의 역활이고 이러한 관계를 $$d^{'}_1$$와 $$d^{'}_2$$는 <point>Q_conjugated</point> 됐다고 함
	* <img src="https://drive.google.com/uc?export=view&id=1p1Lv6FwdC9_nIh8Toml3a4LlG1xdvrlE" width="40%">
	* 이전의 방향 벡터($$d^{(k)}$$)와 Q_conjugated된 방향을 구할 때 밑바닥부터 구하는 방식이 아니라 이전의 방향 벡터와 접하는 지점($$x^{(k+1)}$$)에서 gradient를 구한 뒤에 gradient와 이전의 방향 벡터의 선형 결합을 위한 변수 $$\beta_k$$를 구해서 이전의 방향 벡터와 Q_conjugated된 새로운 방향 벡터($$d^{(k+1)}$$)를 구하게 됨
	* 대부분의 목적 함수는 quadratic form이 아니므로 <point>taylor 2차 근사</point>를 통해서 Q 행렬을 구하게 됨
	* <center><img src="https://drive.google.com/uc?export=view&id=1IA5d1bgYopWnWTm_zCPzWg7x_rd5eMhd" width="40%"></center>


<br><br>
>  <subtitle>reference</subtitle>
* https://www.edwith.org/optimization2017