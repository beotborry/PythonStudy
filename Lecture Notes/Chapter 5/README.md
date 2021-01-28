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

#### Method

클래스 안에서 정의되는 함수들을 메서드(Method)라고 합니다. 다음 코드를 살펴봅시다.

    >>> class Calc():
    ...     def __init__(self, first, second):
    ...             self.first = first
    ...             self.second = second
    ...     def add(self):
    ...             return self.first + self.second

    >>> calculator = Calc(2, 3)
    >>> calculator.add()
    5

클래스 안에서 정의되는 메서드들은 기본적으로 `self`를 첫 argument로 가집니다. 위 코드에서는 `add` 메서드를 추가하였습니다. 객체가 가지고 있는 `first`, `second`의 값은 객체가 만들어질 때 constructor에 의해서 할당이 되기 때문에 `add` 함수에서는 따로 그 값들을 받을 필요가 없습니다. 함수 안에서 `self.first`, `self.second`를 통해 객체가 가지고 있는 변수들의 값을 가지고 오고 그 둘을 더한다음에 반환합니다.

#### 클래스 상속 (Inheritance)

파이썬에도 다른 객체 지향 언어와 유사하게 클래스 상속을 지원하고 있습니다. 클래스 상속은 기존에 있던 클래스의 기능들을 그대로 유지하면서 추가적인 기능을 구현하고자 할 때 사용됩니다. 클래스 상속 방식은 다음과 같습니다.

    >>> class NewCalc(Calc):
    ...     pass

`NewCalc` 뒤에 오는 소괄호 안에 상속의 대상이 되는 클래스의 이름을 적음으로써 상속을 구현할 수 있습니다.

    >>> new_calculator = NewCalc(2, 3)
    >>> new_calculator.add()
    5

그리고 위 코드를 보면 기존에 `Calc` 클래스가 가지고 있던 메서드들이 그대로 유지되어 사용 가능한 것을 확인할 수 있습니다.

이번에는 새로운 메서드를 추가해보겠습니다.

    >>> class NewCalc(Calc):
    ...     def pow(self, n):
    ...             return self.first ** n, self.second ** n

    >>> new_calculator = NewCalc(2, 3)
    >>> new_calculator.pow(2)
    (4, 9)

거듭제곱을 수행하는 `pow` 메서드를 추가해보았습니다. argument로 `n`을 받아서 객체가 가지고 있는 `self.first`, `self.second` 각각을 n번 거듭제곱한 값을 반환합니다.

#### Method Overriding


