---
title: "Compilerfehler CS0562 | Microsoft Docs"
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
  - "CS0562"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "CS0562"
ms.assetid: dceecce5-90ce-4554-820c-f4c06b2b8258
caps.latest.revision: 8
caps.handback.revision: 8
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# Compilerfehler CS0562
Der Parameter eines unären Operators muss der enthaltende Typ sein.  
  
 Bei der Methodendeklaration für eine Operatorüberladung müssen bestimmte Richtlinien beachtet werden. Weitere Informationen finden Sie unter [Überladbare Operatoren](/dotnet/csharp/programming-guide/statements-expressions-operators/overloadable-operators) und [Operator Overloading Sample](http://msdn.microsoft.com/de-de/1c6b4610-0a49-4532-8fa7-f694cfc65743).  
  
## Beispiel  
 Im folgenden Beispiel wird CS0562 generiert:  
  
```  
// CS0562.cs public class iii { public static implicit operator int(iii x) { return 0; } public static implicit operator iii(int x) { return null; } public static iii operator +(int aa)   // CS0562 // try the following line instead // public static iii operator +(iii aa) { return (iii)0; } public static void Main() { } }  
```