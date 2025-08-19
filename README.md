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

# ValueError는 문자열을 숫자로 바꾸려 할 때 문자열이
# 올바른 숫자가 아닐 경우 등 값 자체가 유효하지 않을 때 발생한다
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
[map에 대한 설명] (#map)

[split에 대한 설명] (#split())

# 형 변환(type casting)


### 예외 처리(Excepion)

### map

### list

### split()
