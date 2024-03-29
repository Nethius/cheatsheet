1. [Оглавление](README.md)
1. [Общее](#1)
    1. [Алгоритмическая сложность](#1.1)
1. [Структуры данных](#2)
    1. [Общее про деревья](#2.0)
    1. [Список](#2.1)
    1. [Очередь](#2.2)
    1. [Множество](#2.3)
    1. [Map](#2.4)
    1. [Хэш-таблица](#2.5)
    1. [Стек](#2.6)
    1. [Куча](#2.7)
    1. [Двоичная куча](#2.8)
    1. [Двоичное дерево поиска](#2.9)
    1. [Префиксное дерево](#2.10)
    1. [Графы](#2.11)
    1. [Quadtree](#2.12)
    1. [Красно-черное дерево](#2.13)
1. [Алгоритмы сортировки](#3)
    1. [Быстрая сортировка](#3.1)
    1. [Сортировка вставками](#3.2)
    1. [Сортировка выбором](#3.3)
    1. [Сортировка пузырьком](#3.4)
1. [Алгоритмы поиска](#4)
    1. [Бинарный поиск](#4.1)
    1. [Поиск в глубину](#4.2)
    1. [Поиск в ширину](#4.3)
1. [Алгоритмы кэширования](#5)
    1. [LRU (least recently used)](#5.1)
    1. [MRU (most recently used)](#5.2)

* **Общее**: <a name="1"></a>
    * **Алгоритмическая сложность**: <a name="1.1"></a> как определить сложность алгоритма 
        * **Константная O(1)**
        * **Логарифмическая О(log n)**
        * **Линейное O(n)**
        * **Линейно-логарифмическое (O(n log(n)))**
        * **Квадратическая (O(n<sup>2</sup>))**
        * Если алгоритм имеет сложность _ тогда его эффективность _
            * (о малое) o(n) - < n
            * (О большое) O(n) - <= n
            * (Тета) Θ(n) - = n
            * (Омега большое) Ω(n) - >= n
            * (Омега малое) ω(n) - > n
* **Структуры данных**: <a name="2"></a> https://proglib.io/p/data-structures
    * **Общее про деревья**: <a name="2.0"></a> 
        * Высота дерева - 
    * **Список**: <a name="2.1"></a>
    * **Очередь**: <a name="2.2"></a>
    * **Множество**: <a name="2.3"></a>
    * **Map**: <a name="2.4"></a>
    * **Хэш-таблица**: <a name="2.5"></a>
    * **Стэк**: <a name="2.6"></a>
        * Стэк область память выделяемая в полном объеме, при создании процесса (программы). Работает в порядке LIFO (Last In, First Out).
    * **Куча**: <a name="2.7"></a>
        * Для выделения память из кучи происходит обращение к ОС
    * **Двоичная куча**: <a name="2.8"></a> Это двоичное дерево, обладающее дополнительными свойствами 
        * Значение любого узла не меньше (или не больше), чем значения у его потомков.
        * Глубина всех узлов отличается не более, чем на 1 уровень.
        * Последний слой заполняется слева направо без пропусков.
    * **Двоичное дерево поиска**: <a name="2.9"></a> Это двоичное дерево, обладающее дополнительными свойствами 
        * У всех узлов левого поддерева узла Х, значения меньше, чем у узла Х. 
        * У всех узлов правого поддерева узла Х, значения больше, чем у узла Х.
    * **Префиксное дерево**: <a name="2.10"></a>
    * **Графы**: <a name="2.11"></a>
    * **Quadtree**: <a name="2.12"></a> #TODO
    * **Красно-черное дерево**: <a name="2.13"></a> #TODO
* **Алгоритмы сортировки**: <a name="3"></a>
    * **Быстрая сортировка**: <a name="3.1"></a>
        * Выбрать из массива опорный элемент.
        * Взять два указателя, которые идут от начала и конца массива, до тех пор, пока не встретят элемент больше и меньше опорного.
        * Поменять элементы местами и продолжить следование, пока указатели не пересекутся.
        * При пересечении найдена позиция в массиве для опорного элемента.
        * Рекурсивно повторить алгоритм для правого и левого отрезка.
        * Алгоритмическая сложность - **линейно-логарифмическое (O(n log(n)))**, в худшем случае **квадратическая (O(n<sup>2</sup>))**, при выборе опорным наименьший, либо наибольший элемент.
    * **Сортировка вставками**: <a name="3.2"></a>
        * В начале работы алгоритма, отсортированная последовательность пуста.
        * Поэлементно считываем массив и вставляем на нужную позицию в отсортированную последовательность.
        * Алгоритмическая сложность - в среднем **квадратичная**, в лучшем случае **линейная** (При уже отсортированном массиве).
        * Алгоритм можно улучшить, добавив бинарный поиск в момент вставки в отсортированную последовательность.
    * **Сортировка выбором**: <a name="3.3"></a>
        * Проходим по всему массиву и находим наименьший элемент.
        * Меняем его с первым элементом массива, повторяем для оставшихся элементов.
        * Алгоритмическая сложность - **квадратичная**.
    * **Сортировка пузырьком**: <a name="3.4"></a>
        * Итеративно проходим по массиву и меняем "пары" значений, до тех пор, пока они не будут отсортированы.
        * Алгоритмическая сложность: **квадратичная**.
* **Алгоритмы поиска**: <a name="4"></a>
    * **Бинарный поиск**: <a name="4.1"></a> #TODO
    * **Поиск в глубину**: <a name="4.2"></a> #TODO
    * **Поиск в ширину**: <a name="4.3"></a> #TODO
* **Алгоритмы кэширования**: <a name="5"></a>
    * **LRU (least recently used)**: <a name="5.1"></a> Вытеснение давно неиспользуемых элементов. Реализуется, как вариант, очередью с приоритетами, при добавлении элемента в заполненную очередь, из неё убирается самый старый элемент. В таком виде сложность **логарифмическая**.
    * **MRU (most recently used)**: <a name="5.2"></a> #TODO