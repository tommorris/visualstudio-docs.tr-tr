---
title: T4 Şablon yönergesi | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.topic: conceptual
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.technology: vs-ide-modeling
ms.openlocfilehash: c39783b9ca8be2f9e406782258befecce416f551
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/16/2018
---
# <a name="t4-template-directive"></a>T4 Şablon Yönergesi
A [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] T4 metin şablonu ile genellikle başlayan bir `template` şablonun nasıl işleneceğini belirtir yönergesi. Bir metin şablonu ve içerdiği herhangi bir dosya içinde birden fazla şablon yönergesi bulunmamalıdır.  
  
 Metin şablonları yazma genel bir bakış için bkz: [T4 metin şablonu yazma](../modeling/writing-a-t4-text-template.md).  
  
## <a name="using-the-template-directive"></a>Şablon Yönergesini Kullanma  
  
```  
<#@ template [language="VB"] [compilerOptions="options"] [culture="code"] [debug="true"] [hostspecific="true"] [inherits="templateBaseClass"] [visibility="internal"] [linePragmas="false"] #>  
```  
  
 `template` Yönergesi dönüştürme farklı yönlerini belirtmenize olanak veren birkaç özniteliklere sahip. Tüm öznitelikler isteğe bağlıdır.  
  
## <a name="compileroptions-attribute"></a>compilerOptions özniteliği  
 Örnek:  
 `compilerOptions="optimize+"`  
  
 Geçerli değerler:  
 Tüm geçerli derleyici seçenekleri.  
  
 Çalışma zamanı (önceden işlenmiş) şablonları için yok sayılır.  
  
 Şablon dönüştürüldükten Bu seçenekler uygulanır [!INCLUDE[csprcs](../data-tools/includes/csprcs_md.md)] veya [!INCLUDE[vb_current_short](../debugger/includes/vb_current_short_md.md)], ve ortaya çıkan kodu derlenir.  
  
## <a name="culture-attribute"></a>culture özniteliği  
 Örnek:  
 `culture="de-CH"`  
  
 Geçerli değerler:  
 Sabit kültür olan "" varsayılan değerdir.  
  
 xx-XX biçiminde bir dize olarak ifade edilen bir kültür. Örneğin, en-US, ja-JP, de-CH, de-DE. Daha fazla bilgi için bkz. <xref:System.Globalization.CultureInfo?displayProperty=fullName>.  
  
 Culture özniteliği, bir ifade bloğu metne dönüştürüldüğünde kullanılacak kültürü belirtir.  
  
## <a name="debug-attribute"></a>debug özniteliği  
 Örnek:  
 ```  
debug="true"  
```  
  
 Geçerli değerler:  
 `true, false`. False, varsayılan değerdir.  
  
 Varsa `debug` özniteliği `true`, Ara kod dosyası sonu veya özel durum oluştuğu konum şablonunuzda daha doğru bir şekilde tanımlamak hata ayıklayıcı sağlayan bilgiler içerir.  
  
 Tasarım zamanı şablonları için Ara kod dosyası yazılır, **% TEMP %** dizin.  
  
 Hata Ayıklayıcısı'ndaki bir tasarım zamanı şablonu çalıştırmak için metin şablonu kaydetmek sonra Çözüm Gezgini'nde metin şablonu kısayol menüsünü açın ve seçin **hata ayıklama T4 şablon**.  
  
## <a name="hostspecific-attribute"></a>hostspecific özniteliği  
 Örnek:  
 ```  
hostspecific="true"  
```  
  
 Geçerli değerler:  
 `true, false, trueFromBase`. False, varsayılan değerdir.  
  
 Bu özniteliğin değeri ayarlarsanız `true`, adında bir özellik `Host` metin şablon tarafından oluşturulan sınıf eklenir. Özelliği için dönüştürme altyapısı konak başvurudur ve olarak bildirilen <xref:Microsoft.VisualStudio.TextTemplating.ITextTemplatingEngineHost>. Özel bir sunucu tanımladıysanız, bunu özel ana bilgisayar türüne atayabilirsiniz.  
  
 Bu özelliğin türü ana bilgisayarın türüne bağlı olduğundan, yalnızca belirli bir ana bilgisayar ile çalışan bir metin şablonu yazıyorsanız faydalıdır. İçin geçerli [tasarım zamanı şablonları](../modeling/design-time-code-generation-by-using-t4-text-templates.md), ama [çalışma zamanı şablonları](../modeling/run-time-text-generation-with-t4-text-templates.md).  
  
 Zaman `hostspecific` olan `true` ve kullanmakta olduğunuz [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)], size çevirebilirsiniz `this.Host` erişmek için IServiceProvider için [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] özellikleri. Aynı zamanda `Host.ResolvePath(filename)` proje dosyasında mutlak yolu elde edilir. Örneğin:  
  
