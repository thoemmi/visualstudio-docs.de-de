---
title: 'Idiasymbol:: Get_isnaked | Microsoft Docs'
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords: IDiaSymbol::get_isNaked method
ms.assetid: b16629dc-8e17-476b-9c7b-58e7277c61ed
caps.latest.revision: "7"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.workload: multiple
ms.openlocfilehash: 018c1398f268b28e5bd547bfbcf69335cc973cf4
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="idiasymbolgetisnaked"></a>IDiaSymbol::get_isNaked
Ruft ein Flag, das angibt, ob die Funktion verfügt über die [naked](/cpp/cpp/naked-cpp) Attribut (d. h. für die Funktion hat keinen Prolog oder Epilog Code, der vom Compiler hinzugefügt).  
  
## <a name="syntax"></a>Syntax  
  
```C++  
HRESULT get_isNaked(  
   BOOL *pFlag  
);  
```  
  
#### <a name="parameters"></a>Parameter  
 `pFlag`  
 [out] Gibt `TRUE` Wenn die Funktion der `naked` -Attribut; andernfalls wird zurückgegeben `FALSE`.  
  
## <a name="return-value"></a>Rückgabewert  
 Im Erfolgsfall gibt `S_OK`ist, andernfalls gibt `S_FALSE` oder ein Fehlercode.  
  
> [!NOTE]
>  Ein Rückgabewert von `S_FALSE` bedeutet, dass die Eigenschaft ist nicht verfügbar für das Symbol.  
  
## <a name="requirements"></a>Anforderungen  
  
|Anforderung|Beschreibung|  
|-----------------|-----------------|  
|Header:|dia2.h|  
|Version:|DIA-SDK 8.0|  
  
## <a name="see-also"></a>Siehe auch  
 [IDiaSymbol](../../debugger/debug-interface-access/idiasymbol.md)   
 [Naked-Funktionsaufrufe](/cpp/cpp/naked-function-calls)