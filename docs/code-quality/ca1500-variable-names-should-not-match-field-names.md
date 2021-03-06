---
title: "CA1500: Variablennamen sollten nicht Feldnamen übereinstimmen | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-code-analysis
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- VariableNamesShouldNotMatchFieldNames
- CA1500
helpviewer_keywords:
- VariableNamesShouldNotMatchFieldNames
- CA1500
ms.assetid: fa0e5029-79e9-4a33-8576-787ac3c26c39
caps.latest.revision: "24"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload: multiple
ms.openlocfilehash: b88d0fec56e16dfdb047aa06a5526526f362a7d7
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="ca1500-variable-names-should-not-match-field-names"></a>CA1500: Variablennamen sollten nicht mit Feldnamen übereinstimmen
|||  
|-|-|  
|TypeName|VariableNamesShouldNotMatchFieldNames|  
|CheckId|CA1500|  
|Kategorie|Microsoft.Maintainability|  
|Unterbrechende Änderung|Wenn auf einem Parameter ausgelöst, die den gleichen Namen wie ein Feld hat:<br /><br /> Nicht-unterbrechend – Wenn das Feld und die Methode, die den Parameter deklariert nicht außerhalb der Assembly sichtbar ist müssen unabhängig von der Änderung.<br />Unterbrechend – Wenn Sie den Namen des Felds ändern und außerhalb der Assembly angezeigt werden können.<br />-Unterbrechend – Wenn Sie den Namen des Parameters ändern und die Methode, die es deklariert außerhalb der Assembly angezeigt werden kann.<br /><br /> Wenn auf eine lokale Variable ausgelöst, die den gleichen Namen wie ein Feld hat:<br /><br /> Nicht-unterbrechend – Wenn das Feld nicht außerhalb der Assembly, unabhängig von der Änderung sichtbar ist, die Sie vornehmen.<br />Nicht-unterbrechend – Wenn Sie den Namen der lokalen Variablen ändern, und ändern Sie den Namen des Felds nicht.<br />-Unterbrechend – Wenn Sie den Namen des Felds ändern und außerhalb der Assembly angezeigt werden können.|  
  
## <a name="cause"></a>Ursache  
 Eine Instanzmethode deklariert einen Parameter oder eine lokale Variable, deren Name eines Instanzenfelds des deklarierenden Typs übereinstimmt. Zum Abfangen von lokaler Variablen, die die Regel verletzen, muss die getestete Assembly mit Debuginformationen erstellt werden, und die zugehörigen Programmdatenbankdatei (.pdb) muss verfügbar sein.  
  
## <a name="rule-description"></a>Regelbeschreibung  
 Wenn der Name eines Instanzenfelds einen Parameter oder eine lokale Variable Name übereinstimmt, erfolgt der Instanzfelds mithilfe der `this` (`Me` in [!INCLUDE[vbprvb](../code-quality/includes/vbprvb_md.md)]) Schlüsselwort, wenn innerhalb des Methodentexts. Beim Verwalten von Code, ist es leicht vergessen dieser Unterschied und davon ausgehen, dass der Parameter/lokale Variablen auf das Instanzenfeld bezieht, das führt zu Fehlern. Dies gilt besonders für lange Methodentexte.  
  
## <a name="how-to-fix-violations"></a>Behandeln von Verstößen  
 Um einen Verstoß gegen diese Regel zu beheben, benennen Sie den Parameter/die Variable oder das Feld ein.  
  
## <a name="when-to-suppress-warnings"></a>Wann sollten Warnungen unterdrückt werden?  
 Unterdrücken Sie keine Warnung dieser Regel.  
  
## <a name="example"></a>Beispiel  
 Das folgende Beispiel zeigt zwei Verstöße gegen diese Regel.  
  
 [!code-vb[FxCop.Maintainability.VarMatchesField#1](../code-quality/codesnippet/VisualBasic/ca1500-variable-names-should-not-match-field-names_1.vb)]
 [!code-csharp[FxCop.Maintainability.VarMatchesField#1](../code-quality/codesnippet/CSharp/ca1500-variable-names-should-not-match-field-names_1.cs)]