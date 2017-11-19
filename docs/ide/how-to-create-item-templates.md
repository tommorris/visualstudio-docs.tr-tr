---
title: "Nasıl yapılır: öğe şablonları oluşturma | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-general
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- project item templates, XML reference
- project item templates, custom template locations
- project item templates, creating
- project item templates, metadata files
ms.assetid: 77bc53d4-d607-4820-a032-7e3b365891b5
caps.latest.revision: "23"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: 2ecd17694e65c6273f8e73a321a72bc209038922
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2017
---
# <a name="how-to-create-item-templates"></a>Nasıl Yapılır: Öğe Şablonları Oluşturma
' Ndaki adımları [ilk yordamı](../ide/how-to-create-item-templates.md#export_template) kullanarak bir öğe şablonu oluşturmak nasıl gösterir bu konuda **şablonu dışarı aktar** Sihirbazı. Şablonunuzu birden çok dosya oluşacak olup [nasıl yapılır: çok dosyalı öğe şablonları oluşturma](../ide/how-to-create-multi-file-item-templates.md).  

 Çok fazla iş temel şablonu oluşturmak için Sihirbazı yapar, ancak birçok durumda şablon verdikten sonra .vstemplate dosyasını el ile değiştirmeniz gerekir. Örneğin, görünmesi öğe istiyorsanız **Yeni Öğe Ekle** iletişim kutusu için bir [!INCLUDE[win8_appname_long](../debugger/includes/win8_appname_long_md.md)] uygulama projesi elinizde fazladan birkaç adım gerçekleştirmek. [İkinci yordam](../ide/how-to-create-item-templates.md#modify_template) bu konuda, bu görevi gerçekleştirirken yardımcı olur.  

 Şablonunuzu yalnızca belirli proje alt türleri için Office, veritabanı veya Web gibi yalnızca görünmelidir belirtmek için bkz: [Bu bölümde](#enable_templates).  

 Bazı durumlarda istediğiniz veya bir öğe şablonu sıfırdan el ile oluşturmanız gerekir. [Üçüncü yordamı](../ide/how-to-create-item-templates.md#create_template) bunun nasıl yapılacağını gösterir.  

 Bkz: [Visual Studio şablon şeması başvurusu](../extensibility/visual-studio-template-schema-reference.md) .vstemplate dosyasında kullanılabilen öğeler hakkında bilgi için.  

### <a name="to-add-a-custom-project-item-template-to-the-add-new-item-dialog-box"></a>Yeni Öğe Ekle iletişim kutusuna özel proje öğesi şablon eklemek için  

1.  Bir projesi oluşturun veya açın [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)].  

2.  Projeye bir öğe ekleyin ve isterseniz değiştirin.  

3.  Parametre değiştirme burada gerçekleşeceğini belirtmek için kod dosyasını değiştirin. Daha fazla bilgi için bkz: [nasıl yapılır: şablonda parametreleri ikame](../ide/how-to-substitute-parameters-in-a-template.md).  

4.  Üzerinde **proje** menüsünde tıklatın **şablonu dışarı aktar**.  

5.  Tıklatın **öğe şablonu**öğeyi içeren projeyi seçin ve tıklatın **sonraki**.  

6.  Bir şablonu oluşturup tıklatın istediğiniz öğeyi seçin **sonraki**.  

7.  Derleme başvurularını tıklatın ve şablona dahil seçin **sonraki**.  

8.  Simge dosya adı, Önizleme görünümü, şablon adı ve şablon açıklamasını yazın ve'ı tıklatın **son**.  

     Şablon dosyalarını bir .zip dosyasına eklenir ve iletişim kutusunda belirttiğiniz hangi dizin kopyalanır. Varsayılan konum **... \Users\\< kullanıcı adı\>\Documents\Visual Studio \<sürüm > \My dışa aktarılan şablonları\\**  klasör.  

    > [!WARNING]
    >  Visual Studio'nun önceki sürümleri için varsayılan konumdur **... \Users\\< kullanıcı adı\>\Documents\Visual Studio \<sürüm > \Templates\ItemTemplates**.  

### <a name="to-enable-the-item-template-to-be-used-in-a-store-project"></a>Bir mağaza projesinde kullanılacak öğe şablonu etkinleştirmek için  

1.  Bir öğe şablonu dışarı aktarmak için yukarıdaki yordamdaki adımları izleyin.  

2.  .Vstemplate dosyasının kopyalandığı .zip dosyasını ayıklamak... \Users\\*kullanıcıadı*\Documents\Visual Studio *sürüm*\Templates\ItemTemplates\ (veya **My dışa aktarılan şablonları**) klasör.  

3.  .Vstemplate dosyasını Visual Studio'da açın.  

4.  Bir evrensel Windows C# için açılış içinde aşağıdaki XML ekleme proje, .vstemplate dosyasında `<TemplateData>` etiketi: `<TemplateID>Microsoft.CSharp.Class</TemplateID>`. 

    Windows 8.1 için C# projesinde, .vstemplate dosyada depolar açma ve kapatma içinde aşağıdaki XML eklemek `<TemplateData>` etiketi: `<TemplateGroupID>WinRT-Managed</TemplateGroupID>`.  

    C++ Windows 8.1 mağazası project değerini kullanır `WinRT-Native-6.3`. Windows 10 ve diğer proje türleri için bkz: [Templategroupıd öğesi (Visual Studio şablonları)](../extensibility/templategroupid-element-visual-studio-templates.md).  

    Aşağıdaki örnek, XML satırından sonra bir .vstemplate dosyanın tüm içeriğini gösterir `<TemplateGroupID>WinRT-Managed</TemplateGroupID>` kendisine eklenmiş. Bu örnek, C# projeleri için özeldir. Değiştirebileceğiniz <ProjectTpe> ve \< [Templategroupıd](../extensibility/templategroupid-element-visual-studio-templates.md)> öğeleri diğer dil ve proje türleri belirtin.  

    ```xml  
    <VSTemplate Version="3.0.0" xmlns="http://schemas.microsoft.com/developer/vstemplate/2005" Type="Item">  
      <TemplateData>  
        <DefaultName>MyItemStoreTemplate.xaml</DefaultName>  
        <Name>MyItemStoreTemplate</Name>  
        <Description>This is an example itemtemplate</Description>  
        <ProjectType>CSharp</ProjectType>  
        <SortOrder>10</SortOrder>  
        <Icon>__TemplateIcon.ico</Icon>  
        <TemplateGroupID>WinRT-Managed</TemplateGroupID>  
      </TemplateData>  
      <TemplateContent>  
        <References />  
        <ProjectItem SubType="Designer" TargetFileName="$fileinputname$.xaml" ReplaceParameters="true">MyItemTemplate.xaml</ProjectItem>  
        <ProjectItem SubType="Code" TargetFileName="$fileinputname$.xaml.cs" ReplaceParameters="true">MyItemTemplate.xaml.cs</ProjectItem>  
      </TemplateContent>  
    </VSTemplate>  
    ```  

     Diğer olası Templategroupıd değerleri için bkz: [Templategroupıd öğesi (Visual Studio şablonları)](../extensibility/templategroupid-element-visual-studio-templates.md)). Tam .vstemplate başvuru için bkz: [Visual Studio Şablon Şeması Başvurusu](../extensibility/visual-studio-template-schema-reference.md)  

5.  Visual Studio'da .vstemplate dosyayı kaydedin ve kapatın.  

6.  İçinde bulunan .zip dosyasını .vstemplate dosyasına yapıştırın... \Users\\*kullanıcıadı*\Documents\Visual Studio *sürüm*\Templates\ItemTemplates\ klasör.  

     Varsa **dosya Kopyala** seçin iletişim kutusu görüntülenirse, **Kopyala ve Değiştir** seçeneği.  

 Artık bu şablona dayalı bir öğe ekleyebilirsiniz bir [!INCLUDE[win8_appname_long](../debugger/includes/win8_appname_long_md.md)] kullanarak proje **Yeni Öğe Ekle** iletişim kutusu.  

 Parametre adları hakkında daha fazla bilgi için bkz: [şablon parametreleri](../ide/template-parameters.md).  
  
 
### <a name="enable_templates"></a>Özel proje alt türleri için şablonlar etkinleştirmek için  

1.  Geliştirme ortamı proje öğeleri Öğe Ekle iletişim kutusundan belirli projeler için kullanılabilmesini sağlar. Windows, Web, Office veya veritabanı projeleri için özel öğeler kullanılabilmesi için bu yordamı kullanın.  

     ProjectType öğesi öğe şablonu .vstemplate dosyasını bulun.  

     Ekleme bir [ProjectSubType](../extensibility/projectsubtype-element-visual-studio-templates.md) ProjectType öğesi hemen sonra öğesi.  

2.  Öğesinin metin değeri aşağıdaki değerlerden birine ayarlayın:  

    1.  Windows  

    2.  Office  

    3.  Veritabanı  

    4.  Web  

     Örneğin: `<ProjectSubType>Database</ProjectSubType>`.  

     Aşağıdaki örnek, Office projeleri için kullanılabilir bir öğe şablonu gösterir.  

    ```  
    <VSTemplate Version="2.0.0" Type="Item" Version="2.0.0">  
        <TemplateData>  
            <Name>Class</Name>  
            <Description>An empty class file</Description>  
            <Icon>Class.ico</Icon>  
            <ProjectType>CSharp</ProjectType>  
            <ProjectSubType>Office</ProjectSubType>  
            <DefaultName>Class.cs</DefaultName>  
        </TemplateData>  
        <TemplateContent>  
            <ProjectItem>Class1.cs</ProjectItem>  
        </TemplateContent>  
    </VSTemplate>  

    ```  

### <a name="to-manually-create-an-item-template-without-using-the-export-template-wizard"></a>Şablonu Dışarı Aktar Sihirbazı'nı kullanmadan bir öğe şablonu el ile oluşturmak için  

1.  Proje ve proje öğesi oluşturun.  

2.  Bir şablon olarak kaydedilecek hazır olana kadar proje öğesi değiştirin.  

3.  Parametre değiştirme gerçekleştiği belirtmek için kod dosyası uygun şekilde değiştirin. Parametre değiştirme hakkında daha fazla bilgi için bkz: [nasıl yapılır: şablonda parametreleri ikame.](../ide/how-to-substitute-parameters-in-a-template.md)

4.  Bir XML dosyası oluşturun ve yeni öğe şablon olarak aynı dizinde .vstemplate dosya adı uzantısını kullanarak kaydedin.  

5.  Öğe şablon meta verilerini sağlamak için .vstemplate XML dosyasına yazar. Daha fazla bilgi için bkz: [Visual Studio şablon şeması başvurusu](../extensibility/visual-studio-template-schema-reference.md) ve önceki bölümdeki örnek.  

6.  .Vstemplate dosyayı kaydedin ve kapatın.  

7.  Windows Gezgini'nde, şablonunuzda dahil, seçime sağ tıklayın, göndermek için tıklatın ve sonra sıkıştırılmış klasörü tıklatın istediğiniz dosyaları seçin. Seçtiğiniz dosyaların bir .zip dosyasına sıkıştırılır.  

8.  .Zip dosyasını kopyalayın ve kullanıcı öğesi şablonu konumda yapıştırın. Visual Studio 2017 ' varsayılan dizinidir... \Users\\< kullanıcı adı\>\Documents\Visual Studio 2017\Templates\ItemTemplates\\. Daha fazla bilgi için bkz: nasıl yapılır: bulun ve düzenleme proje ve öğe şablonları.  

## <a name="see-also"></a>Ayrıca Bkz.  
 [Proje ve öğe şablonları oluşturma](../ide/creating-project-and-item-templates.md)   
 [Nasıl yapılır: çok dosyalı öğe şablonları oluşturma](../ide/how-to-create-multi-file-item-templates.md)   
 [Visual Studio Şablon Şeması Başvurusu](../extensibility/visual-studio-template-schema-reference.md)
