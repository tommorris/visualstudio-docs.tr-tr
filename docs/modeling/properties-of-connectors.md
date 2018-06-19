---
title: Bağlayıcıların Özellikleri
ms.date: 11/04/2016
ms.topic: reference
helpviewer_keywords:
- Domain-Specific Language, connectors
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.prod: visual-studio-dev15
ms.technology: vs-ide-modeling
ms.openlocfilehash: e8954727d7ee38b81ba5993b41e300ef1c6d66fc
ms.sourcegitcommit: e13e61ddea6032a8282abe16131d9e136a927984
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/26/2018
ms.locfileid: "31952737"
---
# <a name="properties-of-connectors"></a>Bağlayıcıların Özellikleri
Bağlayıcılar oluşturulan Tasarımcısı'nda etki alanı ilişkileri temsil eder.

 Daha fazla bilgi için bkz: [bir etki alanına özgü dil tanımlamak nasıl](../modeling/how-to-define-a-domain-specific-language.md). Bu özellikleri kullanma hakkında daha fazla bilgi için bkz: [özelleştirme ve bir etki alanına özgü dil genişletme](../modeling/customizing-and-extending-a-domain-specific-language.md).

 Bağlayıcılar aşağıdaki tabloda listelenen özellikleri vardır.

|Özellik|Açıklama|Varsayılan|
|--------------|-----------------|-------------|
|Renk|Bu bağlayıcı rengi.|Siyah|
|Çizgi stili|Bu bağlayıcı (düz, çizgi, nokta, çizgi nokta, çizgi nokta nokta veya özel) satırı için çizgi stili.|Düz|
|Kaynak uç stili|Bu bağlayıcı (HollowArrow, EmptyArrow, FilledArrow, EmptyDiamond, FilledDiamond veya hiçbiri) kaynak bitiş stili.|Yok.|
|Hedef uç stili|Bu bağlayıcı (HollowArrow, EmptyArrow, FilledArrow, EmptyDiamond, FilledDiamond veya hiçbiri) hedef uç stili.|Yok.|
|Metin rengi|Bu bağlayıcı ile ilişkilendirilen metin dekoratörler için kullanılan rengi.|Siyah|
|Kalınlığı|Bu bağlayıcı çizgi kalınlığı inç cinsinden ölçülür.|0.03125|
|Erişim değiştiricisi|Sınıfının erişim düzeyini (`public` veya `internal`).|Ortak|
|Özel Öznitelikler|Bu bağlayıcı oluşturulan kaynak kodu sınıfı öznitelikler eklemek için kullanılır.|\<yok >|
|Çift oluşturur türetilmiş|Varsa `True`, bir taban sınıf ve bir parçalı sınıf (geçersiz kılmaları özelleştirmeyi desteklemek için) oluşturulur. Daha fazla bilgi için bkz: [geçersiz kılma ve oluşturulan sınıflar genişletme](../modeling/overriding-and-extending-the-generated-classes.md).|False|
|Özel bir oluşturucuya sahip|Varsa `True`, özel bir oluşturucu kaynak kodunda sağlanacaktır. Daha fazla bilgi için bkz: [geçersiz kılma ve oluşturulan sınıflar genişletme](../modeling/overriding-and-extending-the-generated-classes.md).|False|
|Devralma değiştiricisi|Bir bağlayıcı oluşturulan kaynak kodu sınıf devralma türünü açıklar (`none`, `abstract` veya `sealed`).|yok|
|Temel Bağlayıcısı|Bu bağlayıcı temel sınıf.|(hiçbiri)|
|Ad|Bu bağlayıcı adı.|Geçerli adı|
|Ad Alanı|Bu bağlayıcı ile bağlantılı olan ad alanı.|Geçerli ad alanı|
|Araç İpucu türü|Nasıl araç ipucu (sabit, değişken veya hiçbiri) tanımlanır. Sabit, ardından değeri `Fixed Tooltip Text` özelliği araç ipucu olarak kullanılır; ardından değişken durumunda, araç ipucu özel kod içinde tanımlanır.|\<yok >|
|Notlar|Bu bağlayıcı ile ilişkilendirilen resmi olmayan notları.|\<yok >|
|Yönlendirme Stili|Bağlayıcı yönlendirme için kullanılan stili. A `Rectilinear` bağlayıcı yapar gerektiği; dik açılı kapatır bir `Straight` bağlayıcı desteklemez.|Dikdörtgen Çizgili|
|Özellik olarak sunulan rengi<br /><br /> Özellik olarak sunulan çizgi stili<br /><br /> Özellik olarak sunulan kalınlığı<br /><br /> Metin rengi gösterir|Varsa `True`, kullanıcı bir şekli belirtilen özelliğini ayarlayabilirsiniz. Bunu ayarlamak için Şekil tanımı sağ tıklatıp **eklemek açığa**.|False|
|Açıklama|Oluşturulan Tasarımcısı belgelemek için kullanılır.|\<yok >|
|Görünen ad|Bu bağlayıcı için oluşturulan Tasarımcısı'nda görüntülenen ad.|\<yok >|
|Sabit araç ipucu metni|Sabit bir araç ipucu için kullanılan metin.|\<yok >|
|Yardım anahtar sözcüğü|Bu öğe için F1 Yardımı dizin oluşturmak için kullanılan anahtar sözcük.|\<yok >|

## <a name="see-also"></a>Ayrıca Bkz.

- [Etki alanına özgü dil araçları sözlüğü](http://msdn.microsoft.com/ca5e84cb-a315-465c-be24-76aa3df276aa)