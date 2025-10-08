# 유클리드 알고리즘
- 유클리드 알고리즘은 주어진 두 수 사이에 존재하는 최대공약수(GCD)를 구하는 알고리즘

## 유클리드 알고리즘 원리
- 임의의 두 자연수 a,b가 주어졌을 때, 둘 중 큰 값이 a라고 가정한다.<br>
- a를 b로 나눈 나머지를 n이라 하면 (a%b=n) n이 0일때, b가 최대 공약수(GCD)이다.

## 유클리드 알고리즘 접근 방법
1. 반복문을 이용한 방법<br>
ex)
```java
int gcd(int a, int b) {
	int tmp,n;
	
	//a에 큰 값을 위치시키기 위한 조건문
	if(a<b){
		tmp=a;
		a=b;
		b=tmp;
	}
	
	//유클리드 알고리즘
	//b가 0이 될 때 까지(a%b), 반복문을 돌게되고, b가 0인 순간의 a를 GCD로 판단하고 리턴한다.
	while(b!=0){
		n=a%b;
		a=b;
		b=n;
	}
	return a;
}
```

2. 재귀를 이용한 방법<br>
ex)
```java
ing gcd(int a,int b){
	
	if(b==0){
		return a;
	}else{
		return gcd(b, a%b);
	}
}
```
