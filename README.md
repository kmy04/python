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

+ 데이터 변환을 **함수 조합**으로 해결

+ 불필요한 클래스 정의 없이 간

### 한 줄 정리

+ OOP(Object-Oriented Programing) -> 구조화, 재사용성, 캡슐화에 강

+ FP(Functional Programming) -> 데이터 변환과 처리 흐름을 간결하게 표현 가능

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
