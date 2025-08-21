파이썬에서는 **;(세미 콜론) 을 사용하지 않는다**.

파이썬은 함수나 클래스 등의 Scope 즉 내부의 **실행 범위를 정할 때 {}(중괄호)를 사용하지 않는다**.

그렇다면 어떻게 판단하나? **들여쓰기(Indentation)로 판단**한다. 그렇기 때문에 들여쓰기를 잘 못 하면 오류가 발생한다.

일반적으로 들여쓰기는 4칸이지만 2칸이나 1칸도 가능하

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

# 제어문

### 1️⃣ 조건문 (Conditional Statements)

조건문은 **어떤 조건에 따라 코드 실행을 분기**하는 구조이다.

```python
if 조건:
    # 조건이 True일 때 실행
elif 다른_조건:
    # 위 조건이 False이고, 다른_조건이 True일 때 실행
else:
    # 모든 조건이 False일 때 실행
```

예제

```
x = 10

if x > 0:
    print("양수")
elif x == 0:
    print("0")
else:
    print("음수")
```
| 항목     | C/C++                          | Python                              | 차이점                         |
| ------ | ------------------------------ | ----------------------------------- | --------------------------- |
| 기본 구조  | `if (조건) { ... } else { ... }` | `if 조건: ... elif 조건: ... else: ...` | 중괄호 대신 **들여쓰기 사용**          |
| 조건 표현식 | 반드시 boolean 또는 0/1             | 모든 객체 가능 (0, None, False → False)   | Python은 **truthy/falsy** 평가 |
| 삼항 연산자 | `조건 ? 참 : 거짓`                  | `참 if 조건 else 거짓`                   | 문법 차이                       |

+ 파이썬에서는 **조건문에서 반드시 `True`/`False`만 사용해야 하는 것이 아니라, 거의 모든 객체가 boolean 값으로 평가될 수 있다.

+ 이때 **`True`처럼 취급되는 값 -> truthy, `false`처럼 취급되는 값 -> falsy** 라고 부른다. 

**Falsy 값**

| 값       | 설명        |
| ------- | --------- |
| `None`  | None 객체   |
| `False` | 불리언 False |
| `0`     | 정수 0      |
| `0.0`   | 실수 0.0    |
| `0j`    | 복소수 0j    |
| `""`    | 빈 문자열     |
| `[]`    | 빈 리스트     |
| `()`    | 빈 튜플      |
| `{}`    | 빈 딕셔너리    |
| `set()` | 빈 집합      |

**boolean 변환**

+ `bool()`함수를 사용하면 객체를 명시적으로 True/False로 변환 가능

```python
print(bool(0))       # False
print(bool(""))      # False
print(bool([1,2]))   # True
print(bool("Python")) # True
```

### 2️⃣ 반복문 (Loop Statements)

#### (1) `for`문

+ **시퀀스 자료형(iterable)** 을 순회할 때 사용

+ 인덱스 기반뿐 아니라 **리스트, 문자열, 튜플 등 모두 사용 가능**

```python
fruits = ["apple", "banana", "cherry"]

for fruit in fruits:
    print(fruit)
```

+ **range() 사용 예제**:

```python
for i in range(5):  # 0,1,2,3,4
    print(i)
```

+ range()함수는 **일정 범위의 연속된 정수를 생성하는데 사용**

#### `while`문

+ 조건이 True일 동안 반복

```python
count = 0
while count < 5:
    print(count)
    count += 1
```

+ **무한 루프**:

```python
while True:
    # break 필요
    if some_condition:
        break
```

### 3️⃣ 반복문 제어: `break` / `continue` / `else`

| 키워드        | 설명                                         |
| ---------- | ------------------------------------------ |
| `break`    | 반복문 즉시 종료                                  |
| `continue` | 현재 반복 건너뛰고 다음 반복으로 이동                      |
| `else`     | 반복문이 **정상 종료**될 때 실행 (`break`로 종료되지 않은 경우) |

