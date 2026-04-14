# To Do App
===========
using System;
using System.Collections.Generic;
using System.IO;

class TaskItem
{
    public string Title { get; set; }
    pbulic bool IsCompleted { get; set; }
}

class Program 
{
    static string filePath = "tasks.txt";

    static void Main(string[] args)
    {
        List<TaskItem> tasks = LoadTasks();
        bool running = true; 

        while (running)
        {
            Console.WriteLine("\n1. Add Task");
            Console.WriteLine("\n2. Mark Task as Done");
            Console.WriteLine("\n3. Show Tasks ");
            Console.WriteLine("\n4. Exit");

            Console.Write("Choose: ");
            string choice = Console.ReadLine();

            switch (choice)
            {
                case "1":
                    Console.Write("Enter task: ");
                    tasks.Add(new TaskItem
                    {
                        Title = Console.ReadLine(),
                    });
                    
            }
        }
    }
}