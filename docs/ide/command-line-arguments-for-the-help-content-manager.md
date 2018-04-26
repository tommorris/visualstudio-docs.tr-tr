---
title: Komut satırı bağımsız değişkenleri için Yardım içeriği Yöneticisi
ms.date: 11/01/2017
ms.prod: visual-studio-dev15
ms.technology: vs-help-viewer
ms.topic: reference
ms.assetid: 3aa9890a-1147-42ba-adea-17935d184038
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 8a804ea329594a342a91c7f74e9ff32cd0206bed
ms.sourcegitcommit: e13e61ddea6032a8282abe16131d9e136a927984
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/26/2018
---
# <a name="command-line-arguments-for-the-help-content-manager"></a>Komut satırı bağımsız değişkenleri için Yardım içeriği Yöneticisi

Dağıtma ve komut satırı bağımsız değişkenleri için Yardım içeriği Yöneticisi'ni kullanarak yerel Yardım içeriği yönetme belirtebilirsiniz (*HlpCtntMgr.exe*). Yönetici izinlerine sahip bu komut satırı aracı için komut dosyalarını çalıştırması gereken ve bir hizmet olarak bu komut dosyalarını çalıştıramazsınız. Bu aracı kullanarak aşağıdaki görevleri gerçekleştirebilirsiniz:

-   Ekleyin veya bir disk veya Bulut yerel Yardım içeriği güncelleştirin.

-   Yerel Yardım içeriğini kaldırın.

-   Yerel Yardım içerik deposu taşıyın.

-   Ekle, Güncelleştir, kaldırın veya yerel Yardım içeriği sessizce taşıyın.

Sözdizimi:

```
HlpCtntmgr.exe /operation Value /catalogname CatalogName /locale Locale /sourceuri InstallationPoint
```

Örneğin:

```
hlpctntmgr.exe /operation install /catalogname VisualStudio15 /locale en-us /sourceuri d:\productDocumentation\HelpContentSetup.msha
```

## <a name="switches-and-arguments"></a>Anahtarlar ve bağımsız değişkenler

Aşağıdaki tabloda anahtarlar ve Yardım içeriği Yöneticisi için komut satırı aracı için kullanabileceğiniz bağımsız değişkenler tanımlar:

|Anahtar|Gerekli mi?|Arguments|
|------------|---------------|---------------|
|/operation|Evet|-   **Yükleme**--books belirtilen yükleme kaynağından yerel içerik deposuna ekler.<br />     Bu anahtar /booklist bağımsız değişkeni, /sourceURI bağımsız değişkeni ya da her ikisini de gerektirir. /SourceURI bağımsız değişkeni belirtmezseniz, varsayılan Visual Studio URI yükleme kaynağı olarak kullanılır. /Booklist bağımsız değişkeni belirtmezseniz, /sourceUri üzerinde tüm kitaplar yüklenir.<br />-   **Kaldırma**--yerel içerik deposundan belirttiğiniz books kaldırır.<br />     Bu anahtar /booklist bağımsız değişken veya /sourceURI bağımsız değişken gerektirir.  /SourceURI bağımsız değişkeni belirtirseniz, tüm books kaldırılır ve /booklist bağımsız değişkeni göz ardı edilir.<br />-   **Taşıma**--belirttiğiniz yolun yerel deposu taşır. Varsayılan yerel deposu yolu altında bir dizin olarak ayarlanmış olan *ProgramData %*<br />     Bu anahtar /locationPath ve /catalogName bağımsız değişkenler gerektirir. Hata iletileri, geçersiz bir yol belirtirseniz veya sürücüyü içeriği tutmak için yeterli boş alan içermiyorsa, olay günlüğüne kaydedilir.<br />-   **Yenileme**--yüklü veya en yakın bir zamanda güncelleştirilmiş bu yana değişmiş konuları güncelleştirir.<br />     Bu anahtar /sourceURI bağımsız değişken gerektiriyor.|
|/catalogName|Evet|İçerik katalog adını belirtir.|
|/ Locale|Hayır|Görüntülemek ve Yardım Görüntüleyici'nin geçerli örneğe ilişkin içeriği yönetmek için kullanılan ürün yerel ayarları belirtir. Örneğin, belirttiğiniz `EN-US` Türkçe için.<br /><br /> Yerel ayar belirtmezseniz, işletim sisteminin yerel kullanılır. Bu yerel ayara belirlenemiyorsa `EN-US` kullanılır.<br /><br /> Geçersiz yerel ayar belirtirseniz, bir hata iletisi olay günlüğüne kaydedilir.|
|/e|Hayır|Geçerli kullanıcının yönetici kimlik bilgileri varsa Yardım içeriği Yöneticisi için yönetici ayrıcalıkları yükseltir.|
|/sourceURI|Hayır|İçerik olduğu URL (hizmeti API'si) yüklü belirtir veya içerik yükleme dosyasının yolunu (*.msha*). URL ürün grubu (en üst düzey düğüm) veya bir Visual Studio 2010 stili uç noktada ürün Books (yaprak düzeyinde düğümü) işaret edebilir. URL'nin sonuna bir eğik çizgi (/) içeren gerek yoktur. Eğik eklerseniz, uygun şekilde ele alınır.<br /><br /> İnternet bağlantısı kullanılamıyor veya içerik yönetilen sırada kesintiye bir hata iletisi ya da günlük bulunamadıysa, bir dosya belirtirseniz, geçerli değil veya erişilebilir değil olay günlüğe kaydedilir.|
|Vendor|Hayır|Kaldırılacak ürün içeriği satıcısının belirtir (örneğin, `Microsoft`). Microsoft bu anahtar için varsayılan değişkendir.|
|/ ProductName|Hayır|Kaldırılacak books ürün adını belirtir. Ürün adı tanımlanmıştır *helpcontentsetup.msha* veya *books.html* içerik ile gönderilen dosyaları. Aynı anda yalnızca bir üründen books kaldırabilirsiniz. Birden çok ürünlerden Books kaldırmak için birden fazla yüklemesi gerçekleştirmeniz gerekir.|
|/booklist|Hayır|Yönetilen, boşluklarla ayırarak books adlarını belirtir. Yükleme medyasında listelendiği gibi değerler kitap adları eşleşmelidir.<br /><br /> Bu bağımsız değişken belirtmezseniz, /sourceURI belirtilen ürün için tüm önerilen kitaplar yüklenir.<br /><br /> Kitap adı bir veya daha fazla boşluk içeriyorsa, böylece listeden uygun şekilde ayrılmış çift tırnak (") koyun.<br /><br /> Geçerli değil veya erişilebilir değil bir /sourceURI belirtirseniz, hata iletisi günlüğe kaydedilmeyecek.|
|/skuId|Hayır|/SourceURI anahtarı tanımlayan books filtreler ve stok birimini (SKU) ürününü yükleme kaynağından tutma belirtir.|
|/Membership|Hayır|-   **En düşük**--/skuId anahtarı kullanarak belirttiğiniz SKU göre Yardım içeriği en az bir dizi yükler. SKU ve İçerik kümesi arasında eşleme hizmeti API'si açıktır.<br />-   **Önerilen**— /skuId bağımsız değişkenini kullanarak belirttiğiniz SKU önerilen books kümesi yükler. Yükleme kaynağını hizmet API'dir veya *. MSHA*.<br />-   **Tam**--kümesinin tamamını books /skuId bağımsız değişkenini kullanarak belirttiğiniz SKU yükler. Yükleme kaynağını hizmet API'dir veya *. MSHA*.|
|/locationpath|Hayır|Yerel Yardım içerik için varsayılan klasörü belirtir. Yalnızca yüklemek veya içeriği taşımak için bu anahtarı kullanmanız gerekir. Bu anahtar belirtirseniz, / silent de belirtmeniz gerekir geçin.|
|/silent|Hayır|Yükler veya kullanıcıya sormadan veya durum bildirim alanında simgesi dahil olmak üzere herhangi bir UI görüntülemeden olmadan Yardım içeriği kaldırır. Çıktıyı bir dosyaya kaydedilir *% Temp %* dizin. **Önemli:** içeriği sessizce yüklemek için dijital olarak imzalanmış kullanmalısınız *.cab* dosyaları değil, *.mshc* dosyaları.|
|/launchingApp|Hayır|Yardım Görüntüleyici üst uygulaması başlatıldığında uygulama ve Katalog bağlamı tanımlar. Bu anahtar için bağımsız değişkenler *ŞirketAdı*, *ProductName*, ve *VersionNumber* (örneğin, `/launchingApp Microsoft,VisualStudio,15.0`).<br /><br /> Bu içeriği ile/silent yüklemek için gerekli parametre.|
|/ wait *saniye*|Hayır|Duraklatır yüklemek, kaldırmak ve işlemleri yenileyin. Bir işlem zaten katalog için devam ediyor, işlemin belirtilen sayıda devam etmek için saniye bekler. Belirsiz bir süre beklemek için 0 kullanın.|
|/?|Hayır|Anahtarlar ve açıklamaları için Yardım içeriği Yöneticisi için komut satırı aracı listeler.|

### <a name="exit-codes"></a>Çıkış kodları

Yardım içeriği Yöneticisi için sessiz modda komut satırı aracı çalıştırdığınızda, aşağıdaki çıkış kodlarını döndürür:

```
Success = 0,

FailureToElevate = 100
InvalidCmdArgs = 101,
FailOnFetchingOnlineContent = 110,
FailOnFetchingContentFromDisk = 120,
FailOnFetchingInstalledBooks = 130,
NoBooksToUninstall = 200,
NoBooksToInstall = 300,
FailOnUninstall = 400,
FailOnInstall = 500,
FailOnMove = 600,
FailOnUpdate = 700,
FailOnRefresh = 800,
Cancelled = 900,
Others = 999,
ContentManagementDisabled = 1200,
OnlineHelpPreferenceDisabled = 1201
UpdateAlreadyRunning = 1300 - (Signals that the update didn't run because another was in progress.)
```

## <a name="see-also"></a>Ayrıca bkz.

- [Yardım Görüntüleyicisi Yönetici Kılavuzu](../ide/help-viewer-administrator-guide.md)
- [Yardım İçerik Yöneticisi geçersiz kılar](../ide/help-content-manager-overrides.md)
- [Microsoft Yardım Görüntüleyicisi](../ide/microsoft-help-viewer.md)