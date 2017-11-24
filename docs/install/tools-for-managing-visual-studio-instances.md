---
title: "Algılama ve Visual Studio Örnekleri yönetmek için Araçlar | Microsoft Docs"
description: '{{YER TUTUCU}}'
ms.date: 08/14/2017
ms.reviewer: 
ms.suite: 
ms.technology: vs-acquisition
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- '{{PLACEHOLDER}}'
- '{{PLACEHOLDER}}'
ms.assetid: 85686707-14C0-4860-9B7A-66485D43D241
author: timsneath
ms.author: tglee
manager: ghogen
ms.openlocfilehash: 28027f4e68231dfe413065e8ef3bf8f4abb2c487
ms.sourcegitcommit: eb954434c34b4df6fd2264266381b23ce9e6204a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/22/2017
---
# <a name="tools-for-detecting-and-managing-visual-studio-instances"></a>Algılama ve Visual Studio Örnekleri yönetmek için Araçlar

## <a name="detecting-existing-visual-studio-instances"></a>Mevcut Visual Studio Örnekleri algılama
Biz kullanılabilir algılamak ve istemci makinelerde yüklü Visual Studio Örnekleri yönetmenize yardımcı olacak birkaç araç yapmış olduğunuz:

* [VSWhere](https://github.com/microsoft/vswhere): Visual Studio yerleşik veya yardımcı olan ayrı dağıtım için kullanılabilir bir yürütülebilir dosya belirli bir makine üzerindeki tüm Visual Studio Örnekleri konumunu bulun.
* [VSSetup.PowerShell](https://github.com/microsoft/vssetup.powershell): yüklü Visual Studio Örnekleri belirlemek için kurulum yapılandırma API'si kullanan bir PowerShell Betiği.
* [VS Kurulum örnekleri](https://github.com/microsoft/vs-setup-samples): Kurulum yapılandırma API'si var olan bir yüklemesini sorgulamak için nasıl kullanılacağını gösteren C# ve C++ örnekleri.

Ayrıca, [kurulum yapılandırma API'si](https://msdn.microsoft.com/en-us/library/microsoft.visualstudio.setup.configuration.aspx) Visual Studio Örnekleri interrogating için kendi yardımcı programları derleme isteyen geliştiriciler için arabirim sağlar.

## <a name="using-vswhereexe"></a>Vswhere.exe kullanma
`vswhere.exe`Visual Studio 2017 sürüm 15.2 veya üzerini, otomatik olarak bulunan veya buradan indirebilirsiniz [sürümleri sayfa](https://github.com/Microsoft/vswhere/releases). Kullanım `vswhere -?` aracı hakkında Yardım bilgilerine ulaşmak için. Örnek olarak, bu komut ürün ve önsürümlerin, eski sürümleri dahil olmak üzere Visual Studio tüm sürümleri gösterir ve sonuçları JSON biçiminde çıkarır:

```cmd
C:\Program Files (x86)\Microsoft Visual Studio\Installer> vswhere.exe -legacy -prerelease -format json
```

>[!TIP]
>Visual Studio 2017 yükleme hakkında daha fazla bilgi için bkz: [sistem durumu Ilgaz'ın blogu makaleleri](https://blogs.msdn.microsoft.com/heaths/tag/vs2017/).


## <a name="editing-the-registry-for-a-visual-studio-instance"></a>Visual Studio örneği için kayıt defterini düzenleme
Visual Studio 2017 ' kayıt defteri ayarları, Visual Studio'nun aynı sürümü aynı bilgisayarda birden çok yan yana örneğini sağlayan özel bir konumda depolanır.

Bu girişler genel kayıt defterinde depolanmaz gibi kayıt defteri ayarları değişiklik yapmak için Kayıt Defteri Düzenleyicisi'ni kullanarak yönelik özel yönergeler vardır:

1. Visual Studio 2017 açık örneği varsa, kapatın.
2. Başlat `regedit.exe`.
3. Seçin `HKEY_LOCAL_MACHINE` düğümü.
4. Regedit ana menüden seçin **Dosya -> yığını...**  ve depolanan özel kayıt defteri dosyasını seçip **AppData\Local** klasör. Örneğin:
   ```
   %localappdata%\Microsoft\VisualStudio\<config>\privateregistry.bin
   ```

> [!NOTE]
> `<config>`Dosyaya Gözat ister Visual Studio örneğine karşılık gelir.

Yalıtılmış hive adı haline gelen bir hive adı sağlamanız istenir. Bunu yaptıktan sonra oluşturduğunuz yalıtılmış hive altında kayıt defterine Gözat yapabiliyor olmanız gerekir.

> [!IMPORTANT]
> Visual Studio yeniden başlatmadan önce oluşturduğunuz yalıtılmış kovanını gerekir. Bunu yapmak için dosyayı seçin yığın Regedit ana menüden ->. (Bunu durumunda dosya kilitli durumda kalır ve Visual Studio başlatmanız mümkün olmayacaktır.)

## <a name="get-support"></a>Destek alma
Bazı durumlarda, şeyler yanlış gidebilirsiniz. Visual Studio yüklemenizin başarısız olursa bkz [sorun giderme Visual Studio 2017 yükleme ve yükseltme sorunlarını](troubleshooting-installation-issues.md) sayfası. Sorun giderme adımlarını hiçbiri yardımcı, bize yükleme Yardımı (yalnızca İngilizce) için canlı sohbet tarafından başvurabilirsiniz. Ayrıntılar için bkz [Visual Studio destek sayfası](https://www.visualstudio.com/vs/support/#talktous).

Birkaç diğer destek seçenekleri şunlardır:
* Ürün sorunları bize bildirebilirsiniz [bir sorun bildirmek](../ide/how-to-report-a-problem-with-visual-studio-2017.md) hem Visual Studio Yükleyicisi ve Visual Studio IDE görünür aracı.
* Üzerinde bir ürün önerisi bizimle paylaşın [UserVoice](https://visualstudio.uservoice.com/forums/121579).
* Ürün sorunları izleyebilir [Visual Studio Geliştirici topluluğu](https://developercommunity.visualstudio.com/), soru sorun ve yanıtlarını bulun.
* ABD ve diğer Visual Studio geliştiriciler aracılığıyla devreye bizim [Gitter topluluk Visual Studio konuşmada](https://gitter.im/Microsoft/VisualStudio).  (Bu seçenek gerektiren bir [GitHub](https://github.com/) hesabı).

## <a name="see-also"></a>Ayrıca bkz.
* [Visual Studio Yöneticiler Kılavuzu](visual-studio-administrator-guide.md)
