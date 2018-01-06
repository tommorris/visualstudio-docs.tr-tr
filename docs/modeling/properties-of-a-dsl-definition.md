---
title: "DSL tanımının özelliklerini | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: Domain-Specific Language, definition file
ms.assetid: 38debcfe-e1a6-4a3f-9d69-3ab07520f2b6
caps.latest.revision: "13"
author: alancameronwills
ms.author: awills
manager: douge
ms.workload: multiple
ms.openlocfilehash: 289c95ebbbd294050b1e5c7cc95656e7ab5eadc0
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/22/2017
---
# <a name="properties-of-a-dsl-definition"></a>DSL Tanımının Özellikleri
DslDefinition özellikleri tanımlama *etki alanına özgü dil* Sürüm numaralandırma gibi tanımı özellikleri. DslDefinition özellikleri görünür **özellikleri** diyagramda açık bir bölümünü tıklattığınızda penceresi *etki alanına özgü dil Tasarımcısı*.  
  
 Daha fazla bilgi için bkz: [bir etki alanına özgü dil tanımlamak nasıl](../modeling/how-to-define-a-domain-specific-language.md). Bu özellikleri kullanma hakkında daha fazla bilgi için bkz: [özelleştirme ve bir etki alanına özgü dil genişletme](../modeling/customizing-and-extending-a-domain-specific-language.md).  
  
 DslDefinition aşağıdaki tabloda özelliklere sahiptir:  
  
|Özellik|Açıklama|Varsayılan|  
|--------------|-----------------|-------------|  
|Erişim değiştiricisi|Etki alanı sınıfı için erişim değiştiricisi genel veya iç olup olmadığını belirler.|public|  
|Özel Öznitelikler|Özel öznitelikler etki alanı sınıfı için tanımlanmış.<br /><br /> **Not** öznitelik eklemek için Gözat düğmesini kullanın.|\<yok >|  
|Şirket adı|Sistem kayıt defterinde geçerli şirket adı adı.|Geçerli şirket adı|  
|Ad|Bu etki alanı sınıfının adı.|Geçerli adı|  
|Ad Alanı|Ad alanı bu etki alanı sınıfa.|Geçerli ad alanı|  
|Paket GUID'si|GUID [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] bu DSL için oluşturulan paketi.|\<yok >|  
|Paket Namespace|Ad alanı için [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] bu DSL için oluşturulan paketi.|\<yok >|  
|Ürün Adı|İçin kaydedilen ürün adı [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] bu DSL için oluşturulan paketi.|\<yok >|  
|Notlar|Bu etki alanı ile ilişkili notları.|\<yok >|  
|Açıklama|Bu etki alanı sınıf açıklaması.|\<yok >|  
|Görünen ad|Bu etki alanı sınıf için oluşturulan Tasarımcısı'nda görüntülenen ad.|\<yok >|  
|Yardım anahtar sözcüğü|Bu etki alanı ile ilişkili Yardım anahtar sözcük.|\<yok >|  
|Derleme|Bu etki alanına özgü dil tanımı için artımlı derleme numarası.|0|  
|Ana sürüm|Bu etki alanına özgü dil tanımı için artımlı ana yapı numarası.|1.|  
|Alt sürümü|Bu etki alanına özgü dil tanımı için artımlı alt yapı numarası.|0|  
|Gözden geçirme|Yapı numarası bu etki alanına özgü dil tanımı için artımlı düzeltme.|0|  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Etki alanına özgü dil araçları sözlüğü](http://msdn.microsoft.com/en-us/ca5e84cb-a315-465c-be24-76aa3df276aa)