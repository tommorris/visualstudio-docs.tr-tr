---
title: "Metin şablonu yardımcı program yöntemleri | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: text templates, utility methods
ms.assetid: 8c11f9f7-678b-4f0c-b634-dc78fda699d1
caps.latest.revision: "50"
author: alancameronwills
ms.author: awills
manager: douge
ms.openlocfilehash: 534a7317b4bca2abe559c028d025a52997a9f508
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2017
---
# <a name="text-template-utility-methods"></a>Metin Şablonu Yardımcı Program Yöntemleri
Kodu yazarken her zaman kullanılabilen çeşitli yöntemler vardır bir [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] metin şablonu. Bu yöntemler tanımlanan <xref:Microsoft.VisualStudio.TextTemplating.TextTransformation>.  
  
> [!TIP]
>  Diğer yöntemleri ve normal (önceden işlenmiş değil) metin şablonu ana ortamında tarafından sağlanan hizmetlerin de kullanabilirsiniz. Örneğin, dosya yolları çözümlemek, oturum hataları ve Hizmetleri tarafından sağlanan alma [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] ve herhangi bir yüklenen paketler.  Daha fazla bilgi için bkz: [metin şablonu Visual Studio'dan erişme](http://msdn.microsoft.com/en-us/0556f20c-fef4-41a9-9597-53afab4ab9e4).  
  
## <a name="write-methods"></a>Yöntemleri yazma  
 Kullanabileceğiniz `Write()` ve `WriteLine()` bir ifade kod bloğunu kullanmak yerine bir standart kod bloğunun metin eklenecek yöntemleri. Aşağıdaki iki kod blokları işlevsel olarak eşdeğerdir.  
  
##### <a name="code-block-with-an-expression-block"></a>Bir ifade bloğu ile kod bloğu  
  
```  
<#  
int i = 10;  
while (i-- > 0)  
    { #>  
        <#= i #>  
    <# }  
#>  
```  
  
##### <a name="code-block-using-writeline"></a>Kod bloğu WriteLine() kullanma  
  
```  
<#   
    int i = 10;  
    while (i-- > 0)  
    {   
        WriteLine((i.ToString()));  
    }  
#>  
```  
  
 Bu yardımcı program yöntemleri biri iç içe geçmiş denetim yapıları ile uzun kod bloğunun bir ifade bloğu yerine kullanmak daha yararlı olabilir.  
  
 `Write()` Ve `WriteLine()` yöntemlerine sahip iki aşırı yüklemeleri, tek bir dize parametresi ve bir alan bir alan bileşik biçim dizesi artı dizesine eklemek için nesneleri içeren bir dizi (gibi `Console.WriteLine()` yöntemi). Aşağıdaki iki kullanımlarını `WriteLine()` işlevsel olarak eşdeğerdir:  
  
```  
<#  
    string msg = "Say: {0}, {1}, {2}";  
    string s1 = "hello";  
    string s2 = "goodbye";  
    string s3 = "farewell";  
  
    WriteLine(msg, s1, s2, s3);  
    WriteLine("Say: hello, goodbye, farewell");  
#>   
```  
  
## <a name="indentation-methods"></a>Girinti yöntemleri  
 Metin şablonu çıktısını biçimlendirmek için girinti yöntemlerini kullanabilirsiniz. <xref:Microsoft.VisualStudio.TextTemplating.TextTransformation> Sınıfına sahip bir `CurrentIndent` dizesi metin şablonu geçerli girintileme gösterir özelliğinin ve bir `indentLengths` diğer bir deyişle, eklenen girintileri listesini alan. İle bir girinti ekleyebilir `PushIndent()` yöntemi ve girinti ile çıkarma `PopIndent()` yöntemi. Tüm girintileri kaldırmak istiyorsanız, kullanmak `ClearIndent()` yöntemi. Aşağıdaki kod bloğu bu yöntemleri kullanımını göstermektedir:  
  
```  
<#  
    WriteLine(CurrentIndent + "Hello");  
    PushIndent("    ");  
    WriteLine(CurrentIndent + "Hello");  
    PushIndent("    ");  
    WriteLine(CurrentIndent + "Hello");  
    ClearIndent();  
    WriteLine(CurrentIndent + "Hello");  
    PushIndent("    ");  
    WriteLine(CurrentIndent + "Hello");  
#>  
```  
  
 Bu kod bloğu şu çıkışı üretir:  
  
```  
Hello  
        Hello  
                Hello  
Hello  
        Hello  
```  
  
## <a name="error-and-warning-methods"></a>Hata ve uyarı yöntemleri  
 Hata ve uyarı yardımcı program yöntemleri iletilerine eklemek için kullanabileceğiniz [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] hata listesi. Örneğin, aşağıdaki kodu bir hata iletisi için hata listesine ekler.  
  
```  
<#  
  try  
  {  
    string str = null;  
    Write(str.Length.ToString());  
  }  
  catch (Exception e)  
  {  
    Error(e.Message);  
  }  
#>    
```  
  
## <a name="access-to-host-and-service-provider"></a>Ana bilgisayar ve hizmet sağlayıcısı erişim  
 Özellik `this.Host` şablonunun yürütülmesinin ana bilgisayar tarafından kullanıma sunulan özellikler erişim sağlayabilir. Kullanılacak `this.Host`, ayarlamalısınız `hostspecific` özniteliğini `<@template#>` yönergesi:  
  
 `<#@template ... hostspecific="true" #>`  
  
 Türü `this.Host` şablonunun yürütülmesinin içinde ana bilgisayar türüne bağlıdır. Çalıştıran bir şablona [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)], size çevirebilirsiniz `this.Host` için `IServiceProvider` IDE gibi hizmetlerine erişmek için. Örneğin:  
  
```  
EnvDTE.DTE dte = (EnvDTE.DTE) ((IServiceProvider) this.Host)  
                       .GetService(typeof(EnvDTE.DTE));  
```  
  
## <a name="using-a-different-set-of-utility-methods"></a>Farklı bir yardımcı program yöntemleri kümesini kullanma  
 Metin oluşturma işleminin bir parçası olarak, her zaman olarak adlandırılan bir sınıfına şablon dosyanızın dönüştürüldüğünde `GeneratedTextTransformation`ve devraldığı <xref:Microsoft.VisualStudio.TextTemplating.TextTransformation>. Farklı bir kullanmak istiyorsanız, bunun yerine, yöntemlerini ayarlayın, kendi sınıfı yazmak ve şablon yönergesi belirtin. Sınıfınızda öğesinden devralmalıdır <xref:Microsoft.VisualStudio.TextTemplating.TextTransformation>.  
  
```  
<#@ template inherits="MyUtilityClass" #>  
```  
  
 Kullanım `assembly` derlenmiş sınıfı burada bulunabilir derleme başvurusu yönergesi.