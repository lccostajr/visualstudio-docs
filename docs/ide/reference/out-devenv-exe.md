---
title: -Out (devenv.exe)
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
ms.technology: vs-ide-general
ms.topic: reference
helpviewer_keywords:
  - "errors [Visual Studio], builds"
  - "Devenv, /out switch"
  - "builds [Visual Studio], logs"
  - "error logs [Visual Studio], command-line build errors"
  - "error logs [Visual Studio]"
  - "/out Devenv switch"
  - "out Devenv switch"
  - "builds [Visual Studio], errors"
  - "output files, build errors"
ms.assetid: 9002d8c2-36d4-451c-b489-8f01932f31f7
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
  - "multiple"
---
# /Out (devenv.exe)
Specifies a file to store and display errors when you run, build, rebuild, or deploy a solution.

## Syntax

```cmd
devenv /out FileName
```

## Arguments
 `FileName`

 Required. The path and name of the file to receive errors when you build an executable.

## Remarks
 If a file name that does not exist is specified, the file is created automatically. If the file already exists, the results are appended to the existing contents of the file.

 Command line build errors are displayed in the **Command** window and the Solution Builder view of the **Output** window. This option is useful if you are running unattended builds and need to see the results.

## Example
 This example runs `MySolution` and writes errors to the file `MyErrorLog.txt`.

```cmd
devenv /run "C:\Documents and Settings\someuser\My Documents\Visual Studio\Projects\MySolution\MySolution.sln" /out "C:\MyErrorLog.txt"
```

## See Also

- [Devenv command-line switches](../../ide/reference/devenv-command-line-switches.md)
- [/Run (devenv.exe)](../../ide/reference/run-devenv-exe.md)
- [/Build (devenv.exe)](../../ide/reference/build-devenv-exe.md)
- [/Rebuild (devenv.exe)](../../ide/reference/rebuild-devenv-exe.md)
- [/Deploy (devenv.exe)](../../ide/reference/deploy-devenv-exe.md)