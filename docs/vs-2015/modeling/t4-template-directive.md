---
title: T4 Şablon yönergesi | Microsoft Docs
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-tfs-dev14
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 2b0a8e04-6fee-4c6c-b086-e49fc728a3ed
caps.latest.revision: 12
author: gewarren
ms.author: gewarren
manager: douge
ms.openlocfilehash: 01369002b5deaa5456d09d6a93e774ad36f85c34
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/22/2018
ms.locfileid: "42678294"
---
# <a name="t4-template-directive"></a>T4 Şablon Yönergesi
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Bu konuda en son sürümünü şu yolda bulunabilir: [T4 şablon yönergesi](https://docs.microsoft.com/visualstudio/modeling/t4-template-directive).  
  
A [!INCLUDE[vsprvs](../includes/vsprvs-md.md)] T4 metin şablonu genellikle başlar ile bir `template` şablonun nasıl işlenmesi belirten yönergesi. Bir metin şablonu ve içerdiği herhangi bir dosya içinde birden fazla şablon yönergesi bulunmamalıdır.  
  
 Metin şablonlarını yazmayla ilgili genel bilgiler için bkz: [T4 metin şablonu yazma](../modeling/writing-a-t4-text-template.md).  
  
## <a name="using-the-template-directive"></a>Şablon Yönergesini Kullanma  
  
```  
<#@ template [language="VB"] [compilerOptions="options"] [culture="code"] [debug="true"] [hostspecific="true"] [inherits="templateBaseClass"] [visibility="internal"] [linePragmas="false"] #>  
```  
  
 `template` Yönergesi dönüşümün farklı özelliklerini belirtmenize olanak tanıyan çeşitli öznitelikler içeriyor. Tüm öznitelikler isteğe bağlıdır.  
  
## <a name="compileroptions-attribute"></a>compilerOptions özniteliği  
 Örnek:  
 `compilerOptions="optimize+"`  
  
 Geçerli değerler:  
 Tüm geçerli derleyici seçenekleri. Daha fazla bilgi için [C# derleyici seçenekleri kategoriye göre listelenmiş](http://msdn.microsoft.com/library/96437ecc-6502-4cd3-b070-e9386a298e83) ve [Visual Basic derleyici seçenekleri listelenen kategoriye göre](http://msdn.microsoft.com/library/fbe36f7a-7cfa-4f77-a8d4-2be5958568e3).  
  
 Çalışma zamanı (önceden işlenmiş) şablonları için yok sayılır.  
  
 Şablon dönüştürüldükten Bu seçenekler uygulanır [!INCLUDE[csprcs](../includes/csprcs-md.md)] veya [!INCLUDE[vb_current_short](../includes/vb-current-short-md.md)], ve sonuçta elde edilen kod derlenir.  
  
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
  
 Varsa `debug` özniteliği `true`, Ara kod dosyası hata ayıklayıcının şablonunuzda bir kesme veya özel durumun oluştuğu konumu daha doğru bir şekilde tanımlamak için sağlayan bilgiler içerir.  
  
 Tasarım zamanı şablonları için Ara kod dosyası için yazılır, **% TEMP %** dizin.  
  
 Hata ayıklayıcıda bir tasarım zamanı şablonu çalıştırmak için metin şablonu kaydettikten sonra Çözüm Gezgini'ndeki metin şablonunun kısayol menüsünü açın ve seçin **T4 şablonunda Hata Ayıkla**.  
  
## <a name="hostspecific-attribute"></a>hostspecific özniteliği  
 Örnek:  
 ```  
hostspecific="true"  
```  
  
 Geçerli değerler:  
 `true, false, trueFromBase`. False, varsayılan değerdir.  
  
 Bu özniteliğin değerini ayarlarsanız `true`, adlı bir özellik `Host` metin şablonunuz tarafından oluşturulan sınıfa eklenir. Özellik dönüşüm motorunun ana bilgisayarına bir başvurudur ve olarak bildirilen <xref:Microsoft.VisualStudio.TextTemplating.ITextTemplatingEngineHost>. Özel bir sunucu tanımladıysanız, bunu özel ana bilgisayar türüne atayabilirsiniz.  
  
 Bu özelliğin türü ana bilgisayarın türüne bağlı olduğundan, yalnızca belirli bir ana bilgisayar ile çalışan bir metin şablonu yazıyorsanız faydalıdır. İçin geçerli [tasarım zamanı şablonları](../modeling/design-time-code-generation-by-using-t4-text-templates.md), ama [çalışma zamanı şablonları](../modeling/run-time-text-generation-with-t4-text-templates.md).  
  
 Zaman `hostspecific` olduğu `true` ve kullanmakta olduğunuz [!INCLUDE[vsprvs](../includes/vsprvs-md.md)], atayabilirsiniz `this.Host` erişmeye IServiceProvider için [!INCLUDE[vsprvs](../includes/vsprvs-md.md)] özellikleri. Ayrıca `Host.ResolvePath(filename)` projedeki bir dosyanın mutlak yolunu elde etmek için. Örneğin:  
  
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
  
 Kullanırsanız `inherits` ve `hostspecific` öznitelikleri birlikte çalışarak, ana bilgisayar belirtin = "trueFromBase" türetilmiş bir sınıf ve ana bilgisayar = "ve taban sınıfta true". Bu bir çift tanımını önler `Host` oluşturulan kodda özelliği.  
  
## <a name="language-attribute"></a>language özniteliği  
 Örnek:  
 `language="VB"`  
  
 Geçerli değerler:  
 `C#` (varsayılan)  
  
 `VB`  
  
 Language özniteliği dili belirtir ([!INCLUDE[vbprvb](../includes/vbprvb-md.md)] veya [!INCLUDE[csprcs](../includes/csprcs-md.md)]) deyim ve ifade bloklarında kaynak kod için kullanılacak. Çıktının oluşturulmasında kullanılan ara kod dosyası bu dili kullanır. Bu dil, şablonunuzun oluşturduğu ve herhangi bir türdeki bir metin olabilecek dille ilişkili değildir.  
  
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
 Türetilmiş birkaç varyanta sahip bir temel şablon oluşturmak için çalışma zamanı metin şablonları arasında devralmayı kullanabilirsiniz. Çalışma zamanı şablonları olanlardır **özel araç** özelliğini **TextTemplatingFilePreprocessor**. Çalışma zamanı şablonu, şablonda tanımlanan metin oluşturmak için uygulamanızda çağırabildiğiniz bir kod oluşturur. Daha fazla bilgi için [T4 metin şablonları ile çalışma süresi metni oluşturma](../modeling/run-time-text-generation-with-t4-text-templates.md).  
  
 Belirtmezseniz, bir `inherits` öznitelik, bir temel sınıf ve türetilen sınıf metin şablonunuzdan oluşturulur. Belirttiğinizde bir `inherits` özniteliği, yalnızca türetilmiş sınıf oluşturulur. Bir taban sınıfı elle yazabilirsiniz, ancak türetilmiş sınıf tarafından kullanılan yöntemleri sağlaması gerekir.  
  
 Daha genel bir durum, önceden işlenmiş başka bir şablonu taban sınıf olarak belirtmenizdir. Temel şablon, türetilmiş şablonlara ait metinle ayrılabilen ortak metin blokları sağlar. Sınıf özelliği bloklarını kullanabileceğiniz `<#+ ... #>` metin parçalarını içeren yöntemleri tanımlamak için. Örneğin, türetilmiş şablonlarda geçersiz kılınabilen sanal yöntemler sağlayacak şekilde, çıktı metninin çerçevesini temel şablona yerleştirebilirsiniz:  
  
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
  
 Temel ve türetilmiş sınıfları farklı projelerde oluşturabilirsiniz. Temel projeyi veya derlemeyi, türetilmiş projenin başvurularına eklemeyi unutmayın.  
  
 Ayrıca sıradan bir elle yazılmış sınıfı taban sınıf olarak kullanabilirsiniz. Taban sınıfın, türetilmiş sınıf tarafından kullanılan yöntemleri sağlaması gerekir.  
  
> [!WARNING]
>  Kullanırsanız `inherits` ve `hostspecific` öznitelikleri birlikte belirtin hostspecific = "trueFromBase" türetilmiş bir sınıf ve ana bilgisayar = "ve taban sınıfta true". Bu bir çift tanımını önler `Host` oluşturulan kodda özelliği.  
  
### <a name="inheritance-in-a-design-time-text-template"></a>Tasarım zamanı metin şablonunda devralma  
 Tasarım zamanı metin şablonu, bir dosyadır **özel araç** ayarlanır **TextTemplatingFileGenerator**. Şablon kod veya metin parçasını çıktı dosyası oluşturur, [!INCLUDE[vsprvs](../includes/vsprvs-md.md)] proje. Çıktı dosyasını oluşturmak için, şablon ilk olarak genellikle görmediğiniz bir ara program kod dosyasına çevrilir. `inherits` Özniteliği, bu Ara kod için temel sınıfı belirtir.  
  
 Tasarım zamanı metin şablonu için türetilmiş herhangi bir taban sınıfı belirtebilirsiniz <xref:Microsoft.VisualStudio.TextTemplating.TextTransformation?displayProperty=fullName>. Kullanım `<#@assembly#>` yönergesi derlemeyi veya projeyi için temel sınıfı içerir.  
  
 Daha fazla bilgi için ["Devralma içinde metin şablonlarında" Gareth Jones'un Blogundaki](http://go.microsoft.com/fwlink/?LinkId=208373).  
  
## <a name="linepragmas-attribute"></a>LinePragmas özniteliği  
 Örnek:  
 `linePragmas="false"`  
  
 Geçerli değerler:  
 `true` (varsayılan)  
  
 `false`  
  
 Bu özniteliğin false olarak ayarlanması, oluşturulan kod içinde satır numaralarınızı tanımlayan etiketleri kaldırır. Bu, derleyicinin tüm hataları oluşturulan kodun satır numaralarını kullanarak bildireceği anlamına gelir. Metin şablonunun veya oluşturulan kodun hatalarını ayıklamayı seçebileceğiniz için bu size daha fazla hata ayıklama seçeneği sunar.  
  
 Bu öznitelik, pragmalardaki mutlak dosya adlarının kaynak kodu denetimi altında dikkat dağıtıcı birleştirmelere neden olduğunu fark etmeniz durumda da yardımcı olabilir.  
  
## <a name="visibility-attribute"></a>Visibility özniteliği  
 Örnek:  
 `visibility="internal"`  
  
 Geçerli değerler:  
 `public` (varsayılan)  
  
 `internal`  
  
 Bir çalışma zamanı şablonunda, bu, oluşturulan sınıfın görünürlük özniteliğini ayarlar. Varsayılan olarak, kodunuzun ancak ayarlayarak Genel API parçası sınıftır `visibility="internal"` yalnızca sizin kodunuzun metin oluşturma sınıfını kullanabilmesini yapabilirsiniz.



