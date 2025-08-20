파이썬에서는 **;(세미 콜론) 을 사용하지 않는다**.

파이썬에서 주석은 #이다.

파이썬은 **변수에 형을 지정하지 않는다**.

문자열의 경우 **쌍따옴표도 되고 단따옴표도 된다**. 그리고 혼용해서 사용도 가능하다.

쌍따옴표가 제일 바깥에 있따면 단따옴표는 안쪽에서 문자로 인식되고 단따옴표가 제일 바깥에 있다면 쌍따옴표가 안쪽에서 문자처럼 인식된다.

```python
print("hello 'kim' \"min\"")
print('hello "kim" \'min\'')
```

파이썬에서의 인덱스

### 1️⃣ 인덱스란?

+ 인덱스는 **순서가 있는 자료형(시퀀스 타입)** 에서 특정 요소를 접근 할 때 사용하는 **번호**이다.

+ 파이썬에서 시퀀스 자료형: `list`, `tuple`, `str`, `range` 등

```python
lst = [10, 20, 30, 40]
print(lst[0])  # 10 → 첫 번째 요소
print(lst[2])  # 30 → 세 번째 요소
```

+ **0부터 시작**: 첫 번 째 요소는 `0`, 두 번째 요소는 `1` 이런 식으로 접근한다.

### 2️⃣ 음수 인덱스

+ 음수 인덱스를 쓰면 **끝에서부터 접근** 가능

```python
lst = [10, 20, 30, 40]
print(lst[-1])  # 40 → 마지막 요소
print(lst[-2])  # 30 → 끝에서 두 번째
```

### 3️⃣ 슬라이싱(Slicing)

+ 범위를 지정해서 부분적으로 접근 가능

```python
lst = [10, 20, 30, 40, 50]
print(lst[1:4])   # [20, 30, 40] → 1 ≤ index < 4
print(lst[:3])    # [10, 20, 30] → 시작부터 index 2까지
print(lst[2:])    # [30, 40, 50] → index 2부터 끝까지
```

+ **스탭(step)지정 가능**

```python
print(lst[::2])  # [10, 30, 50] → 2칸씩 건너뛰기
print(lst[::-1]) # [50, 40, 30, 20, 10] → 뒤집기
```

### 4️⃣ 문자열에서 인덱스

```python
s = "Python"
print(s[0])   # 'P'
print(s[-1])  # 'n'
print(s[0:4]) # 'Pyth'
```

+ **문자열은 불변(immutable)** -> 슬라이싱으로 부분 변경은 불가

```python
s[0] = "J"  # Error
s = "J" + s[1:]  # 이렇게 새로운 문자열 만들어야 함
```


 ### 5️⃣ 인덱스로 값 변경 (가변 객체)

 + 리스트처럼 **가변(mutable) 객체**는 인덱스로 직접 값 변경 가능

```python
lst = [10, 20, 30]
lst[1] = 99
print(lst)  # [10, 99, 30]
```

+ 튜플, 문자열은 불가 -> 새 객체 생성 필요

+ 이해 안되면 4️⃣ 문자열에서 인덱스 다시 보기

### 6️⃣ 범위를 벗어난 인덱스

+ 존재하지 않는 인덱스를 사용하면 **IndexError** 발생

```python
lst = [1,2,3]
print(lst[5])  # IndexError
```

+ 슬라이싱은 범위를 넘어도 오류가 나지 않고, 가능한 부분만 반환

```python
print(lst[1:10])  # [2,3]
```



# 파이썬 연산자 정리

## 1. 산술 연산자 (Arithmetic Operators)

| 연산자 | 의미                     | 예제          | 결과      |
|--------|------------------------|-------------|----------|
| `+`    | 덧셈                    | `5 + 3`     | `8`      |
| `-`    | 뺄셈                    | `5 - 3`     | `2`      |
| `*`    | 곱셈                    | `5 * 3`     | `15`     |
| `/`    | 나눗셈                  | `5 / 2`     | `2.5`    |
| `//`   | 나눗셈 후 **몫**        | `5 // 2`    | `2`      |
| `%`    | 나눗셈 후 **나머지**    | `5 % 2`     | `1`      |
| `**`   | 거듭제곱                | `5 ** 2`    | `25`     |

