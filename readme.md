Алгоритм решения:
Делаем перебор значений из исходного массива
Проверяем каждое значение из массива на соответствие условию: длина строки меньше или равна трем.
Если строка удовлетворяет условию кладем значение в новый массив.
Повторяем пункты 2 и 3 до тех пор пока не достигнем конца исходного массива.Возвращаем новый заполненый массив как результат.


 Блок схема алгоитм ![Схема Итог](https://user-images.githubusercontent.com/122878791/233768253-ae6f9192-5561-40f5-82fc-a46ce0780d6c.jpg)

using System;
using static System.Console;

Clear();

string[] array = AskArray();
string[] result = FindLessThan(array, 3);
WriteLine($"[{string.Join(", ", array)}] -> [{string.Join(", ", result)}]");

string[] FindLessThan(string[] input, int n) {
    string[] output = new string[CountLessThan(input, n)];

    for(int i = 0, j = 0; i < input.Length; i++) {
        if(input[i].Length <= n) {
            output[j] = input[i];
            j++;
        }
    }

    return output;
}

int CountLessThan(string[] input, int n) {
    int count = 0;

    for(int i = 0; i < input.Length; i++) {
        if(input[i].Length <= n) {
            count++;
        }
    }

    return count;
}

string[] AskArray() {
    Write("Введите значения через пробел: ");
    return ReadLine().Split(" ");
}
