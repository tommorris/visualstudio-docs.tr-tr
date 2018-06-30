---
title: Değiştirilebilir parametreler | Microsoft Docs
ms.custom: ''
ms.date: 02/02/2017
ms.technology: office-development
ms.topic: conceptual
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
manager: douge
ms.workload: office
ms.openlocfilehash: f6e311f7c0268cecb94498fffda702438ea921b0
ms.sourcegitcommit: d9e4ea95d0ea70827de281754067309a517205a1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/29/2018
ms.locfileid: "37120621"
---
# <a name="replaceable-parameters"></a>Değiştirilebilir parametreler
  Değiştirilebilir parametreler veya *belirteçleri*, proje dosyalarını gerçek değerleri tasarım zamanında bilinen olmayan SharePoint çözüm öğeleri için değerler sağlamak için kullanılabilir. Standart işlevinde benzer [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)] şablonu belirteçleri. Daha fazla bilgi için bkz: [şablon parametreleri](/visualstudio/ide/template-parameters).  
  
## <a name="token-format"></a>Belirteci biçimi
 Belirteçleri başlar ve bir dolar işareti ($) karakteri ile bitmelidir. Bir proje bir SharePoint çözüm paketi paketlendiğinde, dağıtımda kullanılan herhangi bir belirtece gerçek değerlerle değiştirilir (*.wsp* dosyası). Örneğin, belirteç **$SharePoint.Package.Name$** "Test SharePoint paketi" dizeye çözebilir.  
  
## <a name="token-rules"></a>Belirteç kuralları
 Belirteçleri aşağıdaki kurallar geçerli olur:  
  
-   Belirteçlerin herhangi bir yerden bir satırda belirtilebilir.  
  
-   Belirteçleri birden çok satıra yayılamaz.  
  
-   Aynı belirtecin aynı satırda ve aynı dosyada birden çok kez belirtilebilir.  
  
-   Farklı belirteçleri aynı çizgi üzerinde belirtilebilir.  
  
 Bu kurallar izlemeyin belirteçleri göz ardı edilir ve bir uyarı veya hata neden değil.  
  
 Dize değerlerini tarafından belirteçleri değiştirme hemen bildirim dönüştürme işleminin ardından gerçekleştirilir. Bu değişikliği bildirim şablonları belirteçleri ile düzenlemesine olanak tanır.  
  
### <a name="token-name-resolution"></a>Belirteç ad çözümlemesi
 Çoğu durumda, burada bulunan bağımsız olarak belirli bir değere bir belirteç çözümler. Ancak, belirtecin bir paket veya özellik ilişkili ise, belirtecin değeri, bulunduğu üzerinde bağlıdır. Örneğin, bir özellik ise bir, daha sonra belirteç paketini `$SharePoint.Package.Name$` "Paketi A." değerine çözümler Aynı özellik paketi b'de sonra olup olmadığını `$SharePoint.Package.Name$` "İçin paket b" çözümler  
  
## <a name="tokens-list"></a>Belirteç listesi
 Aşağıdaki tabloda kullanılabilir belirteçleri listeler.  
  
