# Will's First CS193 Homework

Things I like about CS193:
- use of git
- use of latex
- use of markdown

My favourite chunk of code:
```csharp
using System;
using CLICarry;

class Program
{
    public static void Main(string[] args)
    {
        CLIManager.Run<Example>(args);
    }
}

class Example : CLI
{
    void CLI.Error(CLICarry.ErrorContext context)
    {
        Console.WriteLine("An error has occurred!");
    }

    [Command("hello")]
    public void Hello(CommandArgs args)
    {
        Console.WriteLine("Hello!");
    }

    [Command("echo", "message", FlagValueType.String)]
    public void Echo(CommandArgs args)
    {
        if (!args.Flags.HasFlag("message"))
        {
            Console.WriteLine("Provide a message!");
        }
        else
        {
            Console.WriteLine(args.Flags["message"].Value);
        }
    }
}

```

It is a really heavy sort of framework for parsing input. I got tired of writing the same parser whenever I made CLI tools so I decided to make a reuseable system for parsing everything. I love writing code to simplify menial operations.

ok bye
