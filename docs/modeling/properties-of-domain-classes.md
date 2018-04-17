---
title: Etki alanı sınıf özellikleri | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- Domain-Specific Language, domain class
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.technology: vs-ide-modeling
ms.openlocfilehash: 419315e5d8ec44f8065b704612bc50c1788974e3
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/16/2018
---
# <a name="properties-of-domain-classes"></a>Etki Alanı Sınıflarının Özellikleri
Etki alanı sınıfları, özellikleri aşağıdaki tabloda içeriyor. Etki alanı sınıfları hakkında daha fazla bilgi için bkz: [anlama modelleri, sınıflar ve ilişkiler](../modeling/understanding-models-classes-and-relationships.md). Bu özellikleri kullanma hakkında daha fazla bilgi için bkz: [özelleştirme ve bir etki alanına özgü dil genişletme](../modeling/customizing-and-extending-a-domain-specific-language.md).  
  
|Özellik|Açıklama|Varsayılan|  
|--------------|-----------------|-------------|  
|Erişim değiştiricisi|Etki alanı sınıfının erişim düzeyini (`public` veya `internal`).|`public`|  
|Özel Öznitelikler|Bu etki alanı sınıfından oluşturulan kaynak kodu sınıfı öznitelikler eklemek için kullanılır.|\<yok >|  
|Çift oluşturur türetilmiş|Varsa `True`, bir taban sınıf ve bir parçalı sınıf (geçersiz kılmaları özelleştirmeyi desteklemek için) oluşturulur. Daha fazla bilgi için bkz: [geçersiz kılma ve oluşturulan sınıflar genişletme](../modeling/overriding-and-extending-the-generated-classes.md).|`False`|  
|Özel bir oluşturucuya sahip|Varsa `True`, özel bir oluşturucu kaynak kodunda sağlanacaktır. Daha fazla bilgi için bkz: [geçersiz kılma ve oluşturulan sınıflar genişletme](../modeling/overriding-and-extending-the-generated-classes.md).|`False`|  
|Devralma değiştiricisi|Etki alanı sınıfından oluşturulan kaynak kodu sınıf devralma türünü açıklar (`none`, `abstract` veya `sealed`).|`none`|  
|Taban sınıfı|Bu etki alanı sınıfın türetildiği, temel sınıfın adı.|\<yok >|  
|Ad|Bu etki alanı sınıfının adı.|Geçerli adı|  
|Ad Alanı|Bu etki alanı sınıfının ad alanı.|Geçerli ad alanı|  
|Notlar|Bu etki alanı sınıf ile ilişkili resmi olmayan notları.|\<yok >|  
|Açıklama|Oluşturulan Tasarımcısı UI belgelemek için kullanılan açıklaması.|\<yok >|  
|Görünen ad|Bu etki alanı sınıf için oluşturulan Tasarımcısı'nda görüntülenen ad.|\<yok >|  
|Yardım anahtar sözcüğü|Bu etki alanı sınıfı için F1 Yardımı dizin oluşturmak için kullanılan isteğe bağlı anahtar sözcük.|\<yok >|  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Etki alanına özgü dil araçları sözlüğü](http://msdn.microsoft.com/ca5e84cb-a315-465c-be24-76aa3df276aa)