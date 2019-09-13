---
layout: post
title: WEEK 2 - Unconstrained optimization (2)
comments: true
categories : [Lecture/Introduction_to_Optimization_in_Computer_Vision]
tags: [Optimization]
---

<br><br>
* Newton's method
	* 주어진 점에서 Taylor 2차 근사를 통해 2차 함수를 만들어내면 해당 함수에서 minimum 또는 maxmimum은 analytical하게 구할 수 있음
	* 지그재그로 움직이는 steepest gradient descent와 달리 주어진 점에서는 가장 최저점으로 <point>jump</point>하다보니 수렴 속도가 빨라짐
	* <img src="https://drive.google.com/uc?export=view&id=1yqbP2IvD53VLrYcLFPAJsNkIBAmx3Yc3" width="40%">
	* 근사시킨 2차 함수에서 미분이 0이 되는 지점을 기준으로 다음과 같이 update함
	* <img src="https://drive.google.com/uc?export=view&id=1GhuhaN5lgP_lG_sq2S3OGciGo5Ec0LVb" width="30%">
	* Steepest gradient descent와 달리 step size가 없고 quadratic form의 2차 항에 대한 행렬 $$H$$의 역행렬이 step size 부분에 들어가 있음. 행렬 $$H$$를 <point>Hessian 행렬</point>이라고 함.
	* 하지만 2차 근사 함수와 실제 목적 함수의 형태가 달라서 2차 함수의 최저점이 실제 목적 함수에서는 오히려 높은 구간에 해당할 수 있고 이런 경우를 막기 위해 step size를 넣어서 line search를 하는 변형된 형태를 가지기도 함

<br><br>
* Newton's method drawback
	* 차원이 높아질수록 헤시안 행렬과 역행렬을 구하는 <point>computation cost</point>가 너무 큼
		* => 헤시안 행렬의 역행렬을 근사적으로 구하는 <point>Quasi-Newton method</point>를 사용함
	* 헤시안 행렬이 <point>postive definite</point>이 아닐 경우 목적 함수가 감소하는 방향이 아닐수도 있음
		* => positive definite이 되기 위해선 헤시안 행렬의 eigen value가 모두 양수가 되야하므로 헤시안 행렬에 $$\mu_K I$$를 더해서 eigen value가 양수가 되도록 강제하는 <point>Lavenberg-Marquardt(LM) modification</point>을 사용함
		* <img src="https://drive.google.com/uc?export=view&id=1YpqgLWo5NDIJgvFk_2MzVA7YJ3hU0TdC" width="80%">

<br><br>
* Newton's Method for Nonlinear Least Square problems
	* 다음과 같은 형태의 목적함수에는 Gauss-Newton's method를 적용할 수 있음
	* <img src="https://drive.google.com/uc?export=view&id=1XxEgIMIPb35zZCaNpXXpnGe4gwgNnB8Y" width="80%">
	* 목적 함수의 gradient는 다음과 같이 <point>Jacobian 행렬</point>을 사용해 표현 가능함
	* <img src="https://drive.google.com/uc?export=view&id=1rMCY5oGOG_aP7nfuK389frijBIVZV8zD" width="60%">
	* Hessian 행렬을 Jacobian 행렬을 사용해 표현하면 다음과 같음. 2차 미분항은 상대적으로 작은 값이므로 <point>무시</point>함. 이 부분에서 기존의 Newton's method와 차이가 나게 됨
	* <img src="https://drive.google.com/uc?export=view&id=1pOXNPLThTl0xK71KtGCXCuYKXr9P6_rH" width="80%">
	* 앞에서 구한 Hessian, Jacobian 행렬을 사용해서 update 수식을 만들면 다음과 같고 <point>Gauss-Newton's method</point>라고 부름. 차이점은 Hessian 행렬을 구할 때 2차 미분항을 무시한다는 것임.
	* <img src="https://drive.google.com/uc?export=view&id=1_K-oOmedM_BtXM0ed3_vLzImx5rMwP60" width="80%">
	* 앞에서와 같이 LM modification을 적용하면 다음과 같음.
	* <img src="https://drive.google.com/uc?export=view&id=1cY_RlxDxOzYn3_D2jCZUI6p0DyPUfDcD" width="80%">
	* LM modification의 변형된 형태로 항등 행렬 $$I$$ 대신 Hessian 행렬의 diag 행렬이 들어가는데 이는 Hessian 행렬이 기울기의 기울기라는 성질을 가지므로 기울기의 기울기가 크다는 것은 기울기가 급격히 변한다는 것이고 이때 step size를 줄여서 이동하는 것이 minimum으로 수렴할 때 효율적이게 됨. $$\mu_k$$가 클 경우 Hessian 행렬과 더해지는 성분의 크기가 커지고 이 값의 역행렬이 gradient에 곱해지므로 결과적으로 급격히 변할 때는 작게 움직이고 완만히 변할 때는 크게 움직이게 됨. 따라서 $$\mu$$가 작을 경우는 기존의 Newton's method와 비슷하게 작동하지만 클 경우 steepest gradient descent의 step size와 비슷하게 작동하되, <point>adaptive</point>하게 조절되는 step size를 가진다는 차이점이 있음.
	* 왼쪽은 기울기의 기울기가 큰 경우로 step size를 작게 움직이고 오른쪽은 기울기의 기울기가 작은 경우로 step size를 크게 움직이는 것이 효율적임.
	* <img src="https://drive.google.com/uc?export=view&id=1xAEDWQhHxkaE_iCzwZ0z2I5gThcaCPU2" width="80%">

<br><br>
>  <subtitle>reference</subtitle>
* https://www.edwith.org/optimization2017