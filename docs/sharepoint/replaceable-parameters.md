---
title: "Değiştirilebilir parametreler | Microsoft Docs"
ms.custom: 
ms.date: 02/02/2017
ms.reviewer: 
ms.suite: 
ms.technology: office-development
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- VB
- CSharp
- VB
- CSharp
helpviewer_keywords:
- SharePoint development in Visual Studio, tokens
- tokens [SharePoint development in Visual Studio]
- replaceable parameters [SharePoint development in Visual Studio]
- SharePoint development in Visual Studio, replaceable parameters
author: TerryGLee
ms.author: tglee
manager: ghogen
ms.workload: office
ms.openlocfilehash: fa002f58ffd749cef9a4cbf9b536a36d7901b105
ms.sourcegitcommit: f9fbf1f55f9ac14e4e5c6ae58c30dc1800ca6cda
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/10/2018
---
# <a name="replaceable-parameters"></a>Değiştirilebilir Parametreler
  Değiştirilebilir parametreler veya *belirteçleri*, proje dosyalarını gerçek değerleri tasarım zamanında bilinmiyor SharePoint çözüm öğeleri için değerler sağlamak için kullanılabilir. Standart işlevinde benzer [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)] şablonu belirteçleri. Daha fazla bilgi için bkz: [şablon parametreleri](/visualstudio/ide/template-parameters).  
  
## <a name="token-format"></a>Belirteci biçimi  
 Belirteçleri başlar ve bir dolar işareti ($) karakteri ile bitmelidir. Bir proje dağıtım sırasında bir SharePoint çözüm paketi (.wsp) dosyası paketlendiğinde kullanılan herhangi bir belirtece gerçek değerlerle değiştirilir. Örneğin, belirteç **$SharePoint.Package.Name$** "Test SharePoint paketi." dizeye giderebilecek  
  
## <a name="token-rules"></a>Belirteç kuralları  
 Belirteçleri aşağıdaki kurallar geçerli olur:  
  
-   Belirteçlerin herhangi bir yerden bir satırda belirtilebilir.  
  
-   Belirteçleri birden çok satıra yayılamaz.  
  
-   Aynı belirtecin, aynı satırda ve aynı dosyada birden çok kez belirtilebilir.  
  
-   Farklı belirteçleri aynı çizgi üzerinde belirtilebilir.  
  
 Bu kurallar izlemeyin belirteçleri, bir uyarı veya hata sağlamadan göz ardı edilir.  
  
 Dize değerlerini tarafından belirteçleri değiştirme, böylece belirteçlerini kullanmak üzere bir kullanıcı tarafından düzenlenmiş olan bildirim şablonları sağlar hemen bildirim dönüştürme sonra yapılır.  
  
### <a name="token-name-resolution"></a>Belirteç ad çözümlemesi  
 Çoğu durumda, burada bulunan bağımsız olarak belirli bir değere bir belirteç çözümler. Ancak, belirtecin bir paket veya özellik ilişkili ise, belirtecin değeri, bulunduğu üzerinde bağlıdır. Örneğin, bir özellik ise bir, daha sonra belirteç paketini `$SharePoint.Package.Name$` "Paketi A." değerine çözümler Aynı özellik paketi b'de sonra olup olmadığını `$SharePoint.Package.Name$` "İçin paket b" çözümler  
  
## <a name="tokens-list"></a>Belirteç listesi  
 Aşağıdaki tabloda kullanılabilir belirteçleri listeler.  
  
