---
title: 'Idiasymbol:: Get_nostackordering | Microsoft Docs'
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords: IDiaSymbol::get_noStackOrdering method
ms.assetid: a1753917-705b-4165-9880-d05e91e6dcb4
caps.latest.revision: "7"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.workload: multiple
ms.openlocfilehash: ba7232d374e666a84d9d19225981d25c6a78ac3a
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="idiasymbolgetnostackordering"></a>IDiaSymbol::get_noStackOrdering
Diese Funktion ruft ein Flag, das angibt, ob keine Reihenfolge des Stapels im Rahmen des Puffers stapelüberprüfung erzielt werden kann ([/GS (Puffer-Sicherheitsüberprüfung)](/cpp/build/reference/gs-buffer-security-check) (Compileroption)).  
  
## <a name="syntax"></a>Syntax  
  
```C++  
HRESULT get_noStackOrdering(  
   BOOL *pRetVal  
);  
```  
  
#### <a name="parameters"></a>Parameter  
 `pRetVal`  
 [out] Gibt `TRUE` Wenn im Rahmen des Stapels Puffer überprüft werden sollen, keine Stapel Reihenfolge durchgeführt werden konnte, andernfalls `FALSE`.  
  
## <a name="return-value"></a>Rückgabewert  
 Im Erfolgsfall gibt `S_OK`ist, andernfalls gibt `S_FALSE` oder ein Fehlercode.  
  
> [!NOTE]
>  Ein Rückgabewert von `S_FALSE` bedeutet, dass die Eigenschaft nicht für das Symbol verfügbar ist.  
  
## <a name="requirements"></a>Anforderungen  
  
|Anforderung|Beschreibung|  
|-----------------|-----------------|  
|Header:|dia2.h|  
|Version:|DIA-SDK 8.0|  
  
## <a name="see-also"></a>Siehe auch  
 [IDiaSymbol](../../debugger/debug-interface-access/idiasymbol.md)   
 [/ GS (Puffer-Sicherheitsüberprüfung)](/cpp/build/reference/gs-buffer-security-check)