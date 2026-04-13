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


                    }
            }
        }
    }
}