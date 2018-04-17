---
title: Kulvarları özelliklerini | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.topic: conceptual
f1_keywords:
- vs.dsltools.dsldesigner.swimlane
helpviewer_keywords:
- Domain-Specific Language, swimlane
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.technology: vs-ide-modeling
ms.openlocfilehash: 9a9a07549773d9881b3512bdb1b84c0cb6654280
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/16/2018
---
# <a name="properties-of-swimlanes"></a>Kulvarların Özellikleri
Bir diyagrama kulvarları ekleyebilirsiniz. Kulvarları diyagram dikey veya yatay alanlarına bölün. İçinde kulvarları görüntülenecek diğer şekiller tanımlayabilirsiniz. Daha fazla bilgi için bkz: [bir etki alanına özgü dil tanımlamak nasıl](../modeling/how-to-define-a-domain-specific-language.md). Bu özellikleri kullanma hakkında daha fazla bilgi için bkz: [özelleştirme ve bir etki alanına özgü dil genişletme](../modeling/customizing-and-extending-a-domain-specific-language.md).  
  
 Kulvarları aşağıdaki tabloda listelenen özellikleri vardır.  
  
|Özellik|Açıklama|Varsayılan|  
|--------------|-----------------|-------------|  
|Gövde dolgu rengi|Kulvar gövdesi için dolgu rengi.|Beyaz|  
|Üstbilgi dolgu rengi|Kulvar üstbilgisinin dolgu rengi.|Koyu gri|  
|Ayırıcı rengi|Ayırıcı çizginin rengi.|LightGray|  
|Ayırıcı çizgi stili|Ayırıcı çizgi stilini (`Solid`, `Dash`, `Dot`, `DashDot`, `DashDotDot`, veya `Custom`).|`Dash`|  
|Ayırıcı kalınlığı|İnç ayırıcı çizgi kalınlığı.|0.03125|  
|Metin rengi|Bu Kulvar ile ilişkili metin dekoratörler için kullanılan rengi.|Siyah|  
|Erişim değiştiricisi|Sınıfının erişim düzeyini (`public` veya `internal`).|Ortak|  
|Özel Öznitelikler|Bu Kulvar oluşturulan kod sınıfı öznitelikler eklemek için kullanılır.|\<yok >|  
|Çift oluşturur türetilmiş|Varsa `True`, bir taban sınıf ve bir parçalı sınıf (geçersiz kılmaları özelleştirmeyi desteklemek için) oluşturulur. Daha fazla bilgi için bkz: [geçersiz kılma ve oluşturulan sınıflar genişletme](../modeling/overriding-and-extending-the-generated-classes.md).|False|  
|Özel bir oluşturucuya sahip|Varsa `True`, özel bir oluşturucu kaynak kodunda sağlanacaktır. Daha fazla bilgi için bkz: [geçersiz kılma ve oluşturulan sınıflar genişletme](../modeling/overriding-and-extending-the-generated-classes.md).|False|  
|Devralma değiştiricisi|Kulvar oluşturulan kaynak kodu sınıf devralma türünü açıklar (`none`, `abstract` veya `sealed`).|yok|  
|Temel Kulvar|Bu Kulvar temel sınıf.|(hiçbiri)|  
|Ad|Bu Kulvar adı.|Geçerli adı|  
|Ad Alanı|Bu Kulvar ile bağlantılı olan ad alanı.|Geçerli ad alanı|  
|Araç İpucu türü|Araç İpucu nasıl tanımlanır (`fixed`, `variable`, veya `none`). Varsa `fixed`, ardından değeri `Fixed Tooltip Text` özelliği kullanılır; varsa `variable`, araç ipucu özel kod içinde tanımlanan daha sonra.|\<yok >|  
|Notlar|Bu Kulvar ile ilişkili resmi olmayan notları.|\<yok >|  
|Hizalama|Yatay veya dikey hizalama.|Dikey|  
|İlk yükseklik|İnç bu Kulvar ilk yüksekliği. Yalnızca yatay kulvarları uygulanabilir.|0|  
|İlk genişliği|İnç bu Kulvar başlangıç genişliği. Yalnızca dikey kulvarları uygulanabilir.|0|  
|Metin rengi gösterir|Varsa `True`, kullanıcı bir Kulvar rengini oluşturulan Tasarımcısı'nda ayarlayabilirsiniz. Bunu ayarlamak için Kulvar şekli sağ tıklatın ve **eklemek açığa**.|False|  
|Açıklama|Oluşturulan Tasarımcısı belgelemek için kullanılır.|\<yok >|  
|Görünen ad|Bu Kulvar sınıfa başvurmak için oluşturulan Tasarımcısı'nda görüntülenen ad.|\<yok >|  
|Sabit araç ipucu metni|Sabit bir araç ipucu için kullanılan metin.|\<yok >|  
|Yardım anahtar sözcüğü|Bu Kulvar için F1 Yardımı dizin oluşturmak için kullanılan anahtar sözcük.|\<yok >|  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Etki alanına özgü dil araçları sözlüğü](http://msdn.microsoft.com/ca5e84cb-a315-465c-be24-76aa3df276aa)