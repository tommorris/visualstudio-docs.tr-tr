---
title: "T4 metin şablonları kullanarak tasarım zamanı kodu oluşturma | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- text templates, guidelines for code generation
- text templates, data source model
- TextTemplatingFileGenerator custom tool
- Transform All Templates
- text templates, getting started
- Text Template project item
- text templates, generating code for your application
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload: multiple
ms.openlocfilehash: 64a7f5ae729ff2badfc03750efa43c70973a7498
ms.sourcegitcommit: f89ed5fc2e5078213e30a6ade4604e34df48181f
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/13/2018
---
# <a name="design-time-code-generation-by-using-t4-text-templates"></a>T4 Metin Şablonları Kullanarak Tasarım Zamanı Kodu Oluşturma
Tasarım zamanı T4 metin şablonları program kodunu ve diğer dosyalar oluşturmanıza izin, [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] projesi. Genellikle, böylece kullanıcılar verilerinden göre oluşturdukları kod farklılık şablonları yazma bir *modeli*. Bir dosya veya uygulama gereksinimleri hakkında önemli bilgiler içeren bir veri modelidir.  
  
 Örneğin, bir tablo veya bir diyagram olarak bir iş akışını tanımlayan bir model olabilir. Modelden iş akışı yürütür yazılım oluşturabilir. Kullanıcılarınızın gereksinimleri değiştiğinde, yeni bir iş akışı kullanıcılarla tartışın kolaydır. İş akışı koddan yeniden kodu el ile güncelleştirme değerinden daha güvenilirdir.  
  
> [!NOTE]
>  A *modeli* belirli bir uygulamanın durumuyla açıklayan bir veri kaynağıdır. Herhangi bir dosya ya da veritabanı herhangi bir biçimde olabilir. Herhangi bir UML model veya etki alanına özgü dil modeli gibi belirli bir biçimde olmasını yok. Tipik modelleri tablo veya XML dosyaları şeklindedir.  
  
 Büyük olasılıkla kod oluşturma ile bilginiz. Kaynaklarında tanımladığınızda bir **.resx** dosyasını, [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] çözüm, sınıflar ve yöntemler kümesi oluşturulduğunda otomatik olarak. Kaynak dosyasında sınıflar ve yöntemler düzenlemek sahip olması durumuna göre çok daha kolay ve daha güvenilir düzenlemek için kaynakları kolaylaştırır. Metin şablonları ile aynı şekilde, kendi tasarımının bir kaynaktan kodu oluşturabilir.  
  
 Metin şablonu oluşturmak istediğiniz metni ve metin değişken bölümlerini oluşturur program kodu karışımını içerir. Program kodunu ve yineleyin veya koşullu olarak oluşturulan metin bölümlerini atlamasını sağlar. Oluşturulan metnin görüntüleyebilirsiniz. kendisini uygulamanızın parçası oluşturacak program kodu olabilir.  
  
## <a name="creating-a-design-time-t4-text-template"></a>Tasarım zamanı T4 metin şablonu oluşturma  
  
#### <a name="to-create-a-design-time-t4-template-in-visual-studio"></a>Visual Studio tasarım-zamanı T4 şablon oluşturmak için  
  
1.  Oluşturma bir [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] proje veya mevcut bir açın.  
  
     Örneğin, **dosya** menüsünde seçin **yeni**, **proje**.  
  
2.  Metin şablonu dosyasını projenize ekleyin ve uzantıya sahip bir ad verin **.tt**.  
  
     Bunu yapmak için **Çözüm Gezgini**, projenizin kısayol menüsünden seçin **Ekle**, **yeni öğe**. İçinde **Yeni Öğe Ekle** iletişim kutusu seç **metin şablonu** Orta bölmesinden.  
  
     Dikkat **özel araç** özelliği dosyasının **TextTemplatingFileGenerator**.  
  
3.  Dosyasını açın. Ayrıca, aşağıdaki yönergeleri zaten içerecektir:  
  
    ```  
    <#@ template hostspecific="false" language="C#" #>  
    <#@ output extension=".txt" #>  
    ```  
  
     Şablona eklediyseniz bir [!INCLUDE[vbprvb](../code-quality/includes/vbprvb_md.md)] projesi language özniteliği olacaktır "`VB`".  
  
4.  Bazı metinleri dosyanın sonuna ekleyin. Örneğin:  
  
    ```  
    Hello, world!  
    ```  
  
5.  Dosyayı kaydedin.  
  
     Görebilirsiniz bir **Güvenlik Uyarısı** şablon çalıştırmak istediğinizi onaylamanızı ister ileti kutusu. **Tamam**'ı tıklatın.  
  
