---
title: "-SUBSYSTEM (Specify Subsystem)"
ms.custom: na
ms.date: 10/03/2016
ms.devlang: 
  - C++
ms.prod: visual-studio-dev14
ms.reviewer: na
ms.suite: na
ms.technology: 
  - devlang-cpp
ms.tgt_pltfrm: na
ms.topic: article
H1: /SUBSYSTEM (Specify Subsystem)
ms.assetid: d7b133cf-cf22-4da8-ab46-6552702c0b9b
caps.latest.revision: 25
manager: ghogen
translation.priority.ht: 
  - cs-cz
  - de-de
  - es-es
  - fr-fr
  - it-it
  - ja-jp
  - ko-kr
  - pl-pl
  - pt-br
  - ru-ru
  - tr-tr
  - zh-cn
  - zh-tw
---
# -SUBSYSTEM (Specify Subsystem)
```  
/SUBSYSTEM:{BOOT_APPLICATION|CONSOLE|EFI_APPLICATION|  
            EFI_BOOT_SERVICE_DRIVER|EFI_ROM|EFI_RUNTIME_DRIVER|NATIVE|  
            POSIX|WINDOWS)  
            [,major[.minor]]  
```  
  
 BOOT_APPLICATION  
 An application that runs in the Windows boot environment. For more information about boot applications, see [About BCD](http://msdn.microsoft.com/library/windows/desktop/aa362639).  
  
 CONSOLE  
 Win32 character-mode application. The operating system provides a console for console applications. If `main` or `wmain` is defined for native code, `int main(array<String ^> ^)` is defined for managed code, or you build the application completely by using `/clr:safe`, CONSOLE is the default.  
  
 Extensible Firmware Interface  
 The EFI_* subsystems. See the EFI specification for more information. For example, see the Intel Web site. The minimum version and default version is 1.0.  
  
 NATIVE  
 Kernel mode drivers for Windows NT. This option is usually reserved for Windows system components. If [/DRIVER:WDM](../VS_visualcpp/-DRIVER--Windows-NT-Kernel-Mode-Driver-.md) is specified, NATIVE is the default.  
  
 POSIX  
 Application that runs with the POSIX subsystem in Windows NT.  
  
 WINDOWS  
 Application does not require a console, probably because it creates its own windows for interaction with the user. If `WinMain` or `wWinMain` is defined for native code, or `WinMain(HISTANCE *, HINSTANCE *, char *, int)` or `wWinMain(HINSTANCE *, HINSTANCE *, wchar_t *, int)` is defined for managed code, WINDOWS is the default.  
  
 `Major` and `minor` (optional)  
 Specify the minimum required version of the subsystem. The arguments are decimal numbers in the range 0 through 65,535. See the Remarks for more information. There are no upper bounds for version numbers.  
  
## Remarks  
 The /SUBSYSTEM option specifies the environment for the executable.  
  
 The choice of subsystem affects the entry point symbol (or entry point function) that the linker will select.  
  
 The optional minimum and default `major` and `minor` version numbers for the subsystems are as follows.  
  
|Subsystem|Minimum|Default|  
|---------------|-------------|-------------|  
|BOOT_APPLICATION|1.0|1.0|  
|CONSOLE|5.01 (x86) 5.02 (x64) 6.02 (ARM)|6.00 (x86, x64) 6.02 (ARM)|  
|WINDOWS|5.01 (x86) 5.02 (x64) 6.02 (ARM)|6.00 (x86, x64) 6.02 (ARM)|  
|NATIVE (with DRIVER:WDM)|1.00 (x86) 1.10 (x64, ARM)|1.00 (x86) 1.10 (x64, ARM)|  
|NATIVE (without /DRIVER:WDM)|4.00 (x86) 5.02 (x64) 6.02 (ARM)|4.00 (x86) 5.02 (x64) 6.02 (ARM)|  
|POSIX|1.0|19.90|  
|EFI_APPLICATION, EFI_BOOT_SERVICE_DRIVER, EFI_ROM, EFI_RUNTIME_DRIVER|1.0|1.0|  
  
### To set this linker option in the Visual Studio development environment  
  
1.  Open the project's **Property Pages** dialog box. For details, see [Setting Visual C++ Project Properties](../VS_visualcpp/Working-with-Project-Properties.md).  
  
2.  Select the Linker folder.  
  
3.  Select the **System** property page.  
  
4.  Modify the `SubSystem` property.  
  
### To set this linker option programmatically  
  
-   See <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.SubSystem?qualifyHint=False>.  
  
## See Also  
 [Setting Linker Options](../VS_visualcpp/Setting-Linker-Options.md)   
 [Linker Options](../VS_visualcpp/Linker-Options.md)