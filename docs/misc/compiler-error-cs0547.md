---
title: "Compilerfehler CS0547 | Microsoft Docs"
ms.custom: ""
ms.date: "11/17/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "CS0547"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "CS0547"
ms.assetid: aa80873f-deb0-4ff2-8435-92a626bb5b80
caps.latest.revision: 7
caps.handback.revision: 7
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# Compilerfehler CS0547
'property': Die Eigenschaft oder der Indexer dürfen nicht den void\-Typ aufweisen.  
  
 [void](/dotnet/csharp/language-reference/keywords/void) als Rückgabewert für eine Eigenschaft ist ungültig.  
  
 Weitere Informationen finden Sie unter [Eigenschaften](/dotnet/csharp/programming-guide/classes-and-structs/properties).  
  
 Das folgende Beispiel generiert CS0547:  
  
```  
// CS0547.cs public class a { public void i   // CS0547 // Try the following declaration instead: // public int i { get { return 0; } } } public class b : a { public static void Main() { } }  
```