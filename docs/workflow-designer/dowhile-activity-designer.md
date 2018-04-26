---
title: İş Akışı Tasarımcısı - DoWhile etkinlik Tasarımcısı
ms.date: 11/04/2016
ms.topic: reference
ms.prod: visual-studio-dev15
ms.technology: vs-workflow-designer
f1_keywords:
- System.Activities.Statements.DoWhile.UI
ms.assetid: 948deb35-d72f-462b-bea6-4b119c10a148
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 23588a044596ce5250cc68d01263f5d80775866a
ms.sourcegitcommit: e13e61ddea6032a8282abe16131d9e136a927984
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/26/2018
---
# <a name="dowhile-activity-designer"></a>DoWhile etkinlik Tasarımcısı

<xref:System.Activities.Statements.DoWhile> Etkinlik yürütür içinde yer alan etkinlik kendi <xref:System.Activities.Statements.DoWhile.Body%2A> en az bir kez için belirtilen bir koşulu değerlendirir kadar **false**. Sıfır veya daha fazla kez kullanım yürütülecek döngü gövdesinde yer alan etkinlik gerekiyorsa <xref:System.Activities.Statements.While> etkinlik yerine.

## <a name="dowhile-properties-in-the-workflow-designer"></a>İş Akışı Tasarımcısı'nda DoWhile özellikleri

Aşağıdaki tabloda en kullanışlı gösterilmektedir <xref:System.Activities.Statements.DoWhile> etkinlik özellikleri ve Tasarımcısı'nda kullanmayı açıklar:

|Özellik adı|Gerekli|Kullanım|
|-------------------|--------------|-----------|
|<xref:System.Activities.Statements.DoWhile.Body%2A>|False|Koşul ederken yürütmek için etkinlik **doğru**. Eklemek için <xref:System.Activities.Statements.DoWhile.Body%2A> etkinlik, bir etkinlik araç bırakma **gövde** kutusuna **DoWhile** etkinlik Tasarımcısı "Buraya etkinliğini Drop" İpucu metni.|
|<xref:System.Activities.Statements.DoWhile.Condition%2A>|Doğru|Döngünün her yinelemesinden sonra değerlendirmek için koşulu. Ayarlamak için <xref:System.Activities.Statements.DoWhile.Condition%2A>, bir Visual Basic ifadesi yazın **koşulu** kutusuna **DoWhile** etkinlik Tasarımcısı veya özellik kılavuzunda.|

## <a name="see-also"></a>Ayrıca bkz.

- [While](../workflow-designer/while-activity-designer.md)
- [Denetim Akışı](../workflow-designer/control-flow-activity-designers.md)