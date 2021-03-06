---
title: "Die ausgewählte Verbindung nutzt einen nicht unterstützten Datenbankanbieter | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 4d25dfa1-8fa4-4529-9b90-973bc2ec2993
caps.latest.revision: "3"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.technology: vs-data-tools
ms.workload: data-storage
ms.openlocfilehash: abd7ba49b3a9bb449f4f323deee588c3942d37a4
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="the-selected-connection-uses-an-unsupported-database-provider"></a>Die ausgewählte Verbindung nutzt einen nicht unterstützten Anbieter.
Diese Meldung wird angezeigt, wenn Sie Elemente ziehen, die nicht die .NET Framework-Datenanbieter für SQL Server aus verwenden **Server-Explorer**/**Datenbank-Explorer** auf die [LINQ to SQL Tools in Visual Studio](../data-tools/linq-to-sql-tools-in-visual-studio2.md).  
  
 Der [!INCLUDE[vs_ordesigner_short](../data-tools/includes/vs_ordesigner_short_md.md)] unterstützt nur Datenverbindungen, die den .NET Framework-Anbieter für SQL Server verwenden. Nur Verbindungen zu Microsoft SQL Server oder zur Microsoft SQL Server-Datenbankdatei sind gültig.  
  
### <a name="to-correct-this-error"></a>So beheben Sie diesen Fehler  
  
-   Fügen Sie nur Elemente von Datenverbindungen hinzu, die den .NET Framework-Datenanbieter für SQL Server zu [!INCLUDE[vs_ordesigner_short](../data-tools/includes/vs_ordesigner_short_md.md)] verwenden.  
  
## <a name="see-also"></a>Siehe auch
<xref:System.Data.SqlClient>  
[O/R-Designer-Meldungen](../data-tools/o-r-designer-messages.md)  
[LINQ to SQL-tools in Visual Studio](../data-tools/linq-to-sql-tools-in-visual-studio2.md)
