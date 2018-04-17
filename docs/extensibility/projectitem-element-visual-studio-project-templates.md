---
title: ProjectItem öğesi (Visual Studio Proje şablonları) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-general
ms.topic: conceptual
f1_keywords:
- http://schemas.microsoft.com/developer/vstemplate/2005#ProjectItem
helpviewer_keywords:
- ProjectItem element [Visual Studio project templates]
- <ProjectItem> element [Visual Studio project templates]
ms.assetid: 82879fbe-7756-42cd-9a07-c10edf5b4673
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: 8a7dfbfd03df24c2968dc9dae141ffc7a300e8be
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/16/2018
---
# <a name="projectitem-element-visual-studio-project-templates"></a>ProjectItem Öğesi (Visual Studio Proje Şablonları)
Proje şablonu içeren bir dosyayı belirtir.  
  
> [!NOTE]
>  `ProjectItem` Öğesi şablonu için bir proje veya öğeyi olup olmamasına bağlı olarak farklı öznitelikleri kabul eder. Bu konuda açıklanmaktadır `ProjectItem` öğesi proje şablonları için. Bir açıklaması için `ProjectItem` öğesi öğe şablonları için bkz: [ProjectItem öğesi (Visual Studio öğe şablonları)](../extensibility/projectitem-element-visual-studio-item-templates.md).  
  
 \<VSTemplate >  
 \<TemplateContent >  
 \<Proje >  
 \<ProjectItem >  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
<ProjectItem  
    TargetFileName="TargetFileName.ext"  
    ReplaceParameters="true/false"  
    OpenInEditor="true/false"  
    OpenInWebBrowser="true/false"  
    OpenInHelpBrowser="true/false"  
    OpenOrder="Value">  
        FileName.ext  
