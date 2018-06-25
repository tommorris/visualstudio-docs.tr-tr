---
title: İş Akışı Tasarımcısı - AddToCollection<T> etkinlik Tasarımcısı
ms.date: 11/04/2016
ms.topic: reference
ms.prod: visual-studio-dev15
ms.technology: vs-workflow-designer
f1_keywords:
- System.Activities.Statements.AddToCollection`1.UI
ms.assetid: f7fc0702-164e-4370-8946-bb2f9f9384b7
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 0302ef4c974179619800ece37fa7650ea2b4ebd0
ms.sourcegitcommit: 30f653d9625ba763f6b58f02fb74a24204d064ea
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/25/2018
ms.locfileid: "36755830"
---
# <a name="addtocollectiont-activity-designer"></a>AddToCollection\<T > etkinlik Tasarımcısı

**AddToCollection\<T >** etkinlik Tasarımcısı oluşturmak ve yapılandırmak için kullanılan bir <xref:System.Activities.Statements.AddToCollection%601> etkinlik.

## <a name="the-addtocollectiont-activity"></a>AddToCollection\<T > etkinliği

<xref:System.Activities.Statements.AddToCollection%601> Etkinlik bir öğe bir koleksiyona ekler.

### <a name="using-the-addtocollectiont-activity-designer"></a>AddToCollection kullanarak\<T > etkinlik Tasarımcısı

**AddToCollection\<T >** etkinlik Tasarımcısı bulunabilir **koleksiyonu** kategorisini **araç**, hangi tıklayarakerişildiğinde **Araç kutusu** sekmesi iş akışı Tasarımcısı'nın. Alternatif olarak, seçin **araç** gelen **Görünüm** menüsü veya tuşuna **Ctrl**+**Alt** + **X**.

**AddToCollection\<T >** gelen etkinlik Tasarımcısı sürüklenebilir **araç** ve etkinlikleri yerleştirilir olduğunda, böyle bir gibiiçindeişakışıTasarımcısıyüzeyiniaçın<xref:System.Activities.Statements.Sequence>. Bırakma **AddToCollection\<T >** etkinlik Tasarımcısı oluşturur bir <xref:System.Activities.Statements.AddToCollection%601> varsayılan etkinlik <xref:System.Activities.Activity.DisplayName%2A> AddToCollection, < Int32\>. (Varsayılan olarak, *TypeArgument* olan **Int32**. TypeArgument özellik kılavuzunda değiştirilebilir.) <xref:System.Activities.Activity.DisplayName%2A> Değeri üstbilgisinde düzenlenebilir **AddToCollection < T\>**  etkinlik Tasarımcısı veya **DisplayName** ve özellik ızgarasının kutusu. Diğer özellikler ve özellik ızgarasının düzenlenmesi gerekir.

### <a name="the-addtocollectiont-properties"></a>AddToCollection\<T > Özellikler

Aşağıdaki tabloda <xref:System.Activities.Statements.AddToCollection%601> özellikleri ve bunların Tasarımcısı'nda nasıl kullanıldığı açıklanmaktadır.

|Özellik adı|Gerekli|Kullanım|
|-------------------|--------------|-----------|
|<xref:System.Activities.Activity.DisplayName%2A>|False|Kolay adı <xref:System.Activities.Statements.AddToCollection%601> etkinlik. AddToCollection varsayılandır < Int32\>. Ancak <xref:System.Activities.Activity.DisplayName%2A> değeri kesinlikle gerekli değildir, kullanmak için en iyi bir uygulamadır.|
|<xref:System.Activities.Statements.AddToCollection%601.Item%2A>|Doğru|Koleksiyona eklenecek öğe\<T >. Bu öğe türünde *T*, türündeki *TypeArgument*. Öğeyi seçmek için bir Visual Basic ifade özellik kılavuzunda yazın.|
|<xref:System.Activities.Statements.AddToCollection%601.Collection%2A>|Doğru|Öğesinin eklenmesi koleksiyon. Bu koleksiyonu türünde **ICollection < TypeArgument\>**. Koleksiyon belirtmek için özellik kılavuzunda bir Visual Basic ifadesi yazın.|
|*TypeArgument*|Doğru|İçindeki öğe türü T <xref:System.Collections.Generic.ICollection%601>. Varsayılan olarak, bu *TypeArgument* türü ayarlanmış **Int32**. Türünü değiştirmek için değerini değiştirme *TypeArgument* özellik kılavuzunda açılan kutusunda.|

## <a name="see-also"></a>Ayrıca bkz.

- [Koleksiyon](../workflow-designer/collection-activity-designers.md)
- [AddToCollection\<T > etkinlik Tasarımcısı](../workflow-designer/addtocollection-t-activity-designer.md)
- [ClearCollection\<T >](../workflow-designer/clearcollection-t-activity-designer.md)
- [ExistsInCollection\<T >](../workflow-designer/existsincollection-t-activity-designer.md)
- [RemoveFromCollection\<T >](../workflow-designer/removefromcollection-t-activity-designer.md)