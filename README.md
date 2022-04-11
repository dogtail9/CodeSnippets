# CodeSnippets

You can download the code snippets on the [Visual Studio Marketplace](https://marketplace.visualstudio.com/items?itemName=Dogtail.DogtailCodeSnippets).

## Arrange Act Assert (aaa)

```C#
// Arrange

// Act

// Assert
```

## Console Banner (cb)

```C#
var operatingSystem = RuntimeInformation.OSDescription;
var environment = app.Environment.EnvironmentName;
var frameworkDescription = RuntimeInformation.FrameworkDescription;
string framing = new string[] { operatingSystem, environment, frameworkDescription }
.OrderByDescending(x => x.Length)
.Select(x => new string('-', x.Length + 13))
.First();
Console.ForegroundColor = ConsoleColor.Green;
Console.WriteLine(framing);
Console.Write("  Framework: ");
Console.WriteLine(frameworkDescription);
Console.Write("Environment: ");
Console.WriteLine(environment);
Console.Write("   Platform: ");
Console.WriteLine(operatingSystem);
Console.WriteLine(framing);
Console.ResetColor();
```

### Result when running the application

```cmd
-----------------------------------------
  Framework: .NET 6.0.3
Environment: Development
   Platform: Microsoft Windows 10.0.17763
-----------------------------------------
```

## Web Banner (wb)

```C#
var urls = builder.WebHost.GetSetting(WebHostDefaults.ServerUrlsKey)?.Replace(";", " ") ?? string.Empty;
var operatingSystem = RuntimeInformation.OSDescription;
var environment = app.Environment.EnvironmentName;
var frameworkDescription = RuntimeInformation.FrameworkDescription;
string framing = new string[] { urls, operatingSystem, environment, frameworkDescription }
.OrderByDescending(x => x.Length)
.Select(x => new string('-', x.Length + 13))
.First();
Console.ForegroundColor = ConsoleColor.Green;
Console.WriteLine(framing);
Console.Write("       Urls: ");
Console.ForegroundColor = ConsoleColor.Blue;
Console.WriteLine(urls);
Console.ForegroundColor = ConsoleColor.Green;
Console.Write("  Framework: ");
Console.WriteLine(frameworkDescription);
Console.Write("Environment: ");
Console.WriteLine(environment);
Console.Write("   Platform: ");
Console.WriteLine(operatingSystem);
Console.WriteLine(framing);
Console.ResetColor();
```

```cmd
-----------------------------------------
       Urls: https://localhost:7254
  Framework: .NET 6.0.3
Environment: Development
   Platform: Microsoft Windows 10.0.17763
-----------------------------------------
```
