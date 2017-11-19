---
title: "Nasıl yapılır: Proje şablonları oluşturma | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-general
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: VS.ExportTemplateWizard
helpviewer_keywords:
- Visual Studio templates, creating project templates
- project templates, metadata files
- Visual Studio templates, project templates
- project templates, custom template locations
- project templates, creating
ms.assetid: a1a6999d-a34c-48a8-b1cf-027eb5c76398
caps.latest.revision: "19"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: a473ac2be65acc9b08455fe687b52468f5ca9fa6
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2017
---
# <a name="how-to-create-project-templates"></a>Nasıl Yapılır: Proje Şablonları Oluşturma
Bu yordamı kullanarak bir şablon oluşturmanızı sağlayan **şablonu dışarı aktar** bir .zip dosyası şablonunuzda paketleri Sihirbazı. Şablonları VSIX dosyası biçiminde geliştirilmiş dağıtım için şablonu Dışarı Aktarma Sihirbazı uzantısını kullanarak ya da dahil şablonlarıyla oluşturabilirsiniz [!INCLUDE[vsipsdk](../extensibility/includes/vsipsdk_md.md)], veya şablonları el ile oluşturabilirsiniz.  
  
### <a name="to-create-a-custom-project-template-with-the-standard-export-template-wizard"></a>Standart şablon Dışarı Aktarma Sihirbazı'yla bir özel Proje şablonu oluşturmak için  
  
1.  Bir proje oluşturun.  
  
    > [!NOTE]
    >  Bir proje adlandırma bir şablon kaynağı olacaktır, yalnızca geçerli bir tanımlayıcı karakterlerini kullanın. Geçersiz karakterlerle adlı bir projeden dışa aktarılan bir şablonu gelecekte projeleri şablona dayalı derleme hataları neden olabilir. Geçerli bir tanımlayıcı karakterler hakkında daha fazla bilgi için bkz: [bildirilen öğe adları](/dotnet/visual-basic/programming-guide/language-features/declared-elements/declared-element-names).  
  
2.  Bir şablon olarak dışarı hazır olana kadar proje düzenleyin.  
  
3.  Parametre değiştirme burada gerçekleşeceğini belirtmek için kod dosyaları uygun şekilde düzenleyin. Parametre değiştirme hakkında daha fazla bilgi için bkz: [nasıl yapılır: şablonda parametreleri ikame](../ide/how-to-substitute-parameters-in-a-template.md).  
  
4.  Üzerinde **proje** menüsünde tıklatın **şablonu dışarı aktar**. **Şablonu dışarı aktar** Sihirbazı açılır.  
  
5.  Tıklatın **proje şablonu**.  
  
6.  Birden çok proje, geçerli çözümünüz varsa, bir şablonu dışarı aktarmak istediğiniz projeleri seçin.  
  
7.  
              **İleri**'ye tıklayın.  
  
8.  Bir simge ve şablonunuz için Önizleme görünümü seçin. Bunlar görünür **yeni proje** iletişim kutusu.  
  
9. Bir şablon adı ve açıklama girin.  
  
10. **Son**'a tıklayın. Projenizi bir .zip dosyasına dışarı aktardığınız ve belirtilen çıkış konumda ve, seçili olduğunda, içeri aktarılan [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)].  
  
     Varsa [!INCLUDE[vsipsdk](../extensibility/includes/vsipsdk_md.md)] yüklü, tamamlanmış şablon dağıtımı için bir .vsix dosyasında kullanarak kayabilir **VSIX proje** şablonu. Daha fazla bilgi için bkz: [VSIX proje şablonu ile çalışmaya başlama](../extensibility/getting-started-with-the-vsix-project-template.md).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Proje ve öğe şablonları oluşturma](../ide/creating-project-and-item-templates.md)   
 [Nasıl yapılır: öğe şablonları oluşturma](../ide/how-to-create-item-templates.md)
