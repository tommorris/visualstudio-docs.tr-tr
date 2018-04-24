---
title: Bir VS Uzantısında Metin Dönüştürmeyi Çağırma
ms.date: 11/04/2016
ms.topic: conceptual
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.technology: vs-ide-modeling
ms.openlocfilehash: 6fc7190fc8cf2661dd64bbcb6f335d0e63a04e29
ms.sourcegitcommit: 4c0bc21d2ce2d8e6c9d3b149a7d95f0b4d5b3f85
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/20/2018
---
# <a name="invoking-text-transformation-in-a-vs-extension"></a>Bir VS Uzantısında Metin Dönüştürmeyi Çağırma
Visual Studio uzantısı menü komutu gibi yazma varsa veya [etki alanına özgü dil](../modeling/modeling-sdk-for-visual-studio-domain-specific-languages.md), metin şablonları dönüştürme için metin şablonu oluşturma hizmeti kullanabilirsiniz. Alma <xref:Microsoft.VisualStudio.TextTemplating.VSHost.STextTemplating> hizmet ve hangisine <xref:Microsoft.VisualStudio.TextTemplating.VSHost.ITextTemplating>.

## <a name="getting-the-text-templating-service"></a>Metin şablonu oluşturma hizmetini alma

```csharp
using Microsoft.VisualStudio.TextTemplating;
using Microsoft.VisualStudio.TextTemplating.VSHost;
...
// Get a service provider - how you do this depends on the context:
IServiceProvider serviceProvider = ...; // An instance of EnvDTE, for example

// Get the text template service:
ITextTemplating t4 = serviceProvider.GetService(typeof(STextTemplating)) as ITextTemplating;

// Process a text template:
string result = t4.ProcessTemplate(filePath, System.IO.File.ReadAllText(filePath));

```

## <a name="passing-parameters-to-the-template"></a>Parametreleri şablona geçirme
 Parametreleri şablona geçirebilirsiniz. Şablon içinde kullanarak parametre değerleri alabilirsiniz `<#@parameter#>` yönergesi.

 Parametre türü için, seri hale getirilebilen veya sıralanabilen bir tür kullanmalısınız. Diğer bir deyişle, türü ile bildirilmelidir <xref:System.SerializableAttribute>, veya öğesinden türetilmelidir <xref:System.MarshalByRefObject>. Bu kısıtlama gereklidir çünkü metin şablonu ayrı bir AppDomain içinde yürütülür. Tüm yerleşik türleri gibi **System.String** ve **System.Int32** olan seri hale getirilebilir.

 Parametre değerleri geçirmek için arama kodunu değerleri ya da koyabilirsiniz içinde `Session` sözlüğü veya <xref:System.Runtime.Remoting.Messaging.CallContext>.

 Aşağıdaki örnek bir kısa test şablonunu dönüştürmek için her iki yöntemi kullanmaktadır:

```
using Microsoft.VisualStudio.TextTemplating;
using Microsoft.VisualStudio.TextTemplating.VSHost;
...
// Get a service provider - how you do this depends on the context:
IServiceProvider serviceProvider = dte;

// Get the text template service:
ITextTemplating t4 = serviceProvider.GetService(typeof(STextTemplating)) as ITextTemplating;
ITextTemplatingSessionHost sessionHost = t4 as ITextTemplatingSessionHost;

// Create a Session in which to pass parameters:
sessionHost.Session = sessionHost.CreateSession();
sessionHost.Session["parameter1"] = "Hello";
sessionHost.Session["parameter2"] = DateTime.Now;

// Pass another value in CallContext:
System.Runtime.Remoting.Messaging.CallContext.LogicalSetData("parameter3", 42);

// Process a text template:
string result = t4.ProcessTemplate("",
   // This is the test template:
   "<#@parameter type=\"System.String\" name=\"parameter1\"#>"
 + "<#@parameter type=\"System.DateTime\" name=\"parameter2\"#>"
 + "<#@parameter type=\"System.Int32\" name=\"parameter3\"#>"
 + "Test: <#=parameter1#>    <#=parameter2#>    <#=parameter3#>");

// This test code yields a result similar to the following line:
//     Test: Hello    07/06/2010 12:37:45    42

```

