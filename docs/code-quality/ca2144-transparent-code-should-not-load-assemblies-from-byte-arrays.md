---
title: 'CA2144: Transparenter Code sollte nicht laden von Assemblys aus Bytearrays | Microsoft Docs'
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-code-analysis
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: CA2144
ms.assetid: 777b1310-6e16-4413-b4ee-5f3136304f82
caps.latest.revision: "12"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload: multiple
ms.openlocfilehash: acc2b60d0099d09f9aaba7ad77fd82c26ccd22ca
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="ca2144-transparent-code-should-not-load-assemblies-from-byte-arrays"></a>CA2144: Transparenter Code darf keine Assemblys aus Bytearrays laden
|||  
|-|-|  
|TypeName|TransparentMethodsShouldNotLoadAssembliesFromByteArrays|  
|CheckId|CA2144|  
|Kategorie|Microsoft.Security|  
|Unterbrechende Änderung|Breaking|  
  
## <a name="cause"></a>Ursache  
 Eine transparente Methode lädt eine Assembly aus einem Bytearray mit einer der folgenden Methoden:  
  
-   <xref:System.Reflection.Assembly.Load%2A>  
  
-   <xref:System.Reflection.Assembly.Load%2A>  
  
-   <xref:System.Reflection.Assembly.Load%2A>  
  
## <a name="rule-description"></a>Regelbeschreibung  
 Die Sicherheitsüberprüfung für transparenten Code ist nicht so umfassend wie die Sicherheitsüberprüfung für wichtigen Code, da in transparentem Code keine sicherheitsrelevanten Aktionen ausgeführt werden können. Aus einem Bytearray geladene Assemblys werden in transparentem Code eventuell nicht erkannt, und dieses Bytearray könnte wichtigen oder sicherheitsgeschützten Code enthalten, der überwacht werden muss. Aus diesem Grund sollten transparenter Code keine Assemblys aus einem Bytearray geladen werden.  
  
## <a name="how-to-fix-violations"></a>Behandeln von Verstößen  
 Um einen Verstoß gegen diese Regel zu beheben, markieren Sie die Methode, die lädt die Assembly mit dem <xref:System.Security.SecurityCriticalAttribute> oder <xref:System.Security.SecuritySafeCriticalAttribute> Attribut.  
  
## <a name="when-to-suppress-warnings"></a>Wann sollten Warnungen unterdrückt werden?  
 Unterdrücken Sie keine Warnung dieser Regel.  
  
## <a name="example"></a>Beispiel  
 Die Regel wird für den folgenden Code ausgelöst, da eine transparente Methode eine Assembly aus einem Bytearray geladen.  
  
 [!code-csharp[FxCop.Security.CA2144.TransparentMethodsShouldNotLoadAssembliesFromByteArrays#1](../code-quality/codesnippet/CSharp/ca2144-transparent-code-should-not-load-assemblies-from-byte-arrays_1.cs)]