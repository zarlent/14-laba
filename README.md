# 14-laba

## Условие задачи
Каждый вариант оформить в виде отдельной функции, которая возвращает найденного значение и принимает в качестве аргументов – указатель на массив, его размер и необходимые для условий поиска параметры.   
Определение числа изменений знака значений соседних элементов массива.

## 1. Реализация программы

```
#include <stdio.h>
#include <locale.h>

int count(int* arr, int size);

int main() {
    setlocale(LC_CTYPE, "RUS");

    int array[] = { 1, -2, -3, 4, 1, -1 };
    int size = sizeof(array) / sizeof(array[0]);

    printf("Результат: %d\n", count(array, size));

    return 0;
}

int count(int* arr, int size) {
    int count = 0;

    for (int i = 0; i < size - 1; i++) {
        int first = arr[i];
        int second = arr[i + 1];

        if (first > 0 && second < 0) count++;
        else if (first < 0 && second > 0) count++;
    }

    return count;
}
```

## 2. Результаты работы программы
```
Результат: 3
```

## 3. Информация о разработчике

Юрьев Денис [БИЦ-252]
