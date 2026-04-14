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
    }
}