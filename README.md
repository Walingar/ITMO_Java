# Курс «Технологии Java» ИТМО
Tests and problems were taken from [Korneev Georgy site's](http://kgeorgiy.info)

## Запуск тестов
(linux only)

В консоли: `./test.sh {hw#} {easy|hard} {salt}`

По умолчанию salt = ""

## Домашнее задание 4. Implementor

Класс должен реализовывать интерфейс
[Impler](java/info/kgeorgiy/java/advanced/implementor/Impler.java).

Тестирование

 * простой вериант:
    `info.kgeorgiy.java.advanced.implementor.Tester interface <полное имя класса>`
 * сложный вериант:
    `info.kgeorgiy.java.advanced.implementor.Tester class <полное имя класса>`

Исходный код тестов:

* [простой вариант](java/info/kgeorgiy/java/advanced/implementor/BasicInterfaceImplementorTest.java)
* [сложный вариант](java/info/kgeorgiy/java/advanced/implementor/BasicClassImplementorTest.java)


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
