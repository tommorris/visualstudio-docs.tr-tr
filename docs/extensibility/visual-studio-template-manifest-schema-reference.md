---
title: "Visual Studio Şablon Şeması Başvurusu bildirimi | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: bc7d0a81-0df5-41a9-a912-1b30e5da1d13
caps.latest.revision: "3"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: f714120c6f5dced4760bb14cad1e53a794030a19
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2017
---
# <a name="visual-studio-template-manifest-schema-reference"></a>Visual Studio şablon bildirim şema başvurusu
Bu şemayı Visual Studio Proje veya öğesi şablonları için üretilen Visual Studio şablon bildirimi (.vstman) dosyalarını biçimi ve konumu ve şablon ilgili diğer bilgileri açıklar.  
  
 : Olduğundan ayrı öğesi ve proje şablonu dizinleri, bir bildirim hiç öğe ve proje şablonları bir karışımını olması gerekir.  
  
> [!IMPORTANT]
>  Bu bildirim Visual Studio 2017'den itibaren kullanılabilmektedir.  
  
## <a name="vstemplatemanifest-element"></a>VSTemplateManifest öğesi  
 Bildirim kök öğesi.  
  
### <a name="attributes"></a>Öznitelikler  
  
-   **Sürüm**: şablon bildiriminin sürümü temsil eden dize. Gerekli.  
  
-   **Yerel ayar**: yerel ya da yerel ayarlara şablon bildiriminin temsil eden dize. Her yerel ayar için ayrı bir bildirim kullanmalısınız yerel değerin tüm şablonlar için geçerlidir. İsteğe bağlı.  
  
### <a name="child-elements"></a>Alt Öğeler  
  
-   **VSTemplateContainer** isteğe bağlı.  
  
-   **VSTemplateDir** isteğe bağlı.  
  
### <a name="parent-element"></a>Üst Öğe  
 Yok.  
  
## <a name="vstemplatecontainer"></a>VSTemplateContainer  
 Şablon kapsayıcı öğeleri bildirimi. Bir bildirim tanımladığı her şablon için bir şablon kapsayıcı vardır.  
  
### <a name="attributes"></a>Öznitelikler  
 **VSTemplateType** : şablon türünü belirten bir dize değeri (`"Project"`, `"Item"`, veya `"ProjectGroup"`). Gerekli  
  
### <a name="child-elements"></a>Alt Öğeler  
  
-   **RelativePathOnDisk**: diskteki şablonu dosyanın göreli yolu. Bu konum gösterilen şablon ağacında şablon yerleşimini de tanımlar **yeni proje** veya **yeni öğe** iletişim. Bir dizin ve tek tek dosyaları dağıtılan şablonları için bu yol şablon dosyalarını içeren dizini başvuruyor. Bir .zip dosyası olarak dağıtılan şablonları için bu yolu .zip dosyasının yolu olmalıdır.  
  
-   **VSTemplateHeader** : A [TemplateData](../extensibility/templatedata-element-visual-studio-templates.md) üstbilgisini tanımlayan öğesi.  
  
### <a name="parent-element"></a>Üst Öğe  
 **VSTemplateManifest**  
  
## <a name="vstemplatedir"></a>VSTemplateDir  
 Şablon bulunduğu dizin açıklar. Birden çok bildirim içerebilir **VSTemplateDir** girişleri yerelleştirilmiş adı ve şablon kategori ağacında görünümlerini denetlemek için sıralama dizinler için sıralama belirtin.  
  
 Kendi tasarım nedeniyle **VSTemplateDir** girişleri, yalnızca yerel olmayan belirtilen bildirimleri görünmelidir.  
  
### <a name="attributes"></a>Öznitelikler  
 Yok.  
  
### <a name="child-elements"></a>Alt Öğeler  
  
-   **RelativePath**: şablonun yolunu. Tüm bildirimler için birinci yüzden yolu başına yalnızca bir giriş olabilir.  
  
