---
title: Visual Studio 2017 kaldırma | Microsoft Docs
description: Visual Studio, bilgisayarınızdan adım adım tamamen kaldırmak öğrenin.
ms.custom: ''
ms.date: 09/12/2017
ms.technology: vs-acquisition
ms.prod: visual-studio-dev15
ms.topic: conceptual
f1_keywords:
- uninstall
- uninstall Visual Studio
- remove
- remove Visual Studio
- cleanup
- cleanup Visual Studio
- clean up
- clean up Visual Studio
ms.assetid: 9c81a777-9c95-4934-b517-c60c6dc78799
author: heaths
ms.author: tglee
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: b32fc71efadbf319f3d713c3eaf4d86f382646a5
ms.sourcegitcommit: 4cd4aef53e7035d23e7d1d0f66f51ac8480622a1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/05/2018
ms.locfileid: "34476839"
---
# <a name="remove-visual-studio"></a>Visual Studio Kaldır

Yıkıcı hatayla karşılaşan ve onarmak veya Visual Studio'yu kaldırmak, çalıştırabilirsiniz `InstallCleanup.exe` aracı yükleme dosyalarını ve ürün bilgileri kaldırmak için. Bu araç çalışır durumda değilse son çare olarak yapılması onarma veya kaldırma işlemi başarısız oldu ve özellikler, diğer Visual Studio yüklemeleri ya da onarılması gereken diğer ürünleri kaldırabilirsiniz.

Aşağıdaki yönergeleri aşağıdaki davranış ile farklı komut satırı anahtarları ile aracını çalıştırabilirsiniz:

| Anahtar | Davranış |
| ------ | -------- |
| `-i`   | Başka bir anahtarı iletilir ve yalnızca ana yükleme dizini ve ürün bilgileri kaldırır, bu anahtarı varsayılan değerdir. Bu davranış, çalıştırdıktan sonra aynı sürümünü yeniden yüklemek istiyorsanız, tercih edilir `InstallCleanup.exe` aracı. |
| `-f`   | Bu anahtarın belirtilmesi ana yükleme dizini, ürün bilgilerini ve diğer Visual Studio yüklemeler veya diğer ürünleri ile paylaşılan yükleme dizini dışındaki yüklenen çoğu özellikleri kaldırır. Bu davranış, daha sonra yeniden yüklemeden Visual Studio kaldırmak istiyorsanız, tercih edilir. |

1. Visual Studio Yükleyicisi’ni kapatın.
2. Bir yönetici komut istemi açın. Bir yönetici komut istemi açmak için şu adımları izleyin:
   * Tıklatın **Başlat** menüsü
   * Tür **cmd**.
   * **Komut İstemi**'ne sağ tıklayın ve ardından **Yönetici olarak çalıştır**'a tıklayın.
3. Tam yolunu yazın `InstallCleanup.exe` yardımcı programı ve istediğiniz hangi komut satırı anahtarı geçirin. Varsayılan olarak, yardımcı program yolu aşağıdaki gibidir:
   ```
   C:\Program Files (x86)\Microsoft Visual Studio\Installer\resources\app\layout\InstallCleanup.exe
   ```

Bulamadı, `InstallCleanup.exe` Visual Studio yükleyicisi dizini altında - her zaman bulunan `%ProgramFiles(x86)%\Microsoft Visual Studio` -yönergelerini izleyin [Visual Studio yükleme](install-visual-studio.md) ve iş yükünü seçme ekranı görüntülendiğinde, Kapat Pencere ve yukarıdaki yeniden adımları izleyin.

## <a name="get-support"></a>Destek alma

Bazı durumlarda, şeyler yanlış gidebilirsiniz. Visual Studio yüklemenizin başarısız olursa bkz [sorun giderme Visual Studio 2017 yükleme ve yükseltme sorunlarını](troubleshooting-installation-issues.md) sayfası. Sorun giderme adımlarını hiçbiri yardımcı, bize yükleme Yardımı (yalnızca İngilizce) için canlı sohbet tarafından başvurabilirsiniz. Ayrıntılar için bkz [Visual Studio destek sayfası](https://www.visualstudio.com/vs/support/#talktous).

Birkaç diğer destek seçenekleri şunlardır:

* Ürün sorunları bize bildirebilirsiniz [bir sorun bildirmek](../ide/how-to-report-a-problem-with-visual-studio-2017.md) hem Visual Studio Yükleyicisi ve Visual Studio IDE görünür aracı.
* Üzerinde bir ürün önerisi bizimle paylaşın [UserVoice](https://visualstudio.uservoice.com/forums/121579).
* Ürün sorunlarını izlemek ve yanıtlar bulmak [Visual Studio Geliştirici topluluğu](https://developercommunity.visualstudio.com/).
* ABD ve diğer Visual Studio geliştiriciler aracılığıyla devreye [Gitter topluluk Visual Studio konuşmada](https://gitter.im/Microsoft/VisualStudio). (Bu seçenek gerektiren bir [GitHub](https://github.com/) hesabı.)

## <a name="see-also"></a>Ayrıca bkz.

* [Visual Studio 2017 yükleyin](install-visual-studio.md)
* [Visual Studio 2017 güncelleştir](update-visual-studio.md)
* [Visual Studio 2017 değiştirme](modify-visual-studio.md)
* [Visual Studio 2017 kaldırma](uninstall-visual-studio.md)
