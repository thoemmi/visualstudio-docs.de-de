---
title: "Compilerfehler CS1715 | Microsoft Docs"
ms.custom: ""
ms.date: "10/29/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "CS1715"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "CS1715"
ms.assetid: 740044d1-a61c-4156-bc6a-adf26c7499ec
caps.latest.revision: 9
caps.handback.revision: 9
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# Compilerfehler CS1715
"Type1": Der Typ muss "Type2" sein, um mit dem überschriebenen Member "MemberName" übereinzustimmen  
  
 Dieser Fehler ist identisch mit [Compilerfehler CS0508](../misc/compiler-error-cs0508.md), außer dass CS0508 jetzt nur für Methoden mit Rückgabetypen gilt; CS1715 hingegen gilt für Eigenschaften und Indexer, die nur "Typen" anstelle von "Rückgabetypen" aufweisen.  
  
## Beispiel  
 Der folgende Code generiert CS1715.  
  
```  
// CS1715.cs abstract public class Base { abstract public int myProperty { get; set; } } public class Derived : Base { int myField; public override double myProperty  // CS1715 // try the following line instead // public override int myProperty { get { return myField; } set { myField;= value; } } public static void Main() { Derived d = new Derived(); d.myProperty = 5; } }  
```