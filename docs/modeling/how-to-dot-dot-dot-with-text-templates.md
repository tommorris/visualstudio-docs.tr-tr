---
title: Nasıl yapılır... metin şablonları ile | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.topic: article
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload:
- multiple
ms.technology: vs-ide-modeling
ms.openlocfilehash: 47824561813dfc422dfb19460f1c90f7ed78d1ad
ms.sourcegitcommit: 3b692c9bf332b7b9150901e16daf99a64b599fee
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/10/2018
---
# <a name="how-to--with-text-templates"></a>Nasıl yapılır ... Metin Şablonları ile
Metin şablonlarında [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] herhangi bir türde metin oluşturma kullanışlı bir yöntem sunar. Metin şablonları, uygulamanızı bir parçası olarak çalışma zamanında ve bazı proje kodunu oluşturmak için tasarım zamanında metin oluşturmak için kullanabilirsiniz. Bu konu en sık özetler "Nasıl yedeklerim...?" sorular Sorular.  
  
 Bu konuda, madde işaretleri tarafından öncesinde birden çok yanıtlar alternatif önerilerdir.  
  
 Metin şablonları genel bir giriş için okuma [kod oluşturma ve T4 metin şablonları](../modeling/code-generation-and-t4-text-templates.md).  
  
## <a name="how-to-"></a>Nasıl Yapılır...  
  
### <a name="generate-part-of-my-application-code"></a>Uygulama kodumda parçası oluştur  
 Bir yapılandırmasına sahip veya *modeli* bir dosya veya bir veritabanı. Bir veya daha fazla bölümlerini kodumu bu modeline bağlı olarak değişir.  
  