```python
for i in range(5):
    if i == 3:
        break
    print(i)
else:
    print("완료")  # break 때문에 실행 안 됨
```

| 항목    | C/C++                  | Python              | 차이점                                |
| ----- | ---------------------- | ------------------- | ---------------------------------- |
| 반복    | `for(int i=0;i<5;i++)` | `for i in range(5)` | Python은 **iterable 순회 기반**, 인덱스 자동 |
| 조건 반복 | `while(조건)`            | `while 조건:`         | 기본 구조 유사, 들여쓰기 사용                  |
| 반복 제어 | `break`, `continue`    | `break`, `continue` | 기능 유사, `else` 추가 가능 (정상 종료 시 실행)   |
| 무한 루프 | `for(;;)`              | `while True:`       | Python 문법                          |


### 5️⃣ 파이썬의 특수 제어문

#### (1) 삼항 연산자 (조건 표현식)

```python
x = 5
result = "양수" if x > 0 else "음수 또는 0"
print(result)
```

#### (2) 리스트 내포(List Comprehension) + 조건

```python
nums = [1, 2, 3, 4, 5]
evens = [x for x in nums if x % 2 == 0]
print(evens)  # [2,4]
```

+ 반복문과 조건문을 한 줄로 작성 가능

# 네임스페이스(Namespace)

**네임스페이스(Namespace)** 는 **이름(변수, 함수, 클래스 등)** 을 실제 **객체(Object)** 에 매핑하는 시스템을 말한다.

쉽게 말해, 파이썬에서 이름을 쓰면, 그 이름이 가리키는 객체를 찾아야 하는데, 그 "이름 -> 객체" 대응표를 저장한 것이 네임스페이스이다.

## 1. 네임스페이스란?

+ 파이썬에서 `x = 10`을 실행하면:

  + 정수 객체 `10`이 힙(Heap)에 생성
 
  + 현재 네임스페이스(예: 함수 안이면 local, 모듈이면 global)에 `"x"`라는 이름을 만들고 `10`객체를 가리킴
 
  + 즉, **이름표(`x`)가 객체 (`10`)에 붙는 것**이다.

```python
x = 10
y = "hello"
```

👉 네임스페이스 내부적으로는 (딕셔너리 같은) 구조:

```python
{
  "x": <int object at 0x...>,
  "y": <str object at 0x...>
}
```

## 2. 네임스페이스의 종류

파이썬에는 크게 4가지 주요 네임스페이스가 있다.

### (1) BUilt-in namespace

+ 파이썬 실행 시 자동으로 로드되는 최상위 네임스페이스

+ `len()`, `print()`, `range()`같은 기본 함수들이 여기 있다.

+ `import builtins`하면 접근 가능

```python
import builtins
print(dir(builtins))  # 내장 함수들 리스트
```

### (2) Global namespace

+ 모듈이 로드될 때 생성됨

+ 모듈의 최상위에 정의된 변수, 함수, 클래스가 여기에 저장됨

```python
x = 42 # 글로벌 변수
```

### (3) Enclosing namespace

+ 중첩 함수에서 외부 함수의 네임스페이스

```python
def outer():
    a = 10
    def inner():
        print(a)  # enclosing namespace 참조
    inner()
```

👉 `inner()`는 지역(local)에서 `a`를 찾지 못하면, enclosing(outer 함수)에서 탐색

쉽게 표현하면 c언어나 c++에서 이중 for문 생각했을 때 내부 for문은 외부 for문에 변수를 어떻게 찾아서 썼을까를 생각해보면됨

### (4) Local namespace

+ 함수가 호출될 때마다 생성됨

+ 함수 안에서 정의한 변수들이 여기에 저장됨

```python
def foo():
    x = 100  # local namespace
    print(x)
```

## 3. 이름 탐색 규칙 (LEGB Rule)

파이썬은 변수를 찾을 때 **LEGB** 순서로 탐색한다.

