# hst-sequential

## Бизнес логика:
Сформировать M результирующих векторов как квадрат максимального значения по каждой строке M исходных квадратных матриц.

## Вариант исполнения:
Последовательная реализация.

## Особенности исполнения:
Считывание данных происходит из бинарного файла;
Данные генерируются утилитой, принимающей в качестве параметров размер данных для обработки в мегабайтах и имя файла;
Программа выполняет бизнес-логику и записывает результат в выходной файл;
В конце файла с результатами сохраняется информация о времени выполнения вычислений и размере обработанных данных.

## Описание алгоритма выполнения бизнес-логики:
1. Для генерации исходных данных используется функция ```GenerateMatricesAndSaveThemToFile()```. 
С помощью ```std::default_random_engine``` определяется количество строк очередной квадратной матрицы, которая затем заполняется произвольными значениями типа double в диапазоне [0, 10] и записывается в бинарный файл ```InputDataFile```. 
Генерация матриц заканчивается после того, как размер файла с данными превысит размер, введенный пользователем.

2. После этого запускается программа-клиент, считывающая сгенерированные матрицы из ```InputDataFile```. В функции ```CalculateMaxElementsSquare()``` над исходными данными выполняются вычисления: для каждой строки i-ой матрицы с помощью функции MaxElement() вычисляется максимальное значение, которое возводится в квадрат и записывается в результирующий i-ый вектор.
3. С помощью ```std::chrono::steady_clock``` определяется время выполнения вычислений, которое записывается в бинарный файл ```ResultsFile``` вместе с результатами вычислений.

## График зависимости времени вычислений от размера исходных данных:
![Снимок экрана 2022-09-24 122329](https://user-images.githubusercontent.com/55412039/192090624-1fbf1665-c189-4300-80f3-f507aac196a8.png)
