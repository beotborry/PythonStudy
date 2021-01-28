Chapter 3
================

### if Statement

다른 여타 프로그래밍 언어와 유사하게 파이썬에도 프로그램의 흐름을 제어하는 제어문이 존재합니다.

먼저 if문 문법에 관해 살펴보고자 합니다. 큰 틀은 C/C++과 유사하나 문법이 약간 다릅니다.

    >>> a = 3
    >>> if a == 3:
    ...     print("a is 3")
    ... else:
    ...     print("a is not 3")
    ...
    a is 3


위 코드를 보면 일단 C/C++과 다르게 블럭의 구분은 중괄호 `{}`가 아닌, 들여쓰기(Indentation)으로 구분합니다. 또한, 조건문의 끝은 콜론 `:`을 통해 표시합니다.

C/C++ 에서는 `else if`와 같은 방식으로 코드를 작성하나, Python에서는 `elif`라는 키워드가 그것을 대체합니다.

    >>> a = 3
    >>> if a == 1:
    ...     print("a is 1")
    ... elif a == 2:
    ...     print("a is 2")
    ... elif a == 3:
    ...     print("a is 3")
    ...
    a is 3


조건문에 사용되는 논리연산자는 C/C++과 동일하니 생략합니다.

### whlie Statement

`while`문의 경우에도 C/C++의 경우과 크게 다르지 않습니다. 아래 코드를 참고하시면 됩니다.

    >>> a = 0
    >>> while a < 3:
    ...     a += 1
    ...     print(a)
    ...
    1
    2
    3

### for Statement

`for`문의 경우에도 작동방식은 C/C++과 크게 다르지 않으나, 리스트를 traverse하거나 여러 변수들을 순회할 때, index를 이용하는 방식이 아닌 `in` 키워드를 활용하는데, 이 점이 주된 차이입니다.

    >>> arr = [1, 2, 3]
    >>> for number in arr:
    ...     print(number)
    ...
    1
    2
    3

위 코드를 보시면 리스트에 있는 요소들이 `in` 키워드로 인하여 `number` 변수에 할당된 것을 확인할 수 있습니다. 즉, C/C++에서 처럼 반복문에서 배열의 각 요소에 접근하기 위해 index를 따로 사용할 필요가 없습니다.

`continue` 키워드도 Python에서 동일하게 작동합니다.

    >>> for number in arr:
    ...     if number == 2:
    ...             continue
    ...     print(number)
    ...
    1
    3

위와 같이 `continue`에 의해서 다음 반복 분기로 넘어간 것을 확인할 수 있습니다.

`for` 문과 같이 자주 사용되는 함수 중 `range` 함수가 있습니다.

`range` 함수의 용례는 다음과 같습니다.

    >>> for number in range(1, 10):
    ...     print(number)
    ...
    1
    2
    3
    4
    5
    6
    7
    8
    9

`range(1,10)`에 의해서 1부터 9까지의 숫자를 가지고 있는 객체가 생성되고, `in` 키워드에 의해서 그 숫자가 `number` 변수에 할당되어 출력된 것을 확인할 수 있습니다.

또한, 프로그래밍을 진행하다보면 리스트 각 요소의 index가 필요한 경우가 있습니다. 이때는 `enumerate`라는 함수를 사용합니다. 용례는 다음과 같습니다.

    >>> arr = ['a', 'b', 'c', 'd']
    >>> for idx, elem in enumerate(arr):
    ...     print(idx, elem)
    ...
    0 a
    1 b
    2 c
    3 d

위 코드를 보면 `enumerate` 함수에 의해서 각 element의 index가 첫번째로 반환되는 것을 확인할 수 있습니다.

마지막으로 자주 사용되는 리스트 내포(List Comprehension)에 관해서 설명하겠습니다.

1부터 10까지의 수를 가지고 있는 리스트를 만들어야 한다고 가정해 봅시다. 그러면 가장 직관적으로 생각할 수 있는 코드는 다음과 같을 것입니다.

    >>> numbers = []
    >>> for i in range(1, 11):
    ...     numbers.append(i)
    
이러한 코드를 파이썬에서는 "리스트 내포"라는 방식을 이용하여 한 줄의 코드로 작성할 수 있습니다.

    >>> numbers = [num for num in range(1, 11)]

위 코드를 보면 `num` 변수가 `range(1,11)`에서 수를 하나씩 가져오고, `numbers` 는 `num` 을 element로 가지게 됩니다.

리스트 내포에는 조건문도 추가할 수 있습니다. 위 코드를 짝수만 가져오게 변경하고 싶다면, 다음과 같이 코드를 작성할 수 있습니다.

    >>> numbers = [num for num in range(1, 11) if num % 2 == 0]
    >>> numbers
    [2, 4, 6, 8, 10]
    
element에 일괄적인 연산도 가능합니다. 1~10까지의 수에 2를 곱한 값을 element로 갖는 리스트를 만들어보겠습니다.

    >>> numbers = [num * 2 for num in range(1, 11)]
    >>> numbers
    [2, 4, 6, 8, 10, 12, 14, 16, 18, 20]
