---
title: Apply-Methode (Funktion) (JavaScript) | Microsoft Docs
ms.custom: 
ms.date: 01/18/2017
ms.prod: windows-client-threshold
ms.reviewer: 
ms.suite: 
ms.technology: devlang-javascript
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords: apply
dev_langs:
- JavaScript
- TypeScript
- DHTML
helpviewer_keywords: Apply method
ms.assetid: b36df78e-b14b-46ca-b5cb-de752d80f40a
caps.latest.revision: "10"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 5a06a37006937b07214bf5a314d5151c3b658acf
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/27/2017
---
# <a name="apply-method-function-javascript"></a>apply-Methode (Funktion) (JavaScript)
Ruft die Funktion, die das angegebene Objekt zum Ersetzen der `this` Wert der Funktion und des angegebenen Arrays für die Argumente der Funktion.  
  
## <a name="syntax"></a>Syntax  
  
```  
apply([thisObj[,argArray]])  
```  
  
## <a name="parameters"></a>Parameter  
 `thisObj`  
 Dies ist optional. Das Objekt, das als dienen der `this` Objekt.  
  
 `argArray`  
 Dies ist optional. Ein Satz von Argumenten, die an die Funktion übergeben werden.  
  
## <a name="remarks"></a>Hinweise  
 Wenn `argArray` nicht ist ein gültiges Objekt wird ein Fehler "Objekt erwartet" auftritt.  
  
 Wenn weder `argArray` noch `thisObj` angegeben werden, die ursprüngliche `this` Objekt dient als `thisObj` und keine Argumente übergeben werden.  
  
## <a name="example"></a>Beispiel  
 Der folgende Code zeigt, wie die Apply-Methode verwenden.  
  
```JavaScript  
function callMe(arg1, arg2){  
    var s = "";  
  
    s += "this value: " + this;  
    s += "<br />";  
    for (i in callMe.arguments) {  
        s += "arguments: " + callMe.arguments[i];  
        s += "<br />";  
    }  
    return s;  
}  
  
document.write("Original function: <br/>");  
document.write(callMe(1, 2));  
document.write("<br/>");  
  
document.write("Function called with apply: <br/>");  
document.write(callMe.apply(3, [ 4, 5 ]));  
  
// Output:   
// Original function:   
// this value: [object Window]  
// arguments: 1  
// arguments: 2  
  
// Function called with apply:   
// this value: 3  
// arguments: 4  
// arguments: 5  
  
```  
  
## <a name="requirements"></a>Anforderungen  
 [!INCLUDE[jsv55](../../javascript/reference/includes/jsv55-md.md)]  
  
## <a name="see-also"></a>Siehe auch  
 [Function-Objekt](../../javascript/reference/function-object-javascript.md)