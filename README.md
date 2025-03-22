## Тема лабораторной работы
 Лабораторная работа 2- Указатели, арифметика указателей
## Постановка задачи 1
Внутри функции int main(void) { /*...*/ } определите указатель double ***pointer = NULL;. Инициализируйте этот указатель адресом другого указателя типа double **, который указывает на переменную double *, которая указывает на double. Используйте pointer для записи и чтения значения 2.0 в сегмент оперативной памяти для double.
Требования:
- Используйте функции типа *alloc(...) для выделения оперативной памяти под динамические объекты double **, double * и double.
- Запишите и выведите число, указанное в блоке double на диаграмме, на экран, используя указатель double ***pointer = NULL;.
- Используйте функцию free(...) для освобождения оперативной памяти, выделенной под динамические объекты с применением переменной pointer.
## Математическая модель
-
## Список идентификаторов

| Имя        | Тип       | Смысл                                         |
| ---------- | --------- | --------------------------------------------- |
| pointer    | double*** | Указатель на указатель на указатель на double |
| *pointer   | double**  | Указатель на указатель на double              |
| **pointer  | double*   | Указатель на double                           |
| ***pointer | double    | Значение double (2.0)                         |
## Код программы
```C
#include <stdlib.h>
#include <stdio.h>

int main(void) {
    double ***pointer = NULL;

    pointer = (double***)malloc(sizeof(double**));
    *pointer = (double**)malloc(sizeof(double*));
    **pointer = (double*)malloc(sizeof(double));

    ***pointer = 2.0;
    printf("Значение: %lf\n", ***pointer);

    free(**pointer);
    free(*pointer);
    free(pointer);

    return 0;
}
```
## Результаты выполненной работы
[https://imgur.com/a/rnQcIyI](https://i.imgur.com/MRgpvz8.png)

## Постановка задачи 2
Напишите программу, которая складывает два числа с использованием указателей на эти числа.
## Математическая модель
$$
sum = a + b
$$
## Список идентификаторов
| Имя   | Тип  | Смысл                     |
| ----- | ---- | ------------------------- |
| a     | int  | 1-е введённое число       |
| b     | int  | 2-е введённое число       |
| ptr_a | int* | Указатель на переменную a |
| ptr_b | int* | Указатель на переменную b |
| sum   | int  | Сумма                     |
## Код программы
```C
#include <stdio.h>

int main() {
    int a, b;
    int *ptr_a = &a, *ptr_b = &b;

    printf("Введите первое число: ");
    scanf("%d", ptr_a);
    printf("Введите второе число: ");
    scanf("%d", ptr_b);

    int sum = *ptr_a + *ptr_b;
    printf("Сумма: %d\n", sum);

    return 0;
}
```
## Результаты выполненной работы
[https://imgur.com/oaNDh6C](https://i.imgur.com/oaNDh6C.png)

## Постановка задачи 3
Напишите программу, которая находит максимальное число из двух чисел, используя указатели на эти числа.
## Математическая модель
-
## Список идентификаторов
| Имя   | Тип  | Смысл                     |
| ----- | ---- | ------------------------- |
| a     | int  | 1-е введённое число       |
| b     | int  | 2-е введённое число       |
| ptr_a | int* | Указатель на переменную a |
| ptr_b | int* | Указатель на переменную b |
## Код программы
```C
#include <stdio.h>

int main() {
    int a, b;
    int *ptr_a = &a, *ptr_b = &b;

    printf("Введите первое число: ");
    scanf("%d", ptr_a);
    printf("Введите второе число: ");
    scanf("%d", ptr_b);
    
    if (*ptr_a < *ptr_b){
        printf("Число b больше");
    }
    else if (*ptr_a > *ptr_b){
        printf("Число a больше");
    }
    else{
        printf("Числа a и b равны");
    }
    return 0;
}
```
## Результаты выполненной работы
[https://imgur.com/BSiOYQW](https://i.imgur.com/BSiOYQW.png)
## Постановка задачи 4
Напишите программу, которая создаёт одномерный динамический массив из чисел с плавающей точкой двойной точности, заполняет его значениями с клавиатуры и распечатывает все элементы этого массива, используя арифметику указателей (оператор +), а не оператор доступа к элементу массива [].
## Математическая модель
## Список идентификаторов
| Имя | Тип | Смысл |
| --- | --- | ----- |
## Код программы
```C

```
## Результаты выполненной работы

## Информация о студенте
Иванов ФВ, 1 курс, ИВТ-1.2
