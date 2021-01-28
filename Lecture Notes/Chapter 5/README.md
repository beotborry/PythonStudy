Chapter 5
================

### Class

이번에는 파이썬에서 Class를 어떻게 정의하고 사용하는 지에 대해 알아보겠습니다. Class의 정의나 구조는 C++에서와 유사합니다. 

클래스를 정의할 때는 `class` 키워드를 사용합니다.

    >>> class Calc:
    ...     pass

    >>> calculator = Calc()

`pass` 키워드는 아무 작동을 하지 않고 넘어가도록 하는 코드입니다. 주로 임시로 코드의 틀을 작성을 할 때 사용됩니다. 

위와 같이 클래스를 정의하고 C++과 동일한 방식으로 object를 만들 수 있습니다.

#### Constructor

인스턴스를 생성할 때 자동으로 호출되는 함수를 Constructor(생성자)라고 합니다. 파이썬에서의 생성자는 다음과 같이 작성합니다.

    >>> class Calc():
    ...     def __init__(self, first, second):
    ...             self.first = first
    ...             self.second = second
    
    >>> calculator = Calc(2, 3)
    >>> calculator.first
    2
    >>> calculator.second
    3

생성자 함수의 이름은 `__init__` 로 정해져 있습니다. 이 함수의 argument를 보면 `self` 라는 키워드를 확인할 수 있습니다. 이는 파이썬에서 메서드를 생성할 때 맨 처음에 명시해야 하는 키워드이며, 생성되는 객체를 의미합니다. (이름을 꼭 "self"로 지을 필요는 없습니다.)

클래스를 정의한 후 `Calc(2, 3)`을 이용하여 객체를 만들었고, 생성자가 호출되면서 `calculator`라는 객체 안의 변수 `first`, `second`에 각각 2와 3이 할당된 것을 확인할 수 있습니다.



