---
title: Verwalten der Signierung von Assemblys und Manifesten | Microsoft-Dokumentation
ms.custom: 
ms.date: 02/17/2017
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-general
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- manifests [Visual Studio]
- signing manifests [Visual Studio]
- application manifests [Visual Studio]
- assemblies [Visual Studio], signing
ms.assetid: 6c1ef36b-25f7-4ad0-b29a-51801b7a5420
caps.latest.revision: "15"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload: multiple
ms.openlocfilehash: d8227a514887150e3477e026a238df608fe98d11
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="managing-assembly-and-manifest-signing"></a>Verwalten der Signierung von Assemblys und Manifesten
Durch eine Signierung mit starkem Namen erhalten Softwarekomponenten eine global eindeutige Identität. Starke Namen werden verwendet, um sicherzustellen, dass die Assembly nicht von einem anderen Entwickler gespooft werden kann und dass Komponentenabhängigkeiten und Konfigurationsanweisungen der richtigen Komponente und Komponentenversion zugeordnet werden.  
  
 Ein starker Name setzt sich aus der Identität der Assembly – dem einfachen Textnamen, der Versionsnummer und Kulturinformationen – sowie einem öffentlichen Schlüsseltoken und einer digitalen Signatur zusammen.  
  
 Informationen zum Signieren von Assemblys in Visual Basic- und C#-Projekten finden Sie unter [Erstellen und Verwenden von Assemblys mit starkem Namen](http://msdn.microsoft.com/Library/ffbf6d9e-4a88-4a8a-9645-4ce0ee1ee5f9).  
  
 Informationen zum Signieren von Assemblys in Visual C++-Projekten finden Sie unter [Assemblys mit starken Namen (Assemblysignierung) (C++/CLI)](/cpp/dotnet/strong-name-assemblies-assembly-signing-cpp-cli).  

> [!NOTE]
>  Die Signierung mit starken Namen schützt nicht gegen Reverse Engineering (Zurückentwicklung) der Assembly.  Informationen zum Schutz gegen Reverse Engineering finden Sie unter [Dotfuscator Community Edition (CE)](dotfuscator/index.md).
  
## <a name="asset-types-and-signing"></a>Objekttypen und Signierung  
 Sie können .NET-Assemblys und Anwendungsmanifeste signieren. Hierzu gehört Folgendes:  
  
-   Ausführbare Dateien (.exe)  
  
-   Anwendungsmanifeste (.exe.manifest)  
  
-   Bereitstellungsmanifeste (.application)  
  
-   Freigegebene Komponentenassemblys (.dll)  
  
Sie müssen die folgenden Objekttypen signieren:  
  
1.  Assemblys, wenn diese im globalen Assemblycache (GAC) bereitgestellt werden sollen.  
  
2.  Anwendungs- und Bereitstellungsmanifeste in [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)]. Visual Studio aktiviert die Signierung für diese Anwendungen standardmäßig.  
  
3.  Primäre Interop-Assemblys, die für die COM-Interoperabilität verwendet werden. Durch das TLBIMP-Dienstprogramm werden primäre Interop-Assemblys mit einem starken Namen erzwungen, wenn diese aus einer COM-Typbibliothek erstellt werden.  
  
Im Allgemeinen sollten Sie ausführbare Dateien nicht signieren. Eine Komponente mit starkem Namen kann nicht auf eine Komponente ohne starken Namen verweisen, die mit der Anwendung bereitgestellt wird. Visual Studio signiert nicht ausführbare Dateien der Anwendung, signiert jedoch stattdessen das Anwendungsmanifest, das auf die ausführbare Datei mit schwachem Namen zeigt. Sie sollten generell vermeiden, Komponenten zu signieren, die für Ihre Anwendung privat sind, da das Signieren das Verwalten von Abhängigkeiten erschweren kann.  
  
## <a name="how-to-sign-an-assembly-in-visual-studio"></a>So erstellen Sie eine Assembly in Visual Studio  
 Zum Signieren einer Anwendung oder Komponente verwenden Sie die Registerkarte **Signierung** des Projekteigenschaftenfensters (klicken Sie mit der rechten Maustaste auf den Projektknoten im **Projektmappen-Explorer**, und wählen Sie **Eigenschaften** aus, geben Sie **Projekteigenschaften** im Fenster **Schnellstart** ein, oder drücken Sie innerhalb des Fensters **Projektmappen**-Explorer ALT+EINGABE). Aktivieren Sie auf der Registerkarte **Signierung** das Kontrollkästchen **Assembly signieren**.  
  
 Geben Sie eine Schlüsseldatei an. Wenn Sie eine neue Schlüsseldatei erstellen möchten, beachten Sie, dass neue Schlüsseldateien immer im PFX-Format erstellt werden. Sie benötigen einen Namen und ein Kennwort für die neue Datei.  
  
> [!WARNING]
>  Sie sollten die Schlüsseldatei immer mit einem Kennwort schützen, damit sie von keiner anderen Person verwendet werden kann. Sie können die Schlüsseldateien auch schützen, indem Sie Schlüsselanbieter oder Zertifikatspeicher verwenden.  
  
 Außerdem können Sie auf eine Schlüsseldatei, die Sie bereits erstellt haben, zeigen. Weitere Informationen zum Erstellen eines Schlüssels finden Sie unter [How to: Create a Public-Private Key (Vorgehensweise: Erstellen eines öffentlich-privaten Schlüsselpaars)](/dotnet/framework/app-domains/how-to-create-a-public-private-key-pair).  
  
 Wenn Sie nur Zugriff auf einen öffentlichen Schlüssel haben, können Sie verzögertes Signieren verwenden, um das Zuweisen des Schlüssels zu verzögern. Sie können auch das verzögerte Signieren aktivieren, indem Sie das Kontrollkästchen **Nur verzögerte Signierung** aktivieren. Ein verzögert signiertes Projekt wird nicht ausgeführt, und Sie können es nicht debuggen. Allerdings können Sie die Überprüfung während der Entwicklung überspringen, indem Sie [Sn.exe (Strong Name Tool)](/dotnet/framework/tools/sn-exe-strong-name-tool) mit der Option `-Vr` verwenden.  
  
 Weitere Informationen zum Signieren von Manifesten finden Sie unter [Vorgehensweise: Signieren von Anwendungs- und Bereitstellungsmanifesten](../ide/how-to-sign-application-and-deployment-manifests.md).  
  
## <a name="see-also"></a>Siehe auch  
 [Assemblys mit starkem Namen](/dotnet/framework/app-domains/strong-named-assemblies)   
 [Assemblys mit starken Namen (Assemblysignierung) (C++/CLI)](/cpp/dotnet/strong-name-assemblies-assembly-signing-cpp-cli)