1. **Local** (현재 함수의 지역 변수)

2. **Enclosing** (바로 바깥 함수의 변수, 중첩 함수에서 사용됨)

3. **Global** (모듈 전체 번위에서 정의된 변수)

4. **Built-in** (파이썬 내장 함수와 변수)

```python
x = "global"

def outer():
    x = "enclosing"
    def inner():
        x = "local"
        print(x)  # local → enclosing → global → built-in 순으로 탐색
    inner()

outer()
# 출력: local
```

## 4. 네임스페이스와 딕셔너리

네임스페이스는 실제로 **딕셔너리 형태**로 구현되어 있다.

```python
x = 10
print(globals()) # 현재 모듈의 글로벌 네임스페이스 (dict)
```

함수 안에서:

```python
def foo():
    y = 20
    print(locals())  # 지역 네임스페이스 (dict)

foo()
```

## 5. 메모리 관점에서

+ 이름(변수)은 네임스페이스(딕셔너리)에 **key**

+ 실제 객체(숫자, 문자열, 리스트 등)는 **heap 메모리의 주소**

+ 네임스페이스 딕셔너리의 value는 그 객체를 가리키는 **포인터(주소)**

즉: 

```python
네임스페이스 dict
 └── "x" → <주소 0x7f...의 int 객체 10>
```

## 6. C/C++ 스택/힙 VS 네임스페이스

이런 궁굼증이 들었다 네임스페이스는 그럼 메모리인가? 마치 C/C++의 스택/힙처럼?

| 구분        | 스택(Stack) / 힙(Heap) | 네임스페이스(Namespace)     |
| --------- | ------------------- | --------------------- |
| **언어**    | C, C++ 같은 저수준 언어    | Python (고수준)          |
| **개념 레벨** | 메모리 관리 (물리적 영역)     | 이름 → 객체 참조 (추상적 매핑)   |
| **역할**    | 데이터가 어디에 저장되는지 구분   | 이름이 어떤 객체를 가리키는지 관리   |
| **구조**    | 스택 프레임, 힙 블록        | 딕셔너리 (hash map)       |
| **해제**    | 스택: 자동 / 힙: 수동      | 가비지 컬렉션이 참조 카운트 보고 해제 |

✅ 정리하자면:

+ **스택/힙**은 **메모리의 실제 저장 위치**에 대한 개념.

+ **네임스페이스**는 **이름을 어떻게 관리하고 어떤 객체를 가리키는지**에 대한 개념

즉, 네임스페이스는 C/C++의 스택/힙과 직접적으로 대응되지 않고, **심볼 테이블(Symbol Table)** 에 더 가까운 개념이다.

## 7. c++ 심볼 테이블(Symbol Table) VS 네임 스페이스

### (1) C++의 심볼 테이블(Symbol Table)

C/C++ 컴파일러는 코드를 컴파일할 때, 각 **이름(identifier)** 을 **메모리 주소**와 매핑해둔다.

예시 (C++):

```cpp
int a = 10;
int b = 20;

int add(int x, int y) {
    return x + y;
}
```

+ 컴파일러는 다음과 같은 정보를 **심볼 테이블(symbol table)** 에 기록한다.

```cpp
┌─────────┬─────────────┐
│ 이름    │ 메모리 주소 │
├─────────┼─────────────┤
│ a       │ 0x7fffdc30  │  (스택에 저장)
│ b       │ 0x7fffdc34  │  (스택에 저장)
│ add     │ 0x401020    │  (코드 영역의 함수 시작 주소)
└─────────┴─────────────┘
```

즉, **C++에서는 이름 -> 메모리 주소(값이 저장된 위치)** 로 직접 연결된다.

### (2) 파이썬의 네임스페이스(Namespace)

파이썬은 인터프리터 언어라서 C++처럼 직접 메모리 주소에 매핑하지 않고, **이름 -> 객체(레퍼런스)** 매핑을 **네임스페이스(딕셔너리)** 로 관리한다.

