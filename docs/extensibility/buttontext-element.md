---
title: ButtonText Element | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- ButtonText element (VSCT XML schema)
- VSCT XML schema elements, ButtonText
ms.assetid: 56aba884-0356-4894-ae4e-32d3938f6865
caps.latest.revision: "6"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload: vssdk
ms.openlocfilehash: c9f2374af403c37f18d1aa91700e51bd038a71c6
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="buttontext-element"></a>ButtonText-Element
Dieses Feld können Sie die Geben Sie den Text, der angezeigt wird, in verschiedenen Menüs. Wird standardmäßig die `ButtonText` Element wird im Menüsteuerelemente angezeigt. Die `ButtonText` Element wird auch die Standardeinstellung, wenn alle anderen Textfelder leer sind. Die `ButtonText` Element darf nicht leer sein, auch wenn die anderen Textfelder angegeben sind.  
  
## <a name="syntax"></a>Syntax  
  
```  
<ButtonText>My Command</ButtonText>  
```  
  
## <a name="attributes-and-elements"></a>Attribute und Elemente  
 In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.  
  
### <a name="attributes"></a>Attribute  
 Keine  
  
### <a name="child-elements"></a>Untergeordnete Elemente  
 Keine  
  
### <a name="parent-elements"></a>Übergeordnete Elemente  
  
|Element|Beschreibung|  
|-------------|-----------------|  
|[Strings-Element](../extensibility/strings-element.md)|Text-Elemente, wie z. B. gruppiert `ButtonText` und `CommandName`.|  
  
## <a name="text-value"></a>Textwert  
 Der Textwert, der die `ButtonText` Element enthält den Text, der für Menüelemente, Tastenkürzel und andere Elemente der Benutzeroberfläche (UI), für die sichtbaren Text angezeigt wird.  
  
## <a name="see-also"></a>Siehe auch  
 [VSCT-Dateien (Visual Studio Command Table)](../extensibility/internals/visual-studio-command-table-dot-vsct-files.md)