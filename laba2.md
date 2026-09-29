# Ответы на задачи по Python

## Задача 1

**Вопрос:** `convert_types(data)` — преобразует элементы списка: числа в строки, строки в числа (если возможно), остальные — в строку.

```python
def convert_types(data):
    """Преобразует элементы списка по правилам."""
    result = []
    for item in data:
        if isinstance(item, (int, float)) and not isinstance(item, bool):
            result.append(str(item))
        elif isinstance(item, str):
            try:
                result.append(int(item))
            except ValueError:
                try:
                    result.append(float(item))
                except ValueError:
                    result.append(item)
        else:
            result.append(str(item))
    return result


if __name__ == "__main__":
    print(convert_types([1, "2", "hello", 3.5]))
```

**Вывод:**
```text
['1', 2, 'hello', '3.5']
```

---

## Задача 2

**Вопрос:** `swap_values(a, b)` — меняет значения двух переменных местами без третьей переменной.

```python
def swap_values(a, b):
    """Меняет значения двух переменных местами."""
    a, b = b, a
    return a, b


if __name__ == "__main__":
    print(swap_values(5, 10))
```

**Вывод:**
```text
(10, 5)
```

---

## Задача 3

**Вопрос:** `bool_transform(value)` — возвращает `True`, если значение истинное, и `False` иначе, без `bool()`.

```python
def bool_transform(value):
    """Возвращает True для истинного значения и False иначе."""
    if value:
        return True
    return False


if __name__ == "__main__":
    print(bool_transform(5))
    print(bool_transform(0))
```

**Вывод:**
```text
True
False
```

---

## Задача 4

**Вопрос:** `compound_operations(a, b)` — выполняет составные операции и возвращает список результатов.

```python
def compound_operations(a, b):
    """Выполняет составные операции и возвращает список результатов."""
    results = []

    x = a
    x += b
    results.append(x)

    x = a
    x -= b
    results.append(x)

    x = a
    x *= b
    results.append(x)

    x = a
    x /= b
    results.append(x)

    x = a
    x //= b
    results.append(x)

    x = a
    x %= b
    results.append(x)

    x = a
    x **= b
    results.append(x)

    return results


if __name__ == "__main__":
    print(compound_operations(10, 3))
```

**Вывод:**
```text
[13, 7, 30, 3.3333333333333335, 3, 1, 1000]
```

---

## Задача 5

**Вопрос:** `check_type(value, expected_type)` — проверяет тип значения по имени типа.

```python
def check_type(value, expected_type):
    """Проверяет тип значения по имени типа."""
    return type(value).__name__ == expected_type


if __name__ == "__main__":
    print(check_type(5, "int"))
    print(check_type("5", "int"))
```

**Вывод:**
```text
True
False
```

---

## Задача 6

**Вопрос:** `logical_and(a, b, c)` — возвращает `True`, только если все три аргумента истинные, без `and`.

```python
def logical_and(a, b, c):
    """Возвращает True, если все аргументы истинны, без and."""
    if a:
        if b:
            if c:
                return True
    return False


if __name__ == "__main__":
    print(logical_and(True, 5, "x"))
    print(logical_and(True, 0, "x"))
```

**Вывод:**
```text
True
False
```

---

## Задача 7

**Вопрос:** `logical_or(a, b, c)` — возвращает `True`, если хотя бы один аргумент истинный, без `or`.

```python
def logical_or(a, b, c):
    """Возвращает True, если хотя бы один аргумент истинен, без or."""
    if a:
        return True
    if b:
        return True
    if c:
        return True
    return False


if __name__ == "__main__":
    print(logical_or(0, "", False))
    print(logical_or(0, 5, False))
```

**Вывод:**
```text
False
True
```

---

## Задача 8

**Вопрос:** `is_between(value, low, high)` — проверяет, находится ли значение между границами включительно.

```python
def is_between(value, low, high):
    """Проверяет, находится ли value между low и high включительно."""
    if value >= low and value <= high:
        return True
    return False


if __name__ == "__main__":
    print(is_between(5, 1, 10))
    print(is_between(15, 1, 10))
```

**Вывод:**
```text
True
False
```

---

## Задача 9

**Вопрос:** `print_even_numbers(n)` — выводит все чётные числа от 1 до `n`.

```python
def print_even_numbers(n):
    """Выводит чётные числа от 1 до n."""
    for i in range(2, n + 1, 2):
        print(i)


if __name__ == "__main__":
    print_even_numbers(10)
```

**Вывод:**
```text
2
4
6
8
10
```

---

## Задача 10

**Вопрос:** `countdown_while(n)` — выводит числа от `n` до 1 в обратном порядке.

```python
def countdown_while(n):
    """Выводит числа от n до 1 в обратном порядке."""
    while n >= 1:
        print(n)
        n -= 1


if __name__ == "__main__":
    countdown_while(5)
```

**Вывод:**
```text
5
4
3
2
1
```

---

## Задача 11

**Вопрос:** `skip_multiples(n, multiple)` — выводит числа от 1 до `n`, пропуская кратные `multiple`.

