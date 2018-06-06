---
title: Ayarlarınızı eşitleyin
ms.date: 01/23/2017
ms.prod: visual-studio-dev15
ms.technology: vs-ide-general
ms.topic: conceptual
f1_keywords:
- VS.ToolsOptionsPages.Environment.RoamingSettings
ms.assetid: a3d2ea29-be5d-4012-9820-44b06adbb7dd
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 633767e66a4b3d976999574c885a3e6f7a06ddcf
ms.sourcegitcommit: 4cd4aef53e7035d23e7d1d0f66f51ac8480622a1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/05/2018
ms.locfileid: "34766135"
---
# <a name="synchronize-visual-studio-settings-across-multiple-computers"></a>Birden fazla bilgisayara Visual Studio ayarları eşitleme

Visual Studio için birden çok bilgisayar üzerinde aynı kişiselleştirme hesabı kullanarak oturum açtığında, bilgisayarlar arasında ayarlarınızı eşitlenebilir.

## <a name="synchronized-settings"></a>Eşitlenmiş ayarlar

Varsayılan olarak, aşağıdaki ayarları eşitlenir:

- Geliştirme Ayarları. Ayarlar belirlemeniz ilk kez Visual Studio çalıştırın, ancak seçimi dilediğiniz zaman değiştirebilirsiniz. Daha fazla bilgi için bkz: [Visual Studio IDE'yi kişiselleştirme](../ide/personalizing-the-visual-studio-ide.md).

- Kullanıcı tanımlı komut diğer adları. Komut diğer adları tanımlama hakkında daha fazla bilgi için bkz: [Visual Studio komut diğer adları](../ide/reference/visual-studio-command-aliases.md).

- Kullanıcı tanımlı pencere düzenlerini de **penceresi** > **yönetmek pencere düzenlerini** sayfası.

- Aşağıdaki seçenekleri **Araçları** > **seçenekleri** sayfaları:

   - Tema ve menü çubuğu büyük/küçük harf ayarlarının **ortam** > **genel** seçenekler sayfası.

   - Tüm ayarları **ortam** > **yazı tiplerini ve renkleri** seçenekler sayfası.

   - Tüm üzerinde klavye kısayolları **ortam** > **klavye** seçenekler sayfası.

   - Tüm ayarları **ortam** > **sekmeler ve pencereler** seçenekler sayfası.

   - Tüm ayarları **ortam** > **başlangıç** seçenekler sayfası.

   - Tüm ayarları **metin düzenleyici** seçenekleri sayfaları.

   - Tüm ayarları **XAML Tasarımcısı** seçenekleri sayfaları.

## <a name="turn-off-synchronized-settings-on-a-particular-computer"></a>Belirli bir bilgisayardaki eşitlenmiş ayarlar devre dışı bırakma

Visual Studio için eşitlenmiş ayarlar varsayılan olarak açıktır. Bir bilgisayarda eşitlenmiş ayarlar giderek kapatabilirsiniz **Araçları** > **seçenekleri** > **ortam**  >   **Hesapları** işaretleyerek ve sayfa **Visual Studio'ya imzalandığında aygıtları üzerinden ayarları eşitleme**. "A" bilgisayarındaki Visual Studio'nun ayarları senkronize değil karar verirseniz, örneğin, "A" bilgisayar ayarı değişiklikleri "B" veya "C" bilgisayarda görünmez. "B" ve "C" bilgisayarları birbirleriyle ancak değil bilgisayarla "A" eşitlemeye devam eder.

## <a name="reset-settings"></a>Ayarlarını Sıfırla

Aşağıdaki adımları izleyerek, tüm ayarlar için varsayılan ayarlar koleksiyonu sıfırlayabilirsiniz:

1. Visual Studio'da seçin **Araçları** > **içeri ve dışarı aktarma ayarları** açmak için **içeri ve dışarı aktarım ayarları Sihirbazı**.

1. İçinde **içeri ve dışarı aktarım ayarları Sihirbazı**seçin **tüm ayarlara** ve ardından **sonraki**.

   ![İçeri ve dışarı aktarma ayarları Sihirbazı Visual Studio'da](media/reset-all-settings.png)

1. Üzerinde **geçerli ayarları Kaydet** sayfasında, seçin **Evet** veya **Hayır** ve ardından **sonraki**.

1. Üzerinde **varsayılan ayarları koleksiyonu seçin** sayfasında, bir koleksiyon seçin ve ardından **son**.

   ![Visual Studio'da ayarları koleksiyonları](media/settings-collections.png)

1. Üzerinde **sıfırlama tam** sayfasında, **Kapat**.

## <a name="synchronize-settings-across-visual-studio-family-products-and-editions"></a>Visual Studio ailesi ürünleri ve sürümleri üzerinden ayarları eşitleme

Visual Studio Community sürümü de dahil olmak üzere, herhangi bir sürümünü ayarları eşitlenebilir. Ayarlar ayrıca Visual Studio ailesindeki ürünler arasında eşitlenir. Ancak, bu ailesi ürünlerinin her biri Visual Studio ile paylaşılmaz kendi ayarlarına sahip olabilir. Örneğin, ayarları belirli bir ürüne bilgisayarda "A", "B" bilgisayarda başka bir ürün ancak değil bilgisayarlarda "A" veya "B" Visual Studio ile paylaşılır.

## <a name="side-by-side-synchronized-settings"></a>Yan yana eşitlenmiş ayarlar

Visual Studio 2017 sürüm 15.3 ve daha sonra aracı pencere düzenini gibi belirli ayarlar Visual Studio 2017 farklı yan yana yüklemeler arasında paylaşılmaz. *CurrentSettings.vssettings* dosyasını *%userprofile%\Documents\Visual Studio 2017\Settings* benzer bir özel yükleme klasöründeki *%localappdata%\ Microsoft\VisualStudio\15.0_xxxxxxxx\Settings*.

> [!NOTE]
> Yeni yükleme özgü ayarları kullanmak için yeni bir yüklemesidir yapın. Varolan bir Visual Studio 2017 yüklemesinin en güncel güncelleştirmeyi Yükseltme gerçekleştirdiğinizde, var olan paylaşılan konuma kullanır.

Şu anda Visual Studio 2017 yan yana yüklemesini varsa ve yeni yükleme özgü ayarları dosyası konumu kullanmak istiyorsanız, aşağıdaki adımları izleyin:

1. Visual Studio 2017 15.3 veya sonraki bir sürümü yükseltin.

1. Kullanım **Import\Export ayarları** bazı konuma dışında tüm var olan ayarları dışarı aktarmak için Sihirbazı *%localappdata%\Microsoft\VisualStudio\15.0_xxxxxxxx* klasör.

1. Açık **VS 2017 için geliştirici komut istemi** yükseltilen Visual Studio yükleme ve çalıştırma `devenv /resetuserdata`.

1. Visual Studio’yu başlatın ve dışarı aktarılan ayarlar dosyasından kayıtlı ayarları içeri aktarın.

## <a name="see-also"></a>Ayrıca bkz.

[IDE'yi kişiselleştirme](../ide/personalizing-the-visual-studio-ide.md)