예시(Python):

```python
a = 10
b = 20

def add(x, y):
    return x + y
```

+ 파이썬의 네임스페이스(사실상 딕셔너리):

```pgsql
┌─────────┬───────────────────┐
│ 이름    │ 객체(참조)        │
├─────────┼───────────────────┤
│ a       │ <int object at 0x1052e90> (10) 
│ b       │ <int object at 0x1052eb0> (20)
│ add     │ <function add at 0x10539d0>
└─────────┴───────────────────┘
```

여기서 중요한 차이:

+ `a`라는 이름은 **10이라는 값이 들어 있는 int 객체**를 가리킨다.

+ 객체 (`10`)는 힙에 저장되고, 이름(`a`)은 네임스페이스 딕셔너리에 key-value 형태로 등록된다.

즉, **이름 -> 객체 레퍼런스** 구조이다.

### (3) 비교 요약

| 구분    | C++ 심볼 테이블       | 파이썬 네임스페이스                      |
| ----- | ---------------- | ------------------------------- |
| 구조    | 이름 → 메모리 주소      | 이름 → 객체 레퍼런스                    |
| 실행 방식 | 컴파일 시 고정         | 실행 시 동적으로 관리                    |
| 저장소   | 스택/힙/코드 영역       | 딕셔너리(네임스페이스)                    |
| 예시    | `a → 0x7fffdc30` | `a → <int object at 0x1052e90>` |

📌 따라서

+ **C++은 이름이 “주소”로 컴파일 시 매핑되는 직접 참조 방식**

+ **Python은 이름이 “딕셔너리 key”로 런타임에 매핑되는 간접 참조 방식**

이라고 이해하면 된다.

