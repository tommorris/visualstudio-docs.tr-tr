---
title: T4 Metin Dönüştürmeyi Özelleştirme
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- text templates, API
- text templates, custom hosts
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.prod: visual-studio-dev15
ms.technology: vs-ide-modeling
ms.openlocfilehash: b3960d0e511ab42de2bd81765fb395d2e013a493
ms.sourcegitcommit: e13e61ddea6032a8282abe16131d9e136a927984
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/26/2018
---
# <a name="customizing-t4-text-transformation"></a>T4 Metin Dönüştürmeyi Özelleştirme

Metin şablonları, bir özellik olan [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] program kodunu veya diğer metin dosyaları dönüştürme işlemiyle oluşturmak izin verir. Kullanarak [!INCLUDE[vssdk_current_short](../modeling/includes/vssdk_current_short_md.md)], metin şablonu yönerge işlemcisi veya metin şablonu konağı özelleştirerek varsayılan şablonu dönüştürme süreci genişletebilirsiniz.

## <a name="in-this-section"></a>Bu Bölümde
 [Metin şablonu dönüştürme süreci](../modeling/the-text-template-transformation-process.md) metin dönüştürmeyi nasıl çalıştığını, açıklar ve şablonu ana bilgisayarı ve yönerge işlemcileri rolü açıklanmıştır.

 [Özel T4 metin şablonu yönerge işlemcileri oluşturma](../modeling/creating-custom-t4-text-template-directive-processors.md) yönerge işlemcisi yönergeleri için şablonunda gibi ilgilenir `<#@template#>.` şablon derleme sırasında çalışır ve derlemeler ve diğer kaynakları yükleyebilirsiniz. Ayrıca, çalışma zamanında kaynakları yükleyecek kod de ekleyebilirsiniz. Kendi yönerge işlemcisi tanımlayarak, şablonlarınızı karmaşıklığını azaltabilir.

 [Bir VS uzantısında metin dönüştürmeyi çağırma](../modeling/invoking-text-transformation-in-a-vs-extension.md) yazıyorsanız bir [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] uzantısı menüsü komut veya olay işleyicisi gibi uzantınızı metin şablonu oluşturma hizmeti herhangi bir metin şablonu dönüştürme için kullanabilirsiniz. Oturum nesnesi kullanarak şablona parametre veri geçirmek ve kullanarak şablonu içindeki değerleri alma `<#@parameter#>` yönergesi.

 [Bir özel konak kullanarak metin şablonlarını işleme](../modeling/processing-text-templates-by-using-a-custom-host.md) metin şablonu kodu yürütüldüğünde, ana dış dosyalar ve uygulama durumunu erişim sağlar. Örneğin, metin dönüşümleri çalışan konak [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] Çözüm Gezgini erişim sağlayabilir. Ayrıca hataları hata ileti penceresinde görüntüler. Farklı bir bağlamda metin dönüşümleri çalıştırmak istiyorsanız, bu bağlamda kullanılabilir hizmetlerine erişim sağlayan, kendi ana bilgisayar tanımlayabilirsiniz.

 Yazıyorsanız bir [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] uzantısı, var olan metin dönüştürme hizmeti, kendi ana bilgisayar yazmak yerine kullanmayı düşünün. Daha fazla bilgi için bkz: [bir VS uzantısında metin dönüştürmeyi çağırma](../modeling/invoking-text-transformation-in-a-vs-extension.md).

## <a name="reference"></a>Başvuru

- [T4 metin şablonu yazma](../modeling/writing-a-t4-text-template.md) metin şablonu yönergeleri ve denetim blokları sözdizimi sağlar.