Chapter 1
================

## Numeric Variable

### Variable

Python에서의 변수는 C/C++/Java와 다르게 따로 Data type을 명시해주지 않습니다.

변수의 선언방식은 다음과 같습니다
    
    variable_name = value
    
### Operator

Python에서의 연산자는 다른 프로그래밍 언어들과 크게 다르지 않아 생략하고, C++에 없는 연산자를 중심으로 소개하겠습니다.

제곱 연산자 `**`

아래 코드는 2의 3제곱을 계산합니다.

    >>> 2**3
    8

몫 반환 연산자 `//`

C++에서는 나눗셈의 결과가 소수이고 result를 받는 변수가 `int` 타입인 경우에 소숫점 아래 숫자들이 버려집니다. 그러나 Python에서는 소숫점 아래 모든 숫자들이 온전히 결과값으로 나타납니다.

    >>> 4/3
    1.3333333333333333

그러므로, 프로그래밍을 진행하다 보면 종종 몫 만을 가져와야 할 경우가 있는데, 이 경우 `//` 연산자를 사용하면 됩니다.

    >>> 4//3
    1

## Character & String

### Variable

Python에서는 String이나 문자열 type 데이터들을 다루기가 용이합니다. 특수한 경우를 제외하고는 String type 변수를 만들때는 `"`나 `'` 둘 다 사용가능합니다.

    >>> str = "hello"
    >>> print(str)
    hello
    
    >>> str = 'hello'
    >>> print(str)
    hello
    
그러나 String 안에 `'`를 포함시키고 싶은 경우에는 `"`를 사용하여야 합니다.

    >>> str = "He's happy"
    >>> print(str)
    He's happy

### Escape Seqeuence

Escape Seqeuence의 경우 C언어와 크게 다르지 않습니다.

줄 바꿈의 경우 `\n`를 사용하고 그 외는 검색을 해서 그때 그때 필요한 것들을 찾아서 사용하시면 됩니다.
