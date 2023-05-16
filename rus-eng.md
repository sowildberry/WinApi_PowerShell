# Способы взаимодействия PowerShell c Windows API

PowerShell — это средство автоматизации, которое выглядит, как командная строка, имеет скриптовый язык и платформу для управления конфигурацией. С его помощью можно взаимодействовать с операционной системой машины. В данной статье будет рассмотрено взаимодействие PowerShell с ОС Windows через Windows API.

PowerShell может использовать Windows API для выполнения различных задач, например: 
* Для создания, удаления и изменение файлов и папок
* Для управления службами и процессами 
* Для изменения настроек реестра
* Для создания пользовательских интерфейсов, использующих функции Windows API для взаимодействия с операционной системой.

PowerShell может вызывать функции Windows API напрямую из своих скриптов или использовать модули, которые предоставляют интерфейс для работы с определенными функциями Windows API.

Взаимодействие PowerShell и Windows API позволяет автоматизировать задачи, создавать пользовательские приложения и управлять системой с помощью скриптов.

Существуют разные способы взаимодействия PowerShell с Windows API, каждый из которых подходит под определенные задачи и инструменты. В этой статье будут рассмотрены основные:

* Модули PowerShell:  
* * [Модуль PowerShellWin32API](#Модуль-PowerShellWin32API) — набор функций для работы с файлами, папками, процессами и пр.
* * [Модуль P/Invoke](#Модуль-PInvoke) — для вызова функций из библиотек Windows API.
* [Командлеты PowerShell](#Командлеты-PowerShell) — для получения доступа к специфическим функциям Windows API.
* [Скрипты PowerShell](#Скрипты-PowerShell)  — для вызова Windows API через функции-обертки.
* [COM-объекты](#COM-объекты) — для использования объектов и методов, которые доступны через COM-интерфейс.
* [.NET Framework](#NET-Framework) — для использования классов и методов **.NET Framework**.
* [Windows Management Instrumentation](#WMI), или WMI — для получения информацию о системе. С помощью PowerShell можно управлять системой и отслеживать ее состояние.
* [PowerShell Remoting](#PowerShell-Remoting) — для запуска команд на удаленных компьютерах.

## The PowerShellWin32API module 
The PowerShellWin32API module is a set of functions which you need to work with files, folders, registers, processes, services and other elements of Windows OS.

To use the module:

1. Install the module using the command:
```powershell
Install-Module PowerShellWin32API
```
**Attention! To install the module, use PowerShell as an Administrator.**

2.  Import the module into PowerShell:
```powershell
Import-Module PowerShellWin32API
```

Done, installation is complete and the module is ready to work. Now you can use the module's functions for interaction with Windows API.

### Examples

Let us consider at a few examples of using module's functions for interaction with Windows API.

#### Creating window
```powershell
# Create window
$window = New-Object Win32API.Window
$window.Create("My Window", 400, 300)

# Show window
$window.Show()

# Wait until the windows's close
while ($window.IsAlive()) {
    Start-Sleep -Milliseconds 100
}
```
In the end you will get a window named "My Window" and the size of 400x300 px. This window will appear on the screen. And the script will wait until the user closes the window.

#### Creating file
```powershell
# Create file
$handle = CreateFile -FilePath "C:\test.txt" -DesiredAccess Write

# Write a data in a file
WriteFile -Handle $handle -Data "Hello, World!"

# Close file
CloseHandle -Handle $handle

# File copy
CopyFile -SourcePath "C:\test.txt" -DestinationPath "C:\test_copy.txt"

# Move file
MoveFile -SourcePath "C:\test.txt" -DestinationPath "D:\test.txt"

# Remove file
DeleteFile -FilePath "C:\test_copy.txt"
```
## Модуль P/Invoke 
Для вызова функций из библиотек Windows API.
### Примеры использования
```powershell
```
## Командлеты PowerShell
Для получения доступа к специфическим функциям Windows API.
### Примеры использования
```powershell
```
## Скрипты PowerShell
Для вызова Windows API через функции-обертки.
### Примеры использования
```powershell
```
## COM-объекты 
Для использования объектов и методов, которые доступны через COM-интерфейс.
### Примеры использования
```powershell
```
## .NET Framework 
Для использования классов и методов **.NET Framework**.
### Примеры использования
```powershell
```
## WMI (Windows Management Instrumentation) 
Для получения информацию о системе. С помощью PowerShell можно управлять системой и отслеживать ее состояние. 
### Примеры использования
```powershell
```
## PowerShell Remoting 
Для запуска команд на удаленных компьютерах.
### Примеры использования
```powershell
```
