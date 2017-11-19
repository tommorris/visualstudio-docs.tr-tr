---
title: "Nasıl yapılır: bulma ve düzenleme proje ve öğe şablonlarını | Microsoft Docs"
ms.custom: 
ms.date: 06/02/2017
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-general
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- project templates [Visual Studio], locations
- custom template locations [Visual Studio]
- item templates, locations
- Visual Studio templates, locations
- project templates [Visual Studio], displaying
- templates [Visual Studio], locations
ms.assetid: 71f9ed52-c9c9-4818-9bce-c279ffaa0438
caps.latest.revision: "25"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: 1846b145833a7474e8662442313d0e39a262e67c
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2017
---
# <a name="how-to-locate-and-organize-project-and-item-templates"></a>Nasıl Yapılır: Proje ve Öğe Şablonlarını Bulma ve Düzenleme
Şablon dosyalarını yerleştirildiğinde, Visual Studio tanır ve böylece şablonları görünür bir konumda **yeni proje** ve **Yeni Öğe Ekle** iletişim kutuları. Alt kategoriler de kullanıcı arabiriminde görünmesi için özel alt kategorileri şablonları oluşturabilirsiniz.  

## <a name="locating-templates"></a>Şablonları bulma  
 Varsayılan olarak, Visual Studio Proje ve öğe şablonları için iki konumları arar. .Vstemplate dosya içeren sıkıştırılmış bir dosya konumları varsa, bir şablon görünür **yeni proje** veya **Yeni Öğe Ekle** iletişim kutuları.  

### <a name="installed-templates"></a>Yüklü Şablonlar  
 Ürün ile birlikte yüklenen şablonları varsayılan olarak bulunur:  

-   \\*VisualStudioInstallationDirectory*\Common7\IDE\ItemTemplates\\*dil*\\*yerel ayar*\  

-   \\*VisualStudioInstallationDirectory*\Common7\IDE\ProjectTemplates\\*dil*\\*yerel ayar\\*  

 Örneğin, aşağıdaki dizini içeren [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] proje şablonlarını İngilizce için:  

 C:\\*VisualStudioInstallationDirectory*\Common7\IDE\ItemTemplates\VisualBasic\1033\  

### <a name="custom-templates"></a>Özel şablonlar  
 Özel şablonları varsayılan olarak bulunur:  

-   \My Documents\Visual studio *sürüm*\Templates\ProjectTemplates\\*dili*\  

-   \My Documents\Visual studio *sürüm*\Templates\ItemTemplates\\*dili*\  

 Örneğin, şu dizine özel içeren [!INCLUDE[csprcs](../data-tools/includes/csprcs_md.md)] proje şablonları:  

 C:\Documents and Settings\Kullanıcıadı\My Documents\Visual Studio *sürüm*\Templates\ProjectTemplates\Visual C# \  

 Özel şablonlar yerelleştirilmiş şablonlar için bir alt dahil etmeyin. Özel şablonlar, varsayılan dizini değiştirebilirsiniz **seçenekleri** iletişim kutusunda **Environment\Projects ve çözümleri**.  

## <a name="organizing-templates"></a>Şablonları düzenleme  
 Kategorileri **yeni proje** ve **Yeni Öğe Ekle** iletişim kutuları yüklü ve özel şablon konumları mevcut dizin yapıları yansıtır. Şablonlarınızı sizin için anlamlı bir şekilde düzenlemek için bu dizin yapıları değiştirebilirsiniz.  

> [!NOTE]
>  Yeni bir kategori programlama dili düzeyinde oluşturulamıyor. Yeni kategoriler yalnızca her bir dilin oluşturulabilir.  

 Belirli bir dil için yüklü ve özel şablonlar için dizin yapıları aynı yapısını yoksa (diğer bir deyişle, vardır altında bir klasör diğer yok dizinleri) görünür kategorileri kümesini **yeni Proje** iletişim tüm kategorileri birleşme olacaktır.  

### <a name="organizing-installed-templates"></a>Düzenleme yüklenmiş şablonlar  
 Yüklü Şablonlar programlama dili klasöründe alt dizinleri oluşturarak düzenleyebilirsiniz. Bu alt dizinlere görünür **yeni proje** ve **Yeni Öğe Ekle** iletişim kutuları her dil sanal klasörlere olarak.  

##### <a name="to-create-new-installed-project-template-categories"></a>Şablon kategorileri yeni yüklü projesi oluşturmak için  

1.  Yüklü şablon dizin dil klasöründe bir klasör oluşturun. Örneğin, bir Office kategori için oluşturmak için [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] proje şablonları oluşturma şu dizine:  

     \\*VisualStudioInstallationDirectory*\Common7\IDE\ProjectTemplates\VisualBasic\1033\Office\  

2.  Bu kategori için tüm şablonları bu yeni klasöre yerleştirin.  

3.  Tüm örneklerini kapatın [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)].  

4.  Üzerinde **Başlat** menüsünde tıklatın **çalıştırmak**, türü **cmd**, tıklatıp **Tamam**.  

5.  Komut isteminde devenv.exe ve türünü içeren dizine bulun **devenv /installvstemplates**.  

6.  Çalıştırma [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)].  

7.  Üzerinde **dosya** menüsünde tıklatın **yeni**ve ardından **proje**.  

8.  Office kategori göründüğünü doğrulayın **yeni proje** iletişim kutusunda **proje türleri** bölmesi altında [!INCLUDE[vbprvb](../code-quality/includes/vbprvb_md.md)].  

 Bir proje öğesi şablonları alt özel bir klasöre de gruplandırabilirsiniz.  

##### <a name="to-create-new-installed-item-template-categories"></a>Şablon kategorileri yeni yüklü öğesi oluşturmak için  

1.  Yüklü şablon dizin dil klasöründe bir klasör oluşturun. Örneğin, bir Web kategori için oluşturmak için [!INCLUDE[csprcs](../data-tools/includes/csprcs_md.md)] öğe şablonları oluşturma şu dizine:  

     \\*VisualStudioInstallationDirectory*\Common7\IDE\ItemTemplates\CSharp\1033\Web\  

2.  Bu kategori için tüm şablonları bu yeni klasöre yerleştirin.  

3.  Tüm örneklerini kapatın [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)].  

4.  Üzerinde **Başlat** menüsünde tıklatın **çalıştırmak**, türü **cmd**, tıklatıp **Tamam**.  

5.  Komut isteminde devenv.exe ve türünü içeren dizine bulun **devenv/Setup**.  

6.  Çalıştırma [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)].  

7.  Bir proje oluşturun veya varolan projeyi açın.  

8.  Üzerinde **proje** menüsünde tıklatın **Yeni Öğe Ekle**.  

9. Web kategori göründüğünü doğrulayın **Yeni Öğe Ekle** iletişim kutusunda **proje türleri** bölmesi.  

### <a name="organizing-custom-templates"></a>Özel şablonlar düzenleme  
 Özel şablonlar kendi kategoriye özel bir şablon konumda yeni klasörler ekleyerek düzenlenebilir. **Yeni proje** iletişim kutusu, şablon kategorileri yaptığınız değişiklikleri yansıtır.  

##### <a name="to-create-new-custom-project-template-categories"></a>Şablon kategorileri yeni özel projesi oluşturmak için  

1.  Özel proje şablonu dizinine dil klasöründe bir klasör oluşturun. Örneğin, bir HelloWorld kategori için oluşturmak için [!INCLUDE[csprcs](../data-tools/includes/csprcs_md.md)] şablonlar şu dizine oluşturabilir:  

     \My Documents\Visual studio *sürüm*\Templates\ProjectTemplates\CSharp\HelloWorld\  

2.  Bu kategori için tüm şablonları bu yeni klasöre yerleştirin.  

3.  Üzerinde **dosya** menüsünde tıklatın **yeni**ve ardından **proje**.  

4.  HelloWorld kategori göründüğünü doğrulayın **yeni proje** iletişim kutusunda **proje türleri** bölmesi altında [!INCLUDE[csprcs](../data-tools/includes/csprcs_md.md)].  

 Özel öğe şablonları kümesini özel bir klasöre de gruplandırabilirsiniz.  

##### <a name="to-create-new-custom-item-template-categories"></a>Şablon kategorileri yeni özel öğesi oluşturmak için  

1.  Özel öğesi şablon dizini dil klasöründe bir klasör oluşturun. Örneğin, bir HelloWorld kategori için oluşturmak için [!INCLUDE[csprcs](../data-tools/includes/csprcs_md.md)] şablonları aşağıdaki dizini oluşturmak:  

     \My Documents\Visual studio *sürüm*\Templates\ItemTemplates\CSharp\HelloWorld\  

2.  Bu kategori için tüm şablonları bu yeni klasöre yerleştirin.  

3.  Bir proje oluşturun veya varolan projeyi açın.  

4.  Üzerinde **proje** menüsünde tıklatın **Yeni Öğe Ekle**.  

5.  HelloWorld kategori göründüğünü doğrulayın **Yeni Öğe Ekle** iletişim kutusunda **proje türleri** bölmesi.  

### <a name="displaying-templates-in-parent-categories"></a>Ana kategoride şablonları görüntüleme  
 Alt kategorileri kullanarak kendi üst kategori görüntülenecek şablonlarında etkinleştirebilirsiniz `NumberOfParentCategoriesToRollUp` .vstemplate dosyasındaki öğesi. Proje şablonları ve öğe şablonları için aşağıdaki adımları aynıdır.  

##### <a name="to-display-templates-in-parent-categories"></a>Üst kategorilerdeki şablonları görüntülemek için  

1.  Şablonu içeren .zip dosyasını bulun.  

2.  .Zip dosyasını ayıklayın.  

3.  .Vstemplate dosyasında açma [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)].  

4.  İçinde `TemplateData` öğesi ekleme bir `NumberOfParentCategoriesToRollUp` öğesi. Örneğin, aşağıdaki kodu üst kategori görünür, ancak bundan daha yüksek şablonu sağlar.  

    ```  
    <TemplateData>  
        ...  
        <NumberOfParentCategoriesToRollUp>  
            1  
        </NumberOfParentCategoriesToRollUp>  
        ...  
    </TemplateData>  
    ```  

5.  .vstemplate dosyasını kaydedip kapatın.  

6.  Şablonunuzda dosyaları seçin, seçime sağ tıklayın, **göndermek için**ve ardından **sıkıştırılmış (daraltılmış) klasör**. Dosyalar bir .zip dosyasına sıkıştırılır.  

7.  Ayıklanan şablon dosyalarını ve eski şablonu .zip dosyasını silin.  

8.  Yeni .zip dosyasını silinen .zip dosyası olan dizinde koyun.  

## <a name="see-also"></a>Ayrıca Bkz.  
 [Şablonlarını özelleştirme](../ide/customizing-project-and-item-templates.md)   
 [Visual Studio Şablon Şeması Başvurusu](../extensibility/visual-studio-template-schema-reference.md)   
 [NumberOfParentCategoriesToRollUp (Visual Studio şablonları)](../extensibility/numberofparentcategoriestorollup-visual-studio-templates.md)   
 [Nasıl yapılır: Proje şablonları oluşturma](../ide/how-to-create-project-templates.md)   
 [Nasıl yapılır: öğe şablonları oluşturma](../ide/how-to-create-item-templates.md)
