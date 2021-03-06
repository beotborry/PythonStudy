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

### Operator

#### Concatenation

문자열 이어붙이기의 경우 `+`를 통해 할 수 있으며, 비교적 직관적입니다.

    >>> str1 = "hello"
    >>> str2 = "world"
    >>> print(str1 + str2)
    helloworld
    
`*`를 통해 이어붙이는 작업을 반복할 수 있습니다.

    >>> str1 = "hello"
    >>> print(str1 * 3)
    hellohellohello

#### Length

문자열 또는 배열의 길이를 얻기 위해서는 built-in 함수인 `len()` 을 사용하면 됩니다.

    >>> str = "hello world"
    >>> print(len(str))
    11
    
#### Indexing & Slicing

C/C++에서 String을 배열을 이용해서 만들고, 각 문자를 배열의 index로 접근하듯이, Python도 동일한 방식으로 String의 각 문자에 대해 접근할 수 있습니다.

Python의 index도 역시 0부터 시작합니다.

    >>> str = "apple"
    >>> str[1]
    'p'

끝 문자를 접근할 때는 -1을 사용합니다.

    >>> str = "apple"
    >>> str[-1]
    'e'

부분 문자열을 추출하는 Slicing의 경우에는 C++에서 `substr` 함수를 사용하지만 Python에서는 다른 간단한 방법을 이용하여 슬라이싱을 할 수 있습니다.

    >>> str = "abcdefghijklmnopqrstuvwxyz"
    >>> str[1:4]
    'bcd'

위와 같이 `#:#` 과 같은 형태로 Slicing을 할 수 있는데, 위 코드의 같은 경우 1번째 index 문자 부터 4번째 index 문자 전까지를 가져옵니다.

#### Formatting

C에서 `printf`와 유사한 방식으로 Python에서도 출력을 할 수 있습니다.

작동방식 및 사용되는 Escape Sequence 들은 동일합니다.

대신, C에서 값을 넘겨줄 때, `,` 뒤에 값을 입력해줬다면, Python에서는 `%` 를 이용합니다.

    >>> "This is %d dollar" % 3
    'This is 3 dollar'
    

`format` 함수를 이용해서도 Formatting을 할 수 있습니다.

    >>> number = 10
    >>> day = "three"
    >>> "I ate {0} apples. so I was sick for {1} days.".format(number, day)
    'I ate 10 apples. so I was sick for three days.'

위 코드 같은 경우 인덱스를 이용한 Formatting 입니다. 중괄호 안에 숫자가 각각의 Index를 의미하고, 0번째에는 `number` 변수의 값이, 1번째에는 `day` 변수의 값이 각각 들어간 것을 확인할 수 있습니다.

이름을 이용해서 Formatting을 할 수도 있습니다.

    >>> "I ate {number} apples. so I was sick for {day} days.".format(number = 3, day = "three")
    'I ate 3 apples. so I was sick for three days.'

마지막으로 f 문자열 Formatting을 보겠습니다.

    >>> name = '홍길동'
    >>> age = 30
    >>> f'나의 이름은 {name}입니다. 나이는 {age}입니다.'
    '나의 이름은 홍길동입니다. 나이는 30입니다.'

위와 같이 문자열 앞에 `f`를 붙이면 문자열 Formatting 기능을 사용할 수 있습니다.

### Frequently Used Function

문자열과 관련해서 자주 사용되는 함수를 몇 개 소개하겠습니다.

#### Replace

    >>> a = "Life is too short"
    >>> a.replace("Life", "Your leg")
    'Your leg is too short'

`replace(A, B)` 에서 A에 해당하는 부분을 B로 바꾸어줍니다.

#### Split

    >>> b = "a:b:c:d"
    >>> b.split(':')
    ['a', 'b', 'c', 'd']

문자열을 주어진 delimeter에 따라 나누어서 리스트 형태로 반환합니다.


