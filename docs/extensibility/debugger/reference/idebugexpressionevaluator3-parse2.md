---
title: IDebugExpressionEvaluator3::Parse2 | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: IDebugExpressionEvaluator3::Parse2
ms.assetid: 78099628-d600-4f76-b7c8-ee07c864af1e
caps.latest.revision: "11"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload: vssdk
ms.openlocfilehash: c4c5e2a62cfbe44fe6a68da703df6ff81a89d07e
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="idebugexpressionevaluator3parse2"></a>IDebugExpressionEvaluator3::Parse2
Konvertiert eine Ausdruckszeichenfolge eine analysierte Ausdruck erhält die Symbol-Anbieter und die Adresse des Auswertung Frames an.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
HRESULT Parse2 (  
   LPCOLESTR                upstrExpression,  
   PARSEFLAGS               dwFlags,  
   UINT                     nRadix,  
   IDebugSymbolProvider*    pSymbolProvider,  
   IDebugAddress*           pAddress,  
   BSTR*                    pbstrError,  
   UINT*                    pichError,  
   IDebugParsedExpression** ppParsedExpression  
);  
```  
  
```csharp  
HRESULT Parse2 (  
   string                     upstrExpression,  
   enum_PARSEFLAGS            dwFlags,  
   uint                       nRadix,  
   IDebugSymbolProvider       pSymbolProvider,  
   IDebugAddress              pAddress,  
   out string                 pbstrError,  
   out uint                   pichError,  
   out IDebugParsedExpression ppParsedExpression  
);  
```  
  
#### <a name="parameters"></a>Parameter  
 `upstrExpression`  
 [in] Die Ausdruckszeichenfolge analysiert werden soll.  
  
 `dwFlags`  
 [in] Eine Auflistung von [PARSEFLAGS](../../../extensibility/debugger/reference/parseflags.md) Konstanten, die bestimmen, wie der Ausdruck analysiert werden.  
  
 `nRadix`  
 [in] Basis für alle numerischen Informationen interpretieren zu verwendende.  
  
 `pSymbolProvider`  
 [in] Die Symbol-Anbieter-Schnittstelle.  
  
 `pAddress`  
 [in] Die Adresse des Frames, ausgewertet.  
  
 `pbstrError`  
 [out] Gibt den Fehler als einem von Menschen lesbaren Text zurück.  
  
 `pichError`  
 [out] Gibt die Zeichenposition des Beginns des Fehlers in der Zeichenfolge des Ausdrucks zurück.  
  
 `ppParsedExpression`  
 [out] Gibt die analysierten Ausdrucks in einer [IDebugParsedExpression](../../../extensibility/debugger/reference/idebugparsedexpression.md) Objekt.  
  
## <a name="return-value"></a>Rückgabewert  
 Im Erfolgsfall gibt `S_OK`ist, andernfalls wird ein Fehlercode zurückgegeben.  
  
## <a name="remarks"></a>Hinweise  
 Diese Methode erzeugt eine analysierten Ausdrucks, nicht auf einen tatsächlichen Wert. Ein analysierter Ausdruck kann ausgewertet werden, d. h. in einen Wert konvertiert.  
  
## <a name="example"></a>Beispiel  
 Das folgende Beispiel veranschaulicht die Implementierung dieser Methode für eine **CEE** -Objekt, das macht die [IDebugExpressionEvaluator3](../../../extensibility/debugger/reference/idebugexpressionevaluator3.md) Schnittstelle.  
  
```cpp  
HRESULT CEE::Parse2 ( LPCOLESTR in_szExprText,  
  PARSEFLAGS in_FLAGS,  
  UINT in_RADIX,  
  IDebugSymbolProvider *pSymbolProvider,  
  IDebugAddress *pAddress,  
  BSTR* out_pbstrError,  
  UINT* inout_pichError,  
  IDebugParsedExpression** out_ppParsedExpression )  
{  
    // precondition  
    REQUIRE( NULL != in_szExprText );  
    //REQUIRE( NULL != out_pbstrError );  
    REQUIRE( NULL != inout_pichError );  
    REQUIRE( NULL != out_ppParsedExpression );  
  
    if (NULL == in_szExprText)  
        return E_INVALIDARG;  
  
    if (NULL == inout_pichError)  
        return E_POINTER;  
  
    if (NULL == out_ppParsedExpression)  
        return E_POINTER;  
  
    if (out_pbstrError)  
        *out_pbstrError = NULL;  
  
    *out_ppParsedExpression = NULL;  
  
    INVARIANT( this );  
  
    if (!this->ClassInvariant())  
        return E_UNEXPECTED;  
  
    // function body  
    EEDomain::fParseExpression DomainVal =  
    {  
        this,                   // CEE*  
        in_szExprText,          // LPCOLESTR  
        in_FLAGS,               // EVALFLAGS  
        in_RADIX,               // RADIX  
        out_pbstrError      ,   // BSTR*  
        inout_pichError,        // UINT*  
        pSymbolProvider,  
        out_ppParsedExpression  // Output  
    };  
  
    return (*m_LanguageSpecificUseCases.pfParseExpression)(DomainVal);  
}  
```  
  
## <a name="see-also"></a>Siehe auch  
 [IDebugExpressionEvaluator3](../../../extensibility/debugger/reference/idebugexpressionevaluator3.md)