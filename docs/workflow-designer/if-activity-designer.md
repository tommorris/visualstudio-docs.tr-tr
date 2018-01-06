---
title: "Varsa etkinlik Tasarımcısı | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords: System.Activities.Statements.If.UI
ms.assetid: 930a8fa2-db98-43e9-ad6d-a85cc7a6519a
caps.latest.revision: "4"
author: ErikRe
ms.author: erikre
manager: erikre
ms.workload: multiple
ms.openlocfilehash: 950bff10372c9c40e047f891049e7cc387c8efc8
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/22/2017
---
# <a name="if-activity-designer"></a>Varsa etkinlik Tasarımcısı
<xref:System.Activities.Statements.If> Etkinlik bir koşulu değerlendirir ve bu değerlendirme sonuçlarını bağlı olarak bir etkinlik yürütür. Bu etkinlik programlama stilini modelleme bir yordam kullanırken kullanışlıdır. Bir <xref:System.Activities.Statements.If> etkinlik iç içe geçirilemez içinde bir <xref:System.Activities.Statements.Sequence> etkinlik veya <xref:System.Activities.Statements.Parallel> örneğin etkinlik. Kullanıyorsanız bir <xref:System.Activities.Statements.Flowchart> etkinliği kullanmayı bir <xref:System.Activities.Statements.FlowDecision> etkinlik yerine.  
  
## <a name="if-properties-in-the-workflow-designer"></a>İş Akışı Tasarımcısı'nda özellikleri  
 Aşağıdaki tabloda en kullanışlı gösterilmektedir <xref:System.Activities.Statements.If> etkinlik özellikleri ve bunların Tasarımcısı'nda nasıl kullanılacağını açıklar.  
  
|Özellik adı|Gerekli|Kullanım|  
|-------------------|--------------|-----------|  
|<xref:System.Activities.Statements.If.Condition%2A>|Doğru|Yürütmek için hangi alt etkinlik belirler koşulu. Ayarlamak için <xref:System.Activities.Statements.If.Condition%2A>, bir [!INCLUDE[vbprvb](../code-quality/includes/vbprvb_md.md)] ifadesinde **koşulu** kutusuna **varsa** etkinlik Tasarımcısı veya özellik kılavuzunda.|  
|<xref:System.Activities.Statements.If.Else%2A>|False|Etkinlik, yürütmeyi <xref:System.Activities.Statements.If.Condition%2A> olan **false**. Tarafından çalıştırılan bir etkinlik eklemek için <xref:System.Activities.Statements.If.Else%2A> dal, bir etkinlikten bırakma **araç** içine **Else** kutusuna **varsa** ipucu metnini ile etkinlik Tasarımcısı " Etkinlik Buraya Bırak".|  
|<xref:System.Activities.Statements.If.Then%2A>|False|Etkinlik, yürütmeyi <xref:System.Activities.Statements.If.Condition%2A> olan **doğru**. Tarafından çalıştırılan bir etkinlik eklemek için <xref:System.Activities.Statements.If.Then%2A> dal, bir etkinlikten bırakma **araç** içine **sonra** kutusuna **varsa** ipucu metnini ile etkinlik Tasarımcısı " Etkinlik Buraya Bırak".|  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Sırası](../workflow-designer/sequence-activity-designer.md)   
 [Paralel](../workflow-designer/parallel-activity-designer.md)   
 [Denetim Akışı](../workflow-designer/control-flow-activity-designers.md)