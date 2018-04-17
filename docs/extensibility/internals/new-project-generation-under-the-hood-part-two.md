---
title: 'Yeni proje oluşturma: başlık altında iki bölüm | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- projects [Visual Studio], new project dialog
- projects [Visual Studio], new project generation
ms.assetid: 73ce91d8-0ab1-4a1f-bf12-4d3c49c01e13
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: 69174be20a0961a6074650471bcb4b9d1df9fa98
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/16/2018
---
# <a name="new-project-generation-under-the-hood-part-two"></a>Yeni proje oluşturma: başlık altında iki bölüm
İçinde [yeni proje oluşturma: başlık altında Kısım](../../extensibility/internals/new-project-generation-under-the-hood-part-one.md) gördüğümüz nasıl **yeni proje** iletişim kutusu doldurulur. Seçtiğiniz varsayalım bir **Visual C# Windows uygulaması**, doldurulmuş **adı** ve **konumu** metin kutuları ve tıklatılan Tamam.  
  
## <a name="generating-the-solution-files"></a>Çözüm dosyaları oluşturma  
 Bir uygulama şablonunu seçme yönlendirir [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] sıkıştırmasını açın ve karşılık gelen .vstemplate dosyasını açın ve bu dosyasındaki XML komutları yorumlamak için bir şablon başlatmak için. Bu komutlar yeni veya var olan çözümde proje ve proje öğeleri oluşturun.  
  
 Şablonun öğe şablonları .vstemplate dosyanızı .zip klasöründen adlı kaynak dosyalarını ayıklar. Şablon bu dosyaları uygun şekilde özelleştirme yeni projeye kopyalar.  
  
### <a name="template-parameter-replacement"></a>Şablon parametresi değiştirme  
 Şablon için yeni bir proje öğesi şablonu kopyaladığında, herhangi bir şablon parametre dosyasını özelleştirme dizelerle değiştirir. Şablon parametresi var. önce ve bir dolar işareti, örneğin gelmelidir özel belirteç, $date$  
  
 Bir tipik bir proje öğesi şablon bakalım. Ayıklayın ve Program Files\Microsoft Visual Studio 8\Common7\IDE\ProjectTemplates\CSharp\Windows\1033\WindowsApplication.zip klasöründeki Program.cs inceleyin.  
  
```  
using System;  
using System.Collections.Generic;  
using System.Windows.Forms;  
  
namespace $safeprojectname$  
{  
    static class Program  
    {  
        // source code deleted here for brevity  
    }  
}  
```  
  
 Basit adlı yeni bir Windows uygulama projesi oluşturursanız, şablon değiştirir `$safeprojectname$` projesinin adı parametresi.  
  
```  
using System;  
using System.Collections.Generic;  
using System.Windows.Forms;  
  
namespace Simple  
{  
    static class Program  
    {  
        // source code deleted here for brevity  
    }  
}  
```  
  
 Şablon parametreleri tam bir listesi için bkz: [şablon parametreleri](../../ide/template-parameters.md).  
  
## <a name="a-look-inside-a-vstemplate-file"></a>Bir görünüm içindeki bir. VSTemplate dosyası  
 Bu biçim bir temel .vstemplate dosya var  
  
```  
<VSTemplate Version="2.0.0"     xmlns="http://schemas.microsoft.com/developer/vstemplate/2005"     Type="Project">  
    <TemplateData>  
    </TemplateData>  
    <TemplateContent>  
    </TemplateContent>  
</VSTemplate>  
```  
  
 İnceledik \<TemplateData > bölümüne [yeni proje oluşturma: başlık altında bir bölümü](../../extensibility/internals/new-project-generation-under-the-hood-part-one.md). Bu bölümdeki etiketleri görünümünü denetlemek için kullanılan **yeni proje** iletişim kutusu.  
  
 Etiketleri \<TemplateContent > Yeni proje ve proje öğeleri nesil denetim bölüm. Burada \<TemplateContent > \Program Visual Studio 8\Common7\IDE\ProjectTemplates\CSharp\Windows\1033\WindowsApplication.zip klasöründeki cswindowsapplication.vstemplate dosyasını bölümünden.  
  