|Ad|Açıklama|  
|----------|-----------------|  
|$SharePoint.Project.FileName$|Örneğin, "NewProj.csproj" içeren proje dosyasının adı.|  
|$SharePoint.Project.FileNameWithoutExtension$|Dosya adı uzantısı olmadan içeren proje dosyasının adı. Örneğin, "NewProj".|  
|$SharePoint.Project.AssemblyFullName$|Derleme çıktı içeren proje görünen adını (tanımlayıcı ad).|  
|$SharePoint.Project.AssemblyFileName$|Derleme çıktı içeren projesinin adı.|  
|$SharePoint.Project.AssemblyFileNameWithoutExtension$|Dosya adı uzantısı olmadan derleme çıktı içeren projesinin adı.|  
|$SharePoint.Project.AssemblyPublicKeyToken$|Ortak anahtar belirteci içeren projesinin bir dizeye dönüştürülür derleme çıktı. ("x2" 16 karakter onaltılık biçimde.)|  
|$SharePoint.Package.Name$|İçeren paketin adı.|  
|$SharePoint.Package.FileName$|İçeren paket tanım dosyası adı.|  
|$SharePoint.Package.FileNameWithoutExtension$|İçeren paket tanım dosyası adı (uzantısı olmadan).|  
|$SharePoint.Package.Id$|SharePoint kimliği içeren paket. Bir özellik birden fazla paketinde kullanılırsa, bu değeri değişir.|  
|$SharePoint.Feature.FileName$|Tanım dosyası Feature1.feature gibi içeren özelliğinin adı.|  
|$SharePoint.Feature.FileNameWithoutExtension$|Özellik tanım dosyası, dosya adı uzantısı olmadan adı.|  
|$SharePoint.Feature.DeploymentPath$|Özellik paketi içeren klasörün adı. Bu belirteç özelliği Tasarımcısı'nda "Dağıtım yolu" özelliğine karşılık gelir. Örnek bir değer olduğundan, "Project1_Feature1".|  
|$SharePoint.Feature.Id$|İçeren özellik SharePoint kimliği. Bu belirteç olarak tüm özellik düzeyinde belirteçleri ile yalnızca bir özelliği aracılığıyla bir pakette bulunan dosyalar tarafından kullanılan bir özellik dışında bir paket için doğrudan eklenmedi.|  
|$SharePoint.ProjectItem.Name$|Öğesinden alınan olarak (kendi dosya adı değil), proje öğesinin adı **ISharePointProjectItem.Name**.|  
|$SharePoint.Type. \<GUID >. AssemblyQualifiedName$|Türü eşleşen derleme nitelenmiş adı [!INCLUDE[TLA2#tla_guid](../sharepoint/includes/tla2sharptla-guid-md.md)] belirteci. Biçimi [!INCLUDE[TLA2#tla_guid](../sharepoint/includes/tla2sharptla-guid-md.md)] küçük harf ve Guid.ToString("D") biçimine karşılık gelir (diğer bir deyişle, xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx).|  
|$SharePoint.Type. \<GUID >. FullName$|Belirteçte GUID eşleşen türünün tam adı. GUID biçimi küçük harf ve Guid.ToString("D") biçimine karşılık gelir (diğer bir deyişle, xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx).|  
  
## <a name="adding-extensions-to-the-token-replacement-file-extensions-list"></a>Dosya uzantıları listesi ekleme uzantıları için belirteç değiştirme  
 Belirteçleri teorik olarak bir SharePoint proje öğesi, varsayılan olarak, pakete ait olduğu herhangi bir dosyayı tarafından kullanılabilse de [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)] belirteçleri yalnızca şu uzantılara sahip dosyaları paket dosyaları ve bildirim dosyaları arar:  
  
-   [!INCLUDE[TLA2#tla_xml](../sharepoint/includes/tla2sharptla-xml-md.md)]  
  
-   ASCX  
  
-   ASPX  
  
-   Web Bölümü  
  
-   DWP  
  
 Bu uzantıları tarafından tanımlanan `<TokenReplacementFileExtensions>` Microsoft.VisualStudio.SharePoint.targets dosyasında bulunan öğe... \\< program dosyaları\>\MSBuild\Microsoft\VisualStudio\v11.0\SharePointTools klasör.  
  
 Ancak, ek dosya uzantıları listesine ekleyebilirsiniz. Bunu yapmak için ekleyin bir `<TokenReplacementFileExtensions>` önce tanımlanan tüm PropertyGroup SharePoint proje dosyasında öğesine \<alma > SharePoint hedefleri dosyasının.  
  
> [!NOTE]  
>  Bir proje derlendikten sonra belirteci değiştirme oluştuğundan, dosya uzantılarını derlenen dosya türleri için .cs, .vb veya .resx gibi eklemeyin. Belirteçleri değil derlenen dosyalar değiştirilir.  
  
 Örneğin, dosya adı uzantıları ".myextension" ve ".yourextension" belirteci değiştirme dosya adı uzantıları listesine eklemek için aşağıdaki .csproj dosyasına ekleyin:  
  
```  
<Project ToolsVersion="4.0" DefaultTargets="Build" xmlns="http://schemas.microsoft.com/developer/msbuild/2003">  
  <PropertyGroup>  
    <Configuration Condition=" '$(Configuration)' == '' ">Debug</Configuration>  
    <Platform Condition=" '$(Platform)' == '' ">AnyCPU</Platform>  
.  
.  
.  
    <!-- Define the following property to add your extension to the list of token replacement file extensions.  -->  
<TokenReplacementFileExtensions>myextension;yourextension</TokenReplacementFileExtensions>  
</PropertyGroup>  
```  
  
 Alternatif olarak, doğrudan .targets dosya uzantısını ekleyebilirsiniz. Ancak, bunu yerel sistemde yalnızca paketlenmiş tüm SharePoint projeleri için uzantıları listesi değiştirir kendi. Sistemdeki tek Geliştirici olduğunda veya projelerinizi çoğunu gerektiriyorsa, bu bağlantı kullanışlı olabilir. Ancak, sisteme özgü olduğundan, bu yaklaşım çok taşınabilir değildir ve bu nedenle, önerilir, tüm uzantılar için proje dosyası yerine ekleyin.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [SharePoint Çözümleri Geliştirme](../sharepoint/developing-sharepoint-solutions.md)  
  
  