# Курс «Технологии Java» ИТМО
Tests and problems were taken from [Korneev Georgy site's](http://kgeorgiy.info)

## Запуск тестов
(bash)

В консоли: `./test.sh {hw#} {easy|hard} {salt}`

По умолчанию salt = ""

## Домашнее задание 8. Параллельный запуск
Условие:

Решение:
* [простой вариант](java/ru/ifmo/rain/rykunov/mapper)
* [сложный вариант](java/ru/ifmo/rain/rykunov/mapper)

Исходный код тестов:

* [простой вариант](java/info/kgeorgiy/java/advanced/mapper/ScalarMapperTest.java)
* [сложный вариант](java/info/kgeorgiy/java/advanced/mapper/ListMapperTest.java)


## Домашнее задание 7. Итеративный параллелизм

Условие:
  1. Реализуйте класс `IterativeParallelism`, который будет обрабатывать списки в несколько потоков.
  2. В простом варианте должны быть реализованы следующие методы:
     * `minimum(threads, list, comparator)` — первый минимум;
     * `maximum(threads, list, comparator)` — первый максимум;
     * `all(threads, list, predicate)` — проверка, что все элементы списка удовлетворяют предикату;
     * `any(threads, list, predicate)` — проверка, что существует элемент списка, удовлетворяющий предикату.
  3. В сложном варианте должны быть дополнительно реализованы следующие методы:
     * `filter(threads, list, predicate)` — вернуть список, содержащий элементы удовлетворяющие предикату;
     * `map(threads, list, function)` — вернуть список, содержащий результаты применения функции;
     * `join(threads, list)` — конкатенация строковых представлений элементов списка.
  4. Во все функции передается параметр `threads` — сколько потоков надо использовать при вычислении. Вы можете рассчитывать, что число потоков не велико.
  5. Не следует рассчитывать на то, что переданные компараторы, предикаты и функции работают быстро.
  6. При выполнении задания нельзя использовать *Concurrency Utilities*.

Решение:
* [простой вариант](java/ru/ifmo/rain/rykunov/mapper)
* [сложный вариант](java/ru/ifmo/rain/rykunov/mapper)

Интерфейсы:
* простой вариант класс должен реализовывать интерфейс [ScalarIP](java/info/kgeorgiy/java/advanced/concurrent/ScalarIP.java).
* сложный вариант класс должен реализовывать интерфейс [ListIP](java/info/kgeorgiy/java/advanced/concurrent/ListIP.java).

Исходный код тестов:

* [простой вариант](java/info/kgeorgiy/java/advanced/concurrent/ScalarIPTest.java)
* [сложный вариант](java/info/kgeorgiy/java/advanced/concurrent/ListIPTest.java)

## Домашнее задание 6. Javadoc

Условие:
  1. Документируйте класс `Implementor` и сопутствующие классы с применением **Javadoc**.
     * Должны быть документированы все классы и все члены классов, в том числе закрытые (`private`).
     * Документация должна генерироваться без предупреждений.
     * Сгенерированная документация должна содержать корректные ссылки на классы стандартной библиотеки.
  2. Для проверки, кроме исходного кода так же должны быть предъявлены:
     * скрипт для генерации документации;
     * сгенерированная документация.

Генерация **Javadoc**: (bash)
  * `./JDCreator.sh` Перед этим сделать скрипт исполняемым.

## Домашнее задание 5. JarImplementor

Условие:
  1. Создайте *.jar*-файл, содержащий скомпилированный `Implementor` и сопутствующие классы.
     * Созданный *.jar*-файл должен запускаться командой java `-jar`.
     * Запускаемый *.jar*-файл должен принимать те же аргументы командной строки, что и класс `Implementor`.
  2. Модифицируйте `Implemetor` так, что бы при запуске с аргументами `-jar имя-класса файл.jar` он генерировал *.jar*-файл 
     с реализацией соответствующего класса (интерфейса).
  3. Для проверки, кроме исходного кода так же должны быть предъявлены:
     * скрипт для создания запускаемого *.jar*-файла, в том числе, исходный код манифеста;
     * запускаемый *.jar*-файл.

Генерация *.jar* файла:
(bash)
  * `./jarCreator.sh` Перед Этим сделать скрипт исполняемым.

Пример запуска:
(bash)
  * `java -jar Implementor.jar java.util.Set`
  * `java -jar Implementor.jar -jar java.util.Set Set.jar`
  

Класс должен реализовывать интерфейс
[JarImpler](java/info/kgeorgiy/java/advanced/implementor/JarImpler.java).

Решение:
* [простой вариант](java/ru/ifmo/rain/rykunov/implementor)

Исходный код тестов:

* [простой вариант](java/info/kgeorgiy/java/advanced/implementor/InterfaceJarImplementorTest.java)
* [сложный вариант](java/info/kgeorgiy/java/advanced/implementor/ClassJarImplementorTest.java)


## Домашнее задание 4. Implementor

Условие:
  1. Реализуйте класс `Implementor`, который будет генерировать реализации классов и интерфейсов.
     * Аргументы командной строки: полное имя класса/интерфейса, для которого требуется сгенерировать реализацию.
     * В результате работы должен быть сгенерирован java-код класса с суффиксом *Impl*, расширяющий (реализующий) указанный класс (интерфейс).
     * Сгенерированный класс должен компилироваться без ошибок.
     * Сгенерированный класс не должен быть абстрактным.
     * Методы сгенерированного класса должны игнорировать свои аргументы и возвращать значения по умолчанию.
  2. В задании выделяются три уровня сложности:
     *  *Простой* — `Implementor` должен уметь реализовывать только интерфейсы (но не классы). Поддержка *generics* не требуется.
     *  *Сложный* — `Implementor` должен уметь реализовывать и классы и интерфейсы. Поддержка *generics* не требуется.
     *  *Бонусный* — `Implementor` должен уметь реализовывать *generic*-классы и интерфейсы. Сгенерированный код должен иметь корректные параметры типов и не порождать *UncheckedWarning*.

Решение:
* [простой вариант](java/ru/ifmo/rain/rykunov/implementor)

Класс должен реализовывать интерфейс
[Impler](java/info/kgeorgiy/java/advanced/implementor/Impler.java).

Исходный код тестов:

* [простой вариант](java/info/kgeorgiy/java/advanced/implementor/InterfaceImplementorTest.java)
* [сложный вариант](java/info/kgeorgiy/java/advanced/implementor/ClassImplementorTest.java)


## Домашнее задание 3. Студенты

Условие:
  1. Разработайте класс `StudentDB`, осуществляющий поиск по базе данных студентов.
     * Класс `StudentDB` должен реализовывать интерфейс `StudentQuery` (простая версия) или `StudentGroupQuery` (сложная версия).
     * Каждый методы должен состоять из ровного одного оператора. При этом длинные операторы надо разбивать на несколько строк.
  2. При выполнении задания следует обратить внимание на:
     * Применение лямбда-выражений и поток.
     * Избавление от повторяющегося кода.

Решение:
  * [простой вариант](java/ru/ifmo/rain/rykunov/student)


Исходный код

 * простой вариант:
    [интерфейс](java/info/kgeorgiy/java/advanced/student/StudentQuery.java),
    [тесты](java/info/kgeorgiy/java/advanced/student/StudentQueryFullTest.java)
 * сложный вариант:
    [интерфейс](java/info/kgeorgiy/java/advanced/student/StudentGroupQuery.java),
    [тесты](java/info/kgeorgiy/java/advanced/student/StudentGroupQueryFullTest.java)


## Домашнее задание 2. ArraySortedSet

Условие:
  1. Разработайте класс `ArraySet`, реализующие неизменяемое упорядоченное множество.
     * Класс `ArraySet` должен реализовывать интерфейс `SortedSet` (упрощенная версия) или `NavigableSet` (усложненная версия).
     * Все операции над множествами должны производиться с максимально возможной асимптотической эффективностью.
  2. При выполнении задания следует обратить внимание на:
     * Применение стандартных коллекций.
     *  Избавление от повторяющегося кода.

Решение:
 * [сложный вариант](java/ru/ifmo/rain/rykunov/arrayset)

Исходный код тестов:

 * [простой вариант](java/info/kgeorgiy/java/advanced/arrayset/SortedSetTest.java)
 * [сложный вариант](java/info/kgeorgiy/java/advanced/arrayset/NavigableSetTest.java)


## Домашнее задание 1. Обход файлов

Условие:

  1. Разработайте класс Walk, осуществляющий подсчет хеш-сумм файлов.
     * Формат запуска `java Walk <входной файл> <выходной файл>`
     * Входной файл содержит список файлов, которые требуется обойти.
     * Выходной файл должен содержать по одной строке для каждого файла. Формат строки:
         `<шестнадцатеричная хеш-сумма> <путь к файлу>`
     * Для подсчета хеш-суммы используйте алгоритм [FNV](https://ru.wikipedia.org/wiki/FNV).
     * Если при чтении файла возникают ошибки, укажите в качестве его хеш-суммы 00000000.
     * Кодировка входного и выходного файлов — `UTF-8`.
     * Размеры файлов могут превышать размер оперативной памяти.
  2. Усложненная версия:
     * Разработайте класс RecursiveWalk, осуществляющий подсчет хеш-сумм файлов в директориях
     * Входной файл содержит список файлов и директорий, которые требуется обойти.
       Обход директорий осуществляется рекурсивно.
  3. При выполнении задания следует обратить внимание на:
     * Дизайн и обработку исключений, диагностику ошибок.
     * Программа должна корректно завершаться даже в случае ошибки.
     * Корректная работа с вводом-выводом.
     * Отсутствие утечки ресурсов.

Решение:
 * [сложный вариант](java/ru/ifmo/rain/rykunov/walk)


Исходный код тестов:

 * [простой вариант](java/info/kgeorgiy/java/advanced/walk/WalkTest.java)
 * [сложный вариант](java/info/kgeorgiy/java/advanced/walk/RecursiveWalkTest.java)