```python
def skip_multiples(n, multiple):
    """Выводит числа от 1 до n, пропуская кратные multiple."""
    for i in range(1, n + 1):
        if i % multiple == 0:
            continue
        print(i)


if __name__ == "__main__":
    skip_multiples(10, 3)
```

**Вывод:**
```text
1
2
4
5
7
8
10
```

---

## Задача 12

**Вопрос:** `if_elif_else_chain(x)` — возвращает `positive`, `negative` или `zero`.

```python
def if_elif_else_chain(x):
    """Возвращает positive, negative или zero."""
    if x > 0:
        return "positive"
    elif x < 0:
        return "negative"
    else:
        return "zero"


if __name__ == "__main__":
    print(if_elif_else_chain(5))
    print(if_elif_else_chain(-3))
    print(if_elif_else_chain(0))
```

**Вывод:**
```text
positive
negative
zero
```

---

## Задача 13

**Вопрос:** `abs_value(x)` — возвращает абсолютное значение без `abs()`.

```python
def abs_value(x):
    """Возвращает абсолютное значение без abs()."""
    if x < 0:
        return -x
    return x


if __name__ == "__main__":
    print(abs_value(-5))
    print(abs_value(3))
```

**Вывод:**
```text
5
3
```

---

## Задача 14

**Вопрос:** `binary_representation(n)` — возвращает двоичное представление числа без `bin()`.

```python
def binary_representation(n):
    """Возвращает двоичное представление числа без bin()."""
    if n == 0:
        return "0"

    result = ""
    while n > 0:
        result = str(n % 2) + result
        n //= 2
    return result


if __name__ == "__main__":
    print(binary_representation(10))
    print(binary_representation(0))
```

**Вывод:**
```text
1010
0
```

---

## Задача 15

**Вопрос:** `custom_round(number, digits)` — округляет число до `digits` знаков без `round()`.

```python
def custom_round(number, digits):
    """Округляет число до digits знаков после запятой без round()."""
    factor = 10 ** digits
    scaled = number * factor

    if scaled >= 0:
        rounded = int(scaled + 0.5)
    else:
        rounded = int(scaled - 0.5)

    return rounded / factor


if __name__ == "__main__":
    print(custom_round(3.14159, 2))
    print(custom_round(2.5, 0))
```

**Вывод:**
```text
3.14
3.0
```

---

## Задача 16

**Вопрос:** `find_max_min(numbers)` — возвращает `(max_value, min_value)` без `max()` и `min()`.

```python
def find_max_min(numbers):
    """Возвращает (max, min) без max() и min()."""
    max_value = numbers[0]
    min_value = numbers[0]

    for number in numbers:
        if number > max_value:
            max_value = number
        if number < min_value:
            min_value = number

    return max_value, min_value


if __name__ == "__main__":
    print(find_max_min([3, 7, 1, 9, 2]))
```

**Вывод:**
```text
(9, 1)
```

---

## Задача 17

**Вопрос:** `all_true(iterable)` — возвращает `True`, если все элементы истинные, без `all()`.

```python
def all_true(iterable):
    """Возвращает True, если все элементы истинны, без all()."""
    for item in iterable:
        if not item:
            return False
    return True


if __name__ == "__main__":
    print(all_true([1, 2, 3]))
    print(all_true([1, 0, 3]))
```

**Вывод:**
```text
True
False
```

---

## Задача 18

**Вопрос:** `any_true(iterable)` — возвращает `True`, если хотя бы один элемент истинный, без `any()`.

```python
def any_true(iterable):
    """Возвращает True, если хотя бы один элемент истинен, без any()."""
    for item in iterable:
        if item:
            return True
    return False


if __name__ == "__main__":
    print(any_true([0, "", False]))
    print(any_true([0, 5, False]))
```

**Вывод:**
```text
False
True
```

---

## Задача 19

**Вопрос:** `custom_enumerate(sequence, start=0)` — возвращает список кортежей `(index, element)` без `enumerate()`.

```python
def custom_enumerate(sequence, start=0):
    """Возвращает список кортежей (index, element)."""
    result = []
    index = start

    for element in sequence:
        result.append((index, element))
        index += 1

    return result


if __name__ == "__main__":
    print(custom_enumerate(["a", "b", "c"], start=1))
```

**Вывод:**
```text
[(1, 'a'), (2, 'b'), (3, 'c')]
```

---

## Задача 20

**Вопрос:** `custom_filter(func, iterable)` — возвращает список элементов, для которых `func` истинна, без `filter()`.

```python
def custom_filter(func, iterable):
    """Возвращает список элементов, для которых func истинна."""
    result = []
    for element in iterable:
        if func(element):
            result.append(element)
    return result


if __name__ == "__main__":
    print(custom_filter(lambda x: x % 2 == 0, [1, 2, 3, 4, 5]))
```

**Вывод:**
```text
[2, 4]
```

---

## Задача 21

**Вопрос:** `custom_map(func, iterable)` — применяет `func` к каждому элементу без `map()`.

