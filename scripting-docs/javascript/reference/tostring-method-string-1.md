---
title: "toString-Methode (String) | Microsoft Docs"
ms.custom: ""
ms.date: "01/18/2017"
ms.prod: "windows-client-threshold"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-javascript"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
dev_langs: 
  - "JavaScript"
  - "TypeScript"
  - "DHTML"
ms.assetid: 56178c6e-cb08-4b34-824c-f63505379952
caps.latest.revision: 2
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 2
---
# toString-Methode (String)
Gibt eine Zeichenfolgendarstellung einer Zeichenfolge zurück.  
  
## Syntax  
  
```  
  
string.toString()  
```  
  
## Parameter  
 `string`  
 Erforderlich.  Das Array, das als Zeichenfolge dargestellt werden soll.  
  
## Rückgabewert  
 Die Zeichenfolgendarstellung der Zeichenfolge.  
  
## Beispiel  
 Das folgende Beispiel veranschaulicht die Verwendung der **toString**\-Methode mit einer Zeichenfolge.  
  
```javascript  
var string = "this is a test";  
var strStr = string.toString();  
document.write(strStr);  
  
// Output: this is a test  
  
```  
  
## Anforderungen  
 [!INCLUDE[jsv2](../../javascript/reference/includes/jsv2-md.md)]