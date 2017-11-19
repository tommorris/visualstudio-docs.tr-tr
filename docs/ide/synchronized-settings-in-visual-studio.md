---
title: "Visual Studio'da ayarlarınızı eşitleme | Microsoft Docs"
ms.custom: 
ms.date: 01/23/2017
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-general
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: VS.ToolsOptionsPages.Environment.RoamingSettings
ms.assetid: a3d2ea29-be5d-4012-9820-44b06adbb7dd
caps.latest.revision: "10"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: 9d9c163063cfa4e2a78f8a07ab74efbecb355448
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2017
---
# <a name="synchronize-your-settings-in-visual-studio"></a>Visual Studio'da ayarlarınızı eşitleyin

Visual Studio için birden çok bilgisayarda oturum açtığında varsayılan olarak aynı kişiselleştirme hesabı kullanarak tüm bilgisayarlarda ayarlarınızı eşitlenir.

## <a name="synchronized-settings"></a>Eşitlenmiş ayarlar

Varsayılan olarak, aşağıdaki ayarları eşitlenir.

- Geliştirme Ayarları (ayarlar belirlemeniz ilk kez Visual Studio çalıştırın, ancak seçimi dilediğiniz zaman değiştirebilirsiniz. Daha fazla bilgi için bkz: [Visual Studio IDE'yi kişiselleştirme](../ide/personalizing-the-visual-studio-ide.md).)

- Aşağıdaki seçenekleri **Araçları &#124; Seçenekler** sayfaları:

    - **Tema** ve menü çubuğunda ayarlar, büyük/küçük harfleri çubuğu **ortam**, **genel** Seçenekleri sayfası

    - Tüm ayarları **ortam**, **yazı tiplerini ve renkleri** Seçenekleri sayfası

    - Tüm, üzerinde klavye kısayolları **ortam**, **klavye** Seçenekleri sayfası

    - Tüm ayarları **ortamı, sekmeler ve pencereler** Seçenekleri sayfası

    - Tüm ayarları **ortam**, **başlangıç** Seçenekleri sayfası

    - Tüm ayarları **metin düzenleyici** seçenekleri sayfaları

    - Tüm ayarları **XAML Tasarımcısı** seçenekleri sayfaları

- Kullanıcı tanımlı komut diğer adları. Komut diğer adları tanımlama hakkında daha fazla bilgi için bkz: [Visual Studio komut diğer adları](../ide/reference/visual-studio-command-aliases.md).

- Kullanıcı tanımlı pencere düzenlerini de **pencere &#124; Pencere düzenlerini yönetmek** sayfası

## <a name="turn-off-synchronized-settings-on-a-particular-computer"></a>Belirli bir bilgisayardaki eşitlenmiş ayarlar devre dışı bırakma

Visual Studio için eşitlenmiş ayarlar varsayılan olarak açıktır. Bir bilgisayarda eşitlenmiş ayarlar giderek kapatabilirsiniz **Araçları &#124; Seçenekler &#124; Ortam &#124; Ayarları senkronize** onay kutusunu işaretleyerek ve sayfa.  Örneğin, bir bilgisayardaki Visual Studio'nun ayarları senkronize değil karar verirseniz, ayarı yapılan herhangi bir değişiklik bilgisayarda bilgisayar b'de gösterilmiyor yapın veya bilgisayar C. bilgisayar B ve C devam birbirleriyle ancak değil bilgisayarla A. eşitlemek

## <a name="synchronize-settings-across-visual-studio-family-products-and-editions"></a>Visual Studio ailesi ürünleri ve sürümleri üzerinden ayarları eşitleme

Visual Studio Community sürümü de dahil olmak üzere, herhangi bir sürümünü ayarları eşitlenebilir. Ayarlar ayrıca Visual Studio ailesindeki ürünler arasında eşitlenir. Ancak, bu ailesi ürünlerinin her biri ile Visual Studio paylaşılmayan kendi ayarlarına sahip olabilir. Bir bilgisayardaki bir ürün için özel ayarları ile başka bir bilgisayar B, ancak değil bilgisayar A veya b Visual Studio gibi paylaşılır

## <a name="side-by-side-synchronized-settings"></a>Yan yana eşitlenmiş ayarlar

Visual Studio 15.3 ve daha sonra biz konumunu değiştirerek farklı yan yana yüklemesini Visual Studio 2017 arasında aracı pencere düzenini gibi belirli ayarlar paylaşımını durdurdu `CurrentSettings.vssettings` dosyasını `%userprofile%\Documents\Visual Studio 2017\Settings` belirli bir yükleme için benzer klasör `%localappdata%\Microsoft\VisualStudio\15.0_xxxxxxxx\Settings`.

**Not**: yeni yükleme belirli ayarlarını kullanmak için yeni bir yüklemesidir tamamlamanız gerekir. Mevcut bir Visual Studio 2017 yüklemesini son güncelleştirmeye yükselttiğinizde, mevcut paylaşılan konum kullanılır. Şu anda Visual Studio 2017 yan yana yüklemelerine sahip ve yükseltme ve yeni yükleme belirli ayarları dosyası kullanmak istiyorsanız karar verirseniz, aşağıdaki adımları izleyin:

1. Yükseltmeden sonra bazı konuma dışında tüm var olan ayarları dışarı aktarmak için Import\Export Ayarları Sihirbazı'nı kullanın. `%localappdata%\Microsoft\VisualStudio\15.0_xxxxxxxx` klasör.
2. Açık **VS 2017 için geliştirici komut istemi** yükseltilen Visual Studio yükleme ve çalıştırma `devenv /resetuserdata` almaktır.
3. Visual Studio’yu başlatın ve dışarı aktarılan ayarlar dosyasından kayıtlı ayarları içeri aktarın.

## <a name="see-also"></a>Ayrıca bkz.

[IDE'yi kişiselleştirme](../ide/personalizing-the-visual-studio-ide.md)
