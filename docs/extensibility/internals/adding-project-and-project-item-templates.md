---
title: "Datenbankprojekt hinzugefügt und Projektelementvorlagen | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- projects [Visual Studio SDK], adding
- project items [Visual Studio], adding
ms.assetid: 8c59217f-56e5-4540-a73b-cd10de189373
caps.latest.revision: "17"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload: vssdk
ms.openlocfilehash: 1d0c9e684312468011f63bdfbb72d1cdadba6b08
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="adding-project-and-project-item-templates"></a>Hinzufügen von Projekt- und Projektelementvorlagen
Wenn Sie eine eigene Projekttypen erstellen, müssen Sie bieten Unterstützung für das Hinzufügen von neuen Projekten und Projektelementen mit den standardmäßigen [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] Development Environment, (IDE) Dialogfelder integriert. Die folgenden Themen behandeln die verschiedene Verfahren, um Projekte und Projektelemente hinzufügen.  
  
## <a name="in-this-section"></a>In diesem Abschnitt  
 [Projektkontext](../../extensibility/internals/project-context.md)  
 Erläutert, dass das Projekt die meisten der die Kontextinformationen bietet für was, in der Umgebung herausstellt.  
  
 [Projektpriorität](../../extensibility/internals/project-priority.md)  
 Erläutert, dass ein Projektelement in der Regel ein Mitglied eines Projekts zu Mehrdeutigkeiten zu vermeiden, darüber, welche Projekt verwendet wird, um das Element zu öffnen.  
  
 [Verschiedene Projektdateien](../../extensibility/internals/miscellaneous-files-project.md)  
 Enthält Informationen zu den zwei Typen von Editoren, die zum Öffnen von Dateien in einem Projekt und die Rolle verwendet werden können, dass das Projekt spielt bei der Bestimmung der geeigneten Editors verwenden, wenn ein Projektelement geöffnet wird.  
  
 [Registrieren von Projekt- und Elementvorlagen](../../extensibility/internals/registering-project-and-item-templates.md)  
 Erläutert, was geschieht, wenn ein [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] Projekt wird erstellt.  
  
 [Hinzufügen von Elementen zu den Dialogfeldern „Neues Element hinzufügen“](../../extensibility/internals/adding-items-to-the-add-new-item-dialog-boxes.md)  
 Erläutert die Vorgehensweise zum Hinzufügen von Elementen, die **neues Element hinzufügen** (Dialogfeld).  
  
 [Hinzufügen von Verzeichnissen zum Dialogfeld „Neues Projekt“](../../extensibility/internals/adding-directories-to-the-new-project-dialog-box.md)  
 Enthält ein Beispiel registriert ein neues Verzeichnis, das benutzerdefinierte Vorlagen zur Verfügung gestellt, indem Sie ein VSPackage enthält.  
  
 [Hinzufügen von Verzeichnissen zum Dialogfeld „Neues Element hinzufügen“](../../extensibility/internals/adding-directories-to-the-add-new-item-dialog-box.md)  
 Enthält ein Beispiel der Registrierung eines neuen Satzes von Verzeichnissen für die **neues Element hinzufügen** (Dialogfeld).  
  
 [IDE-definierte Befehle zum Erweitern von Projektsystemen](../../extensibility/internals/ide-defined-commands-for-extending-project-systems.md)  
 Listet verschiedene Typen von Befehl-Elementen, die für die Erweiterung von Projektsystemen verwendet.  
  
 [CATIDs für Objekte, die in der Regel zum Erweitern von Projekten verwendet werden](../../extensibility/internals/catids-for-objects-that-are-typically-used-to-extend-projects.md)  
 Listet CATIDs für Objekte, die verwendet werden, um erweitern [!INCLUDE[vcprvc](../../code-quality/includes/vcprvc_md.md)], [!INCLUDE[csprcs](../../data-tools/includes/csprcs_md.md)], und [!INCLUDE[vbprvb](../../code-quality/includes/vbprvb_md.md)] Projektsysteme.  
  
## <a name="related-sections"></a>Verwandte Abschnitte  
 [Gewusst wie: Öffnen von projektspezifischen Editoren](../../extensibility/how-to-open-project-specific-editors.md)  
 Enthält schrittweise Anweisungen zum Öffnen ein Element an keinem bestimmten Editor für ein Projekt systemintern gebunden.  
  
 [Gewusst wie: Öffnen von Standard-Editoren](../../extensibility/how-to-open-standard-editors.md)  
 Enthält schrittweise Anweisungen zum Öffnen eines standard-Editors.  
  
 [Projektuntertypen](../../extensibility/internals/project-subtypes.md)  
 Enthält Links zu konzeptionellen Themen Untertyp Projekt an. Projekt Untertypen erweitert vorhandene [!INCLUDE[csprcs](../../data-tools/includes/csprcs_md.md)] und [!INCLUDE[vbprvb](../../code-quality/includes/vbprvb_md.md)] Projekte.  
  
 [Projekttypen](../../extensibility/internals/project-types.md)  
 Enthält Links zu weiteren Themen, die Informationen zum Entwerfen neuer Projekttypen bieten.