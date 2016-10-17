---
title: "Compiler Error CS1601"
ms.custom: na
ms.date: 10/01/2016
ms.devlang: 
  - CSharp
ms.prod: visual-studio-dev14
ms.reviewer: na
ms.suite: na
ms.technology: 
  - devlang-csharp
ms.tgt_pltfrm: na
ms.topic: article
ms.assetid: 5efa1d2d-c70c-446d-a51f-d23d8a3be22e
caps.latest.revision: 10
manager: douge
translation.priority.ht: 
  - de-de
  - es-es
  - fr-fr
  - it-it
  - ja-jp
  - ko-kr
  - ru-ru
  - zh-cn
  - zh-tw
translation.priority.mt: 
  - cs-cz
  - pl-pl
  - pt-br
  - tr-tr
---
# Compiler Error CS1601
Method or delegate parameter cannot be of type 'type'  
  
 Some types in the .NET Framework class library, for example, <xref:System.TypedReference?qualifyHint=False>, <xref:System.RuntimeArgumentHandle?qualifyHint=False> and <xref:System.ArgIterator?qualifyHint=False> cannot be used as [ref](../Topic/ref%20\(C%23%20Reference\).md) or [out](../Topic/out%20\(C%23%20Reference\).md) parameters because they could potentially be used to perform unsafe operations.  
  
 The following sample generates CS1601:  
  
```  
// CS1601.cs  
using System;  
  
class MyClass  
{  
   public void Test1 (ref TypedReference t)   // CS1601  
   {  
   }  
  
   public void Test2 (out ArgIterator t)   // CS1601  
   {  
   }  
}  
```