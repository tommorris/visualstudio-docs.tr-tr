---
title: DoWhile etkinlik Tasarımcısı | Microsoft Docs
ms.custom: ''
ms.date: 2018-06-30
ms.prod: .net-framework-4.6
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
f1_keywords:
- System.Activities.Statements.DoWhile.UI
ms.assetid: 948deb35-d72f-462b-bea6-4b119c10a148
caps.latest.revision: 7
author: gewarren
ms.author: gewarren
manager: erikre
ms.openlocfilehash: 911e6d6d94090ddcdd43fcd9511624e209f7c03c
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/22/2018
ms.locfileid: "42693751"
---
# <a name="dowhile-activity-designer"></a>DoWhile Etkinlik Tasarımcısı
<xref:System.Activities.Statements.DoWhile> Etkinliği yürütür bulunan etkinlik kendi <xref:System.Activities.Statements.DoWhile.Body%2A> en az bir kez, belirtilen bir koşulu olana kadar **false**. Sıfır veya daha fazla kez kullanım yürütülecek bir döngü gövdesinde yer alan etkinlik gerekiyorsa <xref:System.Activities.Statements.While> etkinliği bunun yerine.  
  
## <a name="dowhile-properties-in-the-workflow-designer"></a>İş akışı tasarımcısında DoWhile özellikleri  
 Aşağıdaki tabloda en kullanışlı gösterilmektedir <xref:System.Activities.Statements.DoWhile> etkinlik özellikleri ve tasarımcıda kullanmayı açıklar.  
  
|Özellik adı|Gerekli|Kullanım|  
|-------------------|--------------|-----------|  
|<xref:System.Activities.Statements.DoWhile.Body%2A>|False|Koşulu sırada yürütmek için etkinlik **true**. Eklemek için <xref:System.Activities.Statements.DoWhile.Body%2A> etkinlik, etkinlik araç kutusundan bir bırakma **gövdesi** kutusuna **DoWhile** etkinlik Tasarımcısı ile "Etkinliği buraya bırakın" İpucu metni.|  
|<xref:System.Activities.Statements.DoWhile.Condition%2A>|Doğru|Döngünün her yinelemesinden sonra değerlendirilecek koşul. Ayarlanacak <xref:System.Activities.Statements.DoWhile.Condition%2A>, tür a [!INCLUDE[vbprvb](../includes/vbprvb-md.md)] ifadesinde **koşul** kutusuna **DoWhile** etkinlik Tasarımcısı veya özellik kılavuzunda.|  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [while](../workflow-designer/while-activity-designer.md)   
 [Denetim Akışı](../workflow-designer/control-flow-activity-designers.md)