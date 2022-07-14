# Тестовое задание Wargaming/Lesta Studio

---
#### На языке Python реализовать алгоритм (функцию) определения четности целого числа, который будет аналогичен нижеприведенному по функциональности, но отличен по своей сути. Объяснить плюсы и минусы обеих реализаций.

Python example:
```python
def isEven(value): return value % 2 == 0
```

Вариант реализации:
```python
def isEven(value): return value & 1 == 0
```

Используем побитовое "И", тогда любой результат `четное_число И 1 == 0`, что и необходимо для решения задачи.  

Плюс реализации: Простота функции, немного быстрее работа программы  
Минус реализации: Может быть не совсем ясна другому разработчику при чтении кода, также есть разница в скорости выполнения

---
#### На языке Python реализовать минимум по 2 класса реализовывающих циклический буфер FIFO.
I.  
```python
class CycleBuff:
    def __init__(self, size):
        self.size = size
        self.data = []

    def append(self, value):
        if len(self.data) == self.size:
            self.data = self.data[1:]
            self.data.append(value)
        else:
            self.data.append(value)

    def current_data(self):
        return self.data
```
OUTPUT:
```
[1, 2, 3, 4]
[2, 3, 4, 5]
[3, 4, 5, 6]
```

II.  
```python
class AnotherCycleBuff:
    def __init__(self, size):
        self.size = size
        self.data = []
        self.index = 0

    def append(self, value):
        if len(self.data) < self.size:
            self.data.append(value)
        else:
            self.data[self.index] = value
            self.index = (self.index + 1) % self.size

    def current_data(self):
        return self.data
```
OUTPUT:
```
[1, 2, 3, 4]
[5, 2, 3, 4]
[5, 6, 3, 4]
```


---
#### На языке Python реализовать функцию, которая быстрее всего (по процессорным тикам) отсортирует данный ей массив чисел. Массив может быть любого размера со случайным порядком чисел (в том числе и отсортированным). Объяснить почему вы считаете, что функция соответствует заданным критериям.

```
Выбор метода сортировки зависит от поставленной задачи и объема данных.
Нельзя однозначно выбрать самый быстрый способ без знания того, что необходимо обрабатывать.
```
