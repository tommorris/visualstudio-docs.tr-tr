---
title: Diyagramların Özellikleri
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- vs.dsltools.dsldesigner.dsldiagram
helpviewer_keywords:
- Domain-Specific Language, diagram
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.prod: visual-studio-dev15
ms.technology: vs-ide-modeling
ms.openlocfilehash: f66c4597116c2dd27320a8ae0bf69314bbb558b4
ms.sourcegitcommit: e13e61ddea6032a8282abe16131d9e136a927984
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/26/2018
ms.locfileid: "31949165"
---
# <a name="properties-of-diagrams"></a>Diyagramların Özellikleri
Diyagramları oluşturulan Tasarımcısı'nda nasıl görüneceğini belirten özellikleri ayarlayabilirsiniz. Örneğin, aşağıdaki çizimde metin varsayılan rengini belirtebilirsiniz.

 Daha fazla bilgi için bkz: [bir etki alanına özgü dil tanımlamak nasıl](../modeling/how-to-define-a-domain-specific-language.md). Bu özellikleri kullanma hakkında daha fazla bilgi için bkz: [özelleştirme ve bir etki alanına özgü dil genişletme](../modeling/customizing-and-extending-a-domain-specific-language.md).

 Aşağıdaki tabloda diyagramları özelliklerini listeler.

|Özellik|Açıklama|Varsayılan|
|--------------|-----------------|-------------|
|Dolgu rengi|Diyagram için dolgu rengi.|Beyaz|
|Metin rengi|Diyagramda görüntülenen metin rengi.|Siyah|
|Erişim değiştiricisi|Sınıfı (ortak veya dahili) erişim değiştiricisi.|Ortak|
|Özel Öznitelikler|Oluşturulan kodun sınıf öznitelikleri eklemek için kullanılır.|\<yok >|
|Çift oluşturur türetilmiş|Varsa `True`, bir taban sınıf ve bir parçalı sınıf (geçersiz kılmaları özelleştirmeyi desteklemek için) oluşturulur. Daha fazla bilgi için bkz: [geçersiz kılma ve oluşturulan sınıflar genişletme](../modeling/overriding-and-extending-the-generated-classes.md).|False|
|Özel bir oluşturucuya sahip|Varsa `True`, özel bir oluşturucu kaynak kodunda sağlanacaktır. Daha fazla bilgi için bkz: [geçersiz kılma ve oluşturulan sınıflar genişletme](../modeling/overriding-and-extending-the-generated-classes.md)...|False|
|Devralma değiştiricisi|Diyagramdan oluşturulan kaynak kodu sınıf devralma türünü açıklar (`none`, `abstract` veya `sealed`).|Yok.|
|Temel diyagramı|Bu diyagramda temel sınıf.|(hiçbiri)|
|Ad|Bu diyagramda adı.|Geçerli adı|
|Ad Alanı|Bu diyagramda ile bağlantılı olan ad alanı.|Geçerli ad alanı|
|Temsil sınıfı|Bu diyagramda temsil eden kök etki alanı sınıf.|Varsa geçerli kök sınıfı|
|Notlar|Bu öğeyle ilişkili resmi olmayan notları.|\<yok >|
|Dolgu rengi özelliği olarak açığa çıkarır|Varsa `True`, kullanıcı oluşturulan Tasarımcısı Diyagramı dolgu rengini ayarlayabilirsiniz. Bunu ayarlamak için diyagram şekli sağ tıklayın ve **ekleme Explosed**.|False|
|Metin rengi özelliği olarak kullanıma sunar.|Varsa `True`, kullanıcı diyagram metin rengi oluşturulan Tasarımcısı'nda ayarlayabilirsiniz. Bunu ayarlamak için diyagram şekli sağ tıklayın ve **ekleme Explosed**.|False|
|Açıklama|Oluşturulan Tasarımcısı belgelemek için kullanılan açıklaması.|\<yok >|
|Görünen ad|Bu diyagramda için oluşturulan Tasarımcısı'nda görüntülenen ad.|\<yok >|
|Yardım anahtar sözcüğü|Bu diyagramda için F1 Yardımı dizin oluşturmak için kullanılan anahtar sözcük.|\<yok >|

## <a name="see-also"></a>Ayrıca Bkz.

- [Etki alanına özgü dil araçları sözlüğü](http://msdn.microsoft.com/ca5e84cb-a315-465c-be24-76aa3df276aa)