
![CODE INFO](2023-10-15_19-36-18.png)

# Код программы:

```cs

// Задача:
// Написать программу, которая из имеющегося массива строк формирует новый массив из строк, 
// длина которых меньше, либо равна 3 символам. Первоначальный массив можно ввести с клавиатуры,
// либо задать на старте выполнения алгоритма. При решении не рекомендуется пользоваться коллекциями,
// лучше обойтись исключительно массивами.

// Примеры:
// [“Hello”, “2”, “world”, “:-)”] → [“2”, “:-)”]
// [“1234”, “1567”, “-2”, “computer science”] → [“-2”]
// [“Russia”, “Denmark”, “Kazan”] → []

class Program
{
    static void Main()
    {
        Constructor();
        string[] array = new string[] { };

        string fromText = ReadInput("ВВЕДИТЕ КОМАНДУ: ");
        switch (fromText)
        {
            case "1":
                array = new string[] { "Hello", "2", "world", ":-)" };
                break;
            case "2":
                array = new string[] { "1234", "1567", "-2", "computer science" };
                break;
            case "3":
                array = new string[] { "Russia", "Denmark", "Kazan" };
                break;
            default:
                Console.WriteLine($"{fromText} - Некорректная команда");
                break;
        }

        var newArray = array.Where(s => s.Length <= 3).ToArray();

        PrintArray(array);
        Console.Write("→ ");
        PrintArray(newArray);
    }

    static void Constructor()
    {
        Console.WriteLine();
        Console.WriteLine("1 – ИСПОЛЬЗОВАТЬ МАССИВ: [“Hello”, “2”, “world”, “:-)”]");
        Console.WriteLine("2 – ИСПОЛЬЗОВАТЬ МАССИВ: [“1234”, “1567”, “-2”, “computer science”]");
        Console.WriteLine("3 – ИСПОЛЬЗОВАТЬ МАССИВ: [“Russia”, “Denmark”, “Kazan”]");
        Console.WriteLine();
    }

    static string ReadInput(string list)
    {
        Console.Write(list);
        return Console.ReadLine()!;
    }

    static void PrintArray(string[] array)
    {
        Console.Write("[ ");
        for (int i = 0; i < array.Length; i++)
        {
           
        Console.Write($"“{array[i]}” ");
    }
    Console.Write("] ");
    }
}
```
