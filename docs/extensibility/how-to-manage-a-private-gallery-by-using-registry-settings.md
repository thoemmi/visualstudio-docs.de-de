---
title: 'Vorgehensweise: Verwalten von privaten Katalog mithilfe von Registrierungseinstellungen | Microsoft Docs'
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- VSIX private galleries, managing
- managing VSIX private galleries
ms.assetid: 86b86442-4293-4cad-9fe2-876eef65f426
caps.latest.revision: "6"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload: vssdk
ms.openlocfilehash: 8d88c4b440f61e87792210e8a0844b6b622e8f05
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-manage-a-private-gallery-by-using-registry-settings"></a>Vorgehensweise: Verwalten von privaten Katalog mithilfe von Registrierungseinstellungen
Wenn Sie ein Administrator oder Entwickler einer isolierten Shell-Erweiterung sind, können Sie den Zugriff auf den Steuerelementen, Vorlagen und Tools in Visual Studio Gallery, Samples Gallery oder private Kataloge steuern. Damit einen Katalog verfügbar oder nicht verfügbar ist, erstellen Sie eine PKGDEF-Datei, die die geänderte Registrierungsschlüssel und ihre Werte beschreibt.  
  
## <a name="managing-private-galleries"></a>Verwalten von Private Kataloge  
 Sie können eine PKGDEF-Datei zum Steuern des Zugriffs auf Galerien auf mehreren Computern erstellen. Diese Datei muss folgende Format aufweisen.  
  
```  
[$RootKey$\ExtensionManager\Repositories\{UniqueGUID}]  
@={URI}  (REG_SZ)  
Disabled=0 | 1 (DWORD)  
Priority=0 (highest priority) ... MaxInt (lowest priority) (DWORD) (uint)  
Protocol=Atom Feed|Sharepoint (REG_SZ)  
DisplayName={DisplayName} (REG_SZ)  
DisplayNameResourceID={ID} (REG_SZ)  
DisplayNamePackageGuid={GUID} (REG_SZ)  
  
```  
  
 Die `Repositories` Schlüssel verweist, an den Katalog aktiviert bzw. deaktiviert werden soll. Der Visual Studio Gallery und der Beispielgalerie verwenden das folgende Repository GUIDs:  
  
-   Visual Studio Gallery: 0F45E408-7995-4375-9485-86B8DB553DC9  
  
-   Samples Gallery: AEB9CB40-D8E6-4615-B52C-27E307F8506C  
  
 Die `Disabled` Wert ist optional. Standardmäßig wird ein Katalog aktiviert.  
  
 Die `Priority` Wert bestimmt die Reihenfolge, in der die Kataloge, im Dialogfeld "Optionen aufgeführt sind". Visual Studio Gallery hat Priorität 10, und die Samples Gallery hat Priorität 20. Private Kataloge, ausgehend von Priorität 100 ab. Wenn mehrere Sammlungen denselben Prioritätswert aufweisen, wird die Reihenfolge der bestimmt, nach den Werten ihrer lokalisierten `DisplayName` Attribute.  
  
 Die `Protocol` Wert ist erforderlich für Atom oder SharePoint-basierte Kataloge.  
  
 Entweder `DisplayName`, oder beides `DisplayNameResourceID` und `DisplayNamePackageGuid`, muss angegeben werden. Wenn all angegeben werden, und klicken Sie dann die `DisplayNameResourceID` und `DisplayNamePackageGuid` -Paar wird verwendet.  
  
## <a name="disabling-the-visual-studio-gallery-using-a-pkgdef-file"></a>Deaktivieren eine PKGDEF-Datei mit Visual Studio Gallery  
 Sie können eine Sammlung in eine PKGDEF-Datei deaktivieren. Der folgende Eintrag wird der Visual Studio Gallery deaktiviert:  
  
```  
[$RootKey$\ExtensionManager\Repositories\{0F45E408-7995-4375-9485-86B8DB553DC9}]  
"Disabled"=dword:00000001  
  
```  
  
 Der folgende Eintrag deaktiviert die Samples Gallery:  
  
```  
[$RootKey$\ExtensionManager\Repositories\{AEB9CB40-D8E6-4615-B52C-27E307F8506C}]  
"Disabled"=dword:00000001  
  
```  
  
## <a name="see-also"></a>Siehe auch  
 [Private Kataloge](../extensibility/private-galleries.md)