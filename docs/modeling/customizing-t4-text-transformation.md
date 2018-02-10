---
title: "T4 metin dönüştürmeyi özelleştirme | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.topic: article
helpviewer_keywords:
- text templates, API
- text templates, custom hosts
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload:
- multiple
ms.technology: vs-ide-modeling
ms.openlocfilehash: db6d65c5dd0c79549516ff3b9c58b8b59c4be885
ms.sourcegitcommit: 205d15f4558315e585c67f33d5335d5b41d0fcea
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/09/2018
---
# <a name="customizing-t4-text-transformation"></a>T4 Metin Dönüştürmeyi Özelleştirme
Metin şablonları, bir özellik olan [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] program kodunu veya diğer metin dosyaları dönüştürme işlemiyle oluşturmak izin verir. Kullanarak [!INCLUDE[vssdk_current_short](../modeling/includes/vssdk_current_short_md.md)], metin şablonu yönerge işlemcisi veya metin şablonu konağı özelleştirerek varsayılan şablonu dönüştürme süreci genişletebilirsiniz.  
  
## <a name="in-this-section"></a>Bu Bölümde  
 [Metin Şablonu Dönüştürme Süreci](../modeling/the-text-template-transformation-process.md)  
 Metin dönüştürmeyi nasıl çalıştığını, açıklar ve şablonu ana bilgisayarı ve yönerge işlemcileri rolü açıklanmıştır.  
  
 [Özel T4 Metin Şablonu Yönerge İşlemcileri Oluşturma](../modeling/creating-custom-t4-text-template-directive-processors.md)  
 Yönerge işlemcisi yönergeleri için şablonunda gibi ilgilenir `<#@template#>.` şablon derleme sırasında çalışır ve derlemeler ve diğer kaynakları yükleyebilirsiniz. Ayrıca, çalışma zamanında kaynakları yükleyecek kod de ekleyebilirsiniz. Kendi yönerge işlemcisi tanımlayarak, şablonlarınızı karmaşıklığını azaltabilir.  
  
 [Bir VS Uzantısında Metin Dönüştürmeyi Çağırma](../modeling/invoking-text-transformation-in-a-vs-extension.md)  
 Yazıyorsanız bir [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] uzantısı menüsü komut veya olay işleyicisi gibi uzantınızı metin şablonu oluşturma hizmeti herhangi bir metin şablonu dönüştürme için kullanabilirsiniz. Oturum nesnesi kullanarak şablona parametre veri geçirmek ve kullanarak şablonu içindeki değerleri alma `<#@parameter#>` yönergesi.  
  
 [Bir Özel Konak kullanarak Metin Şablonlarını İşleme](../modeling/processing-text-templates-by-using-a-custom-host.md)  
 Metin şablonu kodu yürütüldüğünde, ana dış dosya ve uygulama durumunu erişim sağlar. Örneğin, metin dönüşümleri çalışan konak [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] Çözüm Gezgini erişim sağlayabilir. Ayrıca hataları hata ileti penceresinde görüntüler. Farklı bir bağlamda metin dönüşümleri çalıştırmak istiyorsanız, bu bağlamda kullanılabilir hizmetlerine erişim sağlayan, kendi ana bilgisayar tanımlayabilirsiniz.  
  
 Yazıyorsanız bir [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] uzantısı, var olan metin dönüştürme hizmeti, kendi ana bilgisayar yazmak yerine kullanmayı düşünün. Daha fazla bilgi için bkz: [bir VS uzantısında metin dönüştürmeyi çağırma](../modeling/invoking-text-transformation-in-a-vs-extension.md).  
  
## <a name="reference"></a>Başvuru  
 [T4 Metin Şablonu Yazma](../modeling/writing-a-t4-text-template.md)  
  
 Metin şablonu yönergeleri ve denetim blokları sözdizimi sağlar.