-   Kod dosyalarınızın bazılarına metin şablonlardan oluşturun. Daha fazla bilgi için bkz: [T4 metin şablonları kullanarak tasarım zamanı kodu oluşturma](../modeling/design-time-code-generation-by-using-t4-text-templates.md) ve [şablon yazmaya başlamak için en iyi yolu nedir?](#starting).  
  
### <a name="generate-files-at-run-time-passing-data-into-the-template"></a>Şablonuna veri geçirme çalışma zamanında dosyalar oluşturma  
 Çalışma zamanında Uygulamam standart metin ve verileri bir karışımını içeren raporlar gibi metin dosyaları oluşturur. Yüzlerce yazılmasını engellemek istediğiniz `write` deyimleri.  
  
-   Bir çalışma zamanı metin şablonu projenize ekleyin. Bu şablon örneğini oluşturma ve metin oluşturmak için kullanmak, kodunuzda bir sınıf oluşturur. Oluşturucu parametrelerinde için veri geçirebilirsiniz. Daha fazla bilgi için bkz: [T4 metin şablonları ile çalışma zamanı metin oluşturma](../modeling/run-time-text-generation-with-t4-text-templates.md).  
  
-   Yalnızca çalışma zamanında kullanılabilir şablonlardan oluşturmak istiyorsanız, standart metin şablonları kullanabilirsiniz. Yazıyorsanız bir [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] uzantısı, metin şablonu oluşturma hizmeti çağırabilirsiniz. Daha fazla bilgi için bkz: [bir VS uzantısında metin dönüştürmeyi çağırma](../modeling/invoking-text-transformation-in-a-vs-extension.md). Diğer bağlamlarda metin şablon motoru kullanabilirsiniz. Daha fazla bilgi için bkz. <xref:Microsoft.VisualStudio.TextTemplating.Engine?displayProperty=fullName>.  
  
     Kullanım \<#@parameter#> Bu şablonlarını parametreleri geçirmek için yönergesi. Daha fazla bilgi için bkz: [T4 parametre yönergesi](../modeling/t4-parameter-directive.md).  
  
### <a name="read-another-project-file-from-a-template"></a>Bir şablondan başka bir proje dosyası okuma  
 Bir dosyayı aynı okumaya [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] proje şablonu olarak:  
  
-   INSERT `hostSpecific="true"` içine `<#@template#>` yönergesi.  
  
     Kodunuzda kullanmak `this.Host.ResolvePath(filename)` dosyasının tam yolunu elde edilir.  
  
### <a name="invoke-methods-from-a-template"></a>Bir şablondan yöntemleri çağırma  
 Yöntemleri, örneğin, standart zaten varsa [!INCLUDE[dnprdnshort](../code-quality/includes/dnprdnshort_md.md)] sınıfları:  
  
-   Kullanmak \<#@assembly#> derlemeyi yüklemek ve kullanmak için yönergesi \<#@import#> ad alanı bağlam ayarlamak için. Daha fazla bilgi için bkz: [T4 içe aktarma yönergesi](../modeling/t4-import-directive.md).  
  
     Sık derleme aynı kümesini kullanıyorsanız ve yönergeleri almak, bir yönerge işlemcisi yazma göz önünde bulundurun. Her bir şablon derlemelerin ve model dosyalarının yükleme ve ad alanı bağlamını ayarlayın yönerge işlemcisi çağırabilirsiniz. Daha fazla bilgi için bkz: [özel T4 metin şablonu yönerge işlemciler oluşturma](../modeling/creating-custom-t4-text-template-directive-processors.md).  
  
 Yöntemleri kendiniz yazıyorsanız:  
  
-   Bir çalışma zamanı metin şablonu yazıyorsanız, çalışma zamanı metin şablonu aynı ada sahip bir parçalı sınıf tanımını yazın. Ek yöntemleri bu sınıfına ekleyin.  
  
-   Bir sınıf özelliği denetim bloğu yazma `<#+ ... #>` içinde hangi yöntemler, özellikler ve özel sınıflar bildirebilirsiniz. Metin şablonu derlendiğinde bir sınıfa dönüştürülür. Standart denetim blokları `<#...#>` metin tek bir yöntem dönüştürülen ve sınıf özelliği blokları ayrı üye olarak eklenir. Daha fazla bilgi için bkz: [metin şablonu denetim blokları](../modeling/text-template-control-blocks.md).  
  
     Sınıf özellikleri de katıştırılmış metin blokları içerecek şekilde tanımlanan yöntemler.  
  
     Sınıf özellikleri yapabilecekleriniz ayrı bir dosya yerleştirmeyi düşünün `<#@include#>` bir veya daha fazla şablon dosyalarına.  
  
-   Ayrı bir derlemede (sınıf kitaplığı) yöntemler yazmak ve, şablondan çağırın. Kullanım `<#@assembly#>` derlemeyi yüklemek için yönergesi ve `<#@import#>` ad alanı bağlam ayarlamak için. Onu ayıklarken derleme yeniden için durdurma ve yeniden başlatma gerekebilir emin Not [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)]. Daha fazla bilgi için bkz: [T4 metin şablonu yönergeleri](../modeling/t4-text-template-directives.md).  
  
### <a name="generate-many-files-from-one-model-schema"></a>Bir model şemadan çok sayıda dosya oluştur  
 Dosyaları çoğunlukla aynı XML veya veritabanı şeması modellerinden oluşturursanız:  
  
-   Bir yönerge işlemcisi yazma göz önünde bulundurun. Bu, birden çok derleme deyimleri değiştirin ve tek bir özel yönerge her şablonla deyimlerinde içeri aktarmanızı sağlar. Yönerge işlemcisi ayrıca yüklenemedi ve model dosyası ayrıştırılamadı. Daha fazla bilgi için bkz: [özel T4 metin şablonu yönerge işlemciler oluşturma](../modeling/creating-custom-t4-text-template-directive-processors.md).  
  
### <a name="generate-files-from-a-complex-model"></a>Karmaşık bir modelden dosyaları oluştur  
  
