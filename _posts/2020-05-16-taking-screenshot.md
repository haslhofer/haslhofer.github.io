---
layout: post
title:  "Writing code to take a screenshot"
author: gerald
categories: [ explorations]
image: assets/images/landscape2.jpg
---

**What does it take on Windows to take a screenshot and save it as an image file**

Questions: which development environment and language?

Options: 
- **regular .NET**. Pros: familiarity, lots of documentation
- **.NET core**. Pros: future proof. learn something new
- **Python**. Not sure if even possible, but enables workflow into AI

Development enviornment:
- **Visual Studio Code**. Lightweight. Future proof. Learning curve
- **Full blown Visual Studio**. Familiar

Data points:
- [.net core supported with VS code] on official MS documentation (https://docs.microsoft.com/en-us/dotnet/core/tutorials/with-visual-studio-code)

Decision: use .dot net Core with Visual Studio Code.

**Setting up the development environment**

- Official instructions on [docs](https://docs.microsoft.com/en-us/dotnet/core/tutorials/with-visual-studio-code)
- Started using .Net Core 3.1.202

**Create git repo**

Location on Git: [https://github.com/haslhofer/screencapture](https://github.com/haslhofer/screencapture)

**Create Hello World .Net Core app**

Instructions: [https://docs.microsoft.com/en-us/dotnet/core/tutorials/with-visual-studio-code](https://docs.microsoft.com/en-us/dotnet/core/tutorials/with-visual-studio-code)

**Find the right APIs for Screen capture in Windows**

Option 1: PrintWindow
-  example on [stackoverflow](https://stackoverflow.com/questions/891345/get-a-screenshot-of-a-specific-application)

- using [GDI](https://www.developerfusion.com/code/4630/capture-a-screen-shot/) --> solution chosen

add package to dot net core: 
> dotnet add package System.Drawing.Common

**Issues along the way:**
- Monitor scaling. Fix: 
    > call User32.SetProcessDPIAware();

- Multiple monitors: Article that describes doing this in C++ [here](https://www.apriorit.com/dev-blog/193-multi-monitor-screenshot)
    - [MonitorInfoEx structure](https://www.pinvoke.net/default.aspx/user32/MONITORINFO.html)


Need to understand Windows GDI better:
- [GDI introduction](https://docs.microsoft.com/en-us/windows/win32/gdi/multiple-display-monitors)
*Virtual screen:* The bounding rectangle of all the monitors is the virtual screen [source](https://docs.microsoft.com/en-us/windows/win32/gdi/the-virtual-screen)
    - Each *physical* display is represented by a monitor handle of type HMONITOR.
    - Any function that returns a display device context (DC) normally returns a DC for the primary monitor
    - To obtain the DC for another monitor, use the EnumDisplayMonitors function
    - Or, you can use the *device name from the GetMonitorInfo* function to create a DC with CreateDC.