네임스페이스에 대한 깊은 내용은 변수 파트에 나온다. 미리 보고 싶다면 눌러라](#-네임스페이스-Namespace)

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

## 2. 가변 객체 vs 불변 객체

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

## 3. `is`와 `==`의 차이

+ `==` : 값이 같은지 비교

+ `is` : **같은 객체**인지(즉, id가 같은지) 비교

```python
a = [1, 2]
b = [1, 2]
print(a == b)  # True  (값 같음)
print(a is b)  # False (다른 객체)
```

## 4. 스코프와 변수의 유효 범위 (LEGB Rule)

파이썬이 변수를 찾을 때는 다음 순서대로 네임스페이스를 검색한다.

+ **L**ocal (현재 함수 안)

+ **E**nclosing (바로 바깥 함수 안)

+ **G**lobal (모듈 전체)

+ **B**uilt-in (파이썬 내장)

[LEGB RUle 자세한 설명](#3-이름-탐색-규칙-LEGB-Rule)

## 5. 가비지 컬렉션

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

## 6. 네임스페이스 (Namespace)

이미 앞서 네임스페이스에 대해서 설명을 했었다. 여기서부터는 심화 내용이다.

### (1) 파이썬 변수는 "이름 -> PyObject* (C 구조체 포인터)"

파이썬은 C언어로 구현되어 있고, 모든 값은 `PyObject`라는 구조체를 기반으로 표현된다.

```c
// CPython에서 모든 객체의 기반 구조체
typedef struct _object {
    Py_ssize_t ob_refcnt;   // 참조 카운트 (GC용)
    struct _typeobject *ob_type; // 객체의 타입 정보 (int, str 등)
} PyObject;
```

+ `int`, `str`, `list` 등 모든 파이썬 객체는 사실상 **PyObject를 확장한 구조체**이다.

+ ob_refcnt가 0이되면 **가비지 컬렉션** 대상이된다.

좀만 내려가면 설명이 있는데 꼭 지금 봐야겠다면 누르셈

[가비지 컬렉션에 대한 설명](#7-가비지-컬렉션)

+ 예를 들어, 정수는 이렇게 구현돼 있다:

```c
typedef struct {
    PyObject ob_base;   // 참조 카운트 + 타입
    long ob_ival;       // 정수 값
} PyLongObject;
```

위는 **단순화 버전**

실제 CPython 소스 코드

```c
struct _longobject {
    PyObject_VAR_HEAD   // refcnt, type, ob_size (길이 및 부호)
    digit ob_digit[1];  // 정수를 저장하는 "가변 길이 배열"
};
```

+ `PyObject_VAR_HEAD`

 + `Py_ssize_t ob_refcn`t (참조 카운트)

 + `struct _typeobject *ob_type` (타입 포인터, 여기서는 int 타입)

 + `Py_ssize_t ob_size` (자릿수와 부호. 음수면 음수 정수, 양수면 양수 정수)

+ `digit ob_digit[1]`

 + 실제 정수 값을 저장하는 배열.

 + "가변 길이 배열" 기법이라 `[1]`로 선언해두고, 객체를 생성할 때 필요한 크기만큼 메모리를 더 할당다.

 + 따라서 파이썬 정수는 **길이에 제한이 없는 임의 정밀도 정수**가 된다.

즉, 파이썬에서

```python
a = 10
```

을 실행하면 내부적으로는:

1. `10`이라는 값을 가진 `PyLongObject` 구조체가 힙에 생성됨.

   (단순화 버전 설명, `{ob_refcnt:1, ob_type:&PyLong_Type, ob_ival:10}같은 구조체)

2. 네임스페이스(실제로는 C 딕셔너리 `PyDictObjec`)에 `"a"`라는 문자열을 키(key)로 하고,

   그 값(value)으로 `PyObject*`포인터(10을 가리키는 주소)를 저장.

### (2) 네임스페이스(딕셔너리) 내부 구조

파이썬의 **네임스페이스**는 사실상 **C에서 구현된 해시 테이블(PyDictObject)** 이다.

```python
typedef struct {
    PyObject ob_base;            // 공통 헤더: 참조 카운트, 타입 포인터
    Py_ssize_t ma_used;          // "실사용" 항목 수 (활성 값 개수)
    PyDictKeysObject *ma_keys;   // 키 테이블 (인덱스 테이블 + 키 엔트리들)
    PyObject **ma_values;        // 값 배열(옵션). NULL이면 "combined", 비NULL이면 "split"
} PyDictObject;

```

#### 핵심 개념 먼저

 + 파이썬 dict는 **해시 테이블**이다.

 + dict는 두 가지 레이아웃을 가질 수 있다.

#### 1. Combined dict

 + 키와 값이 **같은 엔트리 배열**에 함께 저장됨. `ma_values == NULL`

   **entry** = 경기·경연 등의 참가의 등록. 또는, 참가자 명부. 순화어는 `참가자 명단'.

 + 일반적인 딕셔너리는 대부분 이 모드이다.

📌 예시:

```python
d = {"a": 1, "b": 2}
```

메모리 내부 구조 (단순화):

```sql
PyDictObject
 ├─ ma_keys (dict keys table)
 │    ├─ entry[0] → key="a", value=1
 │    ├─ entry[1] → key="b", value=2
 │    └─ ...
 └─ ma_values = NULL  (Combined 모드에서는 따로 분리하지 않음)
```

즉, 키와 값이 **한 곳에 같이 존재**한다.

-> `ma_used = 2` (실제로 값이 들어간 엔트리 수)

**사용되는 경우**:

 + 일반적인 `dict` 객체 (`{"x": 10, "y": 20}`)

 + 독립적으로 생성된 딕셔너리

#### 2. **Split dict (key-sharing dict)**

 + 키 테이블은 **공유**하고 값은 **별도 배열**에 저장. `ma_values != NULL`

 + `ma_keys`에는 **키만 저장**되고
  
 + `ma_values` 배열에는 **값만 저장**된다.

 + 주로 **여러 인스턴스의 `__dict__`** 에서 메모리 절약을 위해 쓰인다. (키는 클래스/패턴과 공유, 값만 인스턴스 별로 다름)

📌 예시:

```python
class A:
    pass

obj1 = A()
obj2 = A()

obj1.x = 10
obj2.x = 20
```

여기서 `obj1.__dict__`와 `obj2.__dict__`는 보통 **Split Dict** 구조로 만들어진다.

메모리 내부 구조(단순화):

```markdown
공유된 키 테이블 (PyDictKeysObject)
 ├─ entry[0] → key="x"
 └─ ...

obj1.__dict__ (PyDictObject)
 ├─ ma_keys → (위의 공유된 키 테이블)
 ├─ ma_values[0] → 10

obj2.__dict__ (PyDictObject)
 ├─ ma_keys → (같은 공유된 키 테이블)
 ├─ ma_values[0] → 20
```
→ 즉, obj1과 obj2는 같은 키 테이블을 공유하지만, 값(ma_values)은 각각 다릅니다.

**장점**:

+ 같은 클래스로 만들어진 수 많은 객체가 있을 때 **메모리를 절약**할 수 있다.

+ 키를 공유하기 때문에 lookup 속도가 빨라진다.

 + lookup 속도가 빨라진다는 의미

 + **Combined dict**는 `"키 → 해시 → 비교 → 값"` 과정을 거쳐 값을 찾고,

   1. 해시와 키 비교가 필요한 이유
  
      + 파이썬 dict는 **키 기반 해시 테이블**이다.
     
      + 해시는 키 문자열에서 만들어지지만, 서로 다른 키라도 **해시값이 충돌할 수 있다.**(해시 충돌)
     
      + 따라서 단순히 해시값만으로는 통일 키인지 확실히 알 수 없다. 그래서 **실제 키 문자열을 비교**해야 한다.

 + **Split dict**는 `"키 → 미리 정해진 인덱스 → 값"` 으로 바로 접근

 + 즉, **Split dict는 해시와 문자열 비교 단계를 생략하고 곧장 배열 인덱스로 값에 접근하기 때문에 더 빠르다**.

**사용되는 경우**:

+ **인스턴스의** `__dict__`

+ 특히, 같은 클래스에서 만든 객체들이 속성 이름(키)을 공유할 

#### 필드별 역할

#### **1)** `ob_base`

+ 모든 `PyObject`가 가지는 헤더(참조 카운트, 타입 포인터).

#### **2)** `ma_used`

+ 이 dict에서 **실제로 값이 설정된 항목 수**이다.

+ combined에서는 "값이 NULL이 아닌 엔트리 수", split에서는 "`ma_values`배열에서 NULL이 아닌 값 수"에 해당한다.

+ (중요) `ma_used` ≤ `ma_keys`안의 `dk_netries` (키 엔트리 수).

  + split dict에서는 **키 슬롯은 존재하지만 그 값이 아직 설정되지 않아 NULL일 수** 있어서 `ma_used`가 더 작을 수 있다.

#### **3)** `ma_keys` (`PyDictKeysObject*`)

[내용이 너무 길어서 따로 뺌](#ma_keys-PyDictKeysObject)

#### **4) `ma_values` (`Pyobject **`)**

+ **split dict에서만 사용**된다.

+ **값만** 담는 별도의 포인터 배열로, **인덱스가 `ma_keys`의 엔트리 인덱스와 1:1로 대응**한다.

+ combined dict에서는 `NULL`이다. (값이 `ma_keys` 엔트리 안에 같이 있음).


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

# 내용이 너무 길어져서 따로 빼놓은 것

## ma_keys (PyDictKeysObject*)

 **키 테이블의 본체**이다. 내부에:

### 1. 인덱스 테이블(`dk_indices`):
  
   + `dk_indices`는 **해시 -> 엔트리 배열(`entries`) 인덱스로**로 바로 매핑하는 테이블이다.

   + 실제 값이나 키 자체는 여기에 없고, **인덱스만 저장**한다.

   + 즉, 해시값을 계산하면 `dk_indices`를 통해 **엔트리 배열에서 어느 위치를 봐야 하는지** 바로 알 수 있다.

**구조 예시**

```text
dk_indices = [0, 2, EMPTY, 1, ...]  # 인덱스 테이블
entries = [ ("a", 10), ("b", 20), ("c", 30) ]  # 엔트리 배열
```

+ 해시값을 이용해 `dk_indices`에서 엔트리 번호를 찾아서 `entries`를 접근

+ **값과 키는 `entries` 안에 따로 저장**되고 `di_indices`는 "인덱스 포인터"만 가짐.

### 2. **엔트리 배열**(`entries`): 각 엔트리에 키 객체와 키 해시 (그리고 combined일 때는 값까지) 저장

**자 그런데 dk_indices에 값이 왜 저런 형태지?라는 의문이 남았을 것이다.**

### 오픈 어드레싱(Open Addressing) 기반

오픈 어드레싱은 **충돌 해결 방법**중 하나이다.

### 문제

 + 해시값이 다른 키와 겹칠 수 있음(hash colision)

 + 예: `hash("a) % table_size = 1`

   `hash("b") % table_size = 1` -> 충돌

#### 해결 (오픈 어드레싱)

+ 충돌이 발생하면 **다음 빈 슬롯을 찾는 방식**으로 처리

+ CPython은 **perturb + probing** 기법 사용:

  + 해시값 + perturb 변수를 이용해 점진적으로 다른 슬롯으로 이동
 
  + 충돌이 없어질 때까지 반복
 
1. 값: **entries 배열의 인덱스

2. EMPTY: **해당 슬롯이 비어 있음** (아직 키 없음)

3. DUMMY: **삭제된 키 자리** (탐색용 마커)

즉, `dk_indices[i] = j`라면

 해시 -> 슬롯 `i` -> entries[j]를 보면 실제 키와 값(Combined dict) 또는 키만(Split dict)을 찾을 수 있

**예시 (간단화)**

```python
d = {"a": 10, "b": 20, "c": 30}
```

+ `entries` 배열:

| index | key | value |
| ----- | --- | ----- |
| 0     | "a" | 10    |
| 1     | "b" | 20    |
| 2     | "c" | 30    |


+ `dk_indices` 배열(단순화):

| slot | dk\_indices\[slot] | 의미                |
| ---- | ------------------ | ----------------- |
| 0    | 0                  | entries\[0] → "a" |
| 1    | 2                  | entries\[2] → "c" |
| 2    | EMPTY              | 비어 있음             |
| 3    | 1                  | entries\[1] → "b" |


+ `dk_indices`의 **인덱스 값(0, 1, 2) = entries 배열에서 키가 실로 저장된 위치**

**그림으로 표현하면**

```rust
dk_indices (slots) : [ 0 , 2 , EMPTY , 1 ]
                       |   |         |
entries 배열          : [ "a", "b", "c" ]
                         ^   ^    ^
                         |   |    |
slot 0 -> entry 0 -> "a":10
slot 1 -> entry 2 -> "c":30
slot 2 -> EMPTY (빈 슬롯)
slot 3 -> entry 1 -> "b":20
```

**흐름**

1. `"a"`를 넣을 때

	+ slot = hash("a") % table_size = 0

	+ dk_indices[0] = 0 → entries[0]에 "a":10 저장

2. `"b"`를 넣을 때

	+ slot = hash("b") % table_size = 3

	+ dk_indices[3] = 1 → entries[1]에 "b":20 저장

3. `"c"`를 넣을 때

	+ slot = hash("c") % table_size = 0 → 이미 "a" 있음 (충돌)

	+ 다음 빈 슬롯 slot 1 사용

	+ dk_indices[1] = 2 → entries[2]에 "c":30 저장
