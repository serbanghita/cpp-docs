---
title: "OLE Background: Linking and Embedding"
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
ms.assetid: 11107711-eb96-4099-8f5c-7910bb3ecb75
caps.latest.revision: 7
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
# OLE Background: Linking and Embedding
Using the Paste command in a container application can create an embedded component, or embedded item. The source data for an embedded item is stored as part of the OLE document that contains it. In this way, a document file for a word processor document can contain text and also can contain bitmaps, graphs, formulas, or any other type of data.  
  
 OLE provides another way to incorporate data from another application: creating a linked component, or linked item, or a link. The steps for creating a linked item are similar to those for creating an embedded item, except that you use the Paste Link command instead of the Paste command. Unlike an embedded component, a linked component stores a path to the original data, which is often in a separate file.  
  
 For example, if you are working in a word processor document and create a linked item to some spreadsheet cells, the data for the linked item is stored in the original spreadsheet document. The word processor document contains only the information specifying where the item can be found, that is, it contains a link to the original spreadsheet document. When you double-click the cells, the spreadsheet application is launched and the original spreadsheet document is loaded from where it was stored.  
  
 Every OLE item, whether embedded or linked, has a type associated with it based on the application that created it. For example, a Microsoft Paintbrush item is one type of item, and a Microsoft Excel item is another type. Some applications, however, can create more than one item type. For example, Microsoft Excel can create worksheet items, chart items, and macrosheet items. Each of these items can be uniquely identified by the system using a Class Identifier or **CLSID**.  
  
## See Also  
 [OLE Background](../VS_visualcpp/OLE-Background.md)   
 [OLE Background: Containers and Servers](../VS_visualcpp/OLE-Background--Containers-and-Servers.md)   
 [Containers: Client Items](../VS_visualcpp/Containers--Client-Items.md)   
 [Servers: Server Items](../VS_visualcpp/Servers--Server-Items.md)