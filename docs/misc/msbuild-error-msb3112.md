---
title: "MSBuild Error MSB3112 | Microsoft Docs"
ms.custom: ""
ms.date: "11/17/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "MSBuild.GenerateManifest.DuplicateAssemblyIdentity"
helpviewer_keywords: 
  - "MSB3112"
ms.assetid: 90f25254-8148-49ea-9a5a-213feda16df0
caps.latest.revision: 7
caps.handback.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "douge"
---
# MSBuild Error MSB3112
**MSB3112: Mindestens zwei Assemblys weisen die gleiche Identität "\<Assembly\>" auf.**  
  
 Diese Warnung wird generiert, wenn mehr als eine Assembly, auf die verwiesen wird, die gleiche Identität haben.  
  
### So beheben Sie diesen Fehler  
  
-   Entfernen Sie eine der Assemblys, auf die verwiesen wird, aus dem Projekt.  
  
## Siehe auch  
 [\<PackageFiles\>\-Element](../deployment/packagefiles-element-bootstrapper.md)