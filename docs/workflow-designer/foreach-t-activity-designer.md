---
title: "ForEach&lt;T&gt; etkinlik Tasarımcısı | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords: System.Activities.Statements.ForEach`1.UI
ms.assetid: 67097b3a-fcf5-4a72-beb1-2c7784151a86
caps.latest.revision: "5"
author: ErikRe
ms.author: erikre
manager: erikre
ms.workload: multiple
ms.openlocfilehash: 6016947237274d65d3b59954d783c2a31f3d2b91
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/22/2017
---
# <a name="foreachlttgt-activity-designer"></a>ForEach&lt;T&gt; etkinlik Tasarımcısı
<xref:System.Activities.Statements.ForEach%601> Etkinlik yürütür içinde yer alan etkinlik kendi <xref:System.Activities.Statements.ForEach%601.Body%2A> belirtilen her öğe için <xref:System.Activities.Statements.ForEach%601.Values%2A> koleksiyonu.  
  
## <a name="foreacht-properties-in-the-workflow-designer"></a>ForEach < T\> iş akışı Tasarımcısı'nda özellikleri  
 Aşağıdaki tabloda en kullanışlı gösterilmektedir <xref:System.Activities.Statements.ForEach%601> etkinlik özellikleri ve bunların Tasarımcısı'nda nasıl kullanılacağını açıklar.  
  
|Özellik adı|Gerekli|Kullanım|  
|-------------------|--------------|-----------|  
|<xref:System.Activities.Activity.DisplayName%2A>|False|Kolay adı <xref:System.Activities.Statements.ForEach%601> etkinlik. ForEach varsayılandır < Int32\>. Ancak <xref:System.Activities.Activity.DisplayName%2A> değeri kesinlikle gerekli değildir, kullanmak için en iyi bir uygulamadır.|  
|<xref:System.Activities.Statements.ForEach%601.Values%2A>|Doğru|Üzerinden yineleme öğeleri koleksiyonu. Ayarlamak için <xref:System.Activities.Statements.ForEach%601.Values%2A>, bir [!INCLUDE[vbprvb](../code-quality/includes/vbprvb_md.md)] ifadesinde **değerleri** kutusuna **ForEach < T\>**  etkinlik Tasarımcısı veya özellik kılavuzunda.|  
|*TypeArgument*|Doğru|Öğe türü <xref:System.Activities.Statements.ForEach%601.Values%2A> genel parametresi tarafından belirtilen koleksiyon *T*. Varsayılan olarak, *TypeArgument* ayarlanır **Int32**. Türünü değiştirmek için değerini değiştirme *TypeArgument* özellik kılavuzunda birleşik giriş kutusu.|  
  
 Varsayılan olarak, döngü yineleyici adlı **öğesi**. Yineleyici değişken adını değiştirebilirsiniz <xref:System.Activities.Statements.ForEach%601> etkinlik Tasarımcısı. Döngü yineleyici alt ifadelerde kullanılabilir <xref:System.Activities.Statements.ForEach%601> etkinlik.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [ParallelForEach\<T >](../workflow-designer/parallelforeach-t-activity-designer.md)   
 [Denetim Akışı](../workflow-designer/control-flow-activity-designers.md)