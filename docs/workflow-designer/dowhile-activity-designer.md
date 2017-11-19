---
title: "DoWhile etkinlik Tasarımcısı | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords: System.Activities.Statements.DoWhile.UI
ms.assetid: 948deb35-d72f-462b-bea6-4b119c10a148
caps.latest.revision: "7"
author: ErikRe
ms.author: erikre
manager: erikre
ms.openlocfilehash: 43a55a8873fa10fb31db89364c50e084cd72fb5c
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2017
---
# <a name="dowhile-activity-designer"></a>DoWhile etkinlik Tasarımcısı
<xref:System.Activities.Statements.DoWhile> Etkinlik yürütür içinde yer alan etkinlik kendi <xref:System.Activities.Statements.DoWhile.Body%2A> en az bir kez için belirtilen bir koşulu değerlendirir kadar **false**. Sıfır veya daha fazla kez kullanım yürütülecek döngü gövdesinde yer alan etkinlik gerekiyorsa <xref:System.Activities.Statements.While> etkinlik yerine.  
  
## <a name="dowhile-properties-in-the-workflow-designer"></a>İş Akışı Tasarımcısı'nda DoWhile özellikleri  
 Aşağıdaki tabloda en kullanışlı gösterilmektedir <xref:System.Activities.Statements.DoWhile> etkinlik özellikleri ve bunların Tasarımcısı'nda nasıl kullanılacağını açıklar.  
  
|Özellik adı|Gerekli|Kullanım|  
|-------------------|--------------|-----------|  
|<xref:System.Activities.Statements.DoWhile.Body%2A>|False|Koşul ederken yürütmek için etkinlik **doğru**. Eklemek için <xref:System.Activities.Statements.DoWhile.Body%2A> etkinlik, bir etkinlik araç bırakma **gövde** kutusuna **DoWhile** etkinlik Tasarımcısı "Buraya etkinliğini Drop" İpucu metni.|  
|<xref:System.Activities.Statements.DoWhile.Condition%2A>|Doğru|Döngünün her yinelemesinden sonra değerlendirmek için koşulu. Ayarlamak için <xref:System.Activities.Statements.DoWhile.Condition%2A>, bir [!INCLUDE[vbprvb](../code-quality/includes/vbprvb_md.md)] ifadesinde **koşulu** kutusuna **DoWhile** etkinlik Tasarımcısı veya özellik kılavuzunda.|  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [While](../workflow-designer/while-activity-designer.md)   
 [Denetim akışı](../workflow-designer/control-flow-activity-designers.md)