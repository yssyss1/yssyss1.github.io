---
layout: post
title: WEEK 1 - Introduction to Optimization 
comments: true
categories : [Lecture/Introduction_to_Optimization_in_Computer_Vision]
tags: [Optimization]
---

<br><br>
* Optimization
	* 여러 후보들 중에서 내가 세운 기준에 입각해서 <point>최고</point>를 고르는 것
	* 수학적으로 세운 기준을 <point>비용함수</point>, 목적함수라고 함
	* 여러 후보를 <point>feasible set</point>이라고 함
	*	Optimization, Mathematical programming, Energy minimization 모두 동의어
		*	Energy minimization은 특히 image understanding에서 확률 분포의 지수부분을 minimization하는 의미로 사용됨 
		*	확률을 최대화한다는 것은 확률 함수의 지수부분을 최소화하는 것과 같기 때문
	*	feasible set에서 비용함수를 최소화시키는 것을 찾는 것이 Optimization임
	*	비용함수 값 자체보다는 비용함수를 최소화하는 x를 찾는 것이 더 중요함
	*	<center><img src="https://user-images.githubusercontent.com/37978259/64755577-56229c00-d566-11e9-85c9-a2811e725aa3.png" width="25%"></center>
	*	해 x는 특정 집합에 속해야한다는 의미에서 feasible set 이외에도 constraint set이라고도 부름

<br><br>
> <subtitle>reference</subtitle>
* https://www.edwith.org/optimization2017