</ProjectItem>  
```  
  
## <a name="attributes-and-elements"></a>Öznitelikler ve Öğeler  
 Aşağıdaki bölümlerde öznitelik, alt öğeler ve üst öğeler açıklanmaktadır.  
  
### <a name="attributes"></a>Öznitelikler  
  
|Öznitelik|Açıklama|  
|---------------|-----------------|  
|`TargetFileName`|İsteğe bağlı öznitelik.<br /><br /> Bir proje şablonu oluşturulduğunda, adını ve proje öğesi yolunu belirtir. Bu öznitelik, bir dizin yapısına şablon .zip dosyası dizin yapısını farklı oluşturmak veya parametre değiştirme kullanarak bir öğe adı oluşturmak için kullanışlıdır.|  
|`ReplaceParameters`|İsteğe bağlı öznitelik.<br /><br /> Öğe bir proje şablonu oluşturduğunuzda, değiştirilmesi gereken parametre değerlerini sahip olup olmadığını belirten bir Boole değeri. Varsayılan değer `false`.|  
|`OpenInEditor`|İsteğe bağlı öznitelik.<br /><br /> Öğesi kendi ilgili Düzenleyicisi'nde açtığınız olup olmadığını belirten bir Boole değeri [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] bir proje şablonu oluşturulduğunda.<br /><br /> `OpenInWebBrowser` Ve `OpenInHelpBrowser` öznitelikleri yok sayılır sahip bir öğe üzerinde bir `OpenInEditor` değerini `true`.<br /><br /> Varsayılan değer `false` şeklindedir.|  
|`OpenInWebBrowser`|İsteğe bağlı öznitelik.<br /><br /> Bir proje şablonu oluşturulduğunda öğesi Web tarayıcısı açtığınız olup olmadığını belirten bir Boole değeri.<br /><br /> Web tarayıcısında, yalnızca HTML dosyaları ve projeye yerel metin dosyalarını açılabilir. Bu öznitelik ile dış URL'ler açılamaz.<br /><br /> Varsayılan değer `false` şeklindedir.|  
|`OpenInHelpBrowser`|İsteğe bağlı öznitelik.<br /><br /> Bir proje şablonu oluşturulduğunda öğesi Yardım Görüntüleyicisi'nde açtığınız olup olmadığını belirten bir Boole değeri.<br /><br /> Yalnızca HTML dosyaları ve projeye yerel metin dosyalarını Yardım tarayıcıda açılabilir. Bu öznitelik ile dış URL'ler açılamaz.<br /><br /> Varsayılan değer `false` şeklindedir.|  
|`OpenOrder`|İsteğe bağlı öznitelik.<br /><br /> Öğeleri kendi ilgili düzenleyicilerde açılacak sırasını temsil eden bir sayısal değer belirtir. Tüm değerlerin 10'ün katları olmalıdır. Daha yüksek öğelerini `OpenOrder` değerleri ilk açıldığında.|  
  
### <a name="child-elements"></a>Alt Öğeler  
 Yok.  
  
### <a name="parent-elements"></a>Üst Öğeler  
  
|Öğe|Açıklama|  
|-------------|-----------------|  
|[Project](../extensibility/project-element-visual-studio-templates.md)|Dosya veya dizinlerin projeye eklemek için belirtir.|  
  
## <a name="text-value"></a>Metin Değeri  
 Bir metin değeri gereklidir.  
  
 A `string` , adı veya yolu şablon .zip dosyası dosyasında temsil eder.  
  
## <a name="remarks"></a>Açıklamalar  
 `ProjectItem` İsteğe bağlı bir alt `Project`.  
  
 `TargetFileName` Öznitelik, bir dizin yapısına dizin yapısını farklı şablon .zip dosyası oluşturmak için kullanılabilir. Örneğin, varsa dosyayı `MyFile.vb` şablon .zip dosyası kök dizininde var ancak adlı bir dizinde yerleştirilecek dosya istediğiniz `CustomFiles` şablondan oluşturulan tüm projelerde aşağıdaki XML kullanırsınız:  
  
```  
<ProjectItem TargetFileName="CustomFiles\MyFile.vb">MyFile.vb</ProjectItem>  
```  
  
 `TargetFileName` Özniteliği de kendi dosya adları uluslararası karakterler içeren dosyaları yeniden adlandırmak için kullanılabilir. Örneğin, bir .zip dosyasına sıkıştırılmış önce dosyayı yeniden adlandırılması gerekir böylece bir şablon .zip dosyası dosya adları, Unicode karakteri içeremez. `TargetFileName` Özniteliği, özgün Unicode dosya adı dosya adını ayarlamanız için kullanılabilir.  
  
 `TargetFileName` Özniteliği de parametrelere sahip dosyaları yeniden adlandırmak için kullanılabilir. Aşağıdaki yordam, dosyayı yeniden adlandırmak açıklanmaktadır `MyFile.vb`, proje adına göre bir dosya adına şablon .zip dosyasının kök dizininde bulunmaktadır.  
  
### <a name="to-rename-files-with-parameters"></a>Parametrelere sahip dosyaları yeniden adlandırmak için  
  
1.  Aşağıdaki XML .vstemplate dosyasında kullanın:  
  
    ```  
    <ProjectItem TargetFileName="$safeprojectname$.vb">MyFile.vb</ProjectItem>  
    ```  
  
2.  Proje dosyasını açın (.vbproj için bir [!INCLUDE[vbprvb](../code-quality/includes/vbprvb_md.md)] Proje) bir metin düzenleyicisinde veya [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)].  
  
3.  Aşağıdaki XML benzer proje dosyasında satırı bulun:  
  
    ```  
    <Compile Include="MyFile.vb">  
    ```  
  
4.  Kod satırı aşağıdaki XML ile değiştirin:  
  
    ```  
    <Compile Include="$safeprojectname$.vb">  
    ```  
  
     Bu şablonu kullanarak bir proje oluşturduğunuzda, dosya adı kullanıcı girilen ad dayalı olacak **yeni proje** olan tüm güvenli olmayan karakter ve boşlukları kaldırılmış iletişim kutusu. Daha fazla bilgi için bkz: [şablon parametreleri](../ide/template-parameters.md).  
  
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
            <ProjectItem ReplaceParameters="true">Form1.cs<ProjectItem>  
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
 [Proje ve öğe şablonları oluşturma](../ide/creating-project-and-item-templates.md)   
 [Şablon parametreleri](../ide/template-parameters.md)   
 [ProjectItem Öğesi (Visual Studio Öğe Şablonları)](../extensibility/projectitem-element-visual-studio-item-templates.md)