6.  İçinde **Çözüm Gezgini**, şablon dosyası düğümünü genişletin ve uzantıya sahip bir dosyayı bulabilirsiniz **.txt**. Şablondan oluşturulan metin dosyası içerir.  
  
    > [!NOTE]
    >  Projeniz Visual Basic projesinde ise, tıklatmalısınız **tüm dosyaları göster** çıkış dosyasını görmek için.  
  
### <a name="regenerating-the-code"></a>Kod oluşturma  
 Aşağıdaki durumlarda hiçbirinde şube dosya oluşturma şablon yürütülecek:  
  
-   Şablonu düzenleyebilir ve odak farklı bir değiştirme [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] penceresi.  
  
-   Şablonu kaydedin.  
  
-   Tıklatın **tüm şablonları dönüştürme** içinde **yapı** menüsü. Bu, tüm şablonları dönüştürme [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] çözümü.  
  
-   İçinde **Çözüm Gezgini**, kısayol menüsünde herhangi dosya, seçin **çalıştırmak özel araç**. Seçili şablonları kümesini dönüştürmek için bu yöntemi kullanın.  
  
 Ayrıca ayarlayabileceğiniz bir [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] şablonları okurlar veri dosyalarını değiştiğinde yürütülen böylece proje. Daha fazla bilgi için bkz: [kodu otomatik olarak yeniden](#Regenerating).  
  
## <a name="generating-variable-text"></a>Değişken metin oluşturma  
 Metin şablonları oluşturulan dosyanın içeriğini değiştirmek için program kodu kullanmanıza olanak tanır.  
  
#### <a name="to-generate-text-by-using-program-code"></a>Program kodunu kullanarak metin oluşturmak için  
  
1.  İçeriğini değiştirme `.tt` dosyası:  
  
    ```csharp  
    <#@ template hostspecific="false" language="C#" #>  
    <#@ output extension=".txt" #>  
    <#int top = 10;  
  
    for (int i = 0; i<=top; i++)   
    { #>  
       The square of <#= i #> is <#= i*i #>  
    <# } #>  
    ```  
  
    ```vb  
    <#@ template hostspecific="false" language="VB" #>  
    <#@ output extension=".txt" #>  
    <#Dim top As Integer = 10  
  
    For i As Integer = 0 To top  
    #>  
        The square of <#= i #> is <#= i*i #>  
    <#  
    Next  
    #>  
  
    ```  
  
2.  .Tt dosyayı kaydedin ve yeniden oluşturulan .txt dosyasını inceleyin. 0'dan sayıların 10 kareleri listeler.  
  
 Deyimleri içine alınmış olduğunu fark `<#...#>`ve tek içinde ifadeleri `<#=...#>`. Daha fazla bilgi için bkz: [T4 metin şablonu yazma](../modeling/writing-a-t4-text-template.md).  
  
 Şablonunuzda kod yazarsanız [!INCLUDE[vbprvb](../code-quality/includes/vbprvb_md.md)], `template` yönergesi içermelidir `language="VB"`. `"C#"`varsayılandır.  
  
## <a name="debugging-a-design-time-t4-text-template"></a>Tasarım zamanı T4 metin şablonuna ilişkin hata ayıklama  
 Metin şablonu hata ayıklamak için:  
  
-   INSERT `debug="true"` içine `template` yönergesi. Örneğin:  
  
     `<#@ template debug="true" hostspecific="false" language="C#" #>`  
  
-   Kesme noktaları şablonunda sıradan kodunu yaptığınız şekilde ayarlayın.  
  
-   Seçin **hata ayıklama T4 şablon** Çözüm Gezgini'nde metin şablonu dosyasının kısayol menüsünden.  
  
 Şablon çalıştırın ve kesme noktalarında durdurun. Değişkenleri inceleyin ve kod üzerinden Normal yollardan adım.  
  
> [!TIP]
>  `debug="true"`oluşturulan kodun yönergeleri numaralandırma veya daha fazla satır ekleyerek metin şablonu için daha doğru bir şekilde eşleme oluşturulan kod yapar. Teslim değiştirmeden bırakırsanız, kesme noktaları durumu yanlış Çalıştır durabilir.  
>   
>  Ancak bile, değil ayıklarken yan tümcesi içinde şablon yönergesi bırakabilirsiniz. Bu, performans çok küçük bir açılan neden olur.  
  
## <a name="generating-code-or-resources-for-your-solution"></a>Kod veya kaynakları çözümünüz için oluşturma  
 Bir modeline bağlı olarak değişebilir program dosyaları oluşturabilir. Bir veritabanı, yapılandırma dosyası, UML modeli, DSL modeli veya başka bir kaynaktan gibi bir giriş modelidir. Birkaç genellikle oluşturmak program dosyaları olan aynı modelden. Bunun için her oluşturulan program dosyası için bir şablon dosyası oluşturun ve tüm şablonları aynı modelin okuma.  
  
#### <a name="to-generate-program-code-or-resources"></a>Program kodunda veya kaynakları oluşturmak için  
  
1.  Çıktı yönergesi .cs, .vb, .resx veya .xml gibi uygun bir tür bir dosya oluşturmak için değiştirin.  
  
2.  Çözüm kod oluşturacak kodu ekleyin. Örneğin, bir sınıf içinde üç tamsayı alan bildirimleri oluşturmak istiyorsanız:  
  
    ```csharp  
  
              <#@ template debug="false" hostspecific="false" language="C#" #>  
    <#@ output extension=".cs" #>  
    <# var properties = new string [] {"P1", "P2", "P3"}; #>  
    // This is generated code:  
    class MyGeneratedClass {  
    <# // This code runs in the text template:  
      foreach (string propertyName in properties)  { #>  
      // Generated code:  
      private int <#= propertyName #> = 0;  
    <# } #>  
    }  
    ```  
  
    ```vb  
    <#@ template debug="false" hostspecific="false" language="VB" #>  
    <#@ output extension=".cs" #>  
    <# Dim properties = {"P1", "P2", "P3"} #>  
    class MyGeneratedClass {  
    <#   
       For Each propertyName As String In properties  
    #>  
      private int <#= propertyName #> = 0;  
    <#  
       Next  
    #>  
    }  
  
    ```  
  
3.  Dosyayı kaydedin ve şimdi aşağıdaki kodu içeren oluşturulan dosyasını inceleyin:  
  
    ```  
    class MyGeneratedClass {  
      private int P1 = 0;   
      private int P2 = 0;  
      private int P3 = 0;  
    }  
    ```  
  
### <a name="generating-code-and-generated-text"></a>Kod ve oluşturulan metin oluşturma  
 Program kodunu oluşturduğunuzda, şablonunuzda yürütür oluşturma kodu ve çözümünüzün bir parçası haline gelir elde edilen oluşturulan kod kafa karıştırıcı önlemek en önemlidir. İki dil aynı olması gerekmez.  
  
 Önceki örnekte iki sürümü vardır. Bir sürümde oluşturma C# ' ta kodudur. Diğer sürüm oluşturma Visual Basic kodudur. Ancak her ikisi tarafından oluşturulan metnin aynıdır ve C# sınıfı olan.  
  
 Aynı şekilde kullanabileceğinizi bir [!INCLUDE[csprcs](../data-tools/includes/csprcs_md.md)] herhangi bir dil kodu oluşturmak için şablon. Oluşturulan metnin herhangi belirli bir dilde olması gerekmez ve program kodunun olması gerekmez.  
  
### <a name="structuring-text-templates"></a>Metin şablonları yapılandırma  
 Sağlasa da, iyi bir uygulama, biz şablonu kodu iki bölüme ayırın olma eğilimi gösterir:  
  
-   Bir yapılandırma veya değişkenlerinin değerlerini ayarlar, ancak metin blokları içermiyor veri toplama bölümü. Önceki örnekte, bu başlatılması parçasıdır `properties`.  
  
     Bir mağazadaki modeli oluşturur ve genellikle bir model dosyası okuma için buna bazen "model" bölümüne denir.  
  
-   Metin oluşturma bölümü (`foreach(...){...}` örnekte), değişkenlerin değerleri kullanır.  
  
 Bu gerekli bir ayrım değildir, ancak metin içeren bölümü karmaşıklığını azaltarak şablon okuması daha kolay hale getiren bir stil olduğu.  
  
## <a name="reading-files-or-other-sources"></a>Okuma dosyaları veya diğer kaynaklar  
 Bir model dosyası veya veritabanı erişimi için şablon kodunuzu derlemeleri System.XML gibi kullanabilirsiniz. Bu derlemeler erişmek için bunlar gibi yönergeleri eklemeniz gerekir:  
  
```  
<#@ assembly name="System.Xml.dll" #>  
<#@ import namespace="System.Xml" #>  
<#@ import namespace="System.IO" #>  
```  
  
 `assembly` Yönergesi kullanılabilir hale getirir belirtilen derleme şablon kodunuza, başvurular bölümüne aynı şekilde bir [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] projesi. Otomatik olarak başvurulan System.dll bir başvuru eklemek gerekmez. `import` Yönergesi türleri ile aynı şekilde tam adlarını kullanmadan kullanmanıza imkan tanır `using` bir sıradan program dosyasında yönergesi.  
  
 Örneğin, aldıktan sonra **System.IO**, yazma:  
  
```csharp  
  
      <# var properties = File.ReadLines("C:\\propertyList.txt");#>  
...  
<# foreach (string propertyName in properties) { #>  
...  
```  
  
```vb  
<# For Each propertyName As String In   
             File.ReadLines("C:\\propertyList.txt")  
#>  
  
```  
  
### <a name="opening-a-file-with-a-relative-pathname"></a>Göreli bir yol adına sahip bir dosyayı açma  
 Metin şablonu göreli bir konumdan bir dosya yüklemek için kullanabileceğiniz `this.Host.ResolvePath()`. Bunu kullanmak için. Konak, ayarlamalısınız `hostspecific="true"` içinde `template`:  
  
```  
<#@ template debug="false" hostspecific="true" language="C#" #>  
  
```  
  
 Ardından, örneğin yazabilirsiniz:  
  
```csharp  
<# string fileName = this.Host.ResolvePath("filename.txt");  
  string [] properties = File.ReadLines(filename);  
#>  
...  
<#  foreach (string propertyName in properties { #>  
...  
  
```  
  
```vb  
<# Dim fileName = Me.Host.ResolvePath("propertyList.txt")  
   Dim properties = File.ReadLines(filename)  
#>  
...  
<#   For Each propertyName As String In properties  
...  
#>  
  
```  
  
 Aynı zamanda `this.Host.TemplateFile`, geçerli şablon dosyasının adını tanımlar.  
  
 Türü `this.Host` (VB içinde `Me.Host`) olan `Microsoft.VisualStudio.TextTemplating.ITextTemplatingEngineHost`.  
  
### <a name="getting-data-from-includevsprvscode-qualityincludesvsprvsmdmd"></a>İçinden verileri alma[!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)]  
 Sağlanan hizmetleri kullanmaya [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)]ayarlayın `hostSpecific` özniteliği ve yük `EnvDTE` derleme. Ardından IServiceProvider.GetCOMService() DTE ve diğer hizmetlere erişmek için de kullanabilirsiniz. Örneğin:  
  