-   Bir etki alanına özgü dil modeli temsil etmek için (DSL) oluşturmayı düşünün. Türleri ve modelinizdeki öğelerinin adlarını yansıtmak özellikleri kullandığından bu çok şablonları yazmak kolaylaştırır. Dosya ayrıştırma veya XML düğümlerini gidin gerekmez. Örneğin:  
  
     `foreach (Book book in this.Library) { ... }`  
  
     Daha fazla bilgi için bkz: [etki alanına özgü dil ile çalışmaya başlama](../modeling/getting-started-with-domain-specific-languages.md) ve [bir etki alanına özgü dil oluşturma koddan](../modeling/generating-code-from-a-domain-specific-language.md).  
  
### <a name="get-data-from-includevsprvscode-qualityincludesvsprvsmdmd"></a>Veri alma [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)]  
 Sağlanan hizmetleri kullanmaya [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)], kümesi tarafından `hostSpecific` özniteliği ve yük `EnvDTE` derleme. Örneğin:  
  
```csharp  
<#@ template hostspecific="true" language="C#" #>  
<#@ output extension=".txt" #>  
<#@ assembly name="EnvDTE" #>  
<#  
  IServiceProvider serviceProvider = (IServiceProvider)this.Host;  
  EnvDTE.DTE dte = (EnvDTE.DTE) serviceProvider.GetService(typeof(EnvDTE.DTE));  
#>  
  
Number of projects in this VS solution:  <#= dte.Solution.Projects.Count #>  
  
```  
  
### <a name="execute-text-templates-in-the-build-process"></a>Metin şablonları yapı işleminde yürütme  
  
-   Daha fazla bilgi için bkz: [derleme sürecinde kod oluşturma](../modeling/code-generation-in-a-build-process.md).  
  
## <a name="more-general-questions"></a>Daha fazla genel sorular  
  
###  <a name="starting"></a> Metin şablonu yazmaya başlamak için en iyi yolu nedir?  
  
1.  Oluşturulan dosya belirli bir örneği yazma.  
  
2.  Ekleyerek bir metin şablonuna kapatma `<#@template #>` yönerge ve yönergeleri ve kod girdi dosyası veya modeli yüklemek için gerekli.  
  
3.  Aşamalı olarak dosyanın parçalarını ifade ve kod blokları adıyla değiştirin.  
  
### <a name="what-is-a-model"></a>"Modeli" nedir?  
  
-   Şablon tarafından okuma giriş. Bir dosya veya bir veritabanında olabilir. XML, veya bir Visio çizim veya bir etki alanına özgü dil (DSL) ya da bir UML model olabilir veya düz metin olabilir. Çeşitli dosyalar arasında yayılır. Genellikle bir model birden fazla şablon okur.  
  
     Olduğu çıkarımında bulunulur "modelinin" terimi iş oluşturulan program kodunu veya diğer dosyalar daha fazla doğrudan bazı yönlerinin temsil eder. Örneğin, oluşturulan yazılımınızı Denetle iletişim ağı planını temsil edebilir.  
  
### <a name="what-is-the-benefit-of-using-text-templates"></a>Metin şablonları kullanmanın avantajı nedir?  
 Genellikle, birden çok kod veya diğer dosyaları bir modelden oluşturun. Model gereksinimleri oluşturulan kodu daha doğrudan temsil eder. Uygulama ayrıntılarını atlar ve kod yerine gereksinimleri açısından yazılır. Bunlar genellikle yaptığınız gibi - gereksinimler - değiştiğinde model daha kolay ve program kodunun farklı bölümlerinin daha güvenli bir şekilde güncelleştirebilirsiniz.  
  
 Kod oluşturma bu nedenle bir değerli Çevik Geliştirme yöntemleri perspektifinden aracıdır.  
  
### <a name="what-best-practices-are-there-for-text-templates"></a>"En iyi yöntemler" var. metin şablonları nelerdir?  
  
-   Daha fazla bilgi için bkz: [yazma T4 metin şablonları için yönergeler](../modeling/guidelines-for-writing-t4-text-templates.md).  
  
### <a name="what-is-t4"></a>"T4" nedir?  
  
-   Başka bir ad [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] metin şablonu yetenekleri burada açıklanmıştır. Yayımlanmadı, bir önceki sürüme "Metin şablonu dönüştürme" kısaltması oluştu.
