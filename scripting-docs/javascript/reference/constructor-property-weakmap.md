---
title: Constructor-Eigenschaft (WeakMap) | Microsoft Docs
ms.custom: 
ms.date: 01/18/2017
ms.prod: windows-client-threshold
ms.reviewer: 
ms.suite: 
ms.technology: devlang-javascript
ms.tgt_pltfrm: 
ms.topic: language-reference
dev_langs:
- JavaScript
- TypeScript
- DHTML
ms.assetid: 1e3f9333-ce75-4d32-9b14-fbe81fd73dfb
caps.latest.revision: "3"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 5c7340e1e5eeff9a80e231cf1aa49443adc94e72
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/27/2017
---
# <a name="constructor-property-weakmap"></a>constructor-Eigenschaft (WeakMap)
Gibt die Funktion an, durch die ein `WeakMap`-Objekt erstellt wird.  
  
## <a name="syntax"></a>Syntax  
  
```JavaScript  
weakmap.constructor  
```  
  
## <a name="remarks"></a>Hinweise  
 Der erforderliche `weakmap`-Parameter ist der Name des `WeakMap`-Objekts.  
  
 Die `constructor`-Eigenschaft ist ein Member des Prototyps eines jeden Objekts, das einen Prototyp besitzt. Dies schließt alle systeminternen JavaScript-Objekte mit Ausnahme der Objekte `Global` und `Math` ein. Die `constructor`-Eigenschaft enthält einen Verweis auf die Funktion, mit der die Instanzen des betreffenden Objekts erstellt werden.  
  
## <a name="requirements"></a>Anforderungen  
 [!INCLUDE[jsv11](../../javascript/reference/includes/jsv11-md.md)]