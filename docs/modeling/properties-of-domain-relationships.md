---
title: "Etki alanı ilişkilerini özelliklerini | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: Domain-Specific Language, domain relationships
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload: multiple
ms.openlocfilehash: 3f81f4bca6d268cd9fd32a6edf44cbde40d7c357
ms.sourcegitcommit: f89ed5fc2e5078213e30a6ade4604e34df48181f
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/13/2018
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
 [Etki alanına özgü dil araçları sözlüğü](http://msdn.microsoft.com/en-us/ca5e84cb-a315-465c-be24-76aa3df276aa)