---
title: 'Vorgehensweise: Debuggen von XAML mit dem Workflow-Designer | Microsoft Docs'
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: reference
ms.assetid: d9305dbc-af62-4bdd-b03f-c54e3fe9ecc7
caps.latest.revision: "8"
author: ErikRe
ms.author: erikre
manager: erikre
ms.workload: uwp
ms.openlocfilehash: 32144a651fe9178da8bc87a10377e2c4d086d398
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-debug-xaml-with-the-workflow-designer"></a>Vorgehensweise: Debuggen von XAML mit dem Workflow-Designer
Workflows werden in XAML definiert. In der Benutzeroberfläche werden Workflows in Form einer XAML-Struktur dargestellt, die den Workflow definiert. Der Debugprozess gestaltet sich ähnlich dem Debuggen von Workflows in [!INCLUDE[wfd1](../workflow-designer/includes/wfd1_md.md)]. Während des Debuggens von XAML arbeiten beispielsweise die Fenster "Lokal", "Überwachen" und "Threads" genau wie während des [!INCLUDE[wfd2](../workflow-designer/includes/wfd2_md.md)]-Debuggens. Zusätzlich ist während des XAML-Debuggens die Aufruflistenansicht als zeilenbasierte hierarchische Ansicht des Ausführungsflusses für den Workflow verfügbar.  
  
> [!NOTE]
>  Wenn sich das XAML für einen Workflow in derselben Assembly wie die Aktivitäten befindet, wird der Assemblyteil der Klassennamen nicht eingeschlossen. Ohne diesen Teil der Klassen-(Aktivitäts-)namen kann das XAML zur Laufzeit nicht geladen werden. Es wird davon abgeraten, Aktivitäten in demselben Namespace wie das Hauptprojekt zu definieren; andernfalls muss das XAML manuell bearbeitet werden, nachdem es im Designer bearbeitet wurde.  
  
### <a name="to-debug-workflow-xaml"></a>So debuggen Sie Workflow-XAML  
  
1.  Öffnen Sie in [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] ein Workflow- oder ein Aktivitätsprojekt.  
  
2.  Legen Sie einen Haltepunkt für die Aktivität oder Aktivitäten, die zu debuggende wie beschrieben in [Vorgehensweise: Festlegen von Haltepunkten in Workflows](../workflow-designer/how-to-set-breakpoints-in-workflows.md).  
  
3.  Mit der rechten Maustaste in der XAML-Datei, die die Workflowdefinition, und wählen enthält **Code anzeigen**. Der Haltepunkt wird in der gleichen Zeile wie die XAML-Elementdeklaration der Aktivität angezeigt, für die Sie den Haltepunkt in der Entwurfsansicht festgelegt haben.  
  
4.  Rufen Sie den Debugger aus, wie in beschrieben [Vorgehensweise: Aufrufen der Workflow-Debugger](../workflow-designer/how-to-invoke-the-workflow-debugger.md).  
  
5.  Wenn die Codeausführung einen der Haltepunkte erreicht, wird das diesem Haltepunkt zugeordnete XAML-Element hervorgehoben dargestellt. Um zum nächsten Haltepunkt zu verschieben, verwenden die **F10** oder **F11** Schlüssel.  
  
## <a name="see-also"></a>Siehe auch  
 [Vorgehensweise: Festlegen von Haltepunkten in Workflows](../workflow-designer/how-to-set-breakpoints-in-workflows.md)   
 [Vorgehensweise: Aufrufen des Workflow-Debuggers](../workflow-designer/how-to-invoke-the-workflow-debugger.md)