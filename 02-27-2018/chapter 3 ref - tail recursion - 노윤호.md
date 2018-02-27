Factoril 재귀 

	def Factorial(n):
		if n==1:
			return 1
		else:
			return Factorial(n-1)*n


Factiroal 꼬리재귀

	def FactorialTail(n, res):
		if n==1:
			return res
		return FactorialTail(n-1, n*res)
		

Factorial 함수는 다음과 같이 작동
return 에서 추가 연산

	Factorial(3)
	
	3*Factorial(2)
		3*(2*Factorial(1))
		3*(2*1)
		3*2
	6


FactorialTail 함수는 다음과 같이 작동
return 에서 추가 연산 하지 않음

	FactorialTail(3)
	
	Factorial(2,3)
		FactorialTail(1,6)
			6
		6
	6
	
		
Factorial 꼬리재귀 최적화 이후 실제 동작 방식은 사실상 다음의 반복문과 같다

	def FactorialTailLoop(n):
		res = 1
		while n>0:
			res = res*n
			n -= 1
		return res

	FactorialTailLoop(3)
		
	3*res
		3*2*res
			6
		
	