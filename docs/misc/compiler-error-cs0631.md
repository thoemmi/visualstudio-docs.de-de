---
title: "Compilerfehler CS0631 | Microsoft Docs"
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
  - "CS0631"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "CS0631"
ms.assetid: 5ae06b13-7874-4d0d-b256-7d8b33396156
caps.latest.revision: 10
caps.handback.revision: 10
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# Compilerfehler CS0631
"ref" und "out" sind in diesem Kontext nicht gültig.  
  
 Die Deklaration für einen [Indexer](/dotnet/csharp/programming-guide/indexers/index) darf nicht von den Parametern [ref](/dotnet/csharp/language-reference/keywords/ref) und [out](/dotnet/csharp/language-reference/keywords/out) Gebrauch machen.  
  
## Beispiel  
 Im folgenden Beispiel wird CS0631 generiert:  
  
```  
// CS0631.cs public class MyClass { public int this[ref int i]   // CS0631 // try the following line instead // public int this[int i] { get { return 0; } } } public class MyClass2 { public static void Main() { } }  
```