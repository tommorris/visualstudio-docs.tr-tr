---
title: "Visual Studio - etki alanına özgü dil SDK Modelleme | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-devops-techdebt
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Domain-Specific Language Tools
- Domain-Specific Language
ms.assetid: 17a531e2-1964-4a9d-84fd-6fb1b4aee662
caps.latest.revision: "77"
author: alancameronwills
ms.author: awills
manager: douge
ms.openlocfilehash: 48cb7e5a274092a3ed82d2e41137633d12c3be01
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2017
---
# <a name="modeling-sdk-for-visual-studio---domain-specific-languages"></a>Visual Studio için Modelleme SDK'sı - Etki Alanına Özgü Diller
Modelleme SDK kullanarak [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)], içine tümleştirebilir güçlü model tabanlı geliştirme araçlarına oluşturabilirsiniz [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)]. Aynı şekilde, bir veya daha fazla model tanımı oluşturabilir ve bir araç kümesiyle tümleştirebilirsiniz.  
  
 MSDK'nın merkezinde, iş alanınızdaki kavramları göstermek için oluşturabileceğiniz bir model tanımı bulunur. Surround grafiksel bir görünüm gibi araçları çeşitli modeliyle kod ve diğer yapıları oluşturma yeteneği komutları modeli ve kod ve diğer nesneleri ile etkileşim özelliği dönüştürme için [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)]. Modeli geliştirirken, geliştirmenizin merkezine yerleştirilen güçlü bir araç kümesi oluşturmak için onu diğer modellerle birleştirebilirsiniz.  
  
 MSDK, etki alanına özgü dil (DSL) biçiminde bir modeli hızlı bir şekilde geliştirmenize olanak sağlar. Graf gösterimli bir şema veya soyut sözdizimi tanımlamak için özelleştirilmiş bir düzenleyici kullanarak başlarsanız. Bu tanımından, VMSDK şunları oluşturur:  
  
-   İşlem tabanlı bir depoda çalışan, türü kesin belirlenmiş bir API ile model uygulaması.  
  
-   Ağaç tabanlı bir gezgin.  
  
-   Kullanıcıların tanımladığınız modeli veya bölümlerini görüntüleyebildiği bir grafik düzenleyici.  
  
-   Modellerinizi okunabilir XML biçiminde kaydeden serileştirme yöntemleri.  
  
-   Metin şablonu kullanarak program kodu ve diğer yapıları üretmek için olanaklar.  
  
 Bu özelliklerin tümünü özelleştirebilir ve genişletebilirsiniz. Uzantılarınız, DSL tanımını hala güncelleştirebileceğiniz ve uzantılarınızı kaybetmeden özellikleri yeniden üretebileceğiniz bir şekilde tümleştirilir.  
  
[!INCLUDE[modeling_sdk_info](includes/modeling_sdk_info.md)]
 
 [İlgili blog gönderileri](https://blogs.msdn.microsoft.com/visualstudioalm/tag/code-index/)
  
 Gelişmiş teknikleri ve sorun giderme hakkında yönergeler için ziyaret [Visual Studio DSL & modelleme araçları genişletilebilirliği Forumu](http://go.microsoft.com/fwlink/?LinkID=186074).  
  
## <a name="in-this-section"></a>Bu Bölümde  
 [Etki alanına özgü dil ile çalışmaya başlama](../modeling/getting-started-with-domain-specific-languages.md)  
  
 [Anlama modelleri, sınıflar ve ilişkiler](../modeling/understanding-models-classes-and-relationships.md)  
  
 [Bir etki alanına özgü dil tanımlama](../modeling/how-to-define-a-domain-specific-language.md)  
  
 [Özelleştirme ve bir etki alanına özgü dil genişletme](../modeling/customizing-and-extending-a-domain-specific-language.md)  
  
 [Bir etki alanına özgü dil doğrulama](../modeling/validation-in-a-domain-specific-language.md)  
  
 [Bir etki alanına özgü dil kişiselleştirmek için kod yazma](../modeling/writing-code-to-customise-a-domain-specific-language.md)  
  
 [Bir etki alanına özgü dili kod oluşturma](../modeling/generating-code-from-a-domain-specific-language.md)  
  
 [DSL kodu anlama](../modeling/understanding-the-dsl-code.md)  
  
 [Dosya depolama ve XML serileştirme özelleştirme](../modeling/customizing-file-storage-and-xml-serialization.md)  
  
 [Etki alanına özgü dil çözümlerini dağıtma](../modeling/deploying-domain-specific-language-solutions.md)  
  
 [Windows Forms tabanlı bir etki alanına özgü dil oluşturma](../modeling/creating-a-windows-forms-based-domain-specific-language.md)  
  
 [Bir WPF tabanlı etki alanına özgü dil oluşturma](../modeling/creating-a-wpf-based-domain-specific-language.md)  
  
 [Nasıl yapılır: etki alanına özgü dil Tasarımcısı genişletme](../modeling/how-to-extend-the-domain-specific-language-designer.md)  
  
 [Görselleştirme ve modelleme SDK için desteklenen Visual Studio sürümleri](../modeling/supported-visual-studio-editions-for-visualization-amp-modeling-sdk.md)  
  
 [Nasıl yapılır: bir etki alanına özgü dil yeni bir sürüme geçiş](../modeling/how-to-migrate-a-domain-specific-language-to-a-new-version.md)  
  
 [Visual Studio SDK Modelleme için API Başvurusu](../modeling/api-reference-for-modeling-sdk-for-visual-studio.md)