```scr  
<#@ template hostspecific="true" language="C#" #>  
<#@ output extension=".txt" #>  
<#@ assembly name="EnvDTE" #>  
<#  
  IServiceProvider serviceProvider = (IServiceProvider)this.Host;  
  EnvDTE.DTE dte = (EnvDTE.DTE) serviceProvider.GetCOMService(typeof(EnvDTE.DTE));  
#>  
  
Number of projects in this VS solution:  <#= dte.Solution.Projects.Count #>  
  
```  
  
> [!TIP]
>  Metin şablonu kendi uygulama etki alanında çalışır ve Hizmetleri hazırlama tarafından erişilir. Bu durumda GetCOMService() GetService() daha büyük/küçük harf güvenilirdir.  
  
##  <a name="Regenerating"></a>Kodu otomatik olarak yeniden oluşturuluyor  
 Genellikle, birkaç dosyalarında bir [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] çözümü ile bir giriş model oluşturulur. Her dosya kendi şablonu, ancak tüm aynı modelin başvurur şablonları oluşturulur.  
  
 Kaynak modeli değişirse, Çözümdeki tüm şablonları yeniden çalıştırmanız gerekir. Bunu el ile yapmak için seçin **tüm şablonları dönüştürme** üzerinde **yapı** menüsü.  
  
 Yüklediyseniz [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] Görselleştirme ve modelleme SDK, bir derleme yaptığınızda otomatik olarak dönüştürülen tüm şablonları olabilir. Bunu yapmak için proje dosyanızı (.csproj veya .vbproj) bir metin düzenleyicisinde düzenleyin ve sonra diğer yakın dosyasının sonuna şu satırları ekleyin `<import>` deyimleri:  


