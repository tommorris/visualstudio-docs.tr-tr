---
title: "Özel T4 metin şablonu yönerge işlemcileri oluşturma | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: text templates, custom directive processors
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload: multiple
ms.openlocfilehash: fe637b6ae730cf70113abda14fad794c30868242
ms.sourcegitcommit: f89ed5fc2e5078213e30a6ade4604e34df48181f
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/13/2018
---
# <a name="creating-custom-t4-text-template-directive-processors"></a>Özel T4 Metin Şablonu Yönerge İşlemcileri Oluşturma
*Metin şablonu dönüştürme süreci* geçen bir *metin şablonu* dosyası olarak giriş ve çıkış olarak bir metin dosyası oluşturur. *Metin şablonu dönüştürme altyapısı* işlemi ve altyapı metin şablonu dönüştürme ana bilgisayar ve bir veya daha fazla metin şablonu ile etkileşim denetimleri *yönerge işlemcileri* tamamlamak için işlem. Daha fazla bilgi için bkz: [metin şablonu dönüştürme süreci](../modeling/the-text-template-transformation-process.md).  
  
 Özel yönerge işlemcisi oluşturmak için herhangi birinden devralan bir sınıf oluşturun. <xref:Microsoft.VisualStudio.TextTemplating.DirectiveProcessor> veya <xref:Microsoft.VisualStudio.TextTemplating.RequiresProvidesDirectiveProcessor>.  
  
 Bu iki arasındaki fark <xref:Microsoft.VisualStudio.TextTemplating.DirectiveProcessor> kullanıcıdan parametreleri almak ve şablon çıktı dosyası üreten kodunu oluşturmak için gerekli olan minimum arabirimini uygular. <xref:Microsoft.VisualStudio.TextTemplating.RequiresProvidesDirectiveProcessor>uygulayan tasarım deseni gerektirir/sağlar. <xref:Microsoft.VisualStudio.TextTemplating.RequiresProvidesDirectiveProcessor>iki özel parametre işleme `requires` ve `provides`.  Örneğin, özel yönerge işlemcisi, açık şekilde kullanıcıdan dosya adını kabul etmek ve dosyayı okuma ve ardından dosyanın metni adlı bir değişkende saklayın `fileText`. Öğesinin bir alt <xref:Microsoft.VisualStudio.TextTemplating.RequiresProvidesDirectiveProcessor> sınıfı alabilir bir dosya adı kullanıcıdan değeri olarak `requires` parametresi ve değeri olarak metin depolanacağı değişkeninin adı `provides` parametresi. Bu işlemci açın ve dosyayı okuma ve ardından dosyanın metni belirtilen değişkende saklayın.  
  
 Bir metin şablonunda özel yönerge işlemcisi çağırmadan önce [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)], kaydetmeniz gerekir.  
  
 Kayıt defteri anahtarı ekleme hakkında daha fazla bilgi için bkz: [özel yönerge işlemcisi dağıtma](../modeling/deploying-a-custom-directive-processor.md).  
  
## <a name="custom-directives"></a>Özel yönergeleri  
 Özel bir yönerge şöyle görünür:  
  
 `<#@ MyDirective Processor="MyDirectiveProcessor" parameter1="value1" ... #>`  
  
 Dış veri veya kaynakları metin şablonundan erişmek istediğinizde özel yönerge işlemcisi kullanabilirsiniz.  
  
 Yönerge işlemcileri için yeniden faktörü kodu için bir yol sağlamak için farklı bir metin şablonları tek bir yönerge işlemcisi sağlayan, işlevselliği paylaşabilirsiniz. Yerleşik `include` yönergesi benzer, çünkü kodu faktörü ve farklı bir metin şablonları arasında paylaşmak için kullanabilirsiniz. Fark herhangi bir işlevsellik olan, `include` yönergesi sağlar sabittir ve parametreleri kabul etmez. Metin şablonu için ortak işlevsellik sağlar ve izin parametreleri geçirmek şablon istiyorsanız, özel yönerge işlemcisi oluşturmanız gerekir.  
  
 Özel yönerge işlemcileri bazı örnekleri olabilir:  
  
-   Bir kullanıcı adı ve parola parametreleri olarak kabul eden bir veritabanından veri döndürmek için yönerge işlemcisi.  
  
-   Bir yönerge işlemcisi açmak ve bir dosya okuma için parametre olarak dosyanın adını kabul eder.  
  
### <a name="principal-parts-of-a-custom-directive-processor"></a>Özel yönerge işlemcisi asıl bölümleri  
 Bir yönerge işlemcisi geliştirmek için herhangi birinden devralınan bir sınıf oluşturun <xref:Microsoft.VisualStudio.TextTemplating.DirectiveProcessor> veya <xref:Microsoft.VisualStudio.TextTemplating.RequiresProvidesDirectiveProcessor>.  
  
 En önemli `DirectiveProcessor` uygulamanız gereken yöntemler aşağıdaki gibidir.  
  
-   `bool IsDirectiveSupported(string directiveName)`-Dönüş `true` yönerge işlemcisi adlandırılmış yönergesiyle başa durumunda.  
  
-   `void ProcessDirective (string directiveName, IDictionary<string, string> arguments)`-Şablon motoru şablon yönergesinde her örneği için bu yöntemi çağırır. İşlemci sonuçları kaydetmeniz gerekir.  
  
 ProcessDirective() tüm çağrıları sonra şablon altyapısı bu yöntemleri çağırır:  
  
-   `string[] GetReferencesForProcessingRun()`-Şablon kodu gerektirir derlemeleri adlarını döndürür.  
  
-   `string[] GetImportsForProcessingRun()`-Kullanılabilir ad alanlarının şablon kodunda döndür.  
  
-   `string GetClassCodeForProcessingRun()`-Yöntemler, özellikler ve şablon kodu kullanabileceğiniz diğer bildirimleri kodunu döndürür. Bunu yapmanın en kolay yolu C# veya Visual Basic kodu içeren bir dize oluşturmaktır. Yönerge işlemcisi herhangi bir CLR dil kullanan bir şablondan çağrılan yeteneğine yapmak için deyimleri CodeDom ağaç olarak oluşturun ve şablon tarafından kullanılan dil ağacında seri hale getirme sonucunu döndürür.  
  
-   Daha fazla bilgi için bkz: [izlenecek yol: özel yönerge işlemcisi oluşturma](../modeling/walkthrough-creating-a-custom-directive-processor.md).  
  
## <a name="in-this-section"></a>Bu Bölümde  
 [Özel Yönerge İşlemcisi Dağıtma](../modeling/deploying-a-custom-directive-processor.md)  
 Özel yönerge işlemcisi kaydedileceği açıklanmaktadır.  
  
 [İzlenecek yol: Özel Yönerge İşlemcisi Oluşturma](../modeling/walkthrough-creating-a-custom-directive-processor.md)  
 Özel yönerge işlemcisi oluşturma, kaydetme ve yönerge işlemcisi test etmek ve çıktı dosyası HTML olarak biçimlendirmek açıklar.