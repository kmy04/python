python을 공부하기 전에 기억해야될 것.

**python은 완전히 객체 지향 언어(Object-Oriented Language)** 이다.

## 1. Python에서 객체(Object)의 개념

+ 객체 = 데이터(속성, attribute) + 행동(메서드, method)을 함께 가지는 것

+ 파이썬의 모든 값은 사실 **클래스(class)의 인스턴스(instance) = 객체** 이다.

예:

```python
x = 10
print(type(x))  # <class 'int'>
```

👉 `10`도 사실은 `int` 클래스의 객체다.
그래서 10.bit_length() 같은 메서드도 호출할 수 있다.:

```python
print((10).bit_length())  # 4 (2진수로 1010, 4비트 필요)
```

## 2. "모든 게 객체"라는 의미

+ `int`, `float`, `str`, `list`, `dict` ... 전부 객체.

+ 함수도 객체.

+ 클래스 자체도 객체 (`type`의 객체).

```python
def hello():
    print("Hi")

print(type(hello))  # <class 'function'>
```

```python
class MyClass:
    pass

print(type(MyClass))  # <class 'type'>
```

## 3. C++과 비교해서 보면

+ **C++** -> 원시 타입(`int`, `double`)과 객체(`class`로 만든 것)가 구분되어 있음

+ **Python** -> `int`, `str`같은 기본 타입도 전부 클래스 기반 객체. 구분이 없음.

즉, 파이썬은 훨씬 "순수한 객체 지향" 언어이다.

## 4. 한 줄 정리

✔️ Python에서는 **숫자, 문자열, 리스트, 함수, 클래스, 모듈까지 전부 객체**입니다.

## 파이썬 함수형 프로그래밍

파이썬은 기본적으로 **객체지향 언어**이지만, 동시에 **함수형 프로그래밍(Functional Programming) 스타일**도 지원하기 때문에 사람들이 종종 "함수형 언어"처럼 쓸 수 있다고 한다.

### 1. 함수형 프로그래밍이란?

+ 수한의 함수 개념을 기반으로 한 프로그래밍 패러다임.

+ 핵심 특징:
  1. **순수 함수 (pure fucntion)**
     같은 입력 -> 같은 출력, 부수 효과(side effect)가 없음.

  2. **불변성 (immutability)**
     데이터를 직접 변경하지 않고 새로운 데이터를 만들어냄.

  3. **고차 함수 (higher-order function)**
     함수를 값 처럼 다룰 수 있음 (변수에 담거나 다른 함수에 전달 가능)

  4. **함수 조합(function composition)**
     작은 함수들을 합쳐서 큰 동작을 만듦.