---

## 2. 비교 연산자 (Comparison Operators)

| 연산자 | 의미        | 예제       | 결과      |
|--------|-----------|-----------|----------|
| `==`   | 같음       | `5 == 3`  | `False` |
| `!=`   | 같지 않음  | `5 != 3`  | `True`  |
| `>`    | 큼         | `5 > 3`   | `True`  |
| `<`    | 작음       | `5 < 3`   | `False` |
| `>=`   | 크거나 같음 | `5 >= 3`  | `True`  |
| `<=`   | 작거나 같음 | `5 <= 3`  | `False` |

---

## 3. 논리 연산자 (Logical Operators)

| 연산자  | 의미        | 예제            | 결과      |
|---------|-----------|----------------|----------|
| `and`   | 논리 AND   | `True and False` | `False` |
| `or`    | 논리 OR    | `True or False`  | `True`  |
| `not`   | 논리 NOT   | `not True`      | `False` |

---

## 4. 할당 연산자 (Assignment Operators)

| 연산자   | 의미             | 예제        |
|----------|----------------|------------|
| `=`      | 대입            | `x = 5`    |
| `+=`     | 더해서 대입      | `x += 3` → `x = x + 3` |
| `-=`     | 빼서 대입        | `x -= 2` → `x = x - 2` |
| `*=`     | 곱해서 대입      | `x *= 2` → `x = x * 2` |
| `/=`     | 나누어서 대입    | `x /= 2` → `x = x / 2` |
| `//=`    | 몫으로 나누어 대입 | `x //= 2` → `x = x // 2` |
| `%=`     | 나머지로 대입    | `x %= 3` → `x = x % 3` |
| `**=`    | 거듭제곱 대입    | `x **= 2` → `x = x ** 2` |

---

## 5. 멤버 연산자 (Membership Operators)

| 연산자   | 의미                | 예제                 | 결과      |
|----------|-------------------|--------------------|----------|
| `in`     | 포함 여부 확인      | `'a' in 'cat'`     | `True`  |
| `not in` | 미포함 여부 확인    | `'b' not in 'cat'` | `True`  |

---

## 6. 식별 연산자 (Identity Operators)

| 연산자 | 의미                       | 예제               | 결과      |
|--------|--------------------------|------------------|----------|
| `is`   | 같은 객체인지 확인         | `a is b`         | True/False |
| `is not` | 다른 객체인지 확인       | `a is not b`     | True/False |

---

## 7. 비트 연산자 (Bitwise Operators)

| 연산자 | 의미          | 예제        | 결과      |
|--------|-------------|-----------|----------|
| `&`    | AND         | `5 & 3`   | `1`      |
| `|`    | OR          | `5 | 3`   | `7`      |
| `^`    | XOR         | `5 ^ 3`   | `6`      |
| `~`    | NOT         | `~5`      | `-6`     |
| `<<`   | 왼쪽 시프트   | `5 << 1`  | `10`     |
| `>>`   | 오른쪽 시프트 | `5 >> 1`  | `2`      |

