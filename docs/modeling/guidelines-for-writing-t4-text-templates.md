---
title: T4 metin şablonları yazma yönergeleri | Microsoft Docs
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
ms.openlocfilehash: accf32ad313cbbfe11c2e85fdfe3101ab428c4a4
ms.sourcegitcommit: 3b692c9bf332b7b9150901e16daf99a64b599fee
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/10/2018
---
# <a name="guidelines-for-writing-t4-text-templates"></a>T4 Metin Şablonları Yazma Yönergeleri
Şu genel yönergeleri program kodunun veya diğer uygulama kaynakları oluşturma durumunda yararlı olabilir [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)]. Kuralları sabit değil.  
  
## <a name="guidelines-for-design-time-t4-templates"></a>Tasarım zamanı T4 şablonları için yönergeler  
 Tasarım zamanı T4 şablonlarıdır kodda oluşturmak şablonlar, [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] proje tasarım zamanında. Daha fazla bilgi için bkz: [T4 metin şablonları kullanarak tasarım zamanı kodu oluşturma](../modeling/design-time-code-generation-by-using-t4-text-templates.md).  
  
 Uygulama değişken yönlerini oluşturur.  
 Kod oluşturma için bu amaçla proje sırasında değiştirilebilir veya uygulamanın farklı sürümleri arasında değişir uygulamanın en yararlı olur. Ne oluşturulacak olan daha kolay belirleyebilmesi Bu değişken yönlerini daha fazla sabit yönlerini ayırın. Örneğin, uygulamanız bir Web sitesi sağlıyorsa, başka bir sayfadan Gezinti yolları tanımlar mantığı işlevlerden hizmet veren standart sayfa ayırın.  
  
 Bir veya daha fazla kaynak modelleri değişken yönden kodlayın.  
 Bir dosya veya değişken oluşturulması gereken kod parçalarını belirli değerleri almak için her bir şablon okur veritabanını modelidir. Modeller, veritabanları, XML dosyalarını tasarım, diyagramları veya etki alanına özgü dil olabilir. Genellikle, bir model içinde çok sayıda dosya oluşturmak için kullanılan bir [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] projesi. Her dosya ayrı bir şablondan oluşturuldu.  
  
 Bir projede birden fazla modelini kullanabilirsiniz. Örneğin, Web sayfaları ve sayfalar düzen için ayrı bir model arasında gezinme için bir model tanımlayabilirsiniz.  
  
 Model, kullanıcıların gereksinimlerini ve sözlük, uygulamanızın üzerinde odaklanın.  
 Örneğin, bir Web sitesi uygulamasında Web sayfalarını ve köprüleri başvurmak için model beklenir.  
  
 İdeal olarak, bir form modelini gösteren bilgi türünü uygun sunu seçin. Örneğin, bir Web sitesi aracılığıyla gezinti yolları modelinin kutuları ve okları diyagramı olabilir.  
  
 Oluşturulan kodun test edin.  
 Kullanıcıların gerektiği ortaya çıkan kodu çalıştığını doğrulamak için el ile veya otomatikleştirilmiş testleri kullanın. Kod oluşturulduğu modelden testleri oluşturma kaçının.  
  
 Bazı durumlarda, model üzerinde doğrudan genel testleri gerçekleştirilebilir. Örneğin, Web sitesindeki her sayfada gezinme herhangi diğer tarafından erişilebildiğini sağlar bir test yazabilirsiniz.  
  
 İçin özel kod izin ver: Kısmi sınıflar oluşturur.  
 El ile ayrıca için oluşturulan kodu yazdığınız kodu için izin verin. Ortaya çıkabilecek tüm olası farklılıklara hesap bir kod oluşturma düzeni olağandışıdır. Bu nedenle, ekleme veya bazı oluşturulan kod geçersiz kılmak beklemeniz gerekir. Oluşturulan malzemenin olduğu bir .NET dilinde gibi [!INCLUDE[csprcs](../data-tools/includes/csprcs_md.md)] veya [!INCLUDE[vbprvb](../code-quality/includes/vbprvb_md.md)], iki stratejileri özellikle kullanışlıdır:  
  
-   Oluşturulan sınıflar kısmi olmalıdır. Bu içerik için oluşturulan kodu eklemenize olanak sağlar.  
  
