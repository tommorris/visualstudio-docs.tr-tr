---
title: Bağlayıcıların özellikleri | Microsoft Docs
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-tfs-dev14
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- Domain-Specific Language, connectors
ms.assetid: b1f24e8d-cdd7-4a5d-af37-1038f43b45c7
caps.latest.revision: 23
author: gewarren
ms.author: gewarren
manager: douge
ms.openlocfilehash: e2a0dbf1570e8a1ba29c82f1e492b9cc6852cccb
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/22/2018
ms.locfileid: "42693509"
---
# <a name="properties-of-connectors"></a>Bağlayıcıların Özellikleri
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Bu konuda en son sürümünü şu yolda bulunabilir: [özellikleri, bağlayıcılar](https://docs.microsoft.com/visualstudio/modeling/properties-of-connectors).  
  
Bağlayıcılar, etki alanı ilişkileri oluşturulan tasarımcıda temsil eder.  
  
 Daha fazla bilgi için [etki alanına özgü bir dili tanımlama nasıl](../modeling/how-to-define-a-domain-specific-language.md). Bu özellikler kullanma hakkında daha fazla bilgi için bkz. [bir etki alanına özgü dili özelleştirme ve genişletme](../modeling/customizing-and-extending-a-domain-specific-language.md).  
  
 Bağlayıcılar aşağıdaki tabloda listelenen özellikleri vardır.  
  
|Özellik|Açıklama|Varsayılan|  
|--------------|-----------------|-------------|  
|Renk|Bu bağlayıcının rengi.|Siyah|  
|Kesik çizgi stili|Bu bağlayıcının (düz, kesik çizgi, nokta, çizgi nokta, çizgi nokta nokta veya özel) satırı için çizgi stili.|Düz|  
|Kaynak uç stili|(HollowArrow, EmptyArrow, FilledArrow, EmptyDiamond, FilledDiamond veya hiçbiri) bu bağlayıcının kaynak uç stili.|Yok.|  
|Hedef uç stili|(HollowArrow, EmptyArrow, FilledArrow, EmptyDiamond, FilledDiamond veya hiçbiri) bu bağlayıcının hedef uç stili.|Yok.|  
|Metin rengi|Bu bağlayıcıyla ilişkili metin dekoratörleri için kullanılan renk.|Siyah|  
|Kalınlığı|Bu bağlayıcının inç cinsinden ölçülen çizgi kalınlığı.|0.03125|  
|Erişim değiştiricisi|Sınıf erişim düzeyini (`public` veya `internal`).|Ortak|  
|Özel Öznitelikler|Bu bağlayıcı oluşturulan kaynak kod sınıfı öznitelikler eklemek için kullanılır.|\<yok >|  
|Çift oluşturur türetilmiş|Varsa `True`, hem temel sınıf hem de (geçersiz kılmalar aracılığıyla özelleştirmeyi desteklemek için) bir kısmi sınıf oluşturulur. Daha fazla bilgi için [geçersiz kılma ve oluşturulan sınıflar genişletme](../modeling/overriding-and-extending-the-generated-classes.md).|False|  
|Özel oluşturucu vardır.|Varsa `True`, kaynak kodunda özel bir oluşturucu sağlanacaktır. Daha fazla bilgi için [geçersiz kılma ve oluşturulan sınıflar genişletme](../modeling/overriding-and-extending-the-generated-classes.md).|False|  
|Devralma değiştiricisi|Devralma bağlayıcısından oluşturulan kaynak kodu sınıf türünü açıklar (`none`, `abstract` veya `sealed`).|yok|  
|Temel bağlayıcı|Bu bağlayıcının temel sınıf.|(hiçbiri)|  
|Ad|Bu bağlayıcı adı.|Geçerli ad|  
|Ad Alanı|Bu bağlayıcı ile bağlantılı olan ad alanı.|Geçerli ad alanı|  
|Araç İpucu türü|Nasıl bir araç ipucu (sabit, değişken veya hiçbiri) tanımlanır. Fixed ise ardından değerini `Fixed Tooltip Text` özelliği, araç ipucu olarak kullanılır; ardından değişken durumunda, araç ipucu özel kodda tanımlanır.|\<yok >|  
|Notlar|Bu bağlayıcı ile ilişkilendirilen resmi olmayan notlar.|\<yok >|  
|Yönlendirme stilini|Bağlayıcıyı yönlendirmek için kullanılan stil. A `Rectilinear` bağlayıcı yapar dik açılı kapatır gerekli; bir `Straight` Bağlayıcısı yok.|Dönüşler|  
|Özellik olarak kullanıma sunulan rengi<br /><br /> Özellik olarak kullanıma sunulan kesik çizgi stili<br /><br /> Özellik olarak kullanıma sunulan kalınlığı<br /><br /> Kullanıma sunan metin rengi|Varsa `True`, kullanıcının belirtilen özelliği bir şeklin ayarlayabilirsiniz. Bunu ayarlamak için Şekil tanımı sağ tıklatıp **ekleme kullanıma sunulan**.|False|  
|Açıklama|Oluşturulan tasarımcının belge için kullanılır.|\<yok >|  
|Görünen ad|Bu bağlayıcı için oluşturulan tasarımcıda görüntülenecek ad.|\<yok >|  
|Sabit araç ipucu metni|Sabit bir araç ipucu için kullanılan metin.|\<yok >|  
|Yardım anahtar sözcüğü|Bu öğe için F1 Yardımı dizini oluşturmak için kullanılan anahtar sözcüğü.|\<yok >|  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Etki alanına özgü dil araçları sözlüğü](http://msdn.microsoft.com/en-us/ca5e84cb-a315-465c-be24-76aa3df276aa)



