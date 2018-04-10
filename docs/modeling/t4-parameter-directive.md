---
title: T4 Parametre yönergesi | Microsoft Docs
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
ms.openlocfilehash: f44e25f9256cd37692970e92744d7564bc3abd19
ms.sourcegitcommit: 3b692c9bf332b7b9150901e16daf99a64b599fee
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/10/2018
---
# <a name="t4-parameter-directive"></a>T4 Parametre Yönergesi
İçinde bir [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] metin şablonu `parameter` yönergesi dış bağlamdan geçirilen değerlerinden başlatılmış şablon kodunuzu özelliklerinde bildirir. Metin dönüştürmeyi çağıran kodu yazarsanız, bu değerleri ayarlayabilirsiniz.  
  
## <a name="using-the-parameter-directive"></a>Using parametre yönergesi  
  
```  
<#@ parameter type="Full.TypeName" name="ParameterName" #>  
```  
  
 `parameter` Yönergesi dış bağlamdan geçirilen değerlerinden başlatılmış şablon kodunuzu özelliklerinde bildirir. Metin dönüştürmeyi çağıran kodu yazarsanız, bu değerleri ayarlayabilirsiniz. Değerleri ya da geçirilebilir `Session` sözlüğü veya <xref:System.Runtime.Remoting.Messaging.CallContext>.  
  
 Herhangi bir Uzaktan erişilebilir tür parametreleri bildirebilirsiniz. Diğer bir deyişle, türü ile bildirilmelidir <xref:System.SerializableAttribute>, veya öğesinden türetilmelidir <xref:System.MarshalByRefObject>. Bu şablon işlenen AppDomain içinde iletilecek parametre değerlerini sağlar.  
  
 Örneğin, aşağıdaki içeriğe sahip bir metin şablonuna yazabilirsiniz:  
  
```  
<#@ template language="C#" #>  
  
<#@ parameter type="System.Int32" name="TimesToRepeat" #>  
  
<# for (int i = 0; i < TimesToRepeat; i++) { #>  
Line <#= i #>  
<# } #>  
  
```  
  
## <a name="passing-parameter-values-to-a-template"></a>Bir şablon parametre değerlerini geçirme  
 Yazıyorsanız bir [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] uzantısı menü komutu veya bir olay işleyicisi gibi metin şablonu oluşturma hizmeti kullanarak bir şablon işleyebilir:  
  
```csharp  
// Get a service provider - how you do this depends on the context:  
IServiceProvider serviceProvider = dte; // or dslDiagram.Store, for example   
// Get the text template service:  
ITextTemplating t4 = serviceProvider.GetService(typeof(STextTemplating)) as ITextTemplating;  
ITextTemplatingSessionHost host = t4 as ITextTemplatingSessionHost;  
// Create a Session in which to pass parameters:  
host.Session = host.CreateSession();  
// Add parameter values to the Session:  
session["TimesToRepeat"] = 5;  
// Process a text template:  
string result = t4.ProcessTemplate("MyTemplateFile.t4",  
  System.IO.File.ReadAllText("MyTemplateFile.t4"));  
  
```  
  
## <a name="passing-values-in-the-call-context"></a>Çağrı bağlamda değerleri geçirme  
 Alternatif olarak mantıksal veri değerlerinin geçmesini sağlayabilirsiniz <xref:System.Runtime.Remoting.Messaging.CallContext>.  
  
 Aşağıdaki örnekte, her iki yöntemi kullanarak değerleri geçirir:  
  
```csharp  
ITextTemplating t4 = this.Store.GetService(typeof(STextTemplating)) as ITextTemplating;  
ITextTemplatingSessionHost host = t4 as ITextTemplatingSessionHost;  
host.Session = host.CreateSession();  
// Pass a value in Session:  
host.Session["p1"] = 32;  
// Pass another value in CallContext:  
System.Runtime.Remoting.Messaging.CallContext.LogicalSetData("p2", "test");  
  
// Process a small template inline:  
string result = t4.ProcessTemplate("",   
   "<#@parameter type=\"System.Int32\" name=\"p1\"#>"  
 + "<#@parameter type=\"System.String\" name=\"p2\"#>"  
 + "Test <#=p1#> <#=p2#>");  
  
// Result value is:  
//     Test 32 test  
  
```  
  
## <a name="passing-values-to-a-run-time-preprocessed-text-template"></a>Bir çalışma zamanı (Preprocessed) metin şablonu değerleri geçirme  
 Kullanmak için genellikle gerekli değil `<#@parameter#>` çalışma zamanı (önceden işlenmiş) metin şablonları ile yönergesi. Bunun yerine, ek bir oluşturucu ya da ayarlanabilir bir özellik parametre değerlerinin geçmesini üretilen kod için tanımlayabilirsiniz. Daha fazla bilgi için bkz: [T4 metin şablonları ile çalışma zamanı metin oluşturma](../modeling/run-time-text-generation-with-t4-text-templates.md).  
  
 Ancak, kullanmak istiyorsanız, `<#@parameter>` bir çalışma zamanı şablonunda değerleri için oturum sözlüğünü kullanarak geçirebilirsiniz. Örnek olarak, oluşturduğunuz dosya adlı önceden işlenmiş şablon olarak varsayalım `PreTextTemplate1`. Aşağıdaki kodu kullanarak programınıza şablon çağırabilirsiniz.  
  
```csharp  
PreTextTemplate1 t = new PreTextTemplate1();  
t.Session = new Microsoft.VisualStudio.TextTemplating.TextTemplatingSession();  
t.Session["TimesToRepeat"] = 5;  
// Add other parameter values to t.Session here.  
t.Initialize(); // Must call this to transfer values.  
string resultText = t.TransformText();  
  
```  
  
## <a name="obtaining-arguments-from-texttemplateexe"></a>Bağımsız değişkenler TextTemplate.exe alma  
  
> [!IMPORTANT]
>  `parameter` Yönergesi kümesinde değerlerini alır değil `-a` parametresinin `TextTransform.exe` yardımcı programı. Bu değerleri almak üzere `hostSpecific="true"` içinde `template` yönergesi ve kullanım `this.Host.ResolveParameterValue("","","argName")`.