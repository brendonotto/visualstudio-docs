---
title: "Compiler Error CS0551"
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
ms.assetid: fb456ecf-dff3-4e39-b9b3-de23d81dadea
caps.latest.revision: 8
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
# Compiler Error CS0551
Explicit interface implementation 'implementation' is missing accessor 'accessor'  
  
 A class that explicitly implements an interface's property must implement all the accessors that the interface defines.  
  
 For more information, see [Using Properties](../Topic/Using%20Properties%20\(C%23%20Programming%20Guide\).md).  
  
## Example  
 The following sample generates CS0551.  
  
```  
// CS0551.cs  
// compile with: /target:library  
interface ii  
{  
   int i  
   {  
      get;  
      set;  
   }  
}  
  
public class a : ii  
{  
   int ii.i { set {} }   // CS0551  
  
   // OK  
   int ii.i      
   {  
      set {}  
      get { return 0; }  
   }  
}  
```