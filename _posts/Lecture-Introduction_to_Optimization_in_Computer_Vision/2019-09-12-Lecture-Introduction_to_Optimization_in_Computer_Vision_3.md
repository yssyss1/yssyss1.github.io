---
layout: post
title: WEEK 1 - Classification of Optimization Techniques (2) 
comments: true
categories : [Lecture/Introduction_to_Optimization_in_Computer_Vision]
tags: [Optimization]
---

<br><br>
* Variational Optimization Problems
	* 기존에는 feasible set이 하나의 실수, 정수 또는 유한한 객체들의 조합으로 유한(finite)하게 정의됨
	* 변분 최적화는 feasible set이 <point>function</point>으로 정의되고, 따라서 set이 <point>무한(infinite)</point>함
	* Segmentation을 예로, 특정 물체를 분할하는 Curve 함수를 변분 최적화 결과로 구할 수 있음
	* 함수의 함수를 목적함수로 정의하고 최적화 문제를 푸는 방식임
		* Calculus of Variation이란 방법으로 품

<br><br>
* Calculus of Variations
	* Functional: <point>함수의 함수</point>를 의미함. 일반적인 함수는 변수->실수로 매핑해주지만 functional은 <point>함수->실수</point>로 매핑해주는 형식임. 함수의 함수라고 모두 functional이 아니라 <point>함수의 함수면서 실수를 할당</point>해줘야 함.
	* <center><img  src="https://user-images.githubusercontent.com/37978259/64759000-fd0c3580-d570-11e9-8714-550d0e2191bf.png"  width="55%" height="75%"></center>
	* 위 예시는 <a href="https://ko.wikipedia.org/wiki/%EC%98%A4%EC%9D%BC%EB%9F%AC-%EB%9D%BC%EA%B7%B8%EB%9E%91%EC%A3%BC_%EB%B0%A9%EC%A0%95%EC%8B%9D">Euler-Lagrange Equation</a>으로 풀 수 있음

<br><br>
* Variational optimization
	* Finding contour
		* <center><img  src="https://user-images.githubusercontent.com/37978259/64760112-de5b6e00-d573-11e9-8ab0-c7f4e0d658f4.png"  width="55%" height="55%"></center>
	* Image denoising
		* <center><img  src="https://user-images.githubusercontent.com/37978259/64760268-41e59b80-d574-11e9-8351-dd6af939460a.png"  width="75%" height="75%"></center>
 
<br><br>
* Other classification
	* contraints의 유무에 따른 분류
	* 비용 함수가 linear, non linear 또는 convex, non convex인지에 따른 분류

<br><br>
> <subtitle>reference</subtitle>
<br>
* https://www.edwith.org/optimization2017
* https://ko.wikipedia.org/wiki/%EC%98%A4%EC%9D%BC%EB%9F%AC-%EB%9D%BC%EA%B7%B8%EB%9E%91%EC%A3%BC_%EB%B0%A9%EC%A0%95%EC%8B%9D