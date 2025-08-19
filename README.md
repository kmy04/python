# 입력과 출력

### 예제
```py
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
