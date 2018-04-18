---
title: Bir özel konak kullanarak metin şablonlarını işleme | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- text templates, in application or VS extension
- text templates, custom directive hosts
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.technology: vs-ide-modeling
ms.openlocfilehash: aac285701dae7c17d9398de7de0f778530a0e5ea
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/16/2018
---
# <a name="processing-text-templates-by-using-a-custom-host"></a>Bir Özel Konak kullanarak Metin Şablonlarını İşleme
*Metin şablonu dönüştürme* işlem alır bir *metin şablonu* dosyası olarak giriş ve çıkış olarak bir metin dosyası oluşturur. Metin dönüştürme altyapısı çağırabilirsiniz bir [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] uzantısı, veya bir makinede çalışan bir tek başına uygulamasından [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] yüklenir. Ancak, sağlamanız gereken bir *metin şablon konak*. Bu sınıf, derlemeler ve ekleme dosyaları gibi kaynakları bularak ve çıktı ve hata iletilerini işleme alarak şablonu ortama bağlar.  
  
> [!TIP]
>  Bir paket veya içinde çalışacak uzantısı yazma, [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)], kendi ana bilgisayar yazmak yerine metin şablonu oluşturma hizmeti kullanmayı düşünün. Daha fazla bilgi için bkz: [bir VS uzantısında metin dönüştürmeyi çağırma](../modeling/invoking-text-transformation-in-a-vs-extension.md).  
  
> [!NOTE]
>  Metin şablonu dönüştürmelerinin sunucu uygulamalarında kullanılması önerilmez. Metin şablonu dönüştürmelerinin tek bir iş parçacığı dışında kullanılması önerilmez. Bunun nedeni, metin şablonu oluşturma motorunun şablonları çevirmek, derlemek ve yürütmek için tek bir AppDomain öğesini yeniden kullanmasıdır. Çevrilen kod, iş parçacığı açısından güvenli olmak üzere tasarlanmamıştır. Altyapı olduğu gibi dosyalar seri olarak, işlemek için tasarlanmış bir [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] proje tasarım zamanında.  
>   
>  Çalışma zamanı uygulamaları için önceden işlenmiş metin şablonları kullanarak göz önünde bulundurun: bkz [T4 metin şablonları ile çalışma zamanı metin oluşturma](../modeling/run-time-text-generation-with-t4-text-templates.md).  
  
 Uygulamanız, derleme zamanında sabitlenmiş bir grup şablon kullanıyorsa, Önceden İşlenmiş Metin Şablonlarının kullanılması daha kolaydır. Uygulamanızı bir makinede çalışır, bu yaklaşımı de kullanabilirsiniz [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] yüklü değil. Daha fazla bilgi için bkz: [T4 metin şablonları ile çalışma zamanı metin oluşturma](../modeling/run-time-text-generation-with-t4-text-templates.md).  
  
## <a name="executing-a-text-template-in-your-application"></a>Uygulamanızda Metin Şablonu Yürütme  
 Metin şablonu yürütmek için ProcessTemplate yöntemini çağırın. <xref:Microsoft.VisualStudio.TextTemplating.Engine?displayProperty=fullName>:  
  
```  
using Microsoft.VisualStudio.TextTemplating;  
...  
Engine engine = new Engine();  
string output = engine.ProcessTemplate(templateString, host);  
```  
  
 Uygulamanızın şablonu bularak sağlaması ve çıktı ile işlem yapması gerekir.   
  
 İçinde `host` parametresi uygulayan bir sınıf sağlamalıdır <xref:Microsoft.VisualStudio.TextTemplating.ITextTemplatingEngineHost>. Bu, Motor tarafından geri çağrılır.  
  
 Ana bilgisayar hataları günlüğe kaydedebilmeli, derleme ve ekleme dosyalarına yapılan başvuruları çözümleyebilmeli, şablonun yürütülebileceği bir Uygulama Etki Alanı sağlayabilmeli ve her yönerge için uygun işlemciyi çağırabilmelidir.  
  
 <xref:Microsoft.VisualStudio.TextTemplating.Engine?displayProperty=fullName> tanımlanan **Microsoft.VisualStudio.TextTemplating.\*. 0. dll**, ve <xref:Microsoft.VisualStudio.TextTemplating.ITextTemplatingEngineHost> tanımlanan **Microsoft.VisualStudio.TextTemplating.Interfaces.\*. 0. dll**.  
  
## <a name="in-this-section"></a>Bu Bölümde  
 [İzlenecek yol: Özel Metin Şablonu Konağı Oluşturma](../modeling/walkthrough-creating-a-custom-text-template-host.md)  
 Metin şablonu işlevselliği kullanılabilir dışına yapar özel metin şablonu konağı oluşturma gösterilmektedir [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)].  
  
## <a name="reference"></a>Başvuru  
 <xref:Microsoft.VisualStudio.TextTemplating.ITextTemplatingEngineHost>  
  
## <a name="related-sections"></a>İlgili Bölümler  
 [Metin Şablonu Dönüştürme Süreci](../modeling/the-text-template-transformation-process.md)  
 Metin dönüştürmenin nasıl çalıştığını ve hangi kısımları özelleştirebileceğinizi açıklar.  
  
 [Özel T4 Metin Şablonu Yönerge İşlemcileri Oluşturma](../modeling/creating-custom-t4-text-template-directive-processors.md)  
 Metin şablonu yönerge işlemcilerine genel bakış sağlar.