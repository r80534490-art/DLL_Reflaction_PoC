# DLL_Reflaction_PoC


This repository is a proof of concept for reflective DLL injection using manual mapping (also called manual map). It shows how to load a DLL into another process’s memory without using LoadLibrary.

Project structure

DLL_Test – A simple DLL that pops up a "Hello world!" message when it is loaded. This DLL is used as the payload.

Injector – A console application that reads a DLL from disk, maps it into a target process’s memory, fixes relocation and import tables, and starts it in the remote process.

Building and running

Build the DLL_Test project as a DLL.

Build the Injector project as a console application.

Run Injector.exe from a command prompt with the path to the DLL and the name of the target process:

```Injector.exe <path_to_dll> <target_process_name>```


Example:

```Injector.exe C:\Path\To\DLL_Test.dll explorer.exe```


The injector will open the target process, manually map the DLL into its memory, and execute it. You should see a "Hello world!" message box in the target process.

Requirements

Windows (both the injector and the target process must have the same architecture: 32‑bit or 64‑bit).

Visual Studio 2019 or later.
