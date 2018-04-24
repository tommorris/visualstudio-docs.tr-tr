---
title: Visual Studio Proje şablonu ve öğe şablonu yükleme sorunlarını giderme | Microsoft Docs
ms.custom: ''
ms.date: 01/02/2018
ms.technology: vs-ide-general
ms.topic: conceptual
helpviewer_keywords:
- templates [Visual Studio], troubleshooting
author: gewarren
ms.author: gewarren
manager: douge
ms.openlocfilehash: f7e952f8eb445787a2a574ae3431ba6ad8728248
ms.sourcegitcommit: 42ea834b446ac65c679fa1043f853bea5f1c9c95
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/19/2018
---
# <a name="how-to-troubleshoot-templates"></a>Nasıl yapılır: şablonlarda sorun giderme

Geliştirme ortamında yüklemek bir şablon başarısız olursa, sorunu bulmanın birkaç yolu vardır.

## <a name="validate-the-vstemplate-file"></a>.Vstemplate dosyasını doğrulama

Varsa *.vstemplate* şablon dosyasında Visual Studio şablon şeması için uygun değil, şablon görüntülenmeyebilir **yeni proje** iletişim kutusu.

### <a name="to-validate-the-vstemplate-file"></a>.Vstemplate dosyasını doğrulamak için

1. Bulun *.zip* şablonu içeren dosya.

1. Extract *.zip* dosyası.

1. Üzerinde **dosya** Visual Studio menüsünde seçin **açık** > **dosya**.

1. Seçin *.vstemplate* için şablon dosyasını bulun ve seçin **açık**.

1. Doğrulayın XML'sini *.vstemplate* dosya aynılarını şablon şeması. Daha fazla bilgi için *.vstemplate* şeması, bkz: [şablon şeması başvurusu](../extensibility/visual-studio-template-schema-reference.md).

    > [!NOTE]
    > Geliştirme sırasında IntelliSense destek almak için *.vstemplate* dosya, ekleme bir `xmlns` özniteliğini `VSTemplate` öğesi ve değerini atayın http://schemas.microsoft.com/developer/vstemplate/2005.

1. Kaydet ve Kapat *.vstemplate* dosya.

1. Şablonunuzda, bulunan dosyalar seçin, sağ tıklatın ve seçin **göndermek** > **sıkıştırılmış (daraltılmış) klasör**. Seçtiğiniz dosyalar halinde sıkıştırılmış bir *.zip* dosyası.

1. Yeni yerleştirin *.zip* eski ile aynı dizinde dosya *.zip* dosyası.

1. Ayıklanan şablon dosyalarını ve eski şablonu silmek *.zip* dosyası.

## <a name="enable-diagnostic-logging"></a>Tanılama günlük kaydını etkinleştir

İçindeki adımları izleyerek şablon bulma için tanılama günlük kaydını etkinleştirebilirsiniz [sorun giderme şablon bulma (genişletilebilirlik)](../extensibility/troubleshooting-template-discovery.md).

## <a name="see-also"></a>Ayrıca bkz.

[Şablon bulma (genişletilebilirlik) sorunlarını giderme](../extensibility/troubleshooting-template-discovery.md)  
[Şablonları özelleştirme](../ide/customizing-project-and-item-templates.md)  
[Proje ve öğe şablonları oluşturma](../ide/creating-project-and-item-templates.md)  
[Şablon Şeması Başvurusu](../extensibility/visual-studio-template-schema-reference.md)