Chapter 6
================

### Exception Handling

프로그램을 작성해서 실행을 시켜보면 오류로 인해 프로그램이 종료되는 경우가 빈번히 발생합니다. 그러한 오류 상황을 미연에 처리하는 것이 예외 처리(Exception Handling) 입니다. 기존에 코드를 작성하면서 if 문을 이용해서 여러 케이스를 처리하는 것도 예외 처리의 일부라고 할 수 있습니다.

#### try ~ except

파이썬에서는 예외처리와 관련해서 여러 키워드를 제공하고 있습니다. 우선 `try`, `except` 구문을 살펴보겠습니다.

(오류는 수를 0으로 나눌 때 발생하는 오류를 계속 사용하겠습니다.)

기본적으로 파이썬에서 수를 0으로 나누는 경우가 발생하면 오류 문구를 출력하면서 프로그램이 종료가 됩니다. 그러나 아래와 같이 코드를 작성하면 정상적으로 프로그램이 계속 실행됩니다.

    >>> a = 4
    >>> b = 0

    >>> try:
    ...     a / b
    ... except:
    ...     print("denominator is zero!")

    denominator is zero!

위 코드를 보면 나누는 수가 0이 되어서 `try` 구문 안에서 오류가 발생합니다. 이때, 프로그램이 종료가 되지 않고 `except` 구문안의 코드가 실행이 되고 다음 줄로 계속 진행이 됩니다.

위와 같이 코드를 작성하면 `try` 안에서 발생하는 오류의 종류와 상관없이 오류가 발생하면 `except` 구문 안의 코드가 실행이 됩니다. 이때, 오류의 종류를 명시해 줄 수도 있습니다.

    >>> try:
    ...     a / b
    ... except ZeroDivisionError:
    ...     print("denominator is zero!")

    denominator is zero!

위 코드에서는 `try` 구문 안에서 발생하는 오류가 파이썬 내장 오류인 `ZeroDivisionError`이기 때문에 `except` 에서 명시한 오류와 일치하여 구문 안의 코드가 실행이 되었습니다.

    >>> a = [1, 2, 3]
    >>> try:
    ...     a[3]
    ... except ZeroDivisionError:
    ...     print("denominator is zero!")

    Traceback (most recent call last):
    File "<stdin>", line 2, in <module>
    IndexError: list index out of range

그러나 이 경우에서는 `try` 구문 안에서 발생하는 오류가 `IndexError`이고 `except`에서 명시한 오류와 일치하지 않기 때문에 `except` 구문이 실행되지 않고 오류가 발생하며 프로그램이 종료가 됩니다.

이 경우를 해결하기 위해서는 다음과 같이 코드를 작성할 수 있습니다.

    >>> try:
    ...     a[3]
    ... except IndexError:
    ...     print("out of range!")

    out of range!

#### try ~ finallly

`finally` 구문과 같은 경우 `try` 구문 안에서 오류의 발생 여부와 관계없이 항상 실행됩니다. 만약, 파일을 열어서 작업을 수행하는 프로그램을 생각해보면, 오류의 발생과 관계없이 항상 열었던 파일을 닫아주는 과정이 필요합니다. 즉, 아래와 같은 용례를 생각해 볼 수 있습니다.

    >>> f = open("test.txt", "w")
    >>> try:
    ...     # Do Something
    ... finally:
    ...     f.close()


