---
title: ForEach&lt;T&gt; etkinlik Tasarımcısı | Microsoft Docs
ms.custom: ''
ms.date: 2018-06-30
ms.prod: .net-framework-4.6
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
f1_keywords:
- System.Activities.Statements.ForEach`1.UI
ms.assetid: 67097b3a-fcf5-4a72-beb1-2c7784151a86
caps.latest.revision: 5
author: gewarren
ms.author: gewarren
manager: erikre
ms.openlocfilehash: b118eb62f3055486e26f9d90a4e3abb74fe38660
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/22/2018
ms.locfileid: "42683738"
---
# <a name="foreachlttgt-activity-designer"></a>ForEach&lt;T&gt; etkinlik Tasarımcısı
<xref:System.Activities.Statements.ForEach%601> Etkinliği yürütür bulunan etkinlik kendi <xref:System.Activities.Statements.ForEach%601.Body%2A> belirtilen her öğe için <xref:System.Activities.Statements.ForEach%601.Values%2A> koleksiyonu.  
  
## <a name="foreacht-properties-in-the-workflow-designer"></a>ForEach\<T > İş Akışı Tasarımcısı özellikleri  
 Aşağıdaki tabloda en kullanışlı gösterilmektedir <xref:System.Activities.Statements.ForEach%601> etkinlik özellikleri ve tasarımcıda kullanmayı açıklar.  
  
|Özellik adı|Gerekli|Kullanım|  
|-------------------|--------------|-----------|  
|<xref:System.Activities.Activity.DisplayName%2A>|False|Kolay adı <xref:System.Activities.Statements.ForEach%601> etkinlik. ForEach varsayılandır\<Int32 >. Ancak <xref:System.Activities.Activity.DisplayName%2A> değeri kesinlikle gerekli değil, kullanmak için en iyi bir uygulamadır.|  
|<xref:System.Activities.Statements.ForEach%601.Values%2A>|Doğru|Üzerinden yinelemek için öğeleri koleksiyonu. Ayarlanacak <xref:System.Activities.Statements.ForEach%601.Values%2A>, tür a [!INCLUDE[vbprvb](../includes/vbprvb-md.md)] ifadesinde **değerleri** kutusuna **ForEach\<T >** etkinlik Tasarımcısı veya özellik kılavuzunda.|  
|*TypeArgument*|Doğru|Öğelerin türünü <xref:System.Activities.Statements.ForEach%601.Values%2A> genel parametre tarafından belirtilen koleksiyon *T*. Varsayılan olarak, *TypeArgument* ayarlanır **Int32**. Türü değiştirmek için değerini değiştirmek *TypeArgument* özellik kılavuzunda birleşik giriş kutusu.|  
  
 Varsayılan olarak, döngü yineleyici adlı **öğesi**. Yineleyici değişkeni adını değiştirebilirsiniz <xref:System.Activities.Statements.ForEach%601> etkinlik Tasarımcısı. Döngü yineleyici alt ifadelerde kullanılabilir <xref:System.Activities.Statements.ForEach%601> etkinlik.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [ParallelForEach\<T >](../workflow-designer/parallelforeach-t-activity-designer.md)   
 [Denetim Akışı](../workflow-designer/control-flow-activity-designers.md)