```csharp  
<#@ template debug="false" hostspecific="true" language="C#" #>  
<#@ output extension=".txt" #>  
<#@ assembly name="EnvDTE" #>  
<#@ import namespace="EnvDTE" #>  
<#@ import namespace="System.IO" #>  
<# // Get the Visual Studio API as a service:  
 DTE dte = ((IServiceProvider)this.Host).GetCOMService(typeof(DTE)) as DTE;    
#>  
Number of projects in this solution: <#=  dte.Solution.Projects.Count #>  
  
<#  
 // Find a path within the current project:  
 string myFile = File.ReadAllText(this.Host.ResolvePath("MyFile.txt"));  
#>  
Content of myFile is:  
<#= myFile #>  
  
```  
  
 Kullanırsanız `inherits` ve `hostspecific` öznitelikleri birlikte, konak belirtin türetilmiş sınıf ve ana bilgisayar "trueFromBase" = = "true taban sınıf içinde". Bu çift tanımının önler `Host` oluşturulan kodun bir özellik.  
  
## <a name="language-attribute"></a>language özniteliği  
 Örnek:  
 `language="VB"`  
  
 Geçerli değerler:  
 `C#` (varsayılan)  
  
 `VB`  
  
 Dili özniteliğindeki dili belirtir ([!INCLUDE[vbprvb](../code-quality/includes/vbprvb_md.md)] veya [!INCLUDE[csprcs](../data-tools/includes/csprcs_md.md)]) deyimi ve deyim blokları kaynak kodunda için kullanılacak. Çıktının oluşturulmasında kullanılan ara kod dosyası bu dili kullanır. Bu dil, şablonunuzun oluşturduğu ve herhangi bir türdeki bir metin olabilecek dille ilişkili değildir.  
  
 Örneğin:  
  
```vb  
<#@ template language="VB" #>  
<#@ output extension=".txt" #>  
Squares of numbers:  
<#  
  Dim number As Integer  
  For number = 1 To 4  
#>  
  Square of <#= number #> is <#= number * number #>  
<#  
  Next number  
#>  
  
```  
  
## <a name="inherits-attribute"></a>inherits özniteliği  
 Şablonunuzun program kodunun, bir metin şablonundan oluşturulabilen başka bir sınıftan devralma işlemi yapabileceğini belirtebilirsiniz.  
  
### <a name="inheritance-in-a-run-time-preprocessed-text-template"></a>Çalışma zamanı (önceden işlenmiş) metin şablonunda devralma  
 Türetilmiş birkaç varyanta sahip bir temel şablon oluşturmak için çalışma zamanı metin şablonları arasında devralmayı kullanabilirsiniz. Çalışma zamanı şablonlarıdır olan **özel araç** özelliğini **TextTemplatingFilePreprocessor**. Çalışma zamanı şablonu, şablonda tanımlanan metin oluşturmak için uygulamanızda çağırabildiğiniz bir kod oluşturur. Daha fazla bilgi için bkz: [T4 metin şablonları ile çalışma zamanı metin oluşturma](../modeling/run-time-text-generation-with-t4-text-templates.md).  
  
 Belirtmezseniz, bir `inherits` öznitelik, bir taban sınıf ve türetilmiş bir sınıf, metin şablonundan oluşturulur. Belirttiğinizde bir `inherits` özniteliği, yalnızca türetilmiş sınıf oluşturulur. Bir taban sınıfı elle yazabilirsiniz, ancak türetilmiş sınıf tarafından kullanılan yöntemleri sağlaması gerekir.  
  
 Daha genel bir durum, önceden işlenmiş başka bir şablonu taban sınıf olarak belirtmenizdir. Temel şablon, türetilmiş şablonlara ait metinle ayrılabilen ortak metin blokları sağlar. Sınıf özelliği blokları kullanabilirsiniz `<#+ ... #>` metin parçaları içeren yöntemlerini tanımlamak için. Örneğin, türetilmiş şablonlarda geçersiz kılınabilen sanal yöntemler sağlayacak şekilde, çıktı metninin çerçevesini temel şablona yerleştirebilirsiniz:  
  
 Çalışma zamanı (önceden işlenmiş) metin şablonu BaseTemplate.tt:  
 ```scr  
This is the common header.  
<#   
  SpecificFragment1();   
#>  
A common central text.  
<#   
  SpecificFragment2();   
#>  
This is the common footer.  
<#+   
  // Declare abstract methods  
  protected virtual void SpecificFragment1() { }  
  protected virtual void SpecificFragment2() { }  
#>  
  
```  
  
 Çalışma zamanı (önceden işlenmiş) metin şablonu DerivedTemplate1.tt:  
 ```csharp  
<#@ template language="C#" inherits="BaseTemplate" #>  
<#   
  // Run the base template:  
  base.TransformText();  
#>  
<#+  
// Provide fragments specific to this derived template:  
protected override void SpecificFragment1()  
{  
#>  
   Fragment 1 for DerivedTemplate1  
<#+  
}  
protected override void SpecificFragment2()  
{  
#>  
   Fragment 2 for DerivedTemplate1  
<#+  
}  
#>  
  
```  
  
 DerivedTemplate1 olanağını çağırmak için uygulama kodu:  
 ```csharp  
Console.WriteLine(new DerivedTemplate().TransformText());  
```  
  
 Sonuç çıktısı:  
 ```  
This is the common header.  
   Fragment 1 for DerivedTemplate1  
A common central text.  
   Fragment 2 for DerivedTemplate1  
This is the common footer.  
```  
  
 Temel ve türetilmiş sınıfları farklı projelerde oluşturabilirsiniz. Temel Proje veya derleme türetilmiş projenin başvurular eklemeyi unutmayın.  
  
 Ayrıca sıradan bir elle yazılmış sınıfı taban sınıf olarak kullanabilirsiniz. Taban sınıfın, türetilmiş sınıf tarafından kullanılan yöntemleri sağlaması gerekir.  
  