-   Bir diğer devralma çiftler halinde sınıfları yeniden oluşturulması gerekir. Temel sınıfın tüm oluşturulan yöntemleri ve özellikleri içermelidir ve yalnızca oluşturucular türetilmiş bir sınıf içermelidir. Bu, oluşturulan yöntemlerden herhangi birini geçersiz kılmak, elle yazılmış kodunuzu sağlar.  
  
 XML gibi diğer oluşturulan dillerde de kullanmak `<#@include#>` elle yazılmış ve oluşturulan içeriği basit birleşimlerini yapmak için yönergesi. Daha karmaşık durumlarda, elle yazılmış dosyalarla birlikte oluşturulan dosya birleştiren bir işlem sonrası adımı yazmak zorunda kalabilirsiniz.  
  
 Dosyaları Ekle veya çalışma zamanı şablonları ortak malzeme taşıyın  
 Metin ve kod birden fazla şablon içinde benzer bloklarını yinelenen önlemek için `<#@ include #>` yönergesi. Daha fazla bilgi için bkz: [T4 dahil yönergesi](../modeling/t4-include-directive.md).  
  
 Ayrıca ayrı projesindeki çalışma zamanı metin şablonları oluşturmak ve ardından bunları tasarım zamanı şablondan çağırın. Bunu yapmak için kullanın `<#@ assembly #>` ayrı projeye erişmeye yönergesi. Örnekler için bkz: ["Devralma metin şablonları" Gareth CAN günlüğündeki](http://go.microsoft.com/fwlink/?LinkId=208373).  
  
 Ayrı bir derleme büyük kod bloklarını taşımayı düşünün.  
 Büyük kod bloğu ve sınıf özelliği bloğu varsa, bu kod bazıları ayrı bir projede derleme yöntemlerde taşımak yararlı olabilir. Kullanabileceğiniz `<#@ assembly #>` şablon kodda erişmek için yönergesi. Daha fazla bilgi için bkz: [T4 derleme yönergesi](../modeling/t4-assembly-directive.md).  
  
 Şablon devrettiği bir Özet sınıfta yöntemleri koyabilirsiniz. Soyut sınıf öğesinden devralmalıdır <xref:Microsoft.VisualStudio.TextTemplating.TextTransformation?displayProperty=fullName>. Daha fazla bilgi için bkz: [T4 şablon yönergesi](../modeling/t4-template-directive.md).  
  
 Kod, yapılandırma dosyaları oluşturma  
 Bir değişken uygulaması yazma bir yöntemi, bir yapılandırma dosyası kabul genel program kod yazmaktır. Bu şekilde yazılan uygulamanın çok esnektir ve iş gereksinimleri değiştiğinde uygulama derlenmeden yapılandırdı. Ancak, bu yaklaşımın bir dezavantajı uygulama daha belirli bir uygulama'den daha az iyi gerçekleştirecek olur. Ayrıca, kısmen her zaman en genel türleri ile mücadele etmek içerdiğinden, program kodunun okuyun ve bakımı daha zor olacaktır.  
  
 Buna karşın, değişken bölümleri derleme önce oluşturulan bir uygulamayı kesin türü belirtilmiş. Bu yazılım, çok daha kolay ve daha güvenilir elle yazılmış kod yazmak ve oluşturulan ile tümleştirmek için bölümlerini hale getirir.  
  
 Kod oluşturma tüm avantajlarını elde etmek için yapılandırma dosyalarını yerine program kodu oluşturmak deneyin.  
  
 Oluşturulan kod klasörünü kullanın  
 Şablonlar ve oluşturulan dosyaları adlı bir proje klasöre yerleştirmek **oluşturulan kod**, bunu yapmak için bu doğrudan düzenlenmelidir dosyaların olmadığını temizleyin. Oluşturulan sınıf eklemek veya geçersiz kılmak için özel kod oluşturursanız, bu sınıfların adlı bir klasöre yerleştirmek **özel kod**. Tipik bir proje yapısı şuna benzer:  
  
```  
MyProject  
   Custom Code  
      Class1.cs  
      Class2.cs  
   Generated Code  
      Class1.tt  
          Class1.cs  
      Class2.tt  
          Class2.cs  
   AnotherClass.cs  
  
```  
  
## <a name="guidelines-for-run-time-preprocessed-t4-templates"></a>Çalışma zamanı (önceden işlenmiş) T4 şablonları için yönergeler  
 Devralınan şablonlarına genel malzeme taşıma  
 Devralma yöntemleri ve metin blokları T4 metin şablonları arasında paylaşmak için kullanabilirsiniz. Daha fazla bilgi için bkz: [T4 şablon yönergesi](../modeling/t4-template-directive.md).  
  
 Aynı zamanda çalışma zamanı şablonları dosyaları içerir.  
  
 Kod büyük gövdeleri kısmi sınıfına taşıyın.  
 Her bir çalışma zamanı şablon şablon olarak aynı ada sahip bir parçalı sınıf tanımı oluşturur. Aynı sınıfın başka bir kısmi tanımını içeren bir kod dosyası yazabilirsiniz. Bu şekilde sınıfı yöntemleri, alanlar ve oluşturucular ekleyebilirsiniz. Bu üyeler şablondaki kod taşlarından çağrılabilir.  
  
 Bunu yapmanın avantajı IntelliSense kullanılabilir olduğu için kod yazmak daha kolay olmasıdır. Ayrıca, sunu ve temel mantığını arasında daha iyi bir ayrım elde edebilirsiniz.  
  
 Örneğin, **MyReportText.tt**:  
  
 `The total is: <#= ComputeTotal() #>`  
  
 In **MyReportText-Methods.cs**:  
  
 `private string ComputeTotal() { ... }`  
  
 İçin özel kod izin ver: uzantı noktaları sağlayın  
 Sanal yöntemleri oluşturma göz önünde bulundurun \<#+ sınıf özelliği engeller #>. Bu değişiklik gerektirmeden çoğu bağlamlarda kullanılacak tek bir şablon sağlar. Şablonu değiştirmek yerine, en düşük ek mantık sağlayan türetilmiş bir sınıf oluşturabilirsiniz. Türetilmiş sınıf, ya da normal kodu veya bir çalışma zamanı şablonu olabilir.  
  
 Örneğin, MyStandardRunTimeTemplate.tt içinde:  
  
```  
This page is copyright <#= CompanyName() #>.  
<#+ protected virtual string CompanyName() { return ""; } #>  
```  
  
 Bir uygulama kodunda:  
  
```  
class FabrikamTemplate : MyStandardRunTimeTemplate  
{  
  protected override string CompanyName() { return "Fabrikam"; }  
}  
...  
  string PageToDisplay = new FabrikamTemplate().TextTransform();  
  
```  
  
## <a name="guidelines-for-all-t4-templates"></a>Tüm T4 şablonları için yönergeler  
 Veri toplama metin kuşaktan ayırın  
 Hesaplama ve metin blokları karıştırma kaçınmaya çalışın. Her metin şablonunda ilk kullanmak \<# kodu engelleyecek #> değişkenleri ayarlamak ve karmaşık hesaplamalar için. Şablon veya ilk sonuna kadar ilk metin bloğunun \<#+ sınıfı özelliği engelleme #> uzun ifadeleri önlemek ve metin blokları içermiyorsa döngüler ve koşulları kaçının. Bu uygulama şablonu okuma ve bakımını kolaylaştırır.  
  
 Kullanmayan `.tt` için dosyaları Ekle  
 Gibi farklı dosya adı uzantısı kullanın `.ttinclude` için dosyaları Ekle. Kullanım `.tt` olmasını istediğiniz dosyaları olarak çalıştırma ya da Tasarım zamanı metin şablonlarını işleme için yalnızca. Bazı durumlarda, [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] tanıdığı `.tt` dosyaları ve bunların özelliklerini işlemek için otomatik olarak ayarlar.  
  
 Her bir şablon sabit prototip olarak başlatın.  
 Bir örnek oluşturmak ve doğru olduğundan emin olmak için istediğiniz metin ya da kod yazın. Ardından uzantısı için .tt değiştirin ve artımlı olarak içerik modeli okuyarak değiştirir kodu ekleyin.  
  
 Yazılı modelleri kullanmayı düşünün.  
 Modelleriniz için bir XML veya veritabanı şemasını oluşturabilirsiniz, ancak bir etki alanına özgü dil (DSL) oluşturmak yararlı olabilir. DSL her düğüme şema ve öznitelikleri temsil etmek için özellikleri temsil etmek için bir sınıf oluşturur avantajına sahiptir. Bu iş modeli bakımından program anlamına gelir. Örneğin:  
  
```  
Team Members:  
<# foreach (Person p in team.Members)   
 { #>   
    <#= p.Name #>   
<# } #>  
```  
  
 Diyagramları modelleriniz için kullanmayı düşünün.  
 Birçok modelde en verimli şekilde sunulan ve özellikle çok büyük olması durumunda yalnızca metin tabloları olarak yönetilir.  
  
 Ancak, bazı tür iş gereksinimlerini ilişkiler ve iş akışları karmaşık kümelerinin açıklamak önemlidir ve en iyi uyan Orta diyagram olan. Bir diyagram avantajı kullanıcılar ve diğer Paydaşlar ile tartışmak kolay olmasıdır. Gereksinimleri değiştiğinde iş gereksinimlerini düzeyinde modelden kod oluşturarak, kodunuzu daha esnek hale getirmek.  
  
 Bir etki alanına özgü dil (DSL) kendi diyagram türü de tasarlayabilirsiniz. UML hem DSL'ler kod oluşturulabilir. Daha fazla bilgi için bkz: [çözümleme ve modelleme mimarisi](../modeling/analyze-and-model-your-architecture.md).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [T4 metin şablonları kullanarak tasarım zamanı kodu oluşturma](../modeling/design-time-code-generation-by-using-t4-text-templates.md)   
 [T4 Metin Şablonları İle Çalışma Süresi Metni Oluşturma](../modeling/run-time-text-generation-with-t4-text-templates.md)
