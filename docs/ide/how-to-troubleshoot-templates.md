---
title: "Nasıl yapılır: şablonlarda sorun giderme | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-general
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: Visual Studio templates, troubleshooting
ms.assetid: 3e577ad2-f725-4c11-93b3-477f2404ec81
caps.latest.revision: "10"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: af00efbeb759bfc41d12e0ab814ecadd4bbc7799
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2017
---
# <a name="how-to-troubleshoot-templates"></a>Nasıl Yapılır: Şablonlarda Sorun Giderme
Geliştirme ortamında yüklemek bir şablon başarısız olursa, sorunu bulmanın birkaç yolu vardır.  
  
## <a name="validating-the-vstemplate-file"></a>.Vstemplate dosyası doğrulanıyor  
 Bir şablon .vstemplate dosyasında için uymaz varsa [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] şablon şeması şablonu görüntülenmeyebilir **yeni proje** iletişim kutusu.  
  
#### <a name="to-validate-the-vstemplate-file"></a>.Vstemplate dosyasını doğrulamak için  
  
1.  Şablonu içeren .zip dosyasını bulun.  
  
2.  .Zip dosyasını ayıklayın.  
  
3.  Üzerinde **dosya** menüde [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)], tıklatın **açık**ve ardından **dosya**.  
  
4.  Şablon için .vstemplate dosyasını seçin ve tıklatın **açık**.  
  
5.  .Vstemplate dosyasının XML uyduğundan emin olun [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] şablon şeması. .Vstemplate şeması hakkında daha fazla bilgi için bkz: [Visual Studio şablon şeması başvurusu](../extensibility/visual-studio-template-schema-reference.md).  
  
    > [!NOTE]
    >  .Vstemplate dosyasına yazma sırasında IntelliSense destek almak için ekleme bir `xmlns` özniteliğini `VSTemplate` öğesi ve http://schemas.microsoft.com/developer/vstemplate/2005 değerini atayın.  
  
6.  .vstemplate dosyasını kaydedip kapatın.  
  
7.  Şablonunuzda, içerdiği dosyaları seçin dosyaya sağ tıklayın, **göndermek için**, tıklatıp **sıkıştırılmış (daraltılmış) klasör**. Seçtiğiniz dosyaların bir .zip dosyasına sıkıştırılır.  
  
8.  Yeni .zip dosyası eski .zip dosyası ile aynı dizine koyun.  
  
9. Ayıklanan şablon dosyalarını ve eski şablonu .zip dosyasını silin.  
  
## <a name="monitoring-the-event-log"></a>Olay günlüğünü izleme  
 [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)]Şablon .zip dosyalarını işleme sırasında karşılaşılan hataları günlüğe kaydeder. Bir şablon olarak gösterilmez, **yeni proje** iletişim kutusu olarak beklendiği gibi kullanabileceğiniz **Olay Görüntüleyicisi'ni** sorunu gidermek için.  
  
#### <a name="to-locate-template-errors-in-event-viewer"></a>Olay Görüntüleyicisi'nde şablon hatalarını bulmak için  
  
1.  Windows'da tıklatın **Başlat**, tıklatın **Denetim Masası**, çift tıklatın **Yönetimsel Araçlar**, çift tıklayın ve ardından **Olay Görüntüleyicisi'ni**.  
  
2.  Sol bölmede **uygulama**.  
  
3.  Olaylarla arayın bir **kaynak** değerini `Visual Studio - VsTemplate`.  
  
4.  Hatayı görüntülemek için bir şablon olayı çift tıklatın.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Şablonlarını özelleştirme](../ide/customizing-project-and-item-templates.md)   
 [Proje ve öğe şablonları oluşturma](../ide/creating-project-and-item-templates.md)   
 [Visual Studio Şablon Şeması Başvurusu](../extensibility/visual-studio-template-schema-reference.md)