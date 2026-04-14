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
                        IsCompleted = false
                    });
                    break;

                case "2":
                    for (int i = 0, i < task.Count; i++)
                    {
                        Console.WriteLine($"{i + 1}. {tasks[i].Title}");
                    }
                    if (int.TryParse(Console.ReadLine(), out int index))
                    {
                        index -=1;
                        if (index >= 0 && index < tasks.Count)
                        {
                            tasks[index].IsCompleted = true;
                        }
                    }
                    break;

                case "3":
                    Console.WriteLine("\nTasks: ");
                    for (int i = 0, i < tasks.Count; i++)
                    {
                        var task = tasks[i];
                        Console.WriteLine($"(i + 1). {task.Title} - {(task.IsCompleted ? "Done" :  "Pending")}");
                    }
                    break;

                case "4":
                    SaveTasks(tasks);
                    running = false;
                    break;
            }
        }
    }
    static void SaveTasks(List<TaskItem> tasks)
    {
        List<string> lines = new List<string>();

        foreach (var task in tasks)
        {
            lines.Add($"{task.Title} | {task.IsCompleted}");
        }

        File.WriteAllLines(filePath, lines);
    }

    static List<TaskItem> LoadTasks()
    {
        List<TaskItem> tasks = new List<TaskItem>();

        if (File.Exists(filePath))
        {
            string [] lines = File.ReadAllLines(filePath);

            foreach (var line in lines)
            {
                string [] parts = line.Split('|');

                tasks.Add(new TaskItem
                {
                    Title = parts[0];
                    IsCompleted = bool.Parse(parts[1])
                });
            }
        }
        return tasks;
    }
}