[함수형 코드 보기](#함수형(Functional)-방식)

# 변수

# 입력과 출력

### 예제
```python
name = input("이름을 입력하세요: ")
print("안녕하세요, " + name + "님!")
print(f"안녕하세요, {name}님!")

try:
    number = int(input("숫자를 입력하세요: "))

    if number % 2 == 0:
        print(f"{number}는 짝수입니다.")
    else:
        print(f"{number}는 홀수입니다.")

except ValueError:
    print("숫자를 입력해야 합니다.")
```
### 1️⃣ 기본 사용법
```python
name = input("이름을 입력하세요: ")
print(f"안녕하세요, {name}님!")
```
+ `"이름을 입력하세요: "` -> **프롬프트(prompt)**: 사용자가 입력할 때 보여지는 메세지

+ `input()`은 사용자가 입력하고 Enter를 누르면 값을 반환

+ 반환값은 **무조건 문자열(str)** 이다.

### 2️⃣ 숫자 입력 받기

+ 문제: 사용자가 숫자를 입력해도 `input()`은 문자열로 처리한다.

+ 해결: `int()`나 `float()`으로 변환

```python
number = int(input("숫자를 입력하세요: "))
print(f"입력한 숫자는 {number}입니다.")
```

+ 문자열 `"123"` -> 정수 `123`으로 변환

+ 잘못된 값을 입력하면 `ValueError`발생

### 3️⃣ 여러 값 입력 받기
```python
a, b = input().split() #문자열로
a, b = map(int, input().split()) #정수형으로
a, b = map(float, input().split()) #실수형으로
```

+ 
[map에 대한 설명으로 이동](#map)

[split에 대한 설명으로 이동](#split)

# 형 변환(type casting)


# 예외 처리(Excepion)

# map

# list

# split()


# 몰랐던 개념들

## iterable

+ 정의: 반복 가능한 객체

+ 예시: `list`, `tuple`, `str`, `dict`, `set` 같은 자료형.

+ 특징:

  + `for`문에서 쓸 수 있음.
 
  + `iter()` 함수를 호출하면 **iterator**를 반환할 수 있음
 
  + 스스로는 "다음 원소를 꺼내는 기능(next)"은 없음 -> 그건 iterator의 역할.

```python
numbers = [1, 2, 3]   # 리스트는 iterable
it = iter(numbers)    # iter()로 iterator를 꺼낼 수 있음
```

## iterator

+ 정의: 실제로 "값을 하나씩 꺼낸 수 있는 객체".

+ 조건:

  + `__iter__()`메서드가 있음 (자기 자신을 반환)
 
  + `__next__()`메서드가 있음 (다음 원소 반환, 끝나면 `StopIteration` 예외 발생)

+ `next(iterator)`를 호출해서 원소를 순차적으로 꺼낼 수 있음.

```python
numbers = [1, 2, 3]   # iterable
it = iter(numbers)    # iterator 생성

print(next(it))  # 1
print(next(it))  # 2
print(next(it))  # 3
# print(next(it)) → StopIteration 에러
```


## iterable VS iterator

**내부 요소(member)를 하나씩 리턴할 수 있는 객체를 iterable하다고 한다**. 쉽게 for문을 생각해봤을 때
```python
_list = [1,2,3,4,5]

for i in _list:
    print(i)
```

**for문을 통해 순회할 수 있는 객체를 iterable하다고 생각하면 된다.**

그렇다면 iterable한 것과 iterator는 무슨 차이일까?

쉽게 **`iterable`한 것은 `__next__` 메소드가 존재하지 않고 `iterator`는 존재한다**

### 차이를 한 문장으로

+ **iterable**: "반복할 수 있는 객체" (반복할 준비만 되어 있음)

+ **iterator**: "실제로 반복을 진행하는 객체" (next()로 값 꺼냄)

### 비유

+ **iterable** = 책 (내용이 순서대로 있음 -> iter()로 "책갈피"를 만들 수 있음)

+ **iterator** = 책갈피 (현재 어디까지 읽었는지 기억하면서 한 장씩 넘김)

## 1급 객체

프로그래밍 언어에서 어떤 대상을 **값처럼 자유롭게 다룰 수 이쓴 것**을 의미한다.

1급 객체라면:

+ 변수나 데이터에 담을 수 있어야 한다.

+ 함수의 파라미터로 전달 할 수 있어야한다.

+ 함수의 리턴값으로 사용할 수 있어야한다.

python에서 `함수`는 **1급 객체이다.**

```python
def greet(name):
    return f"Hello, {name}"

f = greet           # 함수 자체를 변수에 담음
print(f("민영"))    # Hello, 민영

def apply(func, value):
    return func(value)

print(apply(greet, "철수"))  # Hello, 철수
```

## 람다(lambda)란?

+ 이름 없는 함수(익명 함수, anonymous function).

+ 짧고 단순한 연산을 표현할 때 유용하다.

```python
square = lambda x: x * x
print(square(5))  # 25
```
위 코드는 아래와 동일하다.
```python
def square(x):
    return x * x
```

## 객체지향 프로그래밍 방식 VS 함수형 프로그래밍 방식

### ✅ 객체지향(OOP) 방식
```python
class Processor:
    def __init__(self, numbers):
        self.numbers = numbers

    def get_even_squares(self):
        result = []
        for n in self.numbers:
            if n % 2 == 0:
                result.append(n * n)
        return result


nums = [1, 2, 3, 4, 5, 6]
p = Processor(nums)
print(p.get_even_squares())  # [4, 16, 36]
```

+ `Processor`라는 객체를 만들고

+ 내부 메서드(`get_even_squares`)로 기능을 구현.

+ 객체지향스러운 구조.

### ✅ 함수형(Functional) 방식

```python
nums = [1, 2, 3, 4, 5, 6]

# filter → 짝수만 걸러내기
# map → 제곱 적용
result = list(map(lambda x: x * x, filter(lambda x: x % 2 == 0, nums)))

print(result)  # [4, 16, 36]
```

+ `map`과 `filter`에 **람다 함수**를 전달.

  + [람다 표현에 대한 설명](#람다(lambda)란)

+ 데이터 변환을 **함수 조합**으로 해결

+ 불필요한 클래스 정의 없이 간

### 한 줄 정리

+ OOP(Object-Oriented Programing) -> 구조화, 재사용성, 캡슐화에 강

+ FP(Functional Programming) -> 데이터 변환과 처리 흐름을 간결하게 표현 가능