[!INCLUDE[modeling_sdk_info](includes/modeling_sdk_info.md)]

  
```  
<Import Project="$(MSBuildExtensionsPath)\Microsoft\VisualStudio\v15.0\TextTemplating\Microsoft.TextTemplating.targets" />  
<PropertyGroup>  
   <TransformOnBuild>true</TransformOnBuild>  
   <!-- Other properties can be inserted here -->  
</PropertyGroup>  
```  
  
 Daha fazla bilgi için bkz: [derleme sürecinde kod oluşturma](../modeling/code-generation-in-a-build-process.md).  
  
## <a name="error-reporting"></a>Hata Raporlama  
 Hata ve uyarı iletilerini yerleştirmek için [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] hata penceresinde, bu yöntemleri kullanabilirsiniz:  
  
```  
Error("An error message");  
Warning("A warning message");  
```  
  
##  <a name="Converting"></a>Varolan bir dosyanın bir şablona dönüştürme  
 Yararlı şablonları bunlar çok, bazı eklenen program kod ile birlikte oluşturdukları dosyaları gibi göründüğünü özelliğidir. Bu şablon oluşturma, kullanışlı bir yöntem önerir. Bir sıradan dosyası gibi bir prototip olarak oluşturmanız bir [!INCLUDE[csprcs](../data-tools/includes/csprcs_md.md)] dosya ve sonuçta elde edilen dosyasını değişir oluşturma koduna kademeli olarak tanıtır.  
  
