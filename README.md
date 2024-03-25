# Dotmenu

Dotmenu is a straightforward console menu library designed to streamline user interactions in console applications.

## Features

- Create customizable menus.
- Assign keyboard shortcuts to menu options for quicker navigation.
- Edit menu options dynamically during runtime.
- Dynamic menu option text

## Installation

Dotmenu can be added to your project with:

```bash
dotnet add package Natesworks.Dotmenu
```

## Example

```cs
using Natesworks.Dotmenu

class Program
{
    static void Main(string[] args)
    {
        var mainMenu = new Menu()
            .SetPrompt("Main Menu")
            .AddOption(() => "Option 1", () => Console.WriteLine("Option 1 selected"))
            .AddOption(() => "Option 2", () => Console.WriteLine("Option 2 selected"))
            .AddOption(() => "Sub Menu", () => ShowSubMenu());
        while(true)
        {
            mainMenu.Run();
        }
    }

    static void ShowSubMenu()
    {
        var subMenu1 = new Menu()
            .SetPrompt("Sub Menu 1")
            .AddOption(() => "Sub Option 1-1", () => Console.WriteLine("Sub Option 1-1 selected"))
            .AddOption(() => "Sub Option 1-2", () => Console.WriteLine("Sub Option 1-2 selected"))
            .AddOption(() => "Back", () => {});

        subMenu1.Run();
    }
}
```

# Documentation

Explore our wiki sections for guidance [here](https://github.com/dotmenu/dotmenu/wiki)
