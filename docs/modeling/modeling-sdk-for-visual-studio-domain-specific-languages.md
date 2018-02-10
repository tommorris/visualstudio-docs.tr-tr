---
title: "Visual Studio - etki alanına özgü dil SDK Modelleme | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-modeling
ms.topic: article
helpviewer_keywords:
- Domain-Specific Language Tools
- Domain-Specific Language
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload:
- multiple
ms.openlocfilehash: 1edb30221d85f8e634a9d618d50cd1e0b772b69a
ms.sourcegitcommit: 205d15f4558315e585c67f33d5335d5b41d0fcea
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/09/2018
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
 [Etki Alanına Özgü Dillerle Çalışmaya Başlama](../modeling/getting-started-with-domain-specific-languages.md)  
  
 [Modelleri, Sınıfları ve İlişkileri Anlama](../modeling/understanding-models-classes-and-relationships.md)  
  
 [Nasıl yapılır: Etki Alanına Özgü bir Dili Tanımlama](../modeling/how-to-define-a-domain-specific-language.md)  
  
 [Etki Alanına Özgü Dili Özelleştirme ve Genişletme](../modeling/customizing-and-extending-a-domain-specific-language.md)  
  
 [Etki Alanına Özgü bir Dilde Doğrulama](../modeling/validation-in-a-domain-specific-language.md)  
  
 [Etki Alanına Özgü Dili Özelleştirmek için Kod Yazma](../modeling/writing-code-to-customise-a-domain-specific-language.md)  
  
 [Etki Alanına Özgü Dilden Kod Oluşturma](../modeling/generating-code-from-a-domain-specific-language.md)  
  
 [DSL Kodunu Anlama](../modeling/understanding-the-dsl-code.md)  
  
 [Dosya Depolamayı ve XML Serileştirmeyi Özelleştirme](../modeling/customizing-file-storage-and-xml-serialization.md)  
  
 [Etki Alanına Özgü Dil Çözümlerini Dağıtma](../modeling/deploying-domain-specific-language-solutions.md)  
  
 [Windows Forms Tabanlı Etki Alanına Özgü Dil Oluşturma](../modeling/creating-a-windows-forms-based-domain-specific-language.md)  
  
 [WPF Tabanlı Etki Alanına Özgü Dil Oluşturma](../modeling/creating-a-wpf-based-domain-specific-language.md)  
  
 [Nasıl yapılır: Etki Alanına Özgü Dil Tasarımcısını Genişletme](../modeling/how-to-extend-the-domain-specific-language-designer.md)  
  
 [Görselleştirme ve SDK Modelleme için Desteklenen Visual Studio Sürümleri](../modeling/supported-visual-studio-editions-for-visualization-amp-modeling-sdk.md)  
  
 [Nasıl yapılır: Etki Alanına Özgü Dili Yeni Sürüme Geçirme](../modeling/how-to-migrate-a-domain-specific-language-to-a-new-version.md)  
  
 [Visual Studio için Modelleme SDK'sı için API Başvurusu](../modeling/api-reference-for-modeling-sdk-for-visual-studio.md)
