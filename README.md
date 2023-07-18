# Hw2
// Задача 13: Напишите программу, которая выводит третью цифру заданного числа или сообщает, что третьей цифры нет.
// 645 -> 5
// 78 -> третьей цифры нет
// 32679 -> 6

using System;

class Program
{
    static int Prompt(string message)
    {
        Console.Write(message);
        return Convert.ToInt32(Console.ReadLine());
    }

    static int GetThirdRank(int number)
    {
        while (number > 999)
        {
            number /= 10;
        }
        return number % 10;
    }

    static bool ValidateNumber(int number)
    {
        return number >= 100;
    }

    static void Main()
    {
        int num = Prompt("Введите число: ");

        if (!ValidateNumber(num))
        {
            Console.WriteLine("Третьей цифры нет!");
        }
        else
        {
            Console.WriteLine($"Третьей цифрой числа {num} является {GetThirdRank(num)}");
        }
    }
}