> [!WARNING]
>  Kullanırsanız `inherits` ve `hostspecific` öznitelikleri birlikte hostspecific belirtin türetilmiş sınıf ve ana bilgisayar "trueFromBase" = = "true taban sınıf içinde". Bu çift tanımının önler `Host` oluşturulan kodun bir özellik.  
  
### <a name="inheritance-in-a-design-time-text-template"></a>Tasarım zamanı metin şablonunda devralma  
 Tasarım zamanı metin şablonu kendisi için bir dosyadır **özel araç** ayarlanır **TextTemplatingFileGenerator**. Şablon kodu ya da metin, hangi forms parçası bir çıktı dosyası oluşturur, [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] projesi. Çıktı dosyasını oluşturmak için, şablon ilk olarak genellikle görmediğiniz bir ara program kod dosyasına çevrilir. `inherits` Özniteliği, bu Ara kod için temel sınıfı belirtir.  
  
 Tasarım zamanı metin şablonu için türetilmiş herhangi bir temel sınıf belirtebilirsiniz <xref:Microsoft.VisualStudio.TextTemplating.TextTransformation?displayProperty=fullName>. Kullanım `<#@assembly#>` yönergesi derlemeyi yüklemek veya bu proje için temel sınıf içerir.  
  
 Daha fazla bilgi için bkz: ["Devralma metin şablonları" Gareth CAN günlüğündeki](http://go.microsoft.com/fwlink/?LinkId=208373).  
  
## <a name="linepragmas-attribute"></a>LinePragmas özniteliği  
 Örnek:  
 `linePragmas="false"`  
  
 Geçerli değerler:  
 `true` (varsayılan)  
  
 `false`  
  
 Bu özniteliğin false olarak ayarlanması, oluşturulan kod içinde satır numaralarınızı tanımlayan etiketleri kaldırır. Bu, derleyicinin tüm hataları oluşturulan kodun satır numaralarını kullanarak bildireceği anlamına gelir. Metin şablonunun veya oluşturulan kodun hatalarını ayıklamayı seçebileceğiniz için bu size daha fazla hata ayıklama seçeneği sunar.  
  
 Kaynak kodu denetimi altında dikkat dağıtıcı birleştirmeler pragmaları mutlak adlarında neden olan bulma varsa bu öznitelik de yardımcı olabilir.  
  
## <a name="visibility-attribute"></a>Visibility özniteliği  
 Örnek:  
 `visibility="internal"`  
  
 Geçerli değerler:  
 `public` (varsayılan)  
  
 `internal`  
  
 Bir çalışma zamanı şablonunda, bu, oluşturulan sınıfın görünürlük özniteliğini ayarlar. Varsayılan olarak, ortak bir API kodunuzu ancak ayarlayarak parçası sınıftır `visibility="internal"` yalnızca kodunuzun metin oluşturma sınıfı kullanabileceğiniz emin olun.
