---
title: IDebugNoSymbolsEvent2 | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: IDebugNoSymbolsEvent2 interface
ms.assetid: f6fb6388-47f6-4385-9ad5-95d62f9a7592
caps.latest.revision: "6"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload: vssdk
ms.openlocfilehash: 4c103cdfec8d93c8b43106d5e2b3757750ffda70
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="idebugnosymbolsevent2"></a>IDebugNoSymbolsEvent2
Signalisiert dem [!INCLUDE[vsprvs](../../../code-quality/includes/vsprvs_md.md)] debugger-Benutzeroberfläche, die dem Benutzer gewarnt, dass die Symbole nicht gefunden für gestarteten Programmdateien werden konnte.  
  
## <a name="syntax"></a>Syntax  
  
```  
IDebugNoSymbolsEvent2 : IUnknown  
```  
  
## <a name="notes-for-implementers"></a>Hinweise für Implementierer  
 Durch Debugmodule implementiert und von der [!INCLUDE[vsprvs](../../../code-quality/includes/vsprvs_md.md)] debugger-Benutzeroberfläche.  
  
## <a name="requirements"></a>Anforderungen  
 Header: Msdbg.h  
  
 Namespace: Microsoft.VisualStudio.Debugger.Interop  
  
 Assembly: Microsoft.VisualStudio.Debugger.Interop.dll