```  
<TemplateContent>  
  <Project File="WindowsApplication.csproj" ReplaceParameters="true">  
    <ProjectItem ReplaceParameters="true"  
      TargetFileName="Properties\AssemblyInfo.cs">  
      AssemblyInfo.cs  
    </ProjectItem>  
    <ProjectItem TargetFileName="Properties\Resources.resx">  
      Resources.resx  
    </ProjectItem>  
    <ProjectItem ReplaceParameters="true"       TargetFileName="Properties\Resources.Designer.cs">  
      Resources.Designer.cs  
    </ProjectItem>  
    <ProjectItem TargetFileName="Properties\Settings.settings">  
      Settings.settings  
    </ProjectItem>  
    <ProjectItem ReplaceParameters="true"       TargetFileName="Properties\Settings.Designer.cs">  
      Settings.Designer.cs  
    </ProjectItem>  
    <ProjectItem ReplaceParameters="true" OpenInEditor="true">  
      Form1.cs  
    </ProjectItem>  
    <ProjectItem ReplaceParameters="true">  
      Form1.Designer.cs  
    </ProjectItem>  
    <ProjectItem ReplaceParameters="true">  
      Program.cs  
    </ProjectItem>  
  </Project>  
</TemplateContent>  
```  
  
 \<Proje > etiketi denetleyen bir proje oluşturma ve \<ProjectItem > etiketi bir proje öğesi oluşturma denetler. ReplaceParameters parametresi true ise, şablonu proje dosyası veya öğeyi tüm şablonu parametreleri özelleştirin. Bu durumda, tüm proje öğeleri, Settings.settings dışında özelleştirilir.  
  
 TargetFileName parametre adını ve sonuçta elde edilen proje dosyası veya öğenin göreli yolunu belirtir. Projeniz için bir klasör yapısı oluşturmanıza olanak sağlar. Bu bağımsız değişken belirtmezseniz, proje öğesi proje öğesi şablon olarak aynı ada sahip olacaktır.  
  
 Sonuçta elde edilen Windows uygulama klasör yapısı şuna benzer:  
  
 ![SimpleSolution](../../extensibility/internals/media/simplesolution.png "SimpleSolution")  
  
 İlk ve tek \<Proje > şablon okuma etiketinde:  
  
```  
<Project File="WindowsApplication.csproj" ReplaceParameters="true">  
```  
  
 Bu, kopyalama ve şablon öğesi windowsapplication.csproj özelleştirme Simple.csproj proje dosyası oluşturmak için yeni bir proje şablonu bildirir.  
  
### <a name="designers-and-references"></a>Tasarımcılar ve başvurular  
 Özellikleri klasörü varsa ve beklenen dosyalar içeriyorsa, Çözüm Gezgini'nde görebilirsiniz. Ancak proje hakkında neler başvuruyor ve Resources.resx Resources.Designer.cs ve Form1.cs'in Form1.Designer.cs gibi tasarımcı dosya bağımlılıkları?  Bunu oluşturulduğunda bu Simple.csproj dosyasında ayarlanır.  
  
 Burada \<ItemGroup > Proje başvuruları oluşturur Simple.csproj gelen:  
  
```  
<ItemGroup>  
    <Reference Include="System" />  
    <Reference Include="System.Data" />  
    <Reference Include="System.Deployment" />  
    <Reference Include="System.Drawing" />  
    <Reference Include="System.Windows.Forms" />  
    <Reference Include="System.Xml" />  
</ItemGroup>  
```  
  
 Çözüm Gezgini'nde görünür altı proje başvuruları bunlar görebilirsiniz. Başka bir bölümünden işte \<ItemGroup >. Kod satır sayısını daha anlaşılır olması için silinmiş. Bu bölümde Settings.Designer.cs Settings.settings üzerinde bağımlı hale getirir:  
  
```  
<ItemGroup>  
    <Compile Include="Properties\Settings.Designer.cs">  
        <DependentUpon>Settings.settings</DependentUpon>  
    </Compile>  
</ItemGroup>  
```  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Yeni Proje Oluşturma: Altyapı Öğeleri, Bölüm Bir](../../extensibility/internals/new-project-generation-under-the-hood-part-one.md)  
 [MSBuild](../../msbuild/msbuild.md)