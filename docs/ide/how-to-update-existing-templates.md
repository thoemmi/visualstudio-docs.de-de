---
title: Aktualisieren vorhandener Projekt- und Elementvorlagen in Visual Studio | Microsoft-Dokumentation
ms.custom: 
ms.date: 01/02/2018
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-general
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- item templates, updating
- Visual Studio templates, updating
- project templates, updating
- updating templates [Visual Studio]
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: 9401f8a9a07f7098575ff267825982a03024e968
ms.sourcegitcommit: 9357209350167e1eb7e50b483e44893735d90589
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 01/05/2018
---
# <a name="how-to-update-existing-templates"></a>Vorgehensweise: Aktualisieren vorhandener Vorlagen

Nachdem Sie eine Vorlage erstellt und die Dateien in einer ZIP-Datei komprimiert haben, möchten Sie die Vorlage vielleicht ändern. Dazu können Sie die Dateien in der Vorlage manuell ändern oder aber eine neue Vorlage aus einem Projekt exportieren, das auf der Vorlage basiert.

## <a name="using-the-export-template-wizard-to-update-an-existing-project-template"></a>Verwenden des Assistenten zum Exportieren von Vorlagen zum Aktualisieren einer vorhandenen Projektvorlage

Visual Studio stellt den **Assistenten zum Exportieren von Vorlagen** bereit, der zum Aktualisieren einer vorhandenen Vorlage verwendet werden kann:

1. Wählen Sie **Datei** > **Neu** > **Projekt** aus, um das Dialogfeld **Neues Projekt** zu öffnen.

1. Wählen Sie die zu aktualisierende Vorlage aus, geben Sie einen Namen und Speicherort für Ihr Projekt ein, und klicken Sie auf **OK**.

1. Bearbeiten Sie das Projekt in Visual Studio.

1. Klicken Sie im Menü **Projekt** auf **Vorlage exportieren...**.

    Der **Assistent zum Exportieren von Vorlagen** wird geöffnet.

1. Befolgen Sie die Anweisungen im Assistenten, um die Vorlage als ZIP-Datei zu exportieren.

1. (Optional) Speichern Sie die ZIP-Datei im folgenden Verzeichnis, um die Vorlage dem Dialogfeld **Neues Projekt** hinzuzufügen: „%USERPROFILE%\Documents\Visual Studio \<version\>\Templates\ProjectTemplates“. Sie müssen diesen Schritt ausführen, wenn Sie im **Assistenten zum Exportieren von Vorlagen** nicht die Option **Vorlage automatisch in Visual Studio importieren** ausgewählt haben.

1. Löschen Sie die alte ZIP-Datei der Vorlage.

## <a name="manually-updating-an-existing-template"></a>Manuelles Aktualisieren vorhandener Vorlagen

Sie können eine vorhandene Vorlage ohne den **Assistenten zum Exportieren von Vorlagen** aktualisieren, indem Sie die in der komprimierten ZIP-Datei enthaltenen Dateien ändern.

### <a name="to-manually-update-an-existing-template"></a>So aktualisieren Sie eine vorhandene Vorlage manuell

1. Suchen Sie die ZIP-Datei, die die Vorlage enthält. Benutzerprojektvorlagen werden in der Regel unter „%USERPROFILE%\Documents\Visual Studio \<version\>\Templates\ProjectTemplates“ gespeichert.

1. Extrahieren Sie die ZIP-Datei.

1. Ändern oder löschen Sie die aktuellen Vorlagendateien, oder fügen Sie der Vorlage neue Dateien hinzu.

1. Öffnen, ändern und speichern Sie die XML-Datei mit der Erweiterung .vstemplate, damit das geänderte Verhalten bzw. neue Dateien berücksichtigt werden.

    Weitere Informationen zum VSTEMPLATE-Schema finden Sie unter [Visual Studio Template Schema Reference (Extensibility) (Schemareferenz zu Vorlagen für Visual Studio (Erweiterbarkeit))](../extensibility/visual-studio-template-schema-reference.md). Weitere Informationen darüber, welche Elemente in den Quelldateien parametrisiert werden können, finden Sie unter [Vorlagenparameter](../ide/template-parameters.md).

1. Wählen Sie die Dateien in Ihrer Vorlage aus, führen Sie einen Rechtsklick durch, oder klicken Sie auf das Kontextmenü, und wählen Sie **Senden an** > **ZIP-komprimierter Ordner** aus.

    Die ausgewählten Dateien werden in einer ZIP-Datei komprimiert.

1. Fügen Sie die neue ZIP-Datei in demselben Verzeichnis ein, in dem sich auch die alte ZIP-Datei befand.

1. Löschen Sie die extrahierten Vorlagendateien und die alte ZIP-Datei der Vorlage.

## <a name="see-also"></a>Siehe auch

[Anpassen von Vorlagen](../ide/customizing-project-and-item-templates.md)  
[Erstellen von Projekt- und Elementvorlagen](../ide/creating-project-and-item-templates.md)  
[Schemareferenz zu Visual Studio-Vorlagen](../extensibility/visual-studio-template-schema-reference.md)  
[Vorlagenparameter](../ide/template-parameters.md)  
[Gewusst wie: Erstellen von Starter Kits](../ide/how-to-create-starter-kits.md)