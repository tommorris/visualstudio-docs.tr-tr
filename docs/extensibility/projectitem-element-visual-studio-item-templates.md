---
title: ProjectItem öğesi (Visual Studio öğe şablonları) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-general
ms.topic: conceptual
f1_keywords:
- http://schemas.microsoft.com/developer/vstemplate/2005#ProjectItem
helpviewer_keywords:
- <ProjectItem> element [Visual Studio item templates]
- ProjectItem element [Visual Studio item templates]
ms.assetid: 9ed94112-0c38-49df-b728-0dd2d0d1eb47
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: 886fc57258b4ccafaa4ab8d522fad632de455e17
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/16/2018
---
# <a name="projectitem-element-visual-studio-item-templates"></a>ProjectItem Öğesi (Visual Studio Öğe Şablonları)
Öğe şablona dahil bir dosyayı belirtir.  
  
> [!NOTE]
>  `ProjectItem` Öğesi şablonu için bir proje veya öğeyi olup olmamasına bağlı olarak farklı öznitelikleri kabul eder. Bu konuda açıklanmaktadır `ProjectItem` öğesi için öğe. Bir açıklaması için `ProjectItem` öğesi proje şablonları için bkz: [ProjectItem öğesi (Visual Studio Proje şablonları)](../extensibility/projectitem-element-visual-studio-project-templates.md).  
  
 \<VSTemplate >  
 \<TemplateContent >  
 \<ProjectItem >  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
<ProjectItem  
    SubType="Form/Component/CustomControl/UserControl"  
    CustomTool="string"  
    ItemType="string"  
    ReplaceParameters="true/false"  
    TargetFileName="TargetFileName.ext">  
        FileName.ext  
</ProjectItem>  
```  
  
## <a name="attributes-and-elements"></a>Öznitelikler ve Öğeler  
 Aşağıdaki bölümlerde öznitelik, alt öğeler ve üst öğeler açıklanmaktadır.  
  
### <a name="attributes"></a>Öznitelikler  
  
|Öznitelik|Açıklama|  
|---------------|-----------------|  
|`SubType`|İsteğe bağlı öznitelik.<br /><br /> Çok dosyalı öğe şablonunda alt öğe türünü belirtir. Bu değer Düzenleyici belirlemek için kullanılır, [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] öğesini açmak için kullanır.|  
|`CustomTool`|İsteğe bağlı öznitelik.<br /><br /> Öğenin CustomTool proje dosyasında ayarlar.|  
|`ItemType`|İsteğe bağlı öznitelik.<br /><br /> Öğenin ItemType proje dosyasında ayarlar.|  
|`ReplaceParameters`|İsteğe bağlı öznitelik.<br /><br /> Öğe bir proje şablonu oluşturduğunuzda, değiştirilmesi gereken parametre değerlerini sahip olup olmadığını belirten bir Boole değeri. Varsayılan değer `false`.|  
|`TargetFileName`|İsteğe bağlı öznitelik.<br /><br /> Şablondan oluşturulan öğesinin adını belirtir. Bu öznitelik, parametre değiştirme kullanarak bir öğe adı oluşturmak için kullanışlıdır.|  
  
### <a name="child-elements"></a>Alt Öğeler  
 Yok.  
  
### <a name="parent-elements"></a>Üst Öğeler  
  
|Öğe|Açıklama|  
|-------------|-----------------|  
|[TemplateContent](../extensibility/templatecontent-element-visual-studio-templates.md)|Şablon içeriğini belirtir.|  
  
## <a name="text-value"></a>Metin Değeri  
 Bir metin değeri gereklidir.  
  
 A `string` , bir dosyada şablon .zip dosyası adını temsil eder.  
  
## <a name="remarks"></a>Açıklamalar  
 `ProjectItem` İsteğe bağlı bir alt `TemplateContent`.  
  
 `TargetFileName` Özniteliği parametrelerle dosyaları yeniden adlandırmak için kullanılabilir. Örneğin, varsa dosyayı `MyFile.vb` kullanıcı tarafından sağlanan dosya adı şu şekilde adlandırılabilir dosyaya temel istediğiniz şablon .zip dosyası, ancak kök dizininde mevcut **Yeni Öğe Ekle** iletişim kutusunda, aşağıdaki XML kullanırsınız:  
  
```  
<ProjectItem TargetFileName="$fileinputname$.vb">MyFile.vb</ProjectItem>  
```  
  
 Bu şablonu kullanarak bir öğe oluşturulduğunda dosya adı girilen kullanıcı adı dayalı olacak **Yeni Öğe Ekle** iletişim kutusu. Çok dosyalı öğe şablonları oluşturma durumunda faydalı olur. Daha fazla bilgi için bkz: [nasıl yapılır: çok dosyalı öğe şablonları oluşturma](../ide/how-to-create-multi-file-item-templates.md) ve [şablon parametreleri](../ide/template-parameters.md).  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnek standart madde şablon için meta verileri gösterilmektedir bir [!INCLUDE[csprcs](../data-tools/includes/csprcs_md.md)] sınıfı.  
  
```  
<VSTemplate Type="Item" Version="3.0.0"  
    xmlns="http://schemas.microsoft.com/developer/vstemplate/2005">  
    <TemplateData>  
        <Name>MyClass</Name>  
        <Description>My custom C# class.</Description>  
        <Icon>Icon.ico</Icon>  
        <ProjectType>CSharp</ProjectType>  
        <DefaultName>MyClass.cs</DefaultName>  
    </TemplateData>  
    <TemplateContent>  
        <ProjectItem ReplaceParameters="true">MyClass.cs</ProjectItem>  
    </TemplateContent>  
</VSTemplate>  
```  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Visual Studio Şablon Şeması Başvurusu](../extensibility/visual-studio-template-schema-reference.md)   
 [Proje ve öğe şablonları oluşturma](../ide/creating-project-and-item-templates.md)   
 [Nasıl yapılır: çok dosyalı öğe şablonları oluşturma](../ide/how-to-create-multi-file-item-templates.md)   
 [Şablon Parametreleri](../ide/template-parameters.md)