|Ad|Açıklama|  
|----------|-----------------|  
|$SharePoint.Project.FileName$|Proje dosyası gibi içeren adı *NewProj.csproj*.|  
|$SharePoint.Project.FileNameWithoutExtension$|Dosya adı uzantısı olmadan içeren proje dosyasının adı. Örneğin, "NewProj".|  
|$SharePoint.Project.AssemblyFullName$|Derleme çıktı içeren proje görünen adını (tanımlayıcı ad).|  
|$SharePoint.Project.AssemblyFileName$|Derleme çıktı içeren projesinin adı.|  
|$SharePoint.Project.AssemblyFileNameWithoutExtension$|Dosya adı uzantısı olmadan derleme çıktı içeren projesinin adı.|  
|$SharePoint.Project.AssemblyPublicKeyToken$|Ortak anahtar belirteci içeren projesinin bir dizeye dönüştürülür derleme çıktı. ("x2" 16 karakter onaltılık biçimde.)|  
|$SharePoint.Package.Name$|İçeren paketin adı.|  
|$SharePoint.Package.FileName$|İçeren paket tanım dosyası adı.|  
|$SharePoint.Package.FileNameWithoutExtension$|İçeren paket tanım dosyası adı (uzantısı olmadan).|  
|$SharePoint.Package.Id$|SharePoint kimliği içeren paket. Bir özellik birden fazla paketinde kullanılırsa, bu değeri değişir.|  
|$SharePoint.Feature.FileName$|İçeren tanım dosyasının adını özelliğini kullanmak için aşağıdaki gibi *Feature1.feature*.|  
|$SharePoint.Feature.FileNameWithoutExtension$|Özellik tanım dosyası, dosya adı uzantısı olmadan adı.|  
|$SharePoint.Feature.DeploymentPath$|Özellik paketi içeren klasörün adı. Bu belirteç özelliği Tasarımcısı'nda "Dağıtım yolu" özelliğine karşılık gelir. Örnek bir değer olduğundan, "Project1_Feature1".|  
|$SharePoint.Feature.Id$|İçeren özellik SharePoint kimliği. Bu belirteç olarak tüm özellik düzeyinde belirteçleri ile yalnızca bir özelliği aracılığıyla bir pakette bulunan dosyalar tarafından kullanılan bir özellik dışında bir paket için doğrudan eklenmedi.|  
|$SharePoint.ProjectItem.Name$|Öğesinden alınan olarak (kendi dosya adı değil), proje öğesinin adı **ISharePointProjectItem.Name**.|  
|$SharePoint.Type. \<GUID >. AssemblyQualifiedName$|Türü eşleşen derleme nitelenmiş adı [!INCLUDE[TLA2#tla_guid](../sharepoint/includes/tla2sharptla-guid-md.md)] belirteci. Biçimi [!INCLUDE[TLA2#tla_guid](../sharepoint/includes/tla2sharptla-guid-md.md)] küçük harf ve Guid.ToString("D") biçimine karşılık gelir (diğer bir deyişle, xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx).|  
|$SharePoint.Type. \<GUID >. FullName$|Belirteçte GUID eşleşen türünün tam adı. GUID biçimi küçük harf ve Guid.ToString("D") biçimine karşılık gelir (diğer bir deyişle, xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx).|  
  
## <a name="add-extensions-to-the-token-replacement-file-extensions-list"></a>Uzantıları belirteci değiştirme dosya uzantıları listesine ekle
 Belirteçleri teorik olarak bir SharePoint proje öğesi, varsayılan olarak, pakete ait olduğu herhangi bir dosyayı tarafından kullanılabilse de [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)] belirteçleri yalnızca şu uzantılara sahip dosyaları paket dosyaları ve bildirim dosyaları arar:  
  
-   [!INCLUDE[TLA2#tla_xml](../sharepoint/includes/tla2sharptla-xml-md.md)]  
  
-   ASCX  
  
-   ASPX  
  
-   Web Bölümü  
  
-   DWP  
  
 Bu uzantıları tarafından tanımlanan `<TokenReplacementFileExtensions>` Microsoft.VisualStudio.SharePoint.targets dosyasında bulunan öğe... \\< program dosyaları\>\MSBuild\Microsoft\VisualStudio\v11.0\SharePointTools klasör.  
  
 Ancak, ek dosya uzantıları listesine ekleyebilirsiniz. Ekleme bir `<TokenReplacementFileExtensions>` önce tanımlanan tüm PropertyGroup SharePoint proje dosyasında öğesine \<alma > SharePoint hedefleri dosyasının.  
  
> [!NOTE]  
>  Bir proje derlendikten sonra belirteci değiştirme oluştuğundan, gibi derlenen dosya türleri için dosya uzantıları eklememelisiniz *.cs*, *.vb* veya *.resx*. Belirteçleri değil derlenen dosyalar değiştirilir.  
  
 Örneğin, dosya adı uzantısı eklemek için (*.myextension* ve *.yourextension*) belirteci değiştirme dosya adı uzantıları listesine bir proje aşağıdaki eklersiniz (*.csproj* ) dosyası:  
  
```xml  
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
  
 Doğrudan hedefe uzantısını ekleyebilirsiniz (*.targets*) dosyası. Ancak, uzantı değiştirir yerel sistemde paketlenmiş tüm SharePoint projeleri için uzantıları listesi ekleme, değil yalnızca kendi. Sistemdeki tek Geliştirici olduğunda veya projelerinizi çoğunu gerekiyorsa bu uzantı kullanışlı olabilir. Ancak, sisteme özgü olduğundan, bu yaklaşım taşınabilir değildir ve bu nedenle, önerilir, tüm uzantılar için proje dosyası yerine ekleyin.  
  
## <a name="see-also"></a>Ayrıca bkz.
 [SharePoint çözümleri geliştirme](../sharepoint/developing-sharepoint-solutions.md)  
  
