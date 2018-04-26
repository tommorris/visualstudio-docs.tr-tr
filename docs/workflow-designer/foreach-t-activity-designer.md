---
title: İş Akışı Tasarımcısı - ForEach&lt;T&gt; etkinlik Tasarımcısı
ms.date: 11/04/2016
ms.topic: reference
ms.prod: visual-studio-dev15
ms.technology: vs-workflow-designer
f1_keywords:
- System.Activities.Statements.ForEach`1.UI
ms.assetid: 67097b3a-fcf5-4a72-beb1-2c7784151a86
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: d506be0fbee9ad94e4ed8b97665665bc045ed130
ms.sourcegitcommit: e13e61ddea6032a8282abe16131d9e136a927984
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/26/2018
---
# <a name="foreachlttgt-activity-designer"></a>ForEach&lt;T&gt; etkinlik Tasarımcısı

<xref:System.Activities.Statements.ForEach%601> Etkinlik yürütür içinde yer alan etkinlik kendi <xref:System.Activities.Statements.ForEach%601.Body%2A> belirtilen her öğe için <xref:System.Activities.Statements.ForEach%601.Values%2A> koleksiyonu.

## <a name="foreacht-properties-in-the-workflow-designer"></a>ForEach < T\> iş akışı Tasarımcısı'nda özellikleri

Aşağıdaki tabloda en kullanışlı gösterilmektedir <xref:System.Activities.Statements.ForEach%601> etkinlik özellikleri ve bunların Tasarımcısı'nda nasıl kullanılacağını açıklar.

|Özellik adı|Gerekli|Kullanım|
|-------------------|--------------|-----------|
|<xref:System.Activities.Activity.DisplayName%2A>|False|Kolay adı <xref:System.Activities.Statements.ForEach%601> etkinlik. ForEach varsayılandır < Int32\>. Ancak <xref:System.Activities.Activity.DisplayName%2A> değeri kesinlikle gerekli değildir, kullanmak için en iyi bir uygulamadır.|
|<xref:System.Activities.Statements.ForEach%601.Values%2A>|Doğru|Üzerinden yineleme öğeleri koleksiyonu. Ayarlamak için <xref:System.Activities.Statements.ForEach%601.Values%2A>, bir Visual Basic ifadesi yazın **değerleri** kutusuna **ForEach < T\>**  etkinlik Tasarımcısı veya özellik kılavuzunda.|
|*TypeArgument*|Doğru|Öğe türü <xref:System.Activities.Statements.ForEach%601.Values%2A> genel parametresi tarafından belirtilen koleksiyon *T*. Varsayılan olarak, *TypeArgument* ayarlanır **Int32**. Türünü değiştirmek için değerini değiştirme *TypeArgument* özellik kılavuzunda birleşik giriş kutusu.|

Varsayılan olarak, döngü yineleyici adlı **öğesi**. Yineleyici değişken adını değiştirebilirsiniz <xref:System.Activities.Statements.ForEach%601> etkinlik Tasarımcısı. Döngü yineleyici alt ifadelerde kullanılabilir <xref:System.Activities.Statements.ForEach%601> etkinlik.

## <a name="see-also"></a>Ayrıca bkz.

- [ParallelForEach\<T >](../workflow-designer/parallelforeach-t-activity-designer.md)
- [Denetim Akışı](../workflow-designer/control-flow-activity-designers.md)