```python
def custom_map(func, iterable):
    """Применяет func к каждому элементу и возвращает список результатов."""
    result = []
    for element in iterable:
        result.append(func(element))
    return result


if __name__ == "__main__":
    print(custom_map(lambda x: x * 2, [1, 2, 3]))
```

**Вывод:**
```text
[2, 4, 6]
```

---

## Задача 22

**Вопрос:** `custom_zip(list1, list2)` — возвращает список кортежей из пар элементов без `zip()`.

```python
def custom_zip(list1, list2):
    """Возвращает список кортежей из пар элементов."""
    result = []
    for i in range(min(len(list1), len(list2))):
        result.append((list1[i], list2[i]))
    return result


if __name__ == "__main__":
    print(custom_zip([1, 2, 3], ["a", "b", "c"]))
```

**Вывод:**
```text
[(1, 'a'), (2, 'b'), (3, 'c')]
```

---

## Задача 23

**Вопрос:** `custom_reversed(sequence)` — возвращает развёрнутый список без `reversed()` и срезов.

```python
def custom_reversed(sequence):
    """Возвращает развёрнутый список без reversed() и срезов."""
    result = []
    for i in range(len(sequence) - 1, -1, -1):
        result.append(sequence[i])
    return result


if __name__ == "__main__":
    print(custom_reversed([1, 2, 3, 4]))
```

**Вывод:**
```text
[4, 3, 2, 1]
```

---

## Задача 24

**Вопрос:** `custom_sorted(iterable, reverse=False)` — сортирует список без `sorted()` и `.sort()`.

```python
def custom_sorted(iterable, reverse=False):
    """Возвращает отсортированный список (пузырьковая сортировка)."""
    items = list(iterable)
    n = len(items)

    for i in range(n):
        for j in range(0, n - i - 1):
            if reverse:
                if items[j] < items[j + 1]:
                    items[j], items[j + 1] = items[j + 1], items[j]
            else:
                if items[j] > items[j + 1]:
                    items[j], items[j + 1] = items[j + 1], items[j]

    return items


if __name__ == "__main__":
    print(custom_sorted([3, 1, 4, 1, 5]))
    print(custom_sorted([3, 1, 4], reverse=True))
```

**Вывод:**
```text
[1, 1, 3, 4, 5]
[4, 3, 1]
```

---

## Задача 25

**Вопрос:** `sum_digits(n)` — возвращает сумму цифр числа через `while`.

```python
def sum_digits(n):
    """Возвращает сумму цифр числа."""
    n = abs(n)
    total = 0

    while n > 0:
        total += n % 10
        n //= 10

    return total


if __name__ == "__main__":
    print(sum_digits(1234))
    print(sum_digits(99))
```

**Вывод:**
```text
10
18
```

---

## Задача 26

**Вопрос:** `count_vowels(text)` — подсчитывает количество гласных букв без учёта регистра.

```python
def count_vowels(text):
    """Подсчитывает количество гласных букв в строке."""
    vowels = "aeiouAEIOU"
    count = 0

    for char in text:
        if char in vowels:
            count += 1

    return count


if __name__ == "__main__":
    print(count_vowels("Hello World"))
    print(count_vowels("Python"))
```

**Вывод:**
```text
3
1
```

---

## Задача 27

**Вопрос:** `power(base, exp)` — возводит число в степень без `**` и `pow()`.

```python
def power(base, exp):
    """Возводит base в степень exp без ** и pow()."""
    if exp < 0:
        return 1 / power(base, -exp)

    result = 1
    for _ in range(exp):
        result *= base
    return result


if __name__ == "__main__":
    print(power(2, 5))
    print(power(3, 3))
```

**Вывод:**
```text
32
27
```

---

## Задача 28

**Вопрос:** `is_prime(n)` — проверяет, является ли число простым.

```python
import math


def is_prime(n):
    """Проверяет, является ли число простым."""
    if n < 2:
        return False

    for i in range(2, int(math.sqrt(n)) + 1):
        if n % i == 0:
            return False

    return True


if __name__ == "__main__":
    print(is_prime(17))
    print(is_prime(18))
```

**Вывод:**
```text
True
False
```

---

## Задача 29

**Вопрос:** `factorial(n)` — вычисляет факториал числа.

```python
def factorial(n):
    """Вычисляет факториал числа."""
    result = 1
    for i in range(2, n + 1):
        result *= i
    return result


if __name__ == "__main__":
    print(factorial(5))
    print(factorial(0))
```

**Вывод:**
```text
120
1
```

---

## Задача 30

**Вопрос:** `fibonacci(n)` — возвращает n-е число Фибоначчи.

```python
def fibonacci(n):
    """Возвращает n-е число Фибоначчи."""
    if n < 2:
        return n

    a, b = 0, 1
    for _ in range(2, n + 1):
        a, b = b, a + b

    return b


if __name__ == "__main__":
    print(fibonacci(10))
    print(fibonacci(0))
    print(fibonacci(1))
```

**Вывод:**
```text
55
0
1
```
