---
title: "T4 metin dönüştürmeyi özelleştirme | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- text templates, API
- text templates, custom hosts
ms.assetid: 62cd9a3c-a6e1-4b29-93f5-f2a0cf47dc92
caps.latest.revision: "28"
author: alancameronwills
ms.author: awills
manager: douge
ms.workload: multiple
ms.openlocfilehash: 98d7efc90a07de02f255afe1a75d10fef749e88a
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/22/2017
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