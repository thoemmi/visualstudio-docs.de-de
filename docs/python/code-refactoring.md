---
title: "Umgestalten von Code in Python Tools für Visual Studio | Microsoft-Dokumentation"
ms.custom: 
ms.date: 3/7/2017
ms.prod: visual-studio-dev15
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-python
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 76ebcb29-72d1-4958-9a63-8984c03d5c22
caps.latest.revision: 1
author: kraigb
ms.author: kraigb
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
translationtype: Human Translation
ms.sourcegitcommit: b0d84db6a16861fb9554af2a644423f906784748
ms.openlocfilehash: dc51f41277c91288c0812cb5c22f48d827d741aa
ms.lasthandoff: 03/07/2017

---

# <a name="refactoring-python-code"></a>Umgestalten von Python-Code

Python Tools für Visual Studio (PTVS) bietet verschiedene Befehle zum automatischen Transformieren und Bereinigen Ihres Quellcodes:

- [Umbenennen](#rename): Benennt eine ausgewählte Klasse, Methode oder Variable um.
- [Methode extrahieren](#extract-method): Erstellt eine neue Methode aus dem ausgewählten Code.
- [Import hinzufügen](#add-import): Stellt ein Smarttag zum Hinzufügen eines fehlenden Imports bereit.
- [Nicht verwendete Importe entfernen](#remove-imports): Entfernt nicht verwendete Importe.

<a name="rename-variable"</a>
## <a name="rename"></a>Umbenennen

1. Klicken Sie mit der rechten Maustaste auf den Bezeichner, den Sie umbenennen möchten, und wählen Sie **Umbenennen** aus. Alternativ dazu platzieren Sie den Textcursor in diesem Bezeichner und wählen den Menübefehl **Bearbeiten > Umgestalten > Umbenennen...** aus oder drücken die Taste F2.
1. Geben Sie in dem **Umbenennen**-Dialogfeld, das geöffnet wird, den neuen Namen für den Bezeichner ein, und wählen Sie **OK**:

  ![Eingabe des neuen Bezeichnernamens](media/code-refactor-rename-1.png)

1. Wählen Sie im nächsten Dialogfeld die Dateien und Instanzen in Ihrem Code aus, auf die die Umbenennung angewendet werden soll. Wählen Sie eine beliebige einzelne Instanz aus, um eine Vorschau der Änderung anzuzeigen:

  ![Dialogfeld zum Auswählen der zu ändernden Elemente](media/code-refactor-rename-2.png)

1. Wählen Sie **Anwenden** aus, um die Änderungen für Ihre Quellcodedateien zu übernehmen. Diese Aktion kann nicht rückgängig gemacht werden.

## <a name="extract-method"></a>Methode extrahieren

1. Wählen Sie die Codezeilen oder den Ausdruck aus, die bzw. in eine separate Methode extrahiert werden soll(en).
1. Wählen Sie den Menübefehl **Bearbeiten > Umgestalten > Methode extrahieren...** aus, oder drücken Sie die Tasten STRG-R, M.
1. Geben Sie im angezeigten Dialogfeld einen neuen Methodennamen ein, geben Sie an, wo die Methode extrahiert werden soll, und wählen Sie Abschlussvariablen. Nicht zum Abschließen ausgewählte Variablen werden in Methodenargumente umgewandelt:

  ![Dialogfeld „Methode extrahieren“](media/code-refactor-extract-method-1.png)

1. Wählen Sie **OK** aus, und der Code wird entsprechend geändert:

  ![Auswirkungen des Befehls „Methode extrahieren“](media/code-refactor-extract-method-2.png)

## <a name="add-import"></a>Import hinzufügen

Wenn Sie den Textcursor in einem Bezeichner platzieren, der keine Informationen enthält, stellt PTVS ein Smarttag bereit (das Glühbirnensymbol links neben dem Code), dessen Befehle die erforderliche `import`- oder `from ... import`-Anweisung hinzufügen:

![Smarttag „Import hinzufügen“](media/code-refactor-add-import-1.png)

`import`-Abschlüsse werden für Pakete und Module auf oberster Ebene im aktuellen Projekt und in der Standardbibliothek angeboten. `from ... import`-Abschlüsse werden für untergeordnete Module und Pakete sowie für Modulmember angeboten. Hierzu gehören Funktionen, Klassen oder exportierte Daten. Durch Auswahl einer Option wird die Anweisung am Anfang der Datei hinter anderen Importvorgängen hinzugefügt. Wenn das gleiche Modul bereits importiert wurde, wird die Anweisung in eine vorhandene `from ... import`-Anweisung eingefügt.

![Hinzufügen eines Imports – Ergebnis](media/code-refactor-add-import-2.png)

PTVS versucht, Member herauszufiltern, die nicht tatsächlich in einem Modul definiert sind, wie z.B. Module, die in ein anderes Modul importiert werden, aber keine untergeordneten Elemente des Moduls sind, das den Importvorgang ausführt. Viele Module verwenden z.B. `import sys` statt `from xyz import sys`, daher bietet PTVS keinen Abschluss beim Importieren von `sys` aus anderen Modulen, auch wenn in den Modulen ein `__all__`-Member fehlt, der `sys` ausschließt.

Auf ähnliche Weise filtert PTVS Funktionen, die aus anderen Modulen oder aus dem integrierten Namespace importiert werden. Wenn ein Modul z.B. die `settrace`-Funktion aus dem `sys`-Modul importiert, könnten Sie die Funktion theoretisch aus diesem Modul importieren. Es empfiehlt sich jedoch, `import settrace from sys` direkt zu verwenden, daher bietet PTVS diese Anweisung separat an.

Wenn ein Element aufgrund der oben genannten Regeln ausgeschlossen würde, aber andere Werte enthält, die eingeschlossen würden (weil dem Namen z.B. im Modul ein Wert zugewiesen wurde), schließt PTVS den Import trotzdem aus. Dabei wird davon ausgegangen, dass der Wert nicht exportiert werden sollte, weil er in einem anderen Modul definiert wurde und daher die zusätzliche Zuweisung wahrscheinlich einen Pseudowert erzeugt, der ebenfalls nicht exportiert wird.

<a name="remove-imports"</a>
## <a name="remove-unused-imports"></a>Nicht verwendete Importe entfernen

Beim Schreiben von Code entstehen leicht `import`-Anweisungen für Module, die gar nicht verwendet werden. PTVS analysiert Ihren Code und kann daher automatisch ermitteln, ob eine `import`-Anweisung benötigt wird. Dafür prüft PTVS, ob der importierte Name in dem Geltungsbereich verwendet wird, in dem die Anweisung auftritt.

Klicken Sie mit der rechten Maustaste auf eine beliebige Stelle im Editor, und wählen Sie **Importe entfernen** aus. Sie können aus den Optionen **Alle Geltungsbereiche** oder **Aktueller Geltungsbereich** auswählen:

![Menü zum Entfernen von Importen](media/code-refactor-remove-imports-1.png)

PTVS nimmt dann die entsprechenden Änderungen am Code vor:

![Entfernen von Importen – Auswirkungen](media/code-refactor-remove-imports-2.png)

Beachten Sie, dass PTVS keine Ablaufsteuerung berücksichtigt – die Verwendung eines Namens vor einer `import`-Anweisung wird genauso verarbeitet, als würde der Name tatsächlich verwendet. PTVS ignoriert auch alle `from __future__`-Importe, Importe, die innerhalb einer Klassendefinition ausgeführt werden, sowie Importe aus `from ... import *`-Anweisungen.