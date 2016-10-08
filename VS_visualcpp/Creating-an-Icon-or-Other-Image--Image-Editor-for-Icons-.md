---
title: "Creating an Icon or Other Image (Image Editor for Icons)"
ms.custom: na
ms.date: 10/03/2016
ms.devlang: 
  - C++
  - C++
ms.prod: visual-studio-dev14
ms.reviewer: na
ms.suite: na
ms.technology: 
  - devlang-cpp
ms.tgt_pltfrm: na
ms.topic: article
ms.assetid: 66db3fb2-cfc1-48a2-9bdd-53f61eb7ee30
caps.latest.revision: 9
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
# Creating an Icon or Other Image (Image Editor for Icons)
You can create a new image (bitmap, icon, cursor, or toolbar), then use the Image editor to customize its appearance. You can also create a new bitmap patterned after a [template](../VS_visualcpp/How-to--Use-Resource-Templates.md).  
  
### To add a new image resource to an unmanaged C++ project  
  
1.  In [Resource View](../VS_visualcpp/Resource-View-Window.md), right-click your .rc file, then choose **Insert Resource** from the shortcut menu. (If you already have an existing image resource in your .rc file, such as a cursor, you can simply right-click the **Cursor** folder and select **Insert Cursor** from the shortcut menu.)  
  
    > [!NOTE]
    >  **Note** If your project doesn't already contain an .rc file, please see [Creating a New Resource Script File](../VS_visualcpp/How-to--Create-a-Resource-Script-File.md).  
  
2.  In the [Insert Resource dialog box](../VS_visualcpp/Add-Resource-Dialog-Box.md), select the type of image resource you'd like to create (**Bitmap**, for example) then click **New**.  
  
     If a plus sign (**+**) appears next to the image resource type in the **Insert Resource** dialog box, it means that toolbar templates are available. Click the plus sign to expand the list of templates, select a template, and click **New**.  
  
### To add a new image resource to a project in a .NET programming language  
  
1.  In **Solution Explorer**, right-click the project folder (for example, **WindowsApplication1**).  
  
2.  From the shortcut menu, click **Add**, then choose **Add New Item**.  
  
3.  In the **Categories** pane, expand the **Local Project Items** folder, then choose **Resources**.  
  
4.  In the **Templates** pane, choose the resource type you'd like to add to your project.  
  
     The resource is added to your project in Solution Explorer and the resource opens in the [Image editor](../VS_visualcpp/Image-Editor-for-Icons.md). You can now use all the tools available in the Image editor to modify your image. For more information on adding images to a managed project, see [Loading a Picture at Design Time](../Topic/How%20to:%20Load%20a%20Picture%20Using%20the%20Designer%20\(Windows%20Forms\).md).  
  
    > [!NOTE]
    >  Any managed resources you want to edit must be linked resources. The Visual Studio resource editors do not support editing embedded resources. For more information, see [Creating Resource Files](../Topic/Creating%20Resource%20Files%20for%20Desktop%20Apps.md) in the *.NET Framework Developer's Guide*.  
  
 For information on adding resources to managed projects, please see [Resources in Applications](../Topic/Resources%20in%20Desktop%20Apps.md) in the *.NET Framework Developer's Guide.* For information on manually adding resource files to managed projects, accessing resources, displaying static resources, and assigning resources strings to properties, see [Walkthrough: Localizing Windows Forms](assetId:///9a96220d-a19b-4de0-9f48-01e5d82679e5) and [Walkthrough: Using Resources for Localization with ASP.NET](../Topic/Walkthrough:%20Using%20Resources%20for%20Localization%20with%20ASP.NET.md).  
  
 Requirements  
  
 None  
  
## See Also  
 [Icons and Cursors: Image Resources for Display Devices](../VS_visualcpp/Icons-and-Cursors--Image-Resources-for-Display-Devices--Image-Editor-for-Icons-.md)   
 [Converting Bitmaps to Toolbars](../VS_visualcpp/Converting-Bitmaps-to-Toolbars.md)   
 [Creating New Toolbars](../VS_visualcpp/Creating-New-Toolbars.md)   
 [Editing Graphical Resources](../VS_visualcpp/Editing-Graphical-Resources--Image-Editor-for-Icons-.md)   
 [Image Editor for Icons](../VS_visualcpp/Image-Editor-for-Icons.md)