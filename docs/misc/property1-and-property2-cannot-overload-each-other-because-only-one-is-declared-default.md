---
title: "&#39;&lt;Eigenschaft1&gt;&#39; und &#39;&lt;Eigenschaft2&gt;&#39; k&#246;nnen sich nicht gegenseitig &#252;berladen, da nur eine als &#39;Default&#39; deklariert ist. | Microsoft Docs"
ms.custom: ""
ms.date: "11/17/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "bc30361"
  - "vbc30361"
helpviewer_keywords: 
  - "BC30361"
ms.assetid: bac85b32-1a1f-4c43-817c-76e209cfeb8c
caps.latest.revision: 8
caps.handback.revision: 8
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# &#39;&lt;Eigenschaft1&gt;&#39; und &#39;&lt;Eigenschaft2&gt;&#39; k&#246;nnen sich nicht gegenseitig &#252;berladen, da nur eine als &#39;Default&#39; deklariert ist.
Wenn eine Eigenschaft `Default` angibt, müssen alle für diesen Namen überladenen Eigenschaften ebenfalls `Default` angeben.  
  
 **Fehler\-ID:** BC30361  
  
### So beheben Sie diesen Fehler  
  
-   Stellen Sie sicher, dass alle überladenen Eigenschaften als `Default` deklariert werden.  
  
## Siehe auch  
 [Considerations in Overloading Procedures](/dotnet/visual-basic/programming-guide/language-features/procedures/considerations-in-overloading-procedures)   
 [Default](/dotnet/visual-basic/language-reference/modifiers/default)