## <a name="error-reporting-and-the-output-directive"></a>Hata Raporlama ve Çıkış Yönergesi
 İşleme sırasında ortaya herhangi bir hata görüntülenir [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] hata penceresi. Ayrıca, hataların uygulayan bir geri çağırma belirterek bildirilebilir <xref:Microsoft.VisualStudio.TextTemplating.VSHost.ITextTemplatingCallback>.

 Sonuç dizesini bir dosyaya yazmak istiyorsanız, hangi dosya uzantısı bilmek isteyebilirsiniz ve kodlama belirtildi içinde `<#@output#>` şablondaki yönergesi. Bu bilgiler, geri çağırmanıza da geçirilir. Daha fazla bilgi için bkz: [T4 çıkış yönergesi](../modeling/t4-output-directive.md).

```csharp
void ProcessMyTemplate(string MyTemplateFile)
{
  string templateContent = File.ReadAllText(MyTemplateFile);
  T4Callback cb = new T4Callback();
  // Process a text template:
  string result = t4.ProcessTemplate(MyTemplateFile, templateContent, cb);
  // If there was an output directive in the MyTemplateFile,
  // then cb.SetFileExtension() will have been called.
  // Determine the output file name:
  string resultFileName =
    Path.Combine(Path.GetDirectoryName(MyTemplateFile),
        Path.GetFileNameWithoutExtension(MyTemplateFile))
      + cb.fileExtension;
  // Write the processed output to file:
  File.WriteAllText(resultFileName, result, cb.outputEncoding);
  // Append any error messages:
  if (cb.errorMessages.Count > 0)
  {
    File.AppendAllLines(resultFileName, cb.errorMessages);
  }
}

class T4Callback : ITextTemplatingCallback
{
  public List<string> errorMessages = new List<string>();
  public string fileExtension = ".txt";
  public Encoding outputEncoding = Encoding.UTF8;

  public void ErrorCallback(bool warning, string message, int line, int column)
  { errorMessages.Add(message); }

  public void SetFileExtension(string extension)
  { fileExtension = extension; }

  public void SetOutputEncoding(Encoding encoding, bool fromOutputDirective)
  { outputEncoding = encoding; }
}

```

 Kod, şuna benzer bir şablon dosyasıyla test edilebilir:

```
<#@output extension=".htm" encoding="ASCII"#>
<# int unused;  // Compiler warning "unused variable"
#>
Sample text.
```

 Derleyici Uyarısı görünür [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] hata penceresini ve bu da oluşturacağını yapılan bir çağrı `ErrorCallback`.

## <a name="reference-parameters"></a>Başvuru parametreleri
 Türetilen bir parametre sınıfı kullanarak bir metin şablonuna dışı değerleri geçirebilirsiniz <xref:System.MarshalByRefObject>.

## <a name="related-topics"></a>İlgili Konular
 Metin önceden işlenmiş metin şablonu oluşturmak için: çağrı `TransformText()` oluşturulan sınıfın yöntemi. Daha fazla bilgi için bkz: [T4 metin şablonları ile çalışma zamanı metin oluşturma](../modeling/run-time-text-generation-with-t4-text-templates.md).

 Metin dışında oluşturmak için bir [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] uzantısı: özel bir sunucu tanımlayın. Daha fazla bilgi için bkz: [özel konak kullanarak metin şablonlarını işleme](../modeling/processing-text-templates-by-using-a-custom-host.md).

 Daha sonra derlenmiş ve yürütülen kaynak kodu oluşturmak için: çağrı `t4.PreprocessTemplate()` yöntemi <xref:Microsoft.VisualStudio.TextTemplating.VSHost.ITextTemplating>.