# 파이썬은 어떤 언어인가?

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

    같은 입력 -> 같은 출력, 부수 효과(side effect)가 없음. (전역 변수 변경, I/O, print 등 하지 않음)

    **예시 (순수 함수)**

    ```python
    def add(a, b):
    return a + b

    print(add(2, 3))   # 항상 5
    print(add(2, 3))   # 항상 5 (상태와 무관)
    ```

    **예시 (순수하지 않은 함수)**
    
    ```python
    x = 0

    def add_and_modify(a):
        global x
        x += a        # 외부 상태 변경 (부수 효과)
        return x

    print(add_and_modify(5))  # 출력은 항상 같지 않음
    print(add_and_modify(5))  # 이전 호출에 의존함
    ```

    👉 순수 함수는 **테스트, 디버깅, 병렬 처리**에 유리하다.
 
 3. **불변성 (immutability)**

    데이터를 직접 변경하지 않고 새로운 데이터를 만들어냄.

    즉, 원본 데이터는 그대로 유지

    **파이썬에서 불변(immutable) 자료형**

    + `int`, `float`, `str`, `tuple`, `frozenset`
   
    **예시 (가변성 때문에 문제되는 경우)**

    ```python
    nums = [1, 2, 3]

    def add_item(lst, item):
        lst.append(item)   # 원본 리스트를 수정 (부수 효과)
        return lst
    
    print(add_item(nums, 4))  # [1, 2, 3, 4]
    print(nums)               # 원본도 바뀜 → 예측 불가능한 버그 원인
    ```
    **예시 (불변성 유지)**

    ```python
    nums = (1, 2, 3)

    def add_item(tpl, item):
        return tpl + (item,)   # 새로운 튜플 생성
    
    print(add_item(nums, 4))  # (1, 2, 3, 4)
    print(nums)               # (1, 2, 3) 원본 그대로
    ```
    
    👉 불변성을 지키면 **예측 가능한 코드** 작성 가능.
    
 5. **고차 함수 (higher-order function)**

    함수를 값 처럼 다룰 수 있음 (변수에 담거나 다른 함수에 전달 가능)

    map자체가 예시임
    [map에 대한 설명 바로가기](#map)

 7. **함수 조합(function composition)**

    + 작은 함수들을 합쳐서 큰 동작을 만듦.

    + 수학의 함수 합성 `f(g(x))`과 동일한 개념
   
    **예시 (단계별 함수 정의)**

    ```python
    def add_one(x):
        return x + 1
    
    def square(x):
        return x * x
    
    def half(x):
        return x / 2
    ```

    **조합**

    ```python
    # 수학적으로는: half(square(add_one(x)))
    def composed(x):
        return half(square(add_one(x)))
    
    print(composed(3))  # (3+1)^2 / 2 = 8.0
    ```

    **고차 함수로 일반화**

    ```python
    def compose(f, g):
        return lambda x: f(g(x))
    
    # square(add_one(x))
    f = compose(square, add_one)
    print(f(3))  # 16
    ```

    👉 함수 조합을 사용하면,

    + **복잡한 로직을 작은 블록으로 쪼개고**
   
    + **필요할 때 합쳐서 재사용** 가
    

[함수형 코드 보기](#-함수형Functional-방식)

[객체지향 코드 보기](#-객체지향OOP-방식)

### 2. Python이 함수형 언어처럼 불리는 이유

파이썬은 완전한 함수형 언어(Hackell 같은)는 아니지만, 위 특징을 꽤 많이 지원한다.

#### (1) 함수가 1급 객체 (first-class citizen)

```python
def add(x, y):
    return x + y

f = add
print(f(2, 3))  # 5
```

👉 함수를 변수에 저장하거나, 다른 함수의 인자로 넘길 수 있습니다.

[더 자세한 내용](#1급-객체)

#### (2) 고차 함수 사용 가능

+ `map`, `filter`, `reduce`, `sorted` 등에서 함수를 인자로 넘김.

```python
nums = [1, 2, 3, 4, 5]

print(list(map(lambda x: x * 2, nums)))   # [2, 4, 6, 8, 10]
print(list(filter(lambda x: x % 2 == 0, nums)))  # [2, 4]
```

[map에 대한 자세한 설명](#map)
[list에 대한 자세한 설명](#list)

#### (3) 불변 자료형

+ `tuple`, `str`같은 자료형은 불변(immutable)이라 함수형 스타일을 흉내낼 수 있음.

[tuple에 대한 자세한 설명](#tuple)

[str에 대한 자세한 설명](#str)

#### (4) 람다(lambda) 표현식

짧은 익명 함수 작성 가능.

```python
square = lambda x: x * x
print(square(5))  # 25
```

[람다 표현식 더 자세한 설명](#람다lambda란)

#### (5) C++과 비교

+ **C++** -> 객체지향 중심, 함수 포인터/람다로 함수형 스타일 흉내 가능.

+ **Python** -> 애초에 함수가 1급 객체라서 함수형 스타일을 훨씬 자연스럽게 쓸 수 있음

#### (6) 정리

파이썬은 **객체지향 언어이면서 동시에 함수형 언어 스타일을 지원하는 멀티 패러다임 언어** 이다.

즉, 객체지향스럽게도, 함수형스럽게도, 심지어 절차지향스럽게도 코드를 짤 수 있다.

# 변수

## 1. 변수는 "상자"가 아니다.

C/C++ 같은 언어에서 변수는 메모리 공간(상자)이고 그 안에 값이 직접 저장된다.

하지만 **파이썬 변수는 단순히 객체를 가리키는 "이름표(name""** 이다.

즉, 파이썬에서

```python
x = 10
```

이라고 하면,

+ `10`이라는 **정수 객체(int object)** 가 먼저 메모리에 만들어지고,

+ `x`라는 이름이 그 객체를 참조(바인딩)한다.

그래서 `id(x)`는 "x가 가리키는 객체의 메모리 주소"를 보여준다.

## 2. 네임스페이스 (Namespace)

파이썬에서 모든 변수 이름은 **네임스페이스(사전 형태의 구조)** 안에 키로 저장된다.

예:

```python
a = 10
b = 20
```

-> 내부적으로는

```python
{"a": <int 객체 10>, "b": <int 객체 20>}

이런 식으로 저장된다고 볼 수 있다.

## 3. 변수 재할당

```python
x = 10
x = "str"
```

여기서 `10` 객체와 "str" 객체는 **서로 다른 객체이다.

+ 처음에는 `x -> 10`

+ 그 다음에는 x -> "str"

즉, 이름표가 새로운 박스에 붙는 셈이다. 이전에 쓰던 박스(10)는 더 이상 참조가 없으면 **가비지 컬렉션** 대상이된다.

좀만 내려가면 설명이 있는데 꼭 지금 봐야겠다면 누르셈

[가비지 컬렉션에 대한 설명](#가비지-컬렉션)

## 4. 가변 객체 vs 불변 객체

파이썬의 객체는 크게 두 가지로 나눌 수 있다.

+ **불변 객체(immutable): `int`, `float`, `str`, `tuple` ...

  값을 바꿀 수 없어서, 새로운 값을 만들면 새 객체가 생성되고 이름이 거기로 옮겨진다.

  ```python
  x = 10
  x += 1    # 새로운 int(11) 객체가 만들어지고 x가 그걸 가리킴
  ```

+ **가변 객체(mutable): `list`, `dict`, `set` ...

  내부 데이터를 바꿀 수 있다. 즉, **객체는 그대로고, 내용만 바뀐다.**

    ```python
    lst = [1, 2, 3]
    print(id(lst))  # 예: 140...123
    lst.append(4)
    print(id(lst))  # 같은 id, 내용만 변함
    ```

## 5. `is`와 `==`의 차이

+ `==` : 값이 같은지 비교

+ `is` : **같은 객체**인지(즉, id가 같은지) 비교

```python
a = [1, 2]
b = [1, 2]
print(a == b)  # True  (값 같음)
print(a is b)  # False (다른 객체)
```

## 6. 스코프와 변수의 유효 범위 (LEGB Rule)

파이썬이 변수를 찾을 때는 다음 순서대로 네임스페이스를 검색한다.

+ **L**ocal (현재 함수 안)

+ **E**nclosing (바로 바깥 함수 안)

+ **G**lobal (모듈 전체)

+ **B**uilt-in (파이썬 내장)

## 7. 가비지 컬렉션

어떤 객체를 가리키는 변수가 하나도 없을 때 파이썬은 그 객체를 **자동으로 메모리에서 해제**한다.

```python
x = [1, 2, 3]
x = None  # 리스트 객체를 참조하는 변수가 없어짐 → 가비지 컬렉션 대상
```

## ✅ 정리:

+ 파이썬 변수는 **객체를 담는 상자가 아니라 객체에 붙는 이름표**다.

+ 변수는 네임스페이스 안에 저장되고, 참조하는 객체의 주소(id)를 바꿀 수 있다.

+ 불변 객체는 수정 시 새 객체가 만들어지고, 가변 객체는 같은 객체 안에서 내용만 바뀐다.

+ `==`는 값 비교, `is`는 객체 동일성 비교다.


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

# tuple

# str

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

  + [람다 표현에 대한 설명](#람다lambda란)

+ 데이터 변환을 **함수 조합**으로 해결

+ 불필요한 클래스 정의 없이 간

### 한 줄 정리

+ OOP(Object-Oriented Programing) -> 구조화, 재사용성, 캡슐화에 강

+ FP(Functional Programming) -> 데이터 변환과 처리 흐름을 간결하게 표현 가능
