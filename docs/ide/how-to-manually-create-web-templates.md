---
title: "Nasıl yapılır: Web şablonlarını elle oluşturma | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-general
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Visual Studio templates, Web
- templates [Visual Studio], Web
- Web templates [Visual Studio]
- project templates [Visual Studio], Web
ms.assetid: 731c4027-a152-48c5-bfc4-93490bf1949f
caps.latest.revision: "17"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: 5d5f34e421160e8cca56897e6530ff47da7b1a84
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2017
---
# <a name="how-to-manually-create-web-templates"></a>Nasıl Yapılır: Web Şablonlarını Elle Oluşturma
Bir Web şablonu oluşturma şablonları diğer tür oluşturmaktan daha farklıdır. Web projesi şablonları görünür olduğundan **yeni Web sitesi Ekle** iletişim kutusu ve Web proje öğelerini kategorilere ayrılabilir programlama dili tarafından .vstemplate dosyası şablonu Web şablon olarak belirtin ve programlama tanımlayın dili.  
  
> [!NOTE]
>  Web şablonları kullanarak belirtilen bir boş .webproj dosyası içermelidir `File` özniteliği `Project` öğesi. Web projeleri proje dosyalarını gerektirmeyen rağmen böylece Web şablonu düzgün çalışır, bu dosyası gerekli değildir.  
  
### <a name="to-manually-create-a-web-template"></a>El ile bir Web şablonu oluşturmak için  
  
1.  Bir Web projesi oluşturun.  
  
2.  Değiştirin veya projenin dosyaları silin veya yeni dosyalar projeye ekleyin.  
  
3.  Bir XML dosyası oluşturun ve projenizin ile aynı dizinde .vstemplate dosya adı uzantısını kullanarak kaydedin. Projede eklemeyin [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)].  
  
4.  Proje şablonu meta verilerini sağlamak için .vstemplate XML dosyasına yazar. Daha fazla bilgi için aşağıdaki bölümdeki örnek bakın.  
  
5.  Bulun `ProjectType` .vstemplate dosya ve metin değerini kümesi öğesinde `Web`.  
  
6.  Aşağıdaki `ProjectType` öğesi ekleme bir `ProjectSubType` öğesi ve şablon programlama diline metin değeri ayarlayın. Programlama dili aşağıdaki değerlerden biri olabilir:  
  
    -   CSharp  
  
    -   Visualbasic'tir  
  
     Örneğin:  
  
    ```  
    <TemplateData>  
        ...  
        <ProjectType>Web</ProjectType>  
        <ProjectSubType>CSharp</ProjectSubType>  
        ...  
    </TemplateData>  
    ```  
  
7.  (Buna dahildir .vstemplate dosyası) şablonunuzda dosyaları seçin, seçime sağ tıklayın, **göndermek için**ve ardından **sıkıştırılmış (daraltılmış) klasör**. Dosyalar bir .zip dosyasına sıkıştırılır.  
  
8.  .Zip şablon dosyası içine [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] proje şablonu dizini. Varsayılan olarak, bu \My Documents\Visual Studio dizindir *sürüm*\My dışa aktarılan şablonları\\.  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnek bir Web projesi şablonu için bir temel .vstemplate dosyası gösterir.  
  
```  
<VSTemplate Version="2.0.0" Type="Project"  
    xmlns="http://schemas.microsoft.com/developer/vstemplate/2005">>  
    <TemplateData>  
        <Name>MyWebProjecStarterKit</Name>  
        <Description>A simple Web template</Description>  
        <Icon>icon.ico</Icon>  
        <ProjectType>Web</ProjectType>  
        <ProjectSubType>CSharp</ProjectSubType>  
        <DefaultName>WebSite</DefaultName>  
    </TemplateData>  
    <TemplateContent>  
        <Project File="WebApplication.webproj">  
            <ProjectItem>icon.ico</ProjectItem>  
            <ProjectItem OpenInEditor="true">Default.aspx</ProjectItem>  
            <ProjectItem>Default.aspx.cs</ProjectItem>  
        </Project>  
    </TemplateContent>  
</VSTemplate>  
```  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Proje ve öğe şablonları oluşturma](../ide/creating-project-and-item-templates.md)   
 [Visual Studio Şablon Şeması Başvurusu](../extensibility/visual-studio-template-schema-reference.md)