---
title: "Compilerfehler CS1526 | Microsoft Docs"
ms.custom: ""
ms.date: "11/16/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "CS1526"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "CS1526"
ms.assetid: 92feeb9f-e577-4c08-b12b-c19822857200
caps.latest.revision: 9
caps.handback.revision: 9
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# Compilerfehler CS1526
Ein new\-Ausdruck erfordert \(\), \[\] oder {} nach 'typ'.  
  
 Der [new](/dotnet/csharp/language-reference/keywords/new)\-Operator, der zum dynamischen Zuweisen von Arbeitsspeicher für ein Objekt verwendet wird, wurde nicht ordnungsgemäß angegeben.  
  
## Beispiel  
 Das folgende Beispiel veranschaulicht die Verwendung von `new` zum Zuweisen von Platz für ein Array und ein Objekt.  
  
```  
// CS1526.cs public class y { public static int i = 0; public int myi = 0; } public class z { public static void Main() { y py = new y;   // CS1526 y[] aoys = new y[10];   // Array of Ys for (int i = 0; i < aoys.Length; i++) aoys[i] = new y();   // an object of type y } }  
```