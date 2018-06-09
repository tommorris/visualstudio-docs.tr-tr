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
ms.workload:
- office
ms.openlocfilehash: 407094a1598fa9870866830ac0c40b78a9f615a8
ms.sourcegitcommit: 269b55b413d2c82e6aa56c6ab8e53da7926fb2e8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/08/2018
ms.locfileid: "35237971"
---
# <a name="replaceable-parameters"></a>Değiştirilebilir Parametreler

Değiştirilebilir parametreler veya *belirteçleri*, proje dosyalarını gerçek değerleri tasarım zamanında bilinen olmayan SharePoint çözüm öğeleri için değerler sağlamak için kullanılabilir. Bunlar, standart Visual Studio şablon belirteçleri işlevinde benzer. Daha fazla bilgi için bkz: [şablon parametreleri](../ide/template-parameters.md).

## <a name="token-format"></a>Belirteci biçimi

Belirteçleri başlar ve bir dolar işareti ($) karakteri ile bitmelidir. Bir proje dağıtım sırasında bir SharePoint çözüm paketi (.wsp dosyası) içine paketlendiğinde belirteçleri gerçek değerlerle değiştirilir. Örneğin, belirteç **$SharePoint.Package.Name$** "Test SharePoint paketi" dizeye çözebilir.

## <a name="token-rules"></a>Belirteç kuralları

Belirteçleri aşağıdaki kurallar geçerli olur:

- Belirteçlerin herhangi bir yerden bir satırda belirtilebilir.

- Belirteçleri birden çok satıra yayılamaz.

- Aynı belirtecin, aynı satırda ve aynı dosyada birden çok kez belirtilebilir.

- Farklı belirteçleri aynı çizgi üzerinde belirtilebilir.

Bu kurallar izlemeyin belirteçleri, bir uyarı veya hata sağlamadan göz ardı edilir.

Dize değerlerini tarafından belirteçleri değiştirme hemen bildirim dönüştürme işleminin ardından gerçekleştirilir. Bu değişikliği bildirim şablonları belirteçleri ile düzenlemesine olanak tanır.

### <a name="token-name-resolution"></a>Belirteç ad çözümlemesi

Çoğu durumda, burada bulunan bağımsız olarak belirli bir değere bir belirteç çözümler. Ancak, belirtecin bir paket veya özellik ilişkili ise, belirtecin değeri, bulunduğu üzerinde bağlıdır. İçinde bir özellik olması durumunda bir, daha sonra belirteci paketini `$SharePoint.Package.Name$` "A paketi" değerine giderir. Aynı özellik paketi b'de sonra olup olmadığını `$SharePoint.Package.Name$` "İçin Paket B" giderir.

## <a name="tokens-list"></a>Belirteç listesi

Aşağıdaki tabloda kullanılabilir belirteçleri listelenmektedir:

|Ad|Açıklama|
|----------|-----------------|
|$SharePoint.Project.FileName$|Proje dosyası, gibi içeren adı **NewProj.csproj**.|
|$SharePoint.Project.FileNameWithoutExtension$|Dosya adı uzantısı olmadan içeren proje dosyasının adı. Örneğin, **NewProj**.|
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
|$SharePoint.Feature.DeploymentPath$|Özellik paketi içeren klasörün adı. Bu belirteç özelliği Tasarımcısı'nda "Dağıtım yolu" özelliğine karşılık gelir. Bir örnek değer **Project1_Feature**.|
|$SharePoint.Feature.Id$|İçeren özellik SharePoint kimliği. Bu belirteç ile tüm özellik düzeyinde belirteçleri gibi bir özelliği aracılığıyla bir paketteki dahil ve doğrudan bir özellik dışında bir paket için eklenmedi dosyaları tarafından kullanılabilir.|
|$SharePoint.ProjectItem.Name$|Öğesinden alınan olarak (kendi dosya adı değil), proje öğesinin adı **ISharePointProjectItem.Name**.|
|$SharePoint.Type. \<GUID >. AssemblyQualifiedName$|Derleme nitelenmiş adı GUID belirtecin eşleşen türü. GUID biçimi küçük harf ve Guid.ToString("D") biçimine karşılık gelir (diğer bir deyişle, xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx).|
|$SharePoint.Type. \<GUID >. FullName$|Belirteçte GUID eşleşen türünün tam adı. GUID biçimi küçük harf ve Guid.ToString("D") biçimine karşılık gelir (diğer bir deyişle, xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx).|

## <a name="add-extensions-to-the-token-replacement-file-extensions-list"></a>Belirteç değiştirme uzantıları ekle dosya uzantıları listesi

Belirteçleri teorik olarak, varsayılan olarak, yalnızca paket dosyalarını belirteçleri için Visual Studio aramaları paketinde bir SharePoint proje öğesi ait olduğu herhangi bir dosyayı tarafından kullanılabilse de, dosyaları ve aşağıdaki uzantılara sahip dosyaları bildirimi:

- XML

- ASCX

- ASPX

- Web Bölümü

- DWP

Bu uzantıları tarafından tanımlanan `<TokenReplacementFileExtensions>` öğesinde *Microsoft.VisualStudio.SharePoint.targets* içinde bulunan dosyasını *% ProgramFiles (x86) %\MSBuild\Microsoft\VisualStudio\v14.0\ SharePointTools* klasör.

Ancak, ek dosya uzantıları listesine ekleyebilirsiniz. Ekleme bir `<TokenReplacementFileExtensions>` önce tanımlanan tüm PropertyGroup SharePoint proje dosyasında öğesine \<alma > SharePoint hedefleri dosyasının.

> [!NOTE]
> Bir proje derlendikten sonra belirteci değiştirme oluştuğundan, dosya uzantılarını derlenen dosya türleri için .cs, .vb veya .resx gibi eklemeyin. Belirteçleri değil derlenen dosyalar değiştirilir.

Örneğin, dosya adı uzantısı eklemek için *.myextension* ve *.yourextension* aşağıdaki belirteci değiştirme dosya adı uzantıları listesine eklemek bir *.csproj* dosyası:

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

Uzantısını doğrudan ekleyebilirsiniz *.targets* dosya. Ancak, bunun yapılması yerel sistemde yalnızca paketlenmiş tüm SharePoint projeleri için uzantıları listesi değiştirir kendi. Tüm SharePoint projeleri için uzantıları listesi değiştirilmesine tek Geliştirici olduğunuzda ya da projelerinizi çoğunu gerekiyorsa kullanışlı olabilir. Ancak, sisteme özgü olduğundan bu yaklaşım taşınabilir değildir. Bu, tüm uzantılar için proje dosyası yerine eklemeniz önerilir.

## <a name="see-also"></a>Ayrıca bkz.

- [SharePoint Çözümleri Geliştirme](../sharepoint/developing-sharepoint-solutions.md)