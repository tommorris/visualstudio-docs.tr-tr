---
title: İş Akışı Tasarımcısı - ClearCollection<T> etkinlik Tasarımcısı
ms.date: 11/04/2016
ms.topic: reference
ms.prod: visual-studio-dev15
ms.technology: vs-workflow-designer
f1_keywords:
- System.Activities.Statements.ClearCollection`1.UI
ms.assetid: db0e5da2-7b5a-4f1a-864c-f3aeeeeb51a7
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: d2422f7165e3f00e4059bc593c129c7723daed2f
ms.sourcegitcommit: 30f653d9625ba763f6b58f02fb74a24204d064ea
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/25/2018
ms.locfileid: "36757902"
---
# <a name="clearcollectiont-activity-designer"></a>ClearCollection\<T > etkinlik Tasarımcısı

**ClearCollection\<T >** etkinlik Tasarımcısı oluşturmak ve yapılandırmak için kullanılan bir <xref:System.Activities.Statements.ClearCollection%601> etkinlik.

## <a name="the-clearcollectiont-activity"></a>ClearCollection\<T > etkinliği

<xref:System.Activities.Statements.ClearCollection%601> Etkinlik belirtilen tüm öğeleri koleksiyonu siler.

### <a name="using-the-clearcollectiont-activity-designer"></a>ClearCollection kullanarak\<T > etkinlik Tasarımcısı

**ClearCollection\<T >** etkinlik Tasarımcısı bulunabilir **koleksiyonu** kategorisini **araç**, hangi tıklayarakerişildiğinde **Araç kutusu** sekmesi iş akışı Tasarımcısı'nın. Alternatif olarak, seçin **araç** gelen **Görünüm** menüsü veya tuşuna **Ctrl**+**Alt** + **X**.

**ClearCollection\<T >** gelen etkinlik Tasarımcısı sürüklenebilir **araç** ve etkinlikleri yerleştirilir olduğunda, böyle bir gibiiçindeişakışıTasarımcısıyüzeyiniaçın<xref:System.Activities.Statements.Sequence>. Etkinlik Tasarımcısı bırakarak oluşturur bir <xref:System.Activities.Statements.ClearCollection%601> varsayılan etkinlik <xref:System.Activities.Activity.DisplayName%2A> ClearCollection, < Int32\>. (Varsayılan olarak, *TypeArgument* olan **Int32**. TypeArgument özellik kılavuzunda değiştirilebilir.) <xref:System.Activities.Activity.DisplayName%2A> Değeri üstbilgisinde düzenlenebilir **ClearCollection < T\>**  etkinlik Tasarımcısı veya **DisplayName** ve özellik ızgarasının kutusu. Diğer özellikler ve özellik ızgarasının düzenlenmesi gerekir.

### <a name="the-clearcollectiont-properties"></a>ClearCollection\<T > Özellikler

Aşağıdaki tabloda <xref:System.Activities.Statements.ClearCollection%601> özellikleri ve bunların Tasarımcısı'nda nasıl kullanıldığı açıklanmaktadır.

|Özellik adı|Gerekli|Kullanım|
|-------------------|--------------|-----------|
|<xref:System.Activities.Activity.DisplayName%2A>|False|İsteğe bağlı kolay adı belirtir <xref:System.Activities.Statements.ClearCollection%601> etkinlik. ClearCollection varsayılandır < Int32\>. Ancak <xref:System.Activities.Activity.DisplayName%2A> değeri kesinlikle gerekli değildir, kullanmak için en iyi bir uygulamadır.|
|<xref:System.Activities.Statements.ClearCollection%601.Collection%2A>|Doğru|Öğelerin temizlenecek koleksiyonu belirtir. Bu koleksiyonu türünde **ICollection\<TypeArgument >.** Koleksiyon belirtmek için özellik kılavuzunda bir Visual Basic ifadesi yazın.|
|*TypeArgument*|Doğru|İçindeki öğelerin T türü belirtir <xref:System.Collections.Generic.ICollection%601>. Varsayılan olarak, bu *TypeArgument* türü ayarlanmış **Int32**. Türünü değiştirmek için değerini değiştirme *TypeArgument* özellik kılavuzunda açılan kutusunda.|

## <a name="see-also"></a>Ayrıca bkz.

- [Koleksiyon](../workflow-designer/collection-activity-designers.md)
- [AddToCollection\<T>](../workflow-designer/addtocollection-t-activity-designer.md)
- [ExistsInCollection\<T >](../workflow-designer/existsincollection-t-activity-designer.md)
- [RemoveFromCollection\<T >](../workflow-designer/removefromcollection-t-activity-designer.md)