-   **LocalizedName**: A **NameDescriptionIcon** öğesi yerelleştirilmiş adını belirtir. İsteğe bağlı.  
  
-   **SortOrder** : sıralama düzenini belirten bir dize. İsteğe bağlı.  
  
-   **ParentFolderOverrideName**: geçersiz kılınan üst klasörün adı. İsteğe bağlı. Bu öğeye sahip bir **adı** adını belirten bir dize değeridir özniteliği.  
  
### <a name="parent-element"></a>Üst Öğe  
 **VSTemplateManifest**  
  
## <a name="namedescriptionicon"></a>NameDescriptionIcon  
 Adını ve açıklamasını, büyük olasılıkla yerelleştirilmiş şablonları belirtir. Bkz: **LocalizedName** üstünde.  
  
### <a name="attributes"></a>Öznitelikler  
  
-   **Paket**: Paket belirten bir dize değeri. İsteğe bağlı.  
  
-   **Kimliği**: kimliğini belirtir. bir dize değeri İsteğe bağlı.  
  
### <a name="child-elements"></a>Alt Öğeler  
 Yok.  
  
### <a name="parent-element"></a>Üst Öğe  
 **LocalizedName**  
  
## <a name="examples"></a>Örnekler  
 Bir proje şablonu .vstman dosyası örneği verilmiştir.  
  
```xml  
<VSTemplateManifest Version="1.0" Locale="1033" xmlns="http://schemas.microsoft.com/developer/vstemplatemanifest/2015">  
  <VSTemplateContainer TemplateType="Project">  
    <RelativePathOnDisk>CSharp\1033\TestProjectTemplate</RelativePathOnDisk>  
    <TemplateFileName>TestProjectTemplate.vstemplate</TemplateFileName>  
    <VSTemplateHeader>  
      <TemplateData xmlns="http://schemas.microsoft.com/developer/vstemplate/2005">  
        <Name>TestProjectTemplate</Name>  
        <Description>TestProjectTemplate</Description>  
        <Icon>TestProjectTemplate.ico</Icon>  
        <ProjectType>CSharp</ProjectType>  
        <RequiredFrameworkVersion>2.0</RequiredFrameworkVersion>  
        <SortOrder>1000</SortOrder>  
        <TemplateID>aac0aeea-7883-4003-992f-937d53d70ab1</TemplateID>  
        <CreateNewFolder>true</CreateNewFolder>  
        <DefaultName>TestProjectTemplate</DefaultName>  
        <ProvideDefaultName>true</ProvideDefaultName>  
      </TemplateData>  
    </VSTemplateHeader>  
  </VSTemplateContainer>  
</VSTemplateManifest>  
  
```  
  
 Bir öğe şablonu .vstman dosyası örneği verilmiştir.  
  
```  
VSTemplateManifest Version="1.0" Locale="1033" xmlns="http://schemas.microsoft.com/developer/vstemplatemanifest/2015">  
  <VSTemplateContainer TemplateType="Item">  
    <RelativePathOnDisk>CSharp\1033\ItemTemplate1</RelativePathOnDisk>  
    <TemplateFileName>ItemTemplate1.vstemplate</TemplateFileName>  
    <VSTemplateHeader>  
      <TemplateData xmlns="http://schemas.microsoft.com/developer/vstemplate/2005">  
        <Name>ItemTemplate1</Name>  
        <Description>ItemTemplate1</Description>  
        <Icon>ItemTemplate1.ico</Icon>  
        <TemplateID>bfeadf8e-a251-4109-b605-516b88e38c8d</TemplateID>  
        <ProjectType>CSharp</ProjectType>  
        <RequiredFrameworkVersion>2.0</RequiredFrameworkVersion>  
        <NumberOfParentCategoriesToRollUp>1</NumberOfParentCategoriesToRollUp>  
        <DefaultName>Class.cs</DefaultName>  
      </TemplateData>  
    </VSTemplateHeader>  
  </VSTemplateContainer>  
</VSTemplateManifest>  
  
```