#### <a name="to-convert-an-existing-file-to-a-design-time-template"></a>Varolan bir dosyanın bir tasarım zamanı şablona dönüştürmek için  
  
1.  İçin [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] proje, gibi oluşturmak istediğiniz türde bir dosya ekleme bir `.cs`, `.vb`, veya `.resx` dosyası.  
  
2.  Yeni dosyanın çalıştığını emin olmak için test edin.  
  
3.  Çözüm Gezgini'nde, dosya adı uzantısına değişiklik **.tt**.  
  
4.  Aşağıdaki özelliklerini doğrulamanızı **.tt** dosyası:  
  
    |||  
    |-|-|  
    |**Özel araç =**|**TextTemplatingFileGenerator**|  
    |**Derleme eylemi =**|**Yok**|  
  
5.  Dosyanın başına aşağıdaki satırları ekleyin:  
  
    ```  
    <#@ template debug="false" hostspecific="false" language="C#" #>  
    <#@ output extension=".cs" #>  
    ```  
  
     Şablonunuzda şablonunuzda kod yazmak isterseniz [!INCLUDE[vbprvb](../code-quality/includes/vbprvb_md.md)]ayarlayın `language` özniteliğini `"VB"` yerine `"C#"`.  
  
     Ayarlama `extension` dosya adı uzantısı, örneğin oluşturmak istediğiniz dosya türü için özniteliğini `.cs`, `.resx`, veya `.xml`.  
  
6.  Dosyayı kaydedin.  
  
     Belirtilen uzantılı bir dosyası oluşturulur. Kendi dosya türü için doğru özelliklerdir. Örneğin, **yapı eylemi** .cs dosyasının özelliği olacaktır **derleme**.  
  
     Oluşturulan dosyanın özgün dosyayla aynı içerik içerdiğini doğrulayın.  
  
7.  Farklı hale getirmek istediğiniz dosyanın bir kısmını tanımlar. Örneğin, yalnızca belirli koşullar altında görünür bir bölümü veya yinelenen veya nerede belirli değerler farklı bir bölümü. Kod oluşturma ekleyin. Dosyayı kaydedin ve dosyası doğru şekilde oluşturulan doğrulayın. Bu adımı yineleyin.  
  
## <a name="guidelines-for-code-generation"></a>Kod oluşturma için yönergeler  
 Lütfen bakın [yazma T4 metin şablonları için yönergeler](../modeling/guidelines-for-writing-t4-text-templates.md).  
  
## <a name="next-steps"></a>Sonraki adımlar  
  
|Sonraki adım|Konu|  
|---------------|-----------|  
|Yazma ve hata ayıklama yardımcı işlevleri, eklenen dosyalar ve dış veri kullanan kodu ile daha gelişmiş bir metin şablonu.|[T4 Metin Şablonu Yazma](../modeling/writing-a-t4-text-template.md)|  
|Belgeleri şablonlardan çalışma zamanında oluşturur.|[T4 Metin Şablonları İle Çalışma Süresi Metni Oluşturma](../modeling/run-time-text-generation-with-t4-text-templates.md)|  
|Metin oluşturma dışında çalıştırmak [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)].|[TextTransform Yardımcı Programı ile Dosya Oluşturma](../modeling/generating-files-with-the-texttransform-utility.md)|  
|Verilerinizi bir etki alanına özgü dil biçiminde dönüştürün.|[Etki Alanına Özgü Dilden Kod Oluşturma](../modeling/generating-code-from-a-domain-specific-language.md)|  
|Kendi veri kaynaklarını dönüştürmek için yönerge işlemcileri yazma.|[T4 Metin Dönüştürmeyi Özelleştirme](../modeling/customizing-t4-text-transformation.md)|  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [T4 Metin Şablonları Yazma Yönergeleri](../modeling/guidelines-for-writing-t4-text-templates.md)
