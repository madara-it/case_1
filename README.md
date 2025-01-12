import numpy as np


def sum_negative_elements(arr):
    # Проверка, что массив не пуст
    if arr.size == 0:
        return "Массив пуст."

    # Находим максимальный и минимальные значения в массиве
    max_value = np.max(arr)
    min_value = np.min(arr)

    # Если максимальное и минимальное значения равны, возвращаем 0
    if max_value == min_value:
        return 0

    # Выделяем элементы, расположенные между максимальным и минимальным значением, и оставляем только отрицательные
    negative_elements = arr[(arr < 0) & (arr > min_value) & (arr < max_value)]

    # Суммирование отрицательных элементов
    sum_negative = np.sum(negative_elements)

    return sum_negative


# Пример использования функции
if __name__ == "__main__":
    N = int(input("Введите размерность массива: "))
    arr = np.array([int(input(f"Введите {i + 1}ое значение: ")) for i in range(N)])

    print(
        f"Сумма отрицательных элементов, расположенных между максимальным и минимальным значением: {sum_negative_elements(arr)}")
