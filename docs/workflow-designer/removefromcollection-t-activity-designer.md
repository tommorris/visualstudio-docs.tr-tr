---
title: İş Akışı Tasarımcısı - RemoveFromCollection&lt;T&gt; etkinlik Tasarımcısı
ms.date: 11/04/2016
ms.topic: reference
ms.prod: visual-studio-dev15
ms.technology: vs-workflow-designer
f1_keywords:
- System.Activities.Statements.RemoveFromCollection`1.UI
ms.assetid: 6617ba26-c8bc-4aed-b746-112bf490d288
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 53fc58e231e5ef1cbbc6106e279b4925d145dd9f
ms.sourcegitcommit: 30f653d9625ba763f6b58f02fb74a24204d064ea
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/25/2018
ms.locfileid: "36755943"
---
# <a name="removefromcollectiont-activity-designer"></a>RemoveFromCollection\<T > etkinlik Tasarımcısı

**RemoveFromCollection\<T >** etkinlik Tasarımcısı oluşturmak ve yapılandırmak için kullanılan bir <xref:System.Activities.Statements.RemoveFromCollection%601> etkinlik.

## <a name="the-removefromcollectiontactivity"></a>RemoveFromCollection\<T > etkinliği

<xref:System.Activities.Statements.RemoveFromCollection%601> Etkinlik belirli bir koleksiyondaki belirli bir öğeyi kaldırır.

### <a name="using-the-removefromcollectiont-activity-designer"></a>RemoveFromCollection kullanarak\<T > etkinlik Tasarımcısı

Erişim **RemoveFromCollection\<T >** etkinlik Tasarımcısı'nda **koleksiyonu** kategorisini **araç**. **RemoveFromCollection\<T >** gelen etkinlik Tasarımcısı sürüklenebilir **araç** ve etkinlikleri genellikle, gibi yerleştirilir her yerde iş akışı Tasarımcısı yüzeyini açın içinde bir <xref:System.Activities.Statements.Sequence>. Bu oluşturur bir <xref:System.Activities.Statements.RemoveFromCollection%601> varsayılan etkinlik <xref:System.Activities.Activity.DisplayName%2A> RemoveFromCollection, < Int32\>. <xref:System.Activities.Activity.DisplayName%2A> Değeri üstbilgisinde düzenlenebilir **RemoveFromCollection < T\>**  etkinlik Tasarımcısı veya **DisplayName** ve özellik ızgarasının kutusu. Diğer özellikler ve özellik ızgarasının düzenlenmesi gerekir.

### <a name="the-removefromcollectiont-properties"></a>RemoveFromCollection < T\> özellikleri

Aşağıdaki tabloda <xref:System.Activities.Statements.RemoveFromCollection%601> özellikleri ve bunların Tasarımcısı'nda nasıl kullanıldığı açıklanmaktadır.

|Özellik adı|Gerekli|Kullanım|
|-------------------|--------------|-----------|
|<xref:System.Activities.Activity.DisplayName%2A>|False|İsteğe bağlı kolay adını <xref:System.Activities.Statements.RemoveFromCollection%601> etkinlik. RemoveFromCollection varsayılandır < Int32\>.<br /><br /> Ancak <xref:System.Activities.Activity.DisplayName%2A> kesinlikle gerekli değil kullanmak için en iyi bir uygulamadır.|
|<xref:System.Activities.Statements.RemoveFromCollection%601.Item%2A>|Doğru|Öğe eklemek için **koleksiyonu\<T >**. Bu öğe türünde *T*, türündeki *TypeArgument*. Öğeyi seçmek için bir Visual Basic ifade özellik kılavuzunda yazın.|
|<xref:System.Activities.Statements.RemoveFromCollection%601.Collection%2A>|Doğru|Öğesinin eklenmesi koleksiyon. Bu koleksiyonu türünde **ICollection < TypeArgument\>.** Koleksiyon belirtmek için Visual Basic ifade özellik kılavuzunda yazın.|
|*TypeArgument*|Doğru|İçindeki öğe türü T <xref:System.Collections.Generic.ICollection%601>. Varsayılan olarak, bu *TypeArgument* türü ayarlanmış **Int32**. Türünü değiştirmek için değerini değiştirme *TypeArgument* özellik kılavuzunda açılan kutusunda.|
|<xref:System.Activities.Activity%601.Result%2A>|False|Belirtilen öğeyi koleksiyondan kaldırıldı olup olmadığını belirten bir değer. Bir değişkende özellik kılavuzunda sonucu bağlamak için bir değişken belirtmek için şunu yazın|

## <a name="see-also"></a>Ayrıca bkz.

- [Koleksiyon](../workflow-designer/collection-activity-designers.md)
- [AddToCollection\<T>](../workflow-designer/addtocollection-t-activity-designer.md)
- [ClearCollection\<T >](../workflow-designer/clearcollection-t-activity-designer.md)
- [ExistsInCollection\<T >](../workflow-designer/existsincollection-t-activity-designer.md)