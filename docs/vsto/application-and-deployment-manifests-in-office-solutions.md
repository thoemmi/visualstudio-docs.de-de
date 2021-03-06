---
title: Anwendungs- und Bereitstellungsmanifeste in Office-Projektmappen | Microsoft Docs
ms.custom: 
ms.date: 02/02/2017
ms.reviewer: 
ms.suite: 
ms.technology: office-development
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- manifests [Office development in Visual Studio]
- deployment manifests [Office development in Visual Studio]
- application manifests [Office development in Visual Studio]
- assemblies [Office development in Visual Studio], updating
author: TerryGLee
ms.author: tglee
manager: ghogen
ms.workload: office
ms.openlocfilehash: fe801405795b3ca0fcb28f024a69d0a9c9c22d8b
ms.sourcegitcommit: f9fbf1f55f9ac14e4e5c6ae58c30dc1800ca6cda
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/10/2018
---
# <a name="application-and-deployment-manifests-in-office-solutions"></a>Anwendungs- und Bereitstellungsmanifeste in Office-Projektmappen
  Ein Anwendungsmanifest ist eine XML-Datei, über die Informationen bereitgestellt werden, mit denen eine Office-Projektmappe nach ihren Assemblys sucht und diese aktualisiert. Ein Anwendungsmanifest kann zusammen mit einem Bereitstellungsmanifest verwendet werden. Dabei handelt es sich um eine XML-Datei, die auf dem Server gespeichert ist und die Informationen bereitstellt, die zum Auffinden der aktuellsten Version des Anwendungsmanifests und der Assemblys verwendet werden.  
  
 [!INCLUDE[appliesto_all](../vsto/includes/appliesto-all-md.md)]  
  
## <a name="manifest-structure-for-office-solutions"></a>Manifeststruktur für Office-Projektmappen  
 Für Microsoft Office-Projektmappen, die mit den Office-Entwicklungstools in Visual Studio erstellt wurden, basieren alle Manifeste auf dem standardmäßigen ClickOnce-Schema. Beim Bereitstellen von Office-Projektmappen befinden sich die Anwendungsmanifeste sowohl für Projekte auf Dokumentebene als auch für VSTO-Add-In-Projekte im ClickOnce-Cache. Die Bereitstellungsmanifeste werden nicht auf den Clientcomputer kopiert.  
  
 Informationen zum Inhalt von Anwendungs- und Bereitstellungsmanifesten für Office-Projekte finden Sie unter [Application Manifests for Office Solutions](../vsto/application-manifests-for-office-solutions.md) und [Deployment Manifests for Office Solutions](../vsto/deployment-manifests-for-office-solutions.md).  
  
## <a name="creating-application-and-deployment-manifests"></a>Erstellen von Anwendungs- und Bereitstellungsmanifesten  
 Anwendungsmanifeste werden automatisch als Teil des Buildprozesses erstellt. Bei jeder Erstellung eines Projekts auf Dokumentebene wird der Speicherort des Bereitstellungsmanifests als benutzerdefinierte Dokumenteigenschaft in das Dokument eingebettet. Für VSTO-Add-Ins wird der Speicherort des Bereitstellungsmanifests in der Registrierung gespeichert.  
  
 Weitere Informationen zu den **Veröffentlichungs-Assistenten**, finden Sie unter [Bereitstellen einer Office-Lösung mithilfe von ClickOnce](../vsto/deploying-an-office-solution-by-using-clickonce.md).  
  
 Weitere Informationen zur Verwendung von Manifesten mit Office-Projektmappen finden Sie unter [Bereitstellen einer Office-Lösung](../vsto/deploying-an-office-solution.md).  
  
## <a name="see-also"></a>Siehe auch  
 [Architektur von Anpassungen auf Dokumentebene](../vsto/architecture-of-document-level-customizations.md)   
 [Architektur von VSTO-Add-ins](../vsto/architecture-of-vsto-add-ins.md)   
 [Entwerfen und Erstellen von Office-Projektmappen](../vsto/designing-and-creating-office-solutions.md)   
 [Application Manifests for Office Solutions](../vsto/application-manifests-for-office-solutions.md)   
 [Bereitstellungsmanifeste für Office-Projektmappen](../vsto/deployment-manifests-for-office-solutions.md)   
 [ClickOnce-Anwendungsmanifest](/visualstudio/deployment/clickonce-application-manifest)   
 [ClickOnce-Bereitstellungsmanifest](/visualstudio/deployment/clickonce-deployment-manifest)  
  
  