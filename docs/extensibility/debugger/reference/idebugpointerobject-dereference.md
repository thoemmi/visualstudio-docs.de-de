---
title: IDebugPointerObject::Dereference | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: IDebugPointerObject::Dereference
helpviewer_keywords: IDebugPointerObject::Dereference method
ms.assetid: 196ec2cc-8569-4780-b217-23b24e7f50ca
caps.latest.revision: "9"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload: vssdk
ms.openlocfilehash: 3e743f5a312e437ca48a5e36fb202783f41b934d
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="idebugpointerobjectdereference"></a>IDebugPointerObject::Dereference
Ruft das Objekt verweist.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
HRESULT DeReference(   
   DWORD          dwIndex,  
   IDebugObject** ppObject  
);  
```  
  
```csharp  
int Dereference(  
   uint             dwIndex,   
   out IDebugObject ppObject  
);  
```  
  
#### <a name="parameters"></a>Parameter  
 `dwIndex`  
 [in] Ein einfache Byteoffset vom Beginn des Objekts verweist.  
  
 `ppObject`  
 [out] Gibt eine [IDebugObject](../../../extensibility/debugger/reference/idebugobject.md) Objekt gezeigt wird, die das Objekt darstellt, sowie Werte für offset, sofern vorhanden.  
  
## <a name="return-value"></a>Rückgabewert  
 Im Erfolgsfall gibt S_OK zurück. Andernfalls wird ein Fehlercode zurückgegeben. E_FAIL zurück, wenn dieses Objekt nicht in ein anderes Objekt verweist.  
  
## <a name="remarks"></a>Hinweise  
 Das Objekt verweist, kann ein primitiver oder ein komplexer Typ sein wie z. B. eine Klasse oder Struktur sein.  
  
## <a name="see-also"></a>Siehe auch  
 [IDebugPointerObject](../../../extensibility/debugger/reference/idebugpointerobject.md)