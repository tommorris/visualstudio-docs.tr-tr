---
title: Etki alanı ilişkilerini özelliklerini | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- Domain-Specific Language, domain relationships
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.technology: vs-ide-modeling
ms.openlocfilehash: 6cc2da3665dcf6b5d5ba07fad53c6246c04709cd
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/16/2018
---
# <a name="properties-of-domain-relationships"></a>Etki Alanı İlişkilerinin Özellikleri
Bir etki alanı ilişkisinin ile ilişkili aşağıdaki tabloda özelliklerdir. Etki alanı ilişkileri hakkında daha fazla bilgi için bkz: [anlama modelleri, sınıflar ve ilişkiler](../modeling/understanding-models-classes-and-relationships.md). Bu özellikleri kullanma hakkında daha fazla bilgi için bkz: [özelleştirme ve bir etki alanına özgü dil genişletme](../modeling/customizing-and-extending-a-domain-specific-language.md).  
  
|Özellik|Açıklama|Varsayılan|  
|--------------|-----------------|-------------|  
|Erişim değiştiricisi|Etki alanı ilişkisinin erişim düzeyini (`public` veya `internal`).|`public`|  
|Özel Öznitelikler|Etki alanı ilişkiden oluşturulan kaynak kodu sınıfı öznitelikler eklemek için kullanılır.|\<yok >|  
|Çift oluşturur türetilmiş|Varsa `True`, bir taban sınıf ve bir parçalı sınıf (geçersiz kılmaları özelleştirmeyi desteklemek için) oluşturulur. Daha fazla bilgi için bkz: [geçersiz kılma ve oluşturulan sınıflar genişletme](../modeling/overriding-and-extending-the-generated-classes.md).|`False`|  
|Özel bir oluşturucuya sahip|Varsa `True`, özel bir oluşturucu kaynak kodunda sağlandığını belirtir. Daha fazla bilgi için bkz: [geçersiz kılma ve oluşturulan sınıflar genişletme](../modeling/overriding-and-extending-the-generated-classes.md).|`False`|  
|Devralma değiştiricisi|Etki alanı ilişkiden oluşturulan kaynak kodu sınıf devralma türünü açıklar (`none`, `abstract` veya `sealed`).|\<yok >|  
|Çoğaltmaları sağlar|Varsa `True`, etki alanı ilişkisinin yinelenen bağlantıları aynı iki öğe arasında oluşturulabilir.|`False`|  
|Temel ilişkileri|Etki alanı ilişkisinin türetilmiş, etki alanı ilişkisinin taban ilişki.|\<yok >|  
|Katıştırma olduğu|Varsa `True`, etki alanı ilişkisinin katıştırma ilişkidir. Varsa `False`, bir başvuru ilişkisi ilişkidir.|\<her ikisi de >|  
|Ad|Etki alanı ilişkisinin adı.|Geçerli adı|  
|Ad Alanı|Etki alanı ilişkisinin ile bağlantılı olan ad alanı.|Geçerli ad alanı|  
|Notlar|Etki alanı ilişki ile ilişkilendirilen resmi olmayan notları.|\<yok >|  
|Açıklama|Kod belge için kullanılır ve oluşturulan Tasarımcısı'nın kullanıcı Arabiriminde kullanılan açıklaması.|\<yok >|  
|Görünen ad|Etki alanı ilişkisinin oluşturulan Tasarımcısı'nda görüntülenen ad.|\<yok >|  
|Yardım anahtar sözcüğü|Etki alanı ilişkisinin için F1 Yardımı dizin oluşturmak için kullanılan isteğe bağlı anahtar sözcük.|\<yok >|  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Etki alanına özgü dil araçları sözlüğü](http://msdn.microsoft.com/ca5e84cb-a315-465c-be24-76aa3df276aa)