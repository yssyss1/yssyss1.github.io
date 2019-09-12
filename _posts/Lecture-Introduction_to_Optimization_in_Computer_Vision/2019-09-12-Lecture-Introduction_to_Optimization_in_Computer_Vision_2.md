---
layout: post
title: WEEK 1 - Classification of Optimization Techniques (1) 
comments: true
categories : [Lecture/Introduction_to_Optimization_in_Computer_Vision]
tags: [Optimization]
---

<br><br>
* 분류는 관점에 따라 여러가지 방법으로 가능함
* 여기서는 feasible set S의 성질에 따라 4가지로 분류함
	* continuous (연속)
	* discrete (이산)
	* combinatorial (조합)
	* variational (변분)

<br><br>
* Discrete vs Continuous
	* 어떤 점을 둘러싸는 구(3차원) 또는 원(2차원)이 있을 때 그 안에 다른 점이 없으면 isolated되었다고 함
	* 그 공간을 아무리 줄여도 다른 점이 있으면 그 점들을 붙어있다고 볼 수 있고 그런 점을 accumulated point라고 함
	* Discrete: 점들이 모두 isolated point로 구성
	* Continuous: 점들이 모두 accumulated point로 구성

<br><br>
* Continuous optimization problems
	* feasible set S이 continuous 공간의 subset일 경우
	* <center><img  src="https://user-images.githubusercontent.com/37978259/64756661-a8fe5280-d56a-11e9-8245-c3da4127e06f.png"  width="75%"></center>

<br><br>
* Discrete optimization problems
	* feasible set S가 discrete set인 경우
	* <center><img src="https://user-images.githubusercontent.com/37978259/64756781-0befe980-d56b-11e9-85a6-93dc24107cf4.png" width="55%"></center>
	* Discrete optimization은 다시 두 가지로 나뉨
		* Integer programming: Discrete를 Continuous로 생각하고 Continuous optimization에서 나온 해를 반올림 등 이산화해서 해를 구하는 것
			* 정확도에 살짝 차이가 있을 수 있음
		* Combinatorial optimization: 숫자가 아닌 유한(finite)한 객체(object)의 조합 최적화 문제
			* 비용 함수를 최소화하는 조합을 찾는 것
			* Minimum Spanning Tree도 대표적인 조합 최적화 문제임
			* Object Segmentation (pixel labeling)에서도 Graph Cuts라는 조합 최적화 문제로 접근함
			* <center><img  src="https://user-images.githubusercontent.com/37978259/64757585-7bff6f00-d56d-11e9-9267-f9e2482d37c4.png" width="55%"></center>

<br><br>
<subtitle>reference</subtitle>
* https://www.edwith.org/optimization2017