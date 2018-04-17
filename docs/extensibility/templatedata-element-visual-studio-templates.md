---
title: TemplateData öğesi (Visual Studio şablonları) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-general
ms.topic: conceptual
f1_keywords:
- http://schemas.microsoft.com/developer/vstemplate/2005#TemplateData
helpviewer_keywords:
- TemplateData element [Visual Studio project templates]
ms.assetid: db17ec9b-bfdf-46b1-bbe7-5ccc140056e2
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: bbf5b4c26b46c0be6038651a41c751afc39e4da5
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/16/2018
---
# <a name="templatedata-element-visual-studio-templates"></a>TemplateData Öğesi (Visual Studio Şablonları)
Şablon kategorilere ayırır ve nasıl ya da görüntüler tanımlar **yeni proje** veya **Yeni Öğe Ekle** iletişim kutusu.  
  
 \<VSTemplate >  
 \<TemplateData >  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
<TemplateData>  
    <Name> ... </Name>  
    <Description> ... </Description>  
    <Icon> ... </Icon>  
    <ProjectType> ... </ProjectType>  
    ...  
</TemplateData>  
```  
  
## <a name="attributes-and-elements"></a>Öznitelikler ve Öğeler  
 Öznitelikler, alt ve üst öğeler aşağıdaki bölümlerde açıklanmaktadır.  
  
### <a name="attributes"></a>Öznitelikler  
 Yok.  
  
### <a name="child-elements"></a>Alt Öğeler  
  
|Öğe|Açıklama|  
|-------------|-----------------|  
|[Adı](../extensibility/name-element-visual-studio-templates.md)|Gerekli öğe.<br /><br /> Ya da göründüğü gibi şablon adını belirtir. **yeni proje** veya **Yeni Öğe Ekle** iletişim kutusu.|  
|[Açıklama](../extensibility/description-element-visual-studio-templates.md)|Gerekli öğe.<br /><br /> Ya da göründüğü gibi şablon açıklamasını belirtir **yeni proje** veya **Yeni Öğe Ekle** iletişim kutusu.|  
|[Simgesi](../extensibility/icon-element-visual-studio-templates.md)|Gerekli öğe.<br /><br /> Yol ve dosya adı ya da görüntülenen simge görevi gören görüntü dosyasının belirtir **yeni proje** veya **Yeni Öğe Ekle** şablonu için iletişim kutusu.|  
|[ProjectType](../extensibility/projecttype-element-visual-studio-templates.md)|Gerekli öğe.<br /><br /> Böylece belirtilen grubunda altında görüntülenen proje şablonu kategorilere ayıran **yeni proje** iletişim kutusu.|  
|[ProjectSubType](../extensibility/projectsubtype-element-visual-studio-templates.md)|İsteğe bağlı öğe.<br /><br /> Böylece belirtilen kategori altında görüntülenen proje şablonu sınıflandırır **yeni proje** iletişim kutusu.|  
|[Templateıd](../extensibility/templateid-element-visual-studio-templates.md)|İsteğe bağlı öğe.<br /><br /> Şablon kimliğini belirtir.|  
|[Templategroupıd](../extensibility/templategroupid-element-visual-studio-templates.md)|İsteğe bağlı öğe.<br /><br /> Şablon Grup kimliğini belirtir.|  
|[SortOrder](../extensibility/sortorder-element-visual-studio-templates.md)|İsteğe bağlı öğe.<br /><br /> Ya da göründüğü gibi diğer şablonları aynı kategoride arasında şablonu düzenlemek için kullanılan bir değeri belirtir **yeni proje** veya **Yeni Öğe Ekle** iletişim kutusu.|  
|[CreateNewFolder](../extensibility/createnewfolder-element-visual-studio-templates.md)|İsteğe bağlı öğe.<br /><br /> İçeren bir klasörü proje örneklemesi üzerinde oluşturulup oluşturulmayacağını belirtir.|  
|[DefaultName](../extensibility/defaultname-element-visual-studio-templates.md)|İsteğe bağlı öğe.<br /><br /> Oluşturulduğunda proje ve öğe için Visual Studio Proje sistemi oluşturacak ad belirtir.|  
|[ProvideDefaultName](../extensibility/providedefaultname-element-visual-studio-templates.md)|İsteğe bağlı öğe.<br /><br /> Visual Studio Proje sistemi oluşturulduğunda bir proje veya öğesi için varsayılan ad oluşturmak olup olmadığını belirtir.|  
|[PromptForSaveOnCreation](../extensibility/promptforsaveoncreation-element-visual-studio-templates.md)|İsteğe bağlı öğe.<br /><br /> Proje geçici bir proje oluşturulup olup olmadığını belirtir.|  
|[EnableLocationBrowseButton](../extensibility/enablelocationbrowsebutton-element-visual-studio-templates.md)|İsteğe bağlı öğe.<br /><br /> Belirtir olup olmadığını **Gözat** düğmesi kullanılabilir **yeni proje** iletişim kutusunda, böylece kullanıcıların kolayca yeni bir proje kaydettiğiniz yere varsayılan dizini değiştirebilirsiniz.|  
|[Gizli](../extensibility/hidden-element-visual-studio-templates.md)|İsteğe bağlı öğe.<br /><br /> Şablon ya da görünüp görünmeyeceğini belirtir **yeni proje** veya **Yeni Öğe Ekle** iletişim kutusu.|  
|[NumberOfParentCategoriesToRollUp](../extensibility/numberofparentcategoriestorollup-visual-studio-templates.md)|İsteğe bağlı öğe.<br /><br /> Şablonda görüntüler üst kategori sayısını belirtir **yeni proje** iletişim kutusu.|  
|[LocationFieldMRUPrefix](../extensibility/locationfieldmruprefix-element-visual-studio-templates.md)|İsteğe bağlı öğe.|  
|[LocationField](../extensibility/locationfield-element-visual-studio-project-templates.md)|İsteğe bağlı öğe.<br /><br /> Belirtir desteklemediğini **konumu** metin kutusu **yeni proje** iletişim kutusu etkin, devre dışı ya da gizli için proje şablonu.|  
|[RequiredFrameworkVersion](../extensibility/requiredframeworkversion-element-visual-studio-templates.md)|İsteğe bağlı öğe.<br /><br /> Şablonu yalnızca belirli en düşük sürüm ve sonraki sürümlerinde, .NET Framework destekliyorsa, bu öğeyi kullanın.|  
|[SupportsMasterPage](../extensibility/supportsmasterpage-element-visual-studio-templates.md)|İsteğe bağlı öğe.<br /><br /> Şablon web projeleri için bir ana sayfa destekleyip desteklemediğini belirtir.|  
|[SupportsCodeSeparation](../extensibility/supportscodeseparation-element-visual-studio-templates.md)|İsteğe bağlı öğe.<br /><br /> Belirtir olup şablonu web projeleri için kod ayrımı veya arka plandaki kod sayfası modelini destekler.|  
|[SupportsLanguageDropDown](../extensibility/supportslanguagedropdown-element-visual-studio-templates.md)|İsteğe bağlı öğe.<br /><br /> Şablon için birden çok dil aynı olup olmadığını ve olup olmadığını belirtir **dil** seçeneği edinilebilir **yeni proje** iletişim kutusu.|  
|[TargetPlatformName](../extensibility/targetplatformname-element-visual-studio-templates.md)|İsteğe bağlı öğe.<br /><br /> Platform belirtir, proje şablonu hedefler. Bu öğe için bir proje şablonu oluşturmak için kullanıldığını belirtir [!INCLUDE[win8_appname_long](../debugger/includes/win8_appname_long_md.md)] uygulamalar.|  
  
### <a name="parent-elements"></a>Üst Öğeler  
  
|Öğe|Açıklama|  
|-------------|-----------------|  
|[VSTemplate](../extensibility/vstemplate-element-visual-studio-templates.md)|Gerekli öğe.<br /><br /> Proje şablonu, öğe şablonu veya starter kit tüm meta veriler içeriyor.|  
  
## <a name="remarks"></a>Açıklamalar  
 `TemplateData` gerekli bir öğedir.  
  
 İsteğe bağlı bir öğe içermiyorsa, o öğe için varsayılan değer kullanılır.  
  
## <a name="example"></a>Örnek  
 Meta veriler için bir proje şablonu için aşağıdaki örnekte bir [!INCLUDE[csprcs](../data-tools/includes/csprcs_md.md)] uygulama.  
  
```  
<VSTemplate Type="Project" Version="3.0.0"  
    xmlns="http://schemas.microsoft.com/developer/vstemplate/2005">  
    <TemplateData>  
        <Name>My template</Name>  
        <Description>A basic starter kit</Description>  
        <Icon>TemplateIcon.ico</Icon>  
        <ProjectType>CSharp</ProjectType>  
    </TemplateData>  
    <TemplateContent>  
        <Project File="MyStarterKit.csproj">  
            <ProjectItem>Form1.cs<ProjectItem>  
            <ProjectItem>Form1.Designer.cs</ProjectItem>  
            <ProjectItem>Program.cs</ProjectItem>  
            <ProjectItem>Properties\AssemblyInfo.cs</ProjectItem>  
            <ProjectItem>Properties\Resources.resx</ProjectItem>  
            <ProjectItem>Properties\Resources.Designer.cs</ProjectItem>  
            <ProjectItem>Properties\Settings.settings</ProjectItem>  
            <ProjectItem>Properties\Settings.Designer.cs</ProjectItem>  
        </Project>  
    </TemplateContent>  
</VSTemplate>  
```  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Visual Studio Şablon Şeması Başvurusu](../extensibility/visual-studio-template-schema-reference.md)   
 [Proje ve Öğe Şablonları Oluşturma](../ide/creating-project-and-item-templates.md)