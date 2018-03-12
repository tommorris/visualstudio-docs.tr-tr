---
title: "DoWhile etkinlik Tasarımcısı | Microsoft Docs"
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- System.Activities.Statements.DoWhile.UI
ms.assetid: 948deb35-d72f-462b-bea6-4b119c10a148
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload:
- multiple
ms.openlocfilehash: 76350c1a24b48e283c245180166806afe86aecd7
ms.sourcegitcommit: 37c87118f6f41e832da96f21f6b4cc0cf8fee046
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/12/2018
---
# <a name="dowhile-activity-designer"></a>DoWhile etkinlik Tasarımcısı
<xref:System.Activities.Statements.DoWhile> Etkinlik yürütür içinde yer alan etkinlik kendi <xref:System.Activities.Statements.DoWhile.Body%2A> en az bir kez için belirtilen bir koşulu değerlendirir kadar **false**. Sıfır veya daha fazla kez kullanım yürütülecek döngü gövdesinde yer alan etkinlik gerekiyorsa <xref:System.Activities.Statements.While> etkinlik yerine.

## <a name="dowhile-properties-in-the-workflow-designer"></a>İş Akışı Tasarımcısı'nda DoWhile özellikleri
 Aşağıdaki tabloda en kullanışlı gösterilmektedir <xref:System.Activities.Statements.DoWhile> etkinlik özellikleri ve bunların Tasarımcısı'nda nasıl kullanılacağını açıklar.

|Özellik adı|Gerekli|Kullanım|
|-------------------|--------------|-----------|
|<xref:System.Activities.Statements.DoWhile.Body%2A>|False|Koşul ederken yürütmek için etkinlik **doğru**. Eklemek için <xref:System.Activities.Statements.DoWhile.Body%2A> etkinlik, bir etkinlik araç bırakma **gövde** kutusuna **DoWhile** etkinlik Tasarımcısı "Buraya etkinliğini Drop" İpucu metni.|
|<xref:System.Activities.Statements.DoWhile.Condition%2A>|Doğru|Döngünün her yinelemesinden sonra değerlendirmek için koşulu. Ayarlamak için <xref:System.Activities.Statements.DoWhile.Condition%2A>, bir [!INCLUDE[vbprvb](../code-quality/includes/vbprvb_md.md)] ifadesinde **koşulu** kutusuna **DoWhile** etkinlik Tasarımcısı veya özellik kılavuzunda.|

## <a name="see-also"></a>Ayrıca bkz.

- [While](../workflow-designer/while-activity-designer.md)
- [Denetim Akışı](../workflow-designer/control-flow-activity-designers.md)