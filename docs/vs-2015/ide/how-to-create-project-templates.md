---
title: 'Nasıl yapılır: Proje şablonları oluşturma | Microsoft Docs'
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-general
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- VS.ExportTemplateWizard
helpviewer_keywords:
- Visual Studio templates, creating project templates
- project templates, metadata files
- Visual Studio templates, project templates
- project templates, custom template locations
- project templates, creating
ms.assetid: a1a6999d-a34c-48a8-b1cf-027eb5c76398
caps.latest.revision: 22
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: e7e8efd905667c235d80d64e1c7ca7660281a9ea
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/22/2018
ms.locfileid: "42690305"
---
# <a name="how-to-create-project-templates"></a>Nasıl Yapılır: Proje Şablonları Oluşturma
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Bu konuda en son sürümünü şu yolda bulunabilir: [nasıl yapılır: Proje şablonları oluşturma](https://docs.microsoft.com/visualstudio/ide/how-to-create-project-templates).  
  
Bu yordamı kullanarak bir şablonu oluşturmanızı sağlayan **şablonu dışarı aktar** Sihirbazı'nı, ama bir .zip dosyası, şablonunuzda paketler. Şablonlar için geliştirilmiş dağıtım VSIX dosya biçiminde dışarı aktarma Şablon Sihirbazı uzantısı kullanarak ya da dahil şablonlarla oluşturabilirsiniz [!INCLUDE[vsipsdk](../includes/vsipsdk-md.md)], veya şablonları el ile oluşturabilirsiniz.  
  
### <a name="to-create-a-custom-project-template-with-the-standard-export-template-wizard"></a>Standart dışarı aktarma Şablonu Sihirbazı ile bir özel Proje şablonu oluşturmak için  
  
1.  Bir proje oluşturun.  
  
    > [!NOTE]
    >  Bir proje adlandırma şablon kaynağını ne zaman yalnızca geçerli tanımlayıcı karakterler kullanın. Bir proje adı geçersiz karakterler ile'den dışarı aktarılan bir şablonu gelecekteki projeleri şablonu temel alan derleme hatalarına neden olabilir. Geçerli tanımlayıcı karakter hakkında daha fazla bilgi için bkz. [bildirilen öğe adları](http://msdn.microsoft.com/library/09d8843b-c0dc-4afe-9dab-87c439a69e66).  
  
2.  Bir şablon olarak dışarı hazır olana kadar proje düzenleyin.  
  
3.  Burada parametre değişikliğini gerçekleşmesi belirtmek için kod dosyaları uygun şekilde düzenleyin. Parametre değiştirme hakkında daha fazla bilgi için bkz. [nasıl yapılır: şablonda parametreleri ikame](../ide/how-to-substitute-parameters-in-a-template.md).  
  
4.  Üzerinde **dosya** menüsünü tıklatın **şablonu dışarı aktar**. **Şablonu dışarı aktar** Sihirbazı açılır.  
  
5.  Tıklayın **proje şablonu**.  
  
6.  Geçerli çözümdeki birden fazla projeniz varsa, bir şablonu dışarı aktarmak istediğiniz projeleri seçin.  
  
7.  **İleri**'ye tıklayın.  
  
8.  Bir simge ve şablonunuz için bir önizleme görüntüsü seçin. Bunlar görünür **yeni proje** iletişim kutusu.  
  
9. Bir şablon adı ve açıklama girin.  
  
10. **Son**'a tıklayın. Projenize bir .zip dosyasına dışarı aktardığınız ve belirtilen çıkış konumda ve yanıt seçtiyseniz, içeri aktarılan [!INCLUDE[vsprvs](../includes/vsprvs-md.md)].  
  
     Varsa [!INCLUDE[vsipsdk](../includes/vsipsdk-md.md)] yüklüyse, tamamlanan şablon dağıtımı için bir .vsix dosyasında kullanarak kayabilir **VSIX projesi** şablonu. Daha fazla bilgi için [VSIX proje şablonu ile çalışmaya başlama](../extensibility/getting-started-with-the-vsix-project-template.md).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Proje ve öğe şablonları oluşturma](../ide/creating-project-and-item-templates.md)   
 [Nasıl Yapılır: Öğe Şablonları Oluşturma](../ide/how-to-create-item-templates.md)



