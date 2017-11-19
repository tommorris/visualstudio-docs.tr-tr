---
title: "T4 metin şablonu yazma | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- text templates, syntax
- text templates, guide
- text templates, functions that generate text
ms.assetid: 94328da7-953b-4e92-9587-648543d1f732
caps.latest.revision: "43"
author: alancameronwills
ms.author: awills
manager: douge
ms.openlocfilehash: c5e60ada4489e12312df92ecceab8bc268a6cfac
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2017
---
# <a name="writing-a-t4-text-template"></a>T4 Metin Şablonu Yazma
Metin şablonu ondan oluşturulan metni içerir. Örneğin, bir web sayfası oluşturan bir şablonu içerir "\<html >..." ve diğer tüm standart bölümleri HTML sayfası. Şablona eklenmiş olan *denetim blokları*, program kod parçalarını olduğu. Denetim blokları değişen değerler sağlayın ve koşullu ve yinelenen metni bölümlerini sağlar.  
  
 Bu yapı şablondan oluşturulan dosyanın bir prototip başlatın ve sonucu farklılık denetim blokları artımlı olarak eklemek için geliştirmek kolaylaştırır.  
  
 Metin şablonları aşağıdaki bölümden oluşur:  
  
-   **Yönergeleri** -şablonu nasıl işleneceğini denetim öğeleri.  
  
-   **Metin blokları** - içerik çıkışa doğrudan kopyalanır.  
  
-   **Denetim blokları** -program metne değişken değerlerini ekler ve bu metnin koşullu veya yinelenen bölümleri denetimlerini kodu.  
  
 Bu konudaki örnekler denemek için bunları bir şablon dosyasına açıklandığı gibi kopyalayın [T4 metin şablonları kullanarak tasarım zamanı kodu oluşturma](../modeling/design-time-code-generation-by-using-t4-text-templates.md). Şablon dosyası düzenleme sonra kaydetmeli ve çıktıyı inceleyin **.txt** dosya.  
  
## <a name="directives"></a>Yönergeler  
 Metin şablonu yönergeleri dönüşüm kodu ve çıktı dosyası oluşturmak nasıl hakkında metin şablon motoru için genel yönergeler sağlar.  
  
 Örneğin, aşağıdaki yönergesi çıktı dosyası .txt uzantısı sahip olması gerektiğini belirtir:  
  
```  
  
<#@ output extension=".txt" #>  
```  
  
 Yönergeleri hakkında daha fazla bilgi için bkz: [T4 metin şablonu yönergeleri](../modeling/t4-text-template-directives.md).  
  
## <a name="text-blocks"></a>Metin blokları  
 Bir metin bloğunu metni doğrudan çıktı dosyasına ekler. Hiçbir özel metin blokları için biçimlendirme yoktur. Örneğin, aşağıdaki metin şablonu "Hello" sözcüğünü içeren bir metin dosyası oluşturur:  
  
```  
<#@ output extension=".txt" #>  
Hello  
```  
  
## <a name="control-blocks"></a>Denetim blokları  
 Denetim, şablonları dönüştürmek için kullanılan program kodun bölümlerini taşlarıdır. Varsayılan dil C# ' ta, olduğu için kullanabilir ancak [!INCLUDE[vbprvb](../code-quality/includes/vbprvb_md.md)], bu yönergesi dosyasının başında yazabilirsiniz:  
  
```  
<#@ template language="VB" #>  
```  
  
 Denetim blokları kodda yazma oluşturulan metin dili ilgisiz dilidir.  
  
### <a name="standard-control-blocks"></a>Standart denetim blokları  
 Bir standart denetim bloğu, çıktı dosyası parçası oluşturur program kodunu bölümüdür.  
  
 Metin bloğu ve standart denetim bloğu şablon dosyasında herhangi bir sayıda karıştırabilirsiniz. Bununla birlikte, içinde başka bir denetim bloğu yerleştirilemiyor. Her standart denetim bloğu simgeleriyle ayrılmış `<# ... #>`.  
  
 Örneğin, aşağıdaki denetim bloğu ve metin bloğu satırı içerecek şekilde çıktı dosyası neden "0, 1, 2, 3, 4 Merhaba!":  
  
```  
  
      <#  
    for(int i = 0; i < 4; i++)  
    {  
        Write(i + ", ");  
    }  
    Write("4");  
#> Hello!  
```  
  
 Açık kullanmak yerine `Write()` deyimleri, metin ve kod Interleave. Aşağıdaki örnekte "Hello!" yazdırır. dört kez:  
  
```  
<#  
    for(int i = 0; i < 4; i++)  
    {  
#>  
Hello!  
<#  
    }   
#>  
```  
  
 Bir metin eklemek için yerde engelleme bir `Write();` deyimi kodda izin.  
  
> [!NOTE]
>  Bir metin bloğu içinde bir döngü gibi veya koşullu bileşik bir ifade katıştırma, her zaman küme ayraçları {...} kullanın metin bloğu içerecek şekilde.  
  
### <a name="expression-control-blocks"></a>İfade denetim blokları  
 Bir ifade denetim bloğu bir ifadeyi değerlendirir ve bir dizeye dönüştürür. Bu çıktı dosyasına eklenir.  
  
 İfade denetim blokları simgeleriyle ayrılmış`<#= ... #>`  
  
 Örneğin, aşağıdaki denetim bloğu "5" içerecek şekilde çıktı dosyası neden olur:  
  
```  
<#= 2 + 3 #>  
```  
  
 Açma simgesi üç karakter sahip olmadığına dikkat edin "< #=".  
  
 İfade, kapsam içi herhangi bir değişken içerebilir. Örneğin, bu bloğu numaraları satırıyla baskı:  
  
```  
<#@ output extension=".txt" #>  
<#  
    for(int i = 0; i < 4; i++)  
    {  
#>  
This is hello number <#= i+1 #>: Hello!  
<#  
    }   
#>  
```  
  
### <a name="class-feature-control-blocks"></a>Sınıf özelliği denetim blokları  
 Bir sınıf özelliği denetim bloğu özellikleri, yöntemleri veya ana dönüştürme dahil edilmemesi gereken herhangi bir kod tanımlar. Sınıf özelliği bloklar sık yardımcı işlevleri için kullanılır.  Böylece olabilirler sınıf özelliği blokları ayrı dosyalarda genellikle yerleştirilir [dahil](#Include) birden fazla metin şablonu tarafından.  
  
 Sınıf özelliği denetim blokları simgeleriyle ayrılmış`<#+ ... #>`  
  
 Örneğin, aşağıdaki şablon dosyası bildirir ve bir yöntemi kullanır:  
  
```  
<#@ output extension=".txt" #>  
Squares:  
<#  
    for(int i = 0; i < 4; i++)  
    {  
#>  
    The square of <#= i #> is <#= Square(i+1) #>.  
<#  
    }   
#>  
That is the end of the list.  
<#+   // Start of class feature block  
private int Square(int i)  
{  
    return i*i;  
}  
#>  
```  
  
 Sınıf özellikleri yazılmış olan dosya sona erdiğinde yerleştirilmelidir. Ancak, `<#@include#>` içeren sınıf özelliği, bile dosyası `include` yönergesi standart blokları ve metin tarafından izlendiği.  
  
 Denetim blokları hakkında daha fazla bilgi için bkz: [metin şablonu denetim blokları](../modeling/text-template-control-blocks.md).  
  
### <a name="class-feature-blocks-can-contain-text-blocks"></a>Sınıf özelliği blokları metin blokları içerebilir  
 Metin oluşturan bir yöntem yazabilirsiniz. Örneğin:  
  
```  
List of Squares:  
<#  
   for(int i = 0; i < 4; i++)  
   {  WriteSquareLine(i); }  
#>  
End of list.  
<#+   // Class feature block  
private void WriteSquareLine(int i)  
{  
#>  
   The square of <#= i #> is <#= i*i #>.  
<#+     
}  
#>  
```  
  
 Birden fazla şablon tarafından eklenen ayrı bir dosyada metin oluşturan bir yöntem yerleştirmek özellikle yararlıdır.  
  
## <a name="using-external-definitions"></a>Dış tanımlar kullanma  
  
### <a name="assemblies"></a>Derlemeler  
 Kod blokları şablonunuzun en sık tanımlanan kullanım türlerini kullanabilir .NET derlemelerini System.dll gibi. Ayrıca, diğer .NET derlemelerini veya kendi derlemeleri başvuruda bulunabilir. Bir yol veya bir derleme tanımlayıcı adı sağlayabilirsiniz:  
  
```  
<#@ assembly name="System.Xml" #>  
```  
  
 Mutlak yol adlarını kullanmanız veya yol adındaki standart makrosu adları kullanın. Örneğin:  
  
```  
<#@ assembly name="$(SolutionDir)library\MyAssembly.dll" #>  
```  
  
 Derleme yönergesi etkisizdir bir [önceden işlenmiş metin şablonu](../modeling/run-time-text-generation-with-t4-text-templates.md).  
  
 Daha fazla bilgi için bkz: [T4 derleme yönergesi](../modeling/t4-assembly-directive.md).  
  
### <a name="namespaces"></a>Ad Alanları  
 İçe aktarma yönergesi aynıdır `using` yan tümcesinde C# veya `imports` Visual Basic'te yan tümcesi. Bir tam ad kullanmadan kodunuzu türlerinde bakın sağlar:  
  
```  
<#@ import namespace="System.Xml" #>  
```  
  
 Birçok kullanabileceğiniz `assembly` ve `import` yazarken yönergeleri istiyor. Metin ve denetim blokları önce bunları yerleştirmeniz gerekir.  
  
 Daha fazla bilgi için bkz: [T4 içe aktarma yönergesi](../modeling/t4-import-directive.md).  
  
###  <a name="Include"></a>Kod ve metin dahil  
 `include` Yönergesi başka bir şablon dosyasından metin ekler. Örneğin, bu yönergesi içeriğini ekler `test.txt`.  
  
 `<#@ include file="c:\test.txt" #>`  
  
 Eklenen içerik ekleyen metin şablonunun hemen hemen parçasıymış gibi işlenir. Ancak, bir sınıf özelliği bloğu içeren bir dosya ekleyebilirsiniz `<#+...#>` bile içerme yönergesi normal metin ve standart denetim blokları tarafından izlenir.  
  
 Daha fazla bilgi için bkz: [T4 dahil yönergesi](../modeling/t4-include-directive.md).  
  
### <a name="utility-methods"></a>Yardımcı program yöntemleri  
 Birkaç yöntem vardır gibi `Write()` , her zaman bir denetim bloğu içinde kullanılabilir. Çıktı girinti yardımcı olur ve hatalarını raporlama yöntemleri içerirler.  
  
 Yardımcı program yöntemleri kendi kümesi de yazabilirsiniz.  
  
 Daha fazla bilgi için bkz: [metin şablonu yardımcı program yöntemleri](../modeling/text-template-utility-methods.md).  
  
## <a name="transforming-data-and-models"></a>Veri ve modelleri dönüştürme  
 En kullanışlı bir metin şablonu için bir model, veritabanı veya veri dosyası gibi bir kaynak içeriğini göre malzemesi oluşturmak üzere uygulamasıdır. Şablonunuzu ayıklar ve verileri yeniden biçimlendirir. Şablonları koleksiyonu gibi bir kaynak birden çok dosyaya dönüştürebilirsiniz.  
  
 Kaynak dosya okuma için birçok yaklaşım vardır.  
  
 **Metin şablonu dosyasında okuma**. Bu şablona veri almanın en basit yolu.  
  
```  
<#@ import namespace="System.IO" #>  
<# string fileContent = File.ReadAllText(@"C:\myData.txt"); ...  
```  
  
 **Bir dosya gezinebilir modeli olarak yükleme**. Metin şablonu kodunuzu gidebilirsiniz bir model olarak veri okuma daha güçlü bir yöntemdir. Örneğin, bir XML dosyasını ve XPath ifadelerle gidin. De kullanabilirsiniz [XSD.exe'nin](http://go.microsoft.com/fwlink/?LinkId=178765) ile edinebilirsiniz XML veri sınıfları kümesi oluşturmak için.  
  
 **Bir diyagram veya biçiminde model dosyasını düzenleyin.** [!INCLUDE[dsl](../modeling/includes/dsl_md.md)]model bir diyagram ya da Windows form olarak düzenlemenize olanak sağlayan araçlar sağlar. Bu model oluşturulan uygulama kullanıcılarla tartışın kolaylaştırır. [!INCLUDE[dsl](../modeling/includes/dsl_md.md)]Ayrıca modeli yapısını yansıtacak türü kesin belirlenmiş sınıf kümesi oluşturur. Daha fazla bilgi için bkz: [bir etki alanına özgü dil oluşturma koddan](../modeling/generating-code-from-a-domain-specific-language.md).  
  
### <a name="relative-file-paths-in-design-time-templates"></a>Tasarım zamanı şablonlarındaki göreli dosya yolları  
 İçinde bir [tasarım zamanı metin şablonu](../modeling/design-time-code-generation-by-using-t4-text-templates.md), metin şablonu, kullanım konumuna dosyasında başvurmak istiyorsanız `this.Host.ResolvePath()`. De ayarlamalısınız `hostspecific="true"` içinde `template` yönergesi:  
  
```csharp  
<#@ template hostspecific="true" language="C#" #>  
<#@ output extension=".txt" #>  
<#@ import namespace="System.IO" #>  
<#  
 // Find a path within the same project as the text template:  
 string myFile = File.ReadAllText(this.Host.ResolvePath("MyFile.txt"));  
#>  
Content of MyFile.txt is:  
<#= myFile #>  
  
```  
  
 Ana bilgisayar tarafından sağlanan diğer hizmetler edinebilirsiniz. Daha fazla bilgi için bkz: [erişme Visual Studio'ya veya diğer ana şablondan](http://msdn.microsoft.com/en-us/0556f20c-fef4-41a9-9597-53afab4ab9e4).  
  
### <a name="design-time-text-templates-run-in-a-separate-appdomain"></a>Tasarım zamanı metin şablonları ayrı bir AppDomain içinde çalıştırın  
 Farkında olmalıdır, bir [tasarım zamanı metin şablonu](../modeling/design-time-code-generation-by-using-t4-text-templates.md) ana uygulamadan ayrı bir AppDomain içinde çalışır. Çoğu durumda bu önemli değildir, ancak belirli karmaşık durumlarda kısıtlamaları fark edebilirsiniz. Örneğin, verileri veya şablon dışında ayrı bir hizmetten geçirmek istiyorsanız, hizmet seri hale getirilebilir bir API sağlamanız gerekir.  
  
 (Bu doğru değilse bir [çalışma zamanı metin şablonu](../modeling/run-time-text-generation-with-t4-text-templates.md), kodunuzun geri kalanı ile birlikte derlenmiş kod sağlar.)  
  
## <a name="editing-templates"></a>Şablonları düzenleme  
 Özel metin şablonu düzenleyicileri Uzantı Yöneticisi çevrimiçi galeriden indirilebilir. Üzerinde **Araçları** menüsünde tıklatın **Uzantı Yöneticisi**. Tıklatın **çevrimiçi galeri**ve ardından arama aracını kullanın.  
  
## <a name="related-topics"></a>İlgili konular  
  
|Görev|Konu|  
|----------|-----------|  
|Bir şablon yazma.|[T4 metin şablonları yazma yönergeleri](../modeling/guidelines-for-writing-t4-text-templates.md)|  
|Metin program kodunu kullanarak oluşturun.|[Metin şablonu yapısı](../modeling/writing-a-t4-text-template.md)|  
|Dosyaları oluşturmak bir [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] çözümü.|[T4 metin şablonları kullanarak tasarım zamanı kodu oluşturma](../modeling/design-time-code-generation-by-using-t4-text-templates.md)|  
|Metin oluşturma dışında çalıştırmak [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)].|[TextTransform yardımcı programı ile dosyalar oluşturma](../modeling/generating-files-with-the-texttransform-utility.md)|  
|Verilerinizi bir etki alanına özgü dil biçiminde dönüştürün.|[Bir etki alanına özgü dili kod oluşturma](../modeling/generating-code-from-a-domain-specific-language.md)|  
|Kendi veri kaynaklarını dönüştürmek için yönerge işlemcileri yazma.|[T4 metin dönüştürmeyi özelleştirme](../modeling/customizing-t4-text-transformation.md)|
