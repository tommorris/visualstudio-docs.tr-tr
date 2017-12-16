---
title: "Nasıl yapılır: Visual Studio şablon sorunlarını giderme | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-general
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: templates [Visual Studio], troubleshooting
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: 2e34741e620c471809108f624b8bc0f9120c0a5a
ms.sourcegitcommit: 64c7682ec3a2cbea684e716803398d4278b591d1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/15/2017
---
# <a name="how-to-troubleshoot-templates"></a>Nasıl yapılır: şablonlarda sorun giderme

Geliştirme ortamında yüklemek bir şablon başarısız olursa, sorunu bulmanın birkaç yolu vardır.

## <a name="validating-the-vstemplate-file"></a>.Vstemplate dosyası doğrulanıyor

Bir şablon .vstemplate dosyasında için uymaz varsa [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] şablon şeması şablonu görüntülenmeyebilir **yeni proje** iletişim kutusu.

### <a name="to-validate-the-vstemplate-file"></a>.Vstemplate dosyasını doğrulamak için

1.  Şablonu içeren .zip dosyasını bulun.  

2.  .Zip dosyasını ayıklayın.  

3.  Üzerinde **dosya** menüde [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)], tıklatın **açık**ve ardından **dosya**.

4.  Şablon için .vstemplate dosyasını seçin ve tıklatın **açık**.  
  
5.  .Vstemplate dosyasının XML uyduğundan emin olun [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] şablon şeması. .Vstemplate şeması hakkında daha fazla bilgi için bkz: [Visual Studio şablon şeması başvurusu](../extensibility/visual-studio-template-schema-reference.md).  

    > [!NOTE]
    > .Vstemplate dosyasına yazma sırasında IntelliSense destek almak için ekleme bir `xmlns` özniteliğini `VSTemplate` öğesi ve http://schemas.microsoft.com/developer/vstemplate/2005 değerini atayın.

6.  .vstemplate dosyasını kaydedip kapatın.  
  
7.  Şablonunuzda, içerdiği dosyaları seçin dosyaya sağ tıklayın, **göndermek için**, tıklatıp **sıkıştırılmış (daraltılmış) klasör**. Seçtiğiniz dosyaların bir .zip dosyasına sıkıştırılır.  
  
8.  Yeni .zip dosyası eski .zip dosyası ile aynı dizine koyun.  
  
9. Ayıklanan şablon dosyalarını ve eski şablonu .zip dosyasını silin.

## <a name="monitoring-the-event-log"></a>Olay günlüğünü izleme

[!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)]Şablon .zip dosyalarını işleme sırasında karşılaşılan hataları günlüğe kaydeder. Bir şablon olarak gösterilmez, **yeni proje** iletişim kutusu olarak beklendiği gibi kullanabileceğiniz **Olay Görüntüleyicisi'ni** sorunu gidermek için.

### <a name="to-locate-template-errors-in-event-viewer"></a>Olay Görüntüleyicisi'nde şablon hatalarını bulmak için

1.  Windows'da tıklatın **Başlat**, tıklatın **Denetim Masası**, çift tıklatın **Yönetimsel Araçlar**, çift tıklayın ve ardından **Olay Görüntüleyicisi'ni**.  
  
2.  Sol bölmede **uygulama**.  
  
3.  Olaylarla arayın bir **kaynak** değerini `Visual Studio - VsTemplate`.  
  
4.  Hatayı görüntülemek için bir şablon olayı çift tıklatın.

## <a name="see-also"></a>Ayrıca bkz.

[Şablonlarını özelleştirme](../ide/customizing-project-and-item-templates.md)   
[Proje ve öğe şablonları oluşturma](../ide/creating-project-and-item-templates.md)   
[Visual Studio Şablon Şeması Başvurusu](../extensibility/visual-studio-template-schema-reference.md)