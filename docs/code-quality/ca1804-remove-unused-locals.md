---
title: 'CA1804: Nicht verwendete lokale Variablen entfernen | Microsoft Docs'
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-code-analysis
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- CA1804
- RemoveUnusedLocals
helpviewer_keywords:
- RemoveUnusedLocals
- CA1804
ms.assetid: cc332e67-6543-4813-bd8a-6f6fc75bf22a
caps.latest.revision: "18"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload: multiple
ms.openlocfilehash: d75bc10407e9eae1c23ad06fdc2bd9515bdd505f
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="ca1804-remove-unused-locals"></a>CA1804: Nicht verwendete lokale Variablen entfernen
|||  
|-|-|  
|TypeName|RemoveUnusedLocals|  
|CheckId|CA1804|  
|Kategorie|Microsoft.Performance|  
|Unterbrechende Änderung|Nicht unterbrechend|  
  
## <a name="cause"></a>Ursache  
 Eine Methode deklariert eine lokale Variable verwendet jedoch nicht die Variable außer möglicherweise als Empfänger einer zuweisungsanweisung. Für die Analyse durch diese Regel muss die getestete Assembly mit Debuginformationen erstellt werden, und die zugehörigen Programmdatenbankdatei (.pdb) muss verfügbar sein.  
  
## <a name="rule-description"></a>Regelbeschreibung  
 Nicht verwendete lokale Variablen und unnötige Zuweisungen vergrößern die Assembly unnötig und beeinträchtigen die Leistung.  
  
## <a name="how-to-fix-violations"></a>Behandeln von Verstößen  
 Um einen Verstoß gegen diese Regel zu beheben, entfernen Sie, oder verwenden Sie die lokale Variable. Beachten Sie, dass der C#-Compiler enthalten ist [!INCLUDE[dnprdnlong](../code-quality/includes/dnprdnlong_md.md)] entfernt nicht verwendete lokale Variablen bei der `optimize` aktiviert ist.  
  
## <a name="when-to-suppress-warnings"></a>Wann sollten Warnungen unterdrückt werden?  
 Unterdrücken Sie eine Warnung dieser Regel, wenn die Variable vom Compiler ausgegeben wurde. Sie können ruhig auch zum Unterdrücken einer Warnung dieser Regel, oder um die Regel deaktivieren, wenn Leistung und Wartung des Programmcodes nicht vorrangiger sind.  
  
## <a name="example"></a>Beispiel  
 Das folgende Beispiel zeigt mehrere nicht verwendete lokale Variablen.  
  
 [!code-vb[FxCop.Performance.UnusedLocals#1](../code-quality/codesnippet/VisualBasic/ca1804-remove-unused-locals_1.vb)]
 [!code-csharp[FxCop.Performance.UnusedLocals#1](../code-quality/codesnippet/CSharp/ca1804-remove-unused-locals_1.cs)]  
  
## <a name="related-rules"></a>Verwandte Regeln  
 [CA1809: Übermäßige lokale Variablen vermeiden](../code-quality/ca1809-avoid-excessive-locals.md)  
  
 [CA1811: Nicht aufgerufenen privaten Code vermeiden](../code-quality/ca1811-avoid-uncalled-private-code.md)  
  
 [CA1812: Nicht instanziierte interne Klassen vermeiden](../code-quality/ca1812-avoid-uninstantiated-internal-classes.md)  
  
 [CA1801: Nicht verwendete Parameter überprüfen](../code-quality/ca1801-review-unused-parameters.md)