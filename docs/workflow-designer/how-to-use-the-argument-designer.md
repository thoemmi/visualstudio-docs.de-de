---
title: 'Vorgehensweise: Verwenden des Argument-Designers | Microsoft Docs'
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- System.Activities.Presentation.View.ArgumentDesigner.UI
- System.Activities.Presentation.View.DesignTimeArgument.UI
ms.assetid: 64813fd5-1ea1-499a-98b4-ab2a44b7ee5e
caps.latest.revision: "16"
author: ErikRe
ms.author: erikre
manager: erikre
ms.workload: multiple
ms.openlocfilehash: aa1cdd0dd563a5f87d4e32f779985afd63319032
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-use-the-argument-designer"></a>Vorgehensweise: Verwenden des Argument-Designers
Verglichen mit früheren Versionen von [!INCLUDE[dnprdnshort](../code-quality/includes/dnprdnshort_md.md)], ist es mit dem Argument-Designer einfach, Daten in eine und aus einer Aktivität fließen zu lassen. Der Designer zugegriffen wird, indem Sie auf die **Argumente** Schaltfläche in der unteren linken Ecke des Zeichenbereichs. Der Designer enthält eine Liste von Argumenten, die in einer Tabelle angezeigt und können nach jedem Spaltenkopf, sortiert werden, mit Ausnahme von der **Standardwert** Spalte. Für jedes Argument werden der Name, die Richtung (ein/aus/ein/aus/Eigenschaft), der Typ und ein Standardausdruckswert (sofern vorhanden) angegeben. Der Name und der Standardausdruckswert sind bearbeitbare Textfelder, und der Typ und die Richtung sind Dropdownlisten. [! UMFASSEN[Crabout](/dotnet/framework/windows-workflow-foundation/variables-and-arguments).  
  
### <a name="to-create-a-new-argument"></a>So erstellen Sie ein neues Argument  
  
1.  Öffnen Sie in [!INCLUDE[vs2010](../misc/includes/vs2010_md.md)] eine Workflow- oder Aktivitätsprojektmappe.  
  
2.  Öffnen Sie den Argument-Designer, indem Sie auf die **Argumente** Schaltfläche in der unteren linken Ecke des Zeichenbereichs. Der Argument-Designer wird angezeigt.  
  
3.  Klicken Sie auf die leere Zeile, die mit der Bezeichnung **Argument erstellen**. Dadurch wird eine neue Zeile mit einem neuen Argument mit den folgenden Standardwerten hinzugefügt: Argumentx für den **Namen** , wobei x eine ganze Zahl mit einem Anfangswert von 1 ist, die automatisch, zum Erstellen von eindeutigen Argumentnamen inkrementiert wird, **In**  für die **Richtung**, und **Zeichenfolge** für die **Argumenttyp**. Wird kein Wert für hinzugefügt **Standardwert**. Sie können diese Werte jederzeit während des Workflowentwurfs ändern.  
  
    > [!NOTE]
    >  Um ein Argument zu löschen, wählen Sie das Argument, indem Sie darauf klicken, und drücken Sie dann die **löschen** Schlüssel.  
  
## <a name="see-also"></a>Siehe auch  
 [Mithilfe des Workflowdesigners](../workflow-designer/using-the-workflow-designer.md)   
 [Variablen und Argumente](/dotnet/framework/windows-workflow-foundation/variables-and-arguments)