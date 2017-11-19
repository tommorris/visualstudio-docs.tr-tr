---
title: "Nasıl yapılır: çok dosyalı öğe şablonları oluşturma | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-general
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Visual Studio templates, creating multi-file item templates
- multi-file item templates
- item templates, creating multi-file item templates
ms.assetid: fe3c4257-e383-4c80-b8af-c5c521959c33
caps.latest.revision: "12"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: e3e1f6c6e62494f040e2f52180c5588688f460db
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2017
---
# <a name="how-to-create-multi-file-item-templates"></a>Nasıl Yapılır: Çok Dosyalı Şablonlar Oluşturma
Öğe şablonları yalnızca bir öğe belirtebilirsiniz, ancak bazen öğesi birden fazla dosyadan oluşur. Örneğin, bir Windows Forms öğesi şablonu Visual Basic için aşağıdaki üç dosyalar gerektirir:  
  
-   Form kodunu içeren bir .vb dosyası.  
  
-   A. formu Tasarımcı bilgilerini içeren Designer.vb olarak adlandırılır dosyası.  
  
-   Form için katıştırılmış kaynakları içeren bir .resx dosyası.  
  
 Çok dosyalı öğe şablonları gerektirir doğru dosya adı uzantılarını öğesi oluşturulduğunda kullanılır emin olmak için parametreleri [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)]. Kullanarak bir öğe şablonu oluşturursanız **şablonu dışarı aktar** Sihirbazı'nı bu parametreleri otomatik olarak oluşturulur ve başka düzenleme gereklidir. Aşağıdaki adımlarda parametreleri doğru dosya adı uzantılarını oluşturulmasını sağlamak için nasıl kullanılacağı açıklanmaktadır.  
  
### <a name="to-manually-create-a-multi-file-item-template"></a>Çok dosyalı öğe şablonu el ile oluşturmak için  
  
1.  Tek Dosyalı öğe şablonu oluşturacak şekilde öğesi şablonu oluşturun. Daha fazla bilgi için bkz: [nasıl yapılır: öğe şablonları oluşturma](../ide/how-to-create-item-templates.md).  
  
2.  Ekleme `TargetFileName` her öznitelikleri `ProjectItem` öğesi. Değerlerini ayarlamak `TargetFileName` öznitelikleri $fileinputname$. *FileExtension*, burada *FileExtension* şablona dahil dosyasının dosya adı uzantısıdır. Örneğin:  
  
    ```  
    <ProjectItem TargetFileName="$fileinputname$.vb">  
        Form1.vb  
    </ProjectItem>  
    <ProjectItem TargetFileName="$fileinputname$.Designer.vb">  
        Form1.Designer.vb  
    </ProjectItem>  
    <ProjectItem TargetFileName="$fileinputname$.resx">  
        Form1.resx  
    </ProjectItem>  
    ```  
  
     Bu şablondan türetilen bir öğe projeye eklendiğinde, dosya adları kullanıcı yazdığınız ad dayalı olacak **Yeni Öğe Ekle** iletişim kutusu.  
  
3.  Şablonunuzda eklenmesi, seçime sağ tıklayın, dosyaya seçin **göndermek için**ve ardından **sıkıştırılmış (daraltılmış) klasör**. Seçtiğiniz dosyaların bir .zip dosyasına sıkıştırılır.  
  
4.  .Zip dosyasını kullanıcı öğesi şablonu konumda koyun. Varsayılan olarak, \My Documents\Visual Studio dizindir *sürüm*\Templates\ItemTemplates\\. Daha fazla bilgi için bkz: [nasıl yapılır: bulun ve düzenleme şablonlarını](../ide/how-to-locate-and-organize-project-and-item-templates.md).  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnekte gösterildiği bir [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] Windows Forms şablon. Bir öğe bu şablona dayalı olarak oluşturulduğunda oluşturulan üç dosyaların adlarını girdiğiniz ad ile eşleşir **Yeni Öğe Ekle** iletişim kutusu.  
  
```  
<VSTemplate Version="2.0.0" Type="Item"  
    xmlns="http://schemas.microsoft.com/developer/vstemplate/2005">  
    <TemplateData>  
        <Name>Multi-file Item Template</Name>  
        <Icon>Icon.ico</Icon>  
        <Description>An example of a multi-file item template</Description>  
        <ProjectType>VisualBasic</ProjectType>  
    </TemplateData>  
    <TemplateContent>  
        <ProjectItem TargetFileName="$fileinputname$.vb" SubType="Form">  
            Form1.vb  
        </ProjectItem>  
        <ProjectItem TargetFileName="$fileinputname$.Designer.vb">  
            Form1.Designer.vb  
        </ProjectItem>  
        <ProjectItem TargetFileName="$fileinputname$.resx">  
            Form1.resx  
        </ProjectItem>  
    </TemplateContent>  
</VSTemplate>  
```  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Proje ve öğe şablonları oluşturma](../ide/creating-project-and-item-templates.md)   
 [Nasıl yapılır: öğe şablonları oluşturma](../ide/how-to-create-item-templates.md)   
 [Şablon parametreleri](../ide/template-parameters.md)   
 [Nasıl yapılır: şablonda parametreleri ikame etme](../ide/how-to-substitute-parameters-in-a-template.md)