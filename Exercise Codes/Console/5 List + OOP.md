# List + OOP
============
using System;
using System.Collections.Generic;

class TaskItem
{
    public string Title { get; set; }
    public bool IsCompleted { get; set; }
}
class Program
{
    static void Main(string[] args)
    {
        List<TaskItem> tasks = new List<TaskItem>();
        bool running = true;

        while (running)
        {
            Console.WriteLine("\n1. Add Task");
            Console.WriteLine("2. Mark Task as Done");
            Console.WriteLine("3. Show Tasks");
            Console.WriteLine("4. Exit");
            Console.Write("Choose: ");

            string choice = Console.ReadLine();

            switch (choice)
            {
                case "1":
                    Console.Write("Enter task: ");
                    tasks.Add(new TaskItem
                    {
                        Title = Console.ReadLine(),
                        IsCompleted = false
                    });
                    break;

                case "2":
                    Console.WriteLine("Enter task number:");
                    for (int i = 0; i < tasks.Count; i++)
                        Console.WriteLine($"{i + 1}. {tasks[i].Title}");
                    }
                    int index = int.Parse(Console.ReadLine()) - 1;
                    if (index >= 0 && index < tasks.Count)
                    {
                        tasks[index].IsCompleted = true;
                    }
                    else
                    {
                        Console.WriteLine("Invalid task number");                     
                    }
                    break;

                case "3":
                    Console.WriteLine("\nTasks:");
                    for (int i = 0; i < tasks.Count; i++)

            }
        }
    }
}