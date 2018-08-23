---
title: Bir DSL tanımının özellikleri | Microsoft Docs
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-tfs-dev14
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- Domain-Specific Language, definition file
ms.assetid: 38debcfe-e1a6-4a3f-9d69-3ab07520f2b6
caps.latest.revision: 15
author: gewarren
ms.author: gewarren
manager: douge
ms.openlocfilehash: 5c5ebb4672cdbb82692dc01339409ef7fa91c2d5
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/22/2018
ms.locfileid: "42684301"
---
# <a name="properties-of-a-dsl-definition"></a>DSL Tanımının Özellikleri
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Bu konuda en son sürümünü şu yolda bulunabilir: [DSL tanımının özellikleri](https://docs.microsoft.com/visualstudio/modeling/properties-of-a-dsl-definition).  
  
DslDefinition özelliklerini tanımlayın *etki alanına özgü dil* sürümü numaralandırma gibi tanımı özellikleri. DslDefinition özellikleri görünür **özellikleri** pencere, diyagramdaki boş bir alanı tıkladığınızda *etki alanına özgü dil tasarımcısını*.  
  
 Daha fazla bilgi için [etki alanına özgü bir dili tanımlama nasıl](../modeling/how-to-define-a-domain-specific-language.md). Bu özellikler kullanma hakkında daha fazla bilgi için bkz. [bir etki alanına özgü dili özelleştirme ve genişletme](../modeling/customizing-and-extending-a-domain-specific-language.md).  
  
 DslDefinition aşağıdaki tabloda özelliklere sahiptir:  
  
|Özellik|Açıklama|Varsayılan|  
|--------------|-----------------|-------------|  
|Erişim değiştiricisi|Alan sınıfına ait erişim değiştiricisinin public veya internal olduğunu belirler.|public|  
|Özel Öznitelikler|Özel öznitelikler etki alanı sınıfı için tanımlanmış.<br /><br /> **Not** bir öznitelik eklemek için Gözat düğmesini kullanın.|\<yok >|  
|Şirket adı|Sistem kayıt defterinde geçerli şirket adı adı.|Geçerli bir şirket adı|  
|Ad|Bu alan sınıfının adı.|Geçerli ad|  
|Ad Alanı|Bu alan sınıfıyla ilişkili ad alanı.|Geçerli ad alanı|  
|Paket GUID'si|GUID [!INCLUDE[vsprvs](../includes/vsprvs-md.md)] bu DSL için oluşturulan paket.|\<yok >|  
|Paket Namespace|Ad alanı için [!INCLUDE[vsprvs](../includes/vsprvs-md.md)] bu DSL için oluşturulan paket.|\<yok >|  
|Ürün Adı|İçin kaydedilen ürün adını [!INCLUDE[vsprvs](../includes/vsprvs-md.md)] bu DSL için oluşturulan paket.|\<yok >|  
|Notlar|Bu alan sınıfıyla ilişkili notları.|\<yok >|  
|Açıklama|Bu etki alanı sınıfı için açıklama.|\<yok >|  
|Görünen ad|Bu etki alanı sınıfı için oluşturulan tasarımcıda görüntülenecek ad.|\<yok >|  
|Yardım anahtar sözcüğü|Bu alan sınıfıyla ilişkili Yardım anahtar sözcüğü.|\<yok >|  
|Derleme|Bu etki alanına özgü dil tanımı için artımlı derleme numarası.|0|  
|Ana sürüm|Bu etki alanına özgü dil tanımı için artımlı başlıca yapı numarası.|1.|  
|Alt sürüm|Bu etki alanına özgü dil tanımı için artımlı alt yapı numarası.|0|  
|Gözden geçirme|Artımlı düzeltme numarası için bu etki alanına özgü dil tanımı oluşturun.|0|  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Etki alanına özgü dil araçları sözlüğü](http://msdn.microsoft.com/en-us/ca5e84cb-a315-465c-be24-76aa3df276aa)



