---
title: "CA1816: Rufen Sie GC. SuppressFinalize ordnungsgemäß | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-code-analysis
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- CA1816
- DisposeMethodsShouldCallSuppressFinalize
helpviewer_keywords:
- DisposeMethodsShouldCallSuppressFinalize
- CA1816
ms.assetid: 47915fbb-103f-4333-b157-1da16bf49660
caps.latest.revision: "19"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload: multiple
ms.openlocfilehash: 8d0287b570ed1ff5393ff0ff04b9e5d2252c29bf
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="ca1816-call-gcsuppressfinalize-correctly"></a>CA1816: GC.SuppressFinalize korrekt aufrufen
|||  
|-|-|  
|TypeName|CallGCSuppressFinalizeCorrectly|  
|CheckId|CA1816|  
|Kategorie|Microsoft. Verwendung|  
|Unterbrechende Änderung|Nicht unterbrechende Änderung|  
  
## <a name="cause"></a>Ursache  
  
-   Eine Methode, die Implementierung von <xref:System.IDisposable.Dispose%2A?displayProperty=fullName> nicht aufgerufen, <xref:System.GC.SuppressFinalize%2A?displayProperty=fullName>.  
  
-   Eine Methode, die keine Implementierung von <xref:System.IDisposable.Dispose%2A?displayProperty=fullName> Aufrufe <xref:System.GC.SuppressFinalize%2A?displayProperty=fullName>.  
  
-   Eine Methode ruft <xref:System.GC.SuppressFinalize%2A?displayProperty=fullName> und übergibt ein anderes Element als dieses (Me in Visual Basic).  
  
## <a name="rule-description"></a>Regelbeschreibung  
 Die <xref:System.IDisposable.Dispose%2A?displayProperty=fullName> -Methode ermöglicht es Benutzern, die Ressourcen zu einem beliebigen Zeitpunkt vor dem Objekt eine verlaufsabfrage verfügbar sind, für die Garbagecollection freigegeben. Wenn die <xref:System.IDisposable.Dispose%2A?displayProperty=fullName> -Methode aufgerufen wird, die Ressourcen des Objekts freigegeben. Dadurch wird die Beendigung nicht erforderlich. <xref:System.IDisposable.Dispose%2A?displayProperty=fullName>sollten Aufrufen <xref:System.GC.SuppressFinalize%2A?displayProperty=fullName> , damit der Garbage Collector den Finalizer des Objekts nicht aufgerufen wird.  
  
 Um zu verhindern, dass abgeleitete Typen mit Finalizern erneut implementieren müssen <xref:System.IDisposable> und um es aufzurufen, unversiegelte Typen ohne Finalizer sollten dennoch aufrufen <xref:System.GC.SuppressFinalize%2A?displayProperty=fullName>.  
  
## <a name="how-to-fix-violations"></a>Behandeln von Verstößen  
 Um einen Verstoß gegen diese Regel zu beheben:  
  
 Wenn die Methode eine Implementierung von <xref:System.IDisposable.Dispose%2A>, fügen Sie einen Aufruf von <xref:System.GC.SuppressFinalize%2A?displayProperty=fullName>.  
  
 Wenn die Methode keine Implementierung des ist <xref:System.IDisposable.Dispose%2A>, entfernen Sie entweder den Aufruf von <xref:System.GC.SuppressFinalize%2A?displayProperty=fullName> oder verschieben Sie ihn in des Typs <xref:System.IDisposable.Dispose%2A> Implementierung.  
  
 Ändern Sie alle Aufrufe an <xref:System.GC.SuppressFinalize%2A?displayProperty=fullName> dieses (Me in Visual Basic) übergeben.  
  
## <a name="when-to-suppress-warnings"></a>Wann sollten Warnungen unterdrückt werden?  
 Unterdrücken Sie eine Warnung dieser Regel nur, wenn Sie verwenden möchten <xref:System.GC.SuppressFinalize%2A?displayProperty=fullName> zur Steuerung der Lebensdauer von anderen Objekten. Unterdrücken Sie keine Warnung dieser Regel Wenn eine Implementierung von <xref:System.IDisposable.Dispose%2A> nicht aufgerufen, <xref:System.GC.SuppressFinalize%2A?displayProperty=fullName>. In diesem Fall wird die Leistung beeinträchtigt und bieten keine Vorteile wegen eines Fehlers beim Abschluss zu unterdrücken.  
  
## <a name="example"></a>Beispiel  
 Das folgende Beispiel zeigt eine Methode, die nicht korrekt Aufrufe <xref:System.GC.SuppressFinalize%2A?displayProperty=fullName>.  
  
 [!code-vb[FxCop.Usage.CallGCSuppressFinalizeCorrectly#1](../code-quality/codesnippet/VisualBasic/ca1816-call-gc-suppressfinalize-correctly_1.vb)]
 [!code-csharp[FxCop.Usage.CallGCSuppressFinalizeCorrectly#1](../code-quality/codesnippet/CSharp/ca1816-call-gc-suppressfinalize-correctly_1.cs)]  
  
## <a name="example"></a>Beispiel  
 Das folgende Beispiel zeigt eine Methode, die ordnungsgemäß Aufrufe <xref:System.GC.SuppressFinalize%2A?displayProperty=fullName>.  
  
 [!code-vb[FxCop.Usage.CallGCSuppressFinalizeCorrectly2#1](../code-quality/codesnippet/VisualBasic/ca1816-call-gc-suppressfinalize-correctly_2.vb)]
 [!code-csharp[FxCop.Usage.CallGCSuppressFinalizeCorrectly2#1](../code-quality/codesnippet/CSharp/ca1816-call-gc-suppressfinalize-correctly_2.cs)]  
  
## <a name="related-rules"></a>Verwandte Regeln  
 [CA2215: Dispose-Methoden müssen die Dispose-Funktion der Basisklasse aufrufen](../code-quality/ca2215-dispose-methods-should-call-base-class-dispose.md)  
  
 [CA2216: Verwerfbare Typen sollten einen Finalizer deklarieren](../code-quality/ca2216-disposable-types-should-declare-finalizer.md)  
  
## <a name="see-also"></a>Siehe auch  
 [Dispose-Muster](/dotnet/standard/design-guidelines/dispose-pattern)