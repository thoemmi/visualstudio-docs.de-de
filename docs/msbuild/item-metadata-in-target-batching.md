---
title: Elementmetadaten bei der Batchverarbeitung von Zielen | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- batching [MSBuild]
- MSBuild, target batching
- target batching [MSBuild]
ms.assetid: f3cc4186-6a4c-4161-bbe5-1ec638b4925b
caps.latest.revision: "6"
author: kempb
ms.author: kempb
manager: ghogen
ms.workload: multiple
ms.openlocfilehash: 84be1157000e44b40f93ef51ca173247b3851d5f
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="item-metadata-in-target-batching"></a>Elementmetadaten bei der Batchverarbeitung von Zielen
[!INCLUDE[vstecmsbuild](../extensibility/internals/includes/vstecmsbuild_md.md)] kann eine Abhängigkeitsanalyse für die Ein- und Ausgaben eines Buildziels durchführen. Wenn ermittelt wird, dass die Ein- oder Ausgaben des Ziels auf dem neuesten Stand sind, wird das Ziel übersprungen, und der Build wird fortgesetzt. `Target`-Elemente verwenden die `Inputs`- und `Outputs`-Attribute, um die Elemente festzulegen, die bei der Abhängigkeitsanalyse überprüft werden.  
  
 Wenn ein Ziel eine Aufgabe enthält, die Batchelemente als Eingaben oder Ausgaben verwendet, sollte in den `Inputs`- oder `Outputs`-Attributen des `Target`-Zielelements die Batchverarbeitung genutzt werden, sodass [!INCLUDE[vstecmsbuild](../extensibility/internals/includes/vstecmsbuild_md.md)]-Batchelemente übersprungen werden, die bereits auf dem neuesten Stand sind.  
  
## <a name="batching-targets"></a>Batchverarbeitung von Zielen  
 Das folgende Beispiel enthält die Elementliste `Res`, die mithilfe der `Culture`-Elementmetadaten in zwei Batches aufgeteilt wird. Jeder Batch wird der `AL`-Aufgabe übergeben, die jeweils eine Ausgabeassembly erstellt. Durch die Batchverarbeitung von `Outputs`-Attributen des `Target`-Elements kann [!INCLUDE[vstecmsbuild](../extensibility/internals/includes/vstecmsbuild_md.md)] vor dem Ausführen des Ziels ermitteln, ob jeder Batch aktuell ist. Ohne die Batchverarbeitung von Zielen würden beide Elementbatches immer dann von der Aufgabe ausgeführt werden, wenn das Ziel ausgeführt wird.  
  
```xml  
<Project  
    xmlns="http://schemas.microsoft.com/developer/msbuild/2003">  
  
    <ItemGroup>  
        <Res Include="Strings.fr.resources">  
            <Culture>fr</Culture>  
        </Res>  
        <Res Include="Strings.jp.resources">  
            <Culture>jp</Culture>  
        </Res>  
        <Res Include="Menus.fr.resources">  
            <Culture>fr</Culture>  
        </Res>  
        <Res Include="Dialogs.fr.resources">  
            <Culture>fr</Culture>  
        </Res>  
        <Res Include="Dialogs.jp.resources">  
            <Culture>jp</Culture>  
        </Res>  
        <Res Include="Menus.jp.resources">  
            <Culture>jp</Culture>  
        </Res>  
    </ItemGroup>  
  
    <Target Name="Build"  
        Inputs="@(Res)"  
        Outputs="%(Culture)\MyApp.resources.dll">  
  
        <AL Resources="@(Res)"  
            TargetType="library"  
            OutputAssembly="%(Culture)\MyApp.resources.dll"  
  
    </Target>  
  
</Project>  
```  
  
## <a name="see-also"></a>Siehe auch  
 [Vorgehensweise: Inkrementelles Erstellen](../msbuild/how-to-build-incrementally.md)   
 [Batching (Batchverarbeitung)](../msbuild/msbuild-batching.md)   
 [Target-Element (MSBuild)](../msbuild/target-element-msbuild.md)   
 [Elementmetadaten bei der Batchverarbeitung von Aufgaben](../msbuild/item-metadata-in-task-batching.md)