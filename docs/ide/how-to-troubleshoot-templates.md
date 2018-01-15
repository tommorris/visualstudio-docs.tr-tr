---
title: "Visual Studio Proje şablonu ve öğe şablonu yükleme sorunlarını giderme | Microsoft Docs"
ms.custom: 
ms.date: 01/02/2018
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-general
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: templates [Visual Studio], troubleshooting
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: d9242d053044fa66e6eb3d506382cf7cfb5d0295
ms.sourcegitcommit: f89ed5fc2e5078213e30a6ade4604e34df48181f
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/13/2018
---
# <a name="how-to-troubleshoot-templates"></a>Nasıl yapılır: şablonlarda sorun giderme

Geliştirme ortamında yüklemek bir şablon başarısız olursa, sorunu bulmanın birkaç yolu vardır.

## <a name="validate-the-vstemplate-file"></a>.Vstemplate dosyasını doğrulama

Bir şablon .vstemplate dosyasında için Visual Studio şablon şeması uymaz, şablon görüntülenmeyebilir **yeni proje** iletişim kutusu.

### <a name="to-validate-the-vstemplate-file"></a>.Vstemplate dosyasını doğrulamak için

1. Şablonu içeren .zip dosyasını bulun.

1. .Zip dosyasını ayıklayın.

1. Üzerinde **dosya** Visual Studio menüsünde seçin **açık** > **dosya**.

1. Şablonu için .vstemplate dosyası seçin ve **açık**.

1. .Vstemplate dosyasının XML şablon şeması uyduğundan emin olun. .Vstemplate şeması hakkında daha fazla bilgi için bkz: [şablon şeması başvurusu](../extensibility/visual-studio-template-schema-reference.md).

    > [!NOTE]
    > .Vstemplate dosyasına yazma sırasında IntelliSense destek almak için ekleme bir `xmlns` özniteliğini `VSTemplate` öğesi ve http://schemas.microsoft.com/developer/vstemplate/2005 değerini atayın.

1. .vstemplate dosyasını kaydedip kapatın.

1. Şablonunuzda, bulunan dosyalar seçin, sağ tıklatın ve seçin **göndermek** > **sıkıştırılmış (daraltılmış) klasör**. Seçtiğiniz dosyaların bir .zip dosyasına sıkıştırılır.

1. Yeni .zip dosyası eski .zip dosyası ile aynı dizine koyun.

1. Ayıklanan şablon dosyalarını ve eski şablonu .zip dosyasını silin.

## <a name="enable-diagnostic-logging"></a>Tanılama günlük kaydını etkinleştir

İçindeki adımları izleyerek şablon bulma için tanılama günlük kaydını etkinleştirebilirsiniz [sorun giderme şablon bulma (genişletilebilirlik)](../extensibility/troubleshooting-template-discovery.md).

## <a name="see-also"></a>Ayrıca bkz.

[Sorun giderme şablon bulma (genişletilebilirliği)](../extensibility/troubleshooting-template-discovery.md)  
[Şablonlarını özelleştirme](../ide/customizing-project-and-item-templates.md)  
[Proje ve öğe şablonları oluşturma](../ide/creating-project-and-item-templates.md)  
[Şablon Şeması Başvurusu](../extensibility/visual-studio-template-schema-reference.md)