# Лабораторная Работа №3. Разработка многопоточного приложения в ОС Windows
## Цель работы
Знакомство с многопоточным программированием и методами синхронизации потоков средствами Windows API.

## Задание
1.	Вычислить номер варианта задания как остаток от деления порядкового номера студента по списку в журнале на количество вариантов заданий. Если остаток равен нулю, необходимо брать последнее задание.
2.	Выбрать граф запуска потоков соответственно варианту задания. Вершины графа являются точками запуска/завершения потоков, дугами обозначены сами потоки, длину дуги следует интерпретировать как ориентировочное время выполнения потока.
3.	Самостоятельно выделить на графе три группы потоков. Первая группа не синхронизирована, вторая – синхронизирована мьютексом (захватывает мьютекс на время выполнения), третья – синхронизирована семафорами (передает управление другому потоку после каждой итерации).
4.	Реализовать последовательно-параллельный запуск потоков в ОС Windows с использованием средств Windows API для запуска и синхронизации потоков. Запрещается использовать какие-либо библиотеки и модули, решающие задачу кроссплатформенной разработки многопоточных приложений (std::thread, Qt Thread, Boost Thread и т.п.).  

В процессе своей работы каждый поток выводит свою букву в консоль. Оценка правильности выполнения лабораторной работы осуществляется следующим образом. Если потоки **a** и **b** согласно графу должны выполняться параллельно, то в консоли должна присутствовать последовательность вида **abababab** (или схожая, например, **aabbba**); если задачи выполняются последовательно, то в консоли присутствует последовательность вида **aaaaabbbbbb**, причем после появления первой буквы **b**, буква **a** больше не должна появиться в консоли. Количество букв, выводимых каждым потоком в консоль, должно быть пропорционально длине дуги, соответствующей данному потоку на графе.

## Содержание отчета
- Титульный лист 
- Цель работы
- Задание на лабораторную работу
- Граф запуска потоков
- Результат выполнения работы
- Исходный код программы с комментариями
- Выводы

## Варианты графов запуска потоков

| Номер варианта  | Граф запуска потоков |
| --- | --- |
| 1   | ![Граф запуска потоков №1](thread_graphs/1.png "Граф запуска потоков №1")  |
| 2   | ![Граф запуска потоков №2](thread_graphs/2.png "Граф запуска потоков №2")  |
| 3   | ![Граф запуска потоков №3](thread_graphs/3.png "Граф запуска потоков №3")  |
| 4   | ![Граф запуска потоков №4](thread_graphs/4.png "Граф запуска потоков №4")  |
| 5   | ![Граф запуска потоков №5](thread_graphs/5.png "Граф запуска потоков №5")  |
| 6   | ![Граф запуска потоков №6](thread_graphs/6.png "Граф запуска потоков №6")  |
| 7   | ![Граф запуска потоков №7](thread_graphs/7.png "Граф запуска потоков №7")  |
| 8   | ![Граф запуска потоков №8](thread_graphs/8.png "Граф запуска потоков №8")  |
| 9   | ![Граф запуска потоков №9](thread_graphs/9.png "Граф запуска потоков №9")  |
| 10  | ![Граф запуска потоков №10](thread_graphs/10.png "Граф запуска потоков №10")  |
| 11  | ![Граф запуска потоков №11](thread_graphs/11.png "Граф запуска потоков №11")  |
| 12  | ![Граф запуска потоков №12](thread_graphs/12.png "Граф запуска потоков №12")  |
| 13  | ![Граф запуска потоков №13](thread_graphs/13.png "Граф запуска потоков №13")  |
| 14  | ![Граф запуска потоков №14](thread_graphs/14.png "Граф запуска потоков №14")  |
| 15  | ![Граф запуска потоков №15](thread_graphs/15.png "Граф запуска потоков №15")  |
| 16  | ![Граф запуска потоков №16](thread_graphs/16.png "Граф запуска потоков №16")  |
| 17  | ![Граф запуска потоков №17](thread_graphs/17.png "Граф запуска потоков №17")  |
| 18  | ![Граф запуска потоков №18](thread_graphs/18.png "Граф запуска потоков №18")  |
| 19  | ![Граф запуска потоков №19](thread_graphs/19.png "Граф запуска потоков №19")  |
| 20  | ![Граф запуска потоков №20](thread_graphs/20.png "Граф запуска потоков №20")  |

## Вопросы
Электронный адрес для связи: m.polyak [собачка] guap [точка] ru
