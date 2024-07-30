# PowerShell Basics

PowerShell is a versatile scripting language and command-line shell designed for system administration, automation, and configuration management. It allows administrators to automate repetitive tasks, manage systems, and access a wide range of tools and resources.

## Key Concepts

### Cmdlets
Cmdlets are specialized .NET classes that perform specific operations. They follow the naming convention of `Verb-Noun`, such as `Get-Process` or `Set-Item`. Cmdlets are the fundamental building blocks of PowerShell scripts and commands.

### Objects
Unlike traditional shells that output plain text, PowerShell outputs objects. These objects contain data and metadata, allowing for rich interaction and data manipulation. For example, when you use the `Get-Process` cmdlet, it returns objects representing the running processes.

### Pipelining
The pipeline (`|`) is a powerful feature that allows you to pass the output of one cmdlet as input to another. This enables chaining commands to perform complex tasks efficiently. For example, you can list processes and filter by CPU usage:

```powershell
Get-Process | Where-Object { $_.CPU -gt 100 }
```

### Variables
Variables in PowerShell are used to store data, and they are prefixed with the $ symbol. For example:

```powershell
$greeting = "Hello, World!"
Write-Output $greeting
```

### Common Cmdlets
Here are some commonly used cmdlets:

- `Get-Help`: Displays help about cmdlets and concepts.
- `Get-Command`: Lists all available cmdlets, functions, workflows, aliases, and scripts.
- `Get-Process`: Retrieves information about running processes.
- `Get-Service`: Displays the status of services.
- `Set-Item`: Changes the value of an item, such as a registry entry or a file attribute.
- `Get-ChildItem`: Lists the contents of a directory or registry key.