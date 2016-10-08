---
title: "How to: Copy Resources"
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
ms.assetid: 65f523e8-017f-4fc6-82d1-083c56d9131f
caps.latest.revision: 6
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
# How to: Copy Resources
You can copy resources from one file to another without changing them or you can [change the language or condition of a resource while copying it](../VS_visualcpp/How-to--Change-the-Language-or-Condition-of-a-Resource-While-Copying.md).  
  
 You can easily copy resources from an existing resource or executable file to your current resource file. To do this, you open both files containing resources at the same time and drag items from one file to another or copy and paste between the two files. This method works for resource script (.rc) files and resource template (.rct) files, as well as executable (.exe) files.  
  
> [!NOTE]
>  Visual C++ includes sample resource files that you can use in your own application. For more information, see [CLIPART: Common Resources](assetId:///9bac2891-b6b3-49ec-a287-cec850c707e0).  
  
 You can use the drag-and-drop method between .rc files that are open [outside of the project](../VS_visualcpp/How-to--Open-a-Resource-Script-File-Outside-of-a-Project--Standalone-.md).  
  
### To copy resources between files using the drag-and-drop method  
  
1.  Open both resource files stand-alone (for more information, see [Viewing Resources in an .rc File Outside of a Project](../VS_visualcpp/How-to--Open-a-Resource-Script-File-Outside-of-a-Project--Standalone-.md)). For example, open Source1.rc and Source2.rc.  
  
2.  Inside the first .rc file, click the resource you wish to copy. For example, in Source1.rc, click IDD_DIALOG1.  
  
3.  Hold down the CTRL key and drag the resource to the second .rc file. For example, drag IDD_DIALOG1 from Source1.rc to Source2.rc.  
  
    > [!NOTE]
    >  Dragging the resource without holding down the CTRL key moves the resource rather than copying it.  
  
### To copy resources using copy and paste  
  
1.  Open both resource files stand-alone (for more information, see [Viewing Resources in an .rc File Outside of a Project](../VS_visualcpp/How-to--Open-a-Resource-Script-File-Outside-of-a-Project--Standalone-.md)). For example, Source1.rc and Source2.rc.  
  
2.  In the source file from which you wish to copy a resource (for example, Source1.rc), right-click a resource and choose **Copy** from the shortcut menu.  
  
3.  Right-click the resource file into which you'd like to paste the resource (for example, Source2.rc). Choose **Paste** from the shortcut menu.  
  
    > [!NOTE]
    >  You cannot drag and drop, copy, cut, or paste between resource files in the project (Resource View) and stand-alone .rc files (those open in document windows). You could do this in previous versions of the product.  
  
    > [!NOTE]
    >  To avoid conflicts with symbol names or values in the existing file, Visual C++ may change the transferred resource's symbol value or symbol name and value when you copy it to the new file.  
  
 For information on adding resources to managed projects, please see [Resources in Applications](../Topic/Resources%20in%20Desktop%20Apps.md) in the *.NET Framework Developer's Guide.* For information on manually adding resource files to managed projects, accessing resources, displaying static resources, and assigning resources strings to properties, see [Walkthrough: Localizing Windows Forms](assetId:///9a96220d-a19b-4de0-9f48-01e5d82679e5) and [Walkthrough: Using Resources for Localization with ASP.NET](../Topic/Walkthrough:%20Using%20Resources%20for%20Localization%20with%20ASP.NET.md).  
  
 Requirements  
  
 Win32  
  
## See Also  
 [How to: Open a Resource Script File Outside of a Project (Standalone)](../VS_visualcpp/How-to--Open-a-Resource-Script-File-Outside-of-a-Project--Standalone-.md)   
 [Resource Files](../VS_visualcpp/Resource-Files--Visual-Studio-.md)   
 [Resource Editors](../VS_visualcpp/Resource-Editors.md)