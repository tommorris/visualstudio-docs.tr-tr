---
title: Etki alanı sınıflarının özellikleri | Microsoft Docs
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-tfs-dev14
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- Domain-Specific Language, domain class
ms.assetid: a3993995-19e7-4761-a972-b1de89131a1b
caps.latest.revision: 23
author: gewarren
ms.author: gewarren
manager: douge
ms.openlocfilehash: 3d5ea3d5cad378a476c9080cd56143b1600b7b4d
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/22/2018
ms.locfileid: "42686260"
---
# <a name="properties-of-domain-classes"></a>Etki Alanı Sınıflarının Özellikleri
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Bu konuda en son sürümünü şu yolda bulunabilir: [etki alanı sınıflarının özellikleri](https://docs.microsoft.com/visualstudio/modeling/properties-of-domain-classes).  
  
Etki alanı sınıfları aşağıdaki tabloda özelliklere sahiptir. Etki alanı sınıfları hakkında daha fazla bilgi için bkz: [anlama modelleri, sınıfları ve ilişkileri](../modeling/understanding-models-classes-and-relationships.md). Bu özellikler kullanma hakkında daha fazla bilgi için bkz. [bir etki alanına özgü dili özelleştirme ve genişletme](../modeling/customizing-and-extending-a-domain-specific-language.md).  
  
|Özellik|Açıklama|Varsayılan|  
|--------------|-----------------|-------------|  
|Erişim değiştiricisi|Etki alanı sınıfı, erişim düzeyi (`public` veya `internal`).|`public`|  
|Özel Öznitelikler|Bu alan sınıfından oluşturulan kaynak kod sınıfı öznitelikler eklemek için kullanılır.|\<yok >|  
|Çift oluşturur türetilmiş|Varsa `True`, hem temel sınıf hem de (geçersiz kılmalar aracılığıyla özelleştirmeyi desteklemek için) bir kısmi sınıf oluşturulur. Daha fazla bilgi için [geçersiz kılma ve oluşturulan sınıflar genişletme](../modeling/overriding-and-extending-the-generated-classes.md).|`False`|  
|Özel oluşturucu vardır.|Varsa `True`, kaynak kodunda özel bir oluşturucu sağlanacaktır. Daha fazla bilgi için [geçersiz kılma ve oluşturulan sınıflar genişletme](../modeling/overriding-and-extending-the-generated-classes.md).|`False`|  
|Devralma değiştiricisi|Alan sınıfından oluşturulan kaynak kodu sınıf devralma türü açıklar (`none`, `abstract` veya `sealed`).|`none`|  
|Temel sınıf|Bu etki alanı sınıfı türetiliyorsa temel sınıfın adı.|\<yok >|  
|Ad|Bu alan sınıfının adı.|Geçerli ad|  
|Ad Alanı|Bu alan sınıfının ad alanı.|Geçerli ad alanı|  
|Notlar|Bu alan sınıfıyla ilişkili resmi olmayan notlar.|\<yok >|  
|Açıklama|Belge oluşturulan tasarımcının kullanıcı Arabirimi için kullanılan bir açıklaması.|\<yok >|  
|Görünen ad|Bu etki alanı sınıfı için oluşturulan tasarımcıda görüntülenecek ad.|\<yok >|  
|Yardım anahtar sözcüğü|Bu etki alanı sınıfı için F1 Yardımı dizini oluşturmak için kullanılan isteğe bağlı anahtar sözcük.|\<yok >|  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Etki alanına özgü dil araçları sözlüğü](http://msdn.microsoft.com/en-us/ca5e84cb-a315-465c-be24-76aa3df276aa)



