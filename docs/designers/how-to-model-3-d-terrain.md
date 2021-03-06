---
title: "Vorgehensweise: Modellieren eines 3D-Geländes | Microsoft-Dokumentation"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-designers
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: f779b1fd-82a9-4a11-8ab7-c1c9caabc883
caps.latest.revision: "17"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload: multiple
ms.openlocfilehash: cccd65c62d8b5a0f75052c3121e313507ad5d8b8
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-model-3-d-terrain"></a>Gewusst wie: Modellieren eines 3D-Geländes
In diesem Dokument wird gezeigt, wie der Modell-Editor zum Erstellen eines 3D-Geländes verwendet wird.  
  
 In diesem Dokument werden die folgenden Aktivitäten veranschaulicht:  
  
-   Hinzufügen von Objekten in einer Szene  
  
-   Auswählen von Flächen und Punkten  
  
-   Übertragen der Auswahl  
  
-   Verwenden des Tools **Flächen unterteilen**  
  
-   Umrahmen eines Objekt in der Entwurfsoberfläche  
  
## <a name="creating-a-3-d-terrain-model"></a>Erstellen eines 3D-Geländemodells  
 Sie können ein 3D-Gelände erstellen, indem Sie eine Ebene unterteilen, um zusätzliche Flächen zu erstellen und anschließend ihre Schnittpunkte zur Erstellung interessanter Geländefunktionen zu bearbeiten.  
  
 Das Modell sollte dann etwa so aussehen:  
  
 ![3D-Szene zur Darstellung eines Geländemodells](../designers/media/digit-terrain-model.png "Digit-Terrain-Model")  
  
 Bevor Sie beginnen, stellen Sie sicher, dass das Fenster **Eigenschaften** und die **Toolbox** angezeigt werden.  
  
#### <a name="to-create-a-3-d-terrain-model"></a>So erstellen Sie ein 3D-Geländemodell  
  
1.  Erstellen Sie ein 3D-Modell, mit dem Sie arbeiten. Weitere Informationen zum Hinzufügen eines Modells zu Ihren Projekten finden Sie im Abschnitt „Erste Schritte“ unter [Modell-Editor](../designers/model-editor.md).  
  
2.  Fügen Sie eine Fläche in die Szene ein. Klicken Sie in der **Toolbox** unter **Formen** auf **Ebene**, und verschieben Sie es auf die Entwurfsoberfläche.  
  
    > [!TIP]
    >  Sie können das Ebenenobjekt auf der Entwurfsoberfläche umrahmen, um damit einfacher arbeiten zu können. Klicken Sie im Modus **Auswählen** auf das Ebenenobjekt und anschließend auf der Symbolleiste des Modell-Editors auf die Schaltfläche **Rahmenobjekt**  
  
3.  Gehen Sie in den Flächenauswahlmodus. Wählen Sie auf der Symbolleiste des Modell-Editors **Fläche auswählen** aus.  
  
4.  Unterteilen Sie die Ebene. Klicken Sie im Flächenauswahlmodus die Ebene einmal an, um sie auswählen zu können. Klicken Sie anschließend auf die Oberfläche der Ebene, um ihre einzige Fläche auszuwählen. Klicken Sie auf der Symbolleiste des Modell-Editors auf **Fläche unterteilen**. Dadurch werden neue Schnittpunkte auf der Oberfläche der Ebene hinzugefügt, die sie in vier gleichgroße Teile aufteilen.  
  
5.  Erstellen Sie weitere Unterteilungen. Klicken Sie zweimal auf **Fläche unterteilen**, während die neuen Flächen noch ausgewählt sind. Dadurch werden insgesamt 64 Flächen erstellt. Sie können dem Gelände sogar noch mehr Details verleihen, indem Sie mehr Unterteilungen erstellen.  
  
6.  Gehen Sie in den Punktauswahlmodus. Wählen Sie auf der Symbolleiste des Modell-Editors **Punkt auswählen** aus.  
  
7.  Ändern Sie einen Punkt, um eine Geländefunktion zu erstellen. Klicken Sie im Punktauswahlmodus auf einen der Punkte und wählen Sie anschließend auf der Symbolleiste des Modell-Editors das Tool **Übertragen** aus. Ein Feld, das den Punkt darstellt, wird auf der Entwurfsoberfläche angezeigt. Verwenden Sie den grünen Pfeil, um das Feld zu verschieben, wodurch die Punkthöhe verändert wird. Wiederholen Sie diesen Schritt für verschiedene Punkte, um interessante Geländefunktionen zu erstellen.  
  
    > [!TIP]
    >  Sie können mehrere Punkte gleichzeitig auswählen, um sie auf einmal zu bearbeiten.  
  
 Das Geländemodell ist fertig. Hier ist noch einmal das fertige Modell, bei dem eine Phong-Schattierung angewandt wurde.  
  
 ![3D-Szene zur Darstellung eines Geländemodells](../designers/media/digit-terrain-model.png "Digit-Terrain-Model")  
  
 Sie können dieses Geländemodell zur Veranschaulichung des Effekts des Farbverlauf-Shaders verwenden, das unter [Vorgehensweise: Erstellen eines geometriebasierten Farbverlauf-Shaders](../designers/how-to-create-a-geometry-based-gradient-shader.md) beschrieben wird.  
  
## <a name="see-also"></a>Siehe auch  
 [Modell-Editor](../designers/model-editor.md)