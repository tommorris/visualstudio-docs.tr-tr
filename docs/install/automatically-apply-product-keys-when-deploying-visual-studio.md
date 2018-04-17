---
title: Visual Studio'yu dağıtırken ürün anahtarlarını otomatik olarak Uygula | Microsoft Docs
ms.custom: ''
ms.date: 08/14/2017
ms.reviewer: tims
ms.technology:
- vs-acquisition
ms.topic: conceptual
ms.assetid: d79260be-6234-4fd3-89b5-a9756b4a93c1
author: TerryGLee
ms.author: tglee
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: f6a8e00d15e49aeab990c797197fec445db45b59
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/16/2018
---
# <a name="automatically-apply-product-keys-when-deploying-visual-studio"></a>Visual Studio'yu dağıtırken ürün anahtarlarını otomatik olarak Uygula
Ürün anahtarınızı program aracılığıyla Visual Studio dağıtımını otomatik hale getirmek için kullanılan bir komut dosyasının parçası olarak uygulayabilirsiniz. Bir ürün anahtarı bir aygıtta program aracılığıyla Visual Studio veya bir yükleme tamamlandıktan sonra bir yükleme sırasında ya da ayarlayabilirsiniz.

## <a name="apply-the-license-after-installation"></a>Yüklemeden sonra lisans Uygula
 Kullanarak bir yüklü olan sürümü Visual Studio ürün anahtarıyla etkinleştirebilirsiniz `StorePID.exe` sessiz modda hedef makinelere yardımcı programı. `StorePID.exe` Visual Studio 2017 aşağıdaki varsayılan konuma yükler bir yardımcı programdır: <br> `C:\Program Files (x86)\Microsoft Visual Studio\2017\Enterprise\Common7\IDE`

 Çalıştırma `StorePID.exe` yükseltilmiş ayrıcalıklarla ya da kullanarak System Center aracı veya yükseltilmiş bir komut istemi. Ürün anahtarı ve Microsoft ürün kodu (MPC) ile izleyin.

>[!IMPORTANT]
> Ürün anahtarı tireler dahil ettiğinizden emin olun.

 ```
 StorePID.exe [product key including the dashes] [MPC]
 ```

 Visual Studio 2017 bir MPC 08860 biri olan bir kuruluş için lisans uygulamak için bir komut satırı aşağıdaki örnekte bir ürün anahtarı `AAAAA-BBBBB-CCCCC-DDDDDD-EEEEEE`, varsayılan yükleme konumu varsayar:

 ```cmd
 "C:\Program Files (x86)\Microsoft Visual Studio\2017\Enterprise\Common7\IDE\StorePID.exe" AAAAA-BBBBB-CCCCC-DDDDDD-EEEEEE 08860
 ```

 Aşağıdaki tabloda her Visual Studio sürümü için MPC kodlarını listeler:

| Visual Studio sürümü                | MPC   |
|--------------------------------------|-------|
| Visual Studio Enterprise 2017        | 08860 |
| Visual Studio Professional 2017      | 08862 |
| Visual Studio Test Uzmanı 2017 | 08866 |

Varsa `StorePID.exe` başarıyla döndürür ürün anahtarı geçerli bir `%ERRORLEVEL%` 0. Hatayla karşılaştığında hata koşulu bağlı olarak aşağıdaki kodlarından birini döndürür:

| Hata                     | Kod |
|---------------------------|------|
| `PID_ACTION_SUCCESS`      | 0    |
| `PID_ACTION_NOTINSTALLED` | 1.    |
| `PID_ACTION_INVALID`      | 2    |
| `PID_ACTION_EXPIRED`      | 3    |
| `PID_ACTION_INUSE`        | 4    |
| `PID_ACTION_FAILURE`      | 5    |
| `PID_ACTION_NOUPGRADE`    | 6    |

## <a name="get-support"></a>Destek alma
Bazı durumlarda, şeyler yanlış gidebilirsiniz. Visual Studio yüklemenizin başarısız olursa bkz [sorun giderme Visual Studio 2017 yükleme ve yükseltme sorunlarını](troubleshooting-installation-issues.md) sayfası. Sorun giderme adımlarını hiçbiri yardımcı, bize yükleme Yardımı (yalnızca İngilizce) için canlı sohbet tarafından başvurabilirsiniz. Ayrıntılar için bkz [Visual Studio destek sayfası](https://www.visualstudio.com/vs/support/#talktous).

Birkaç diğer destek seçenekleri şunlardır:
* Ürün sorunları bize bildirebilirsiniz [bir sorun bildirmek](../ide/how-to-report-a-problem-with-visual-studio-2017.md) hem Visual Studio Yükleyicisi ve Visual Studio IDE görünür aracı.
* Üzerinde bir ürün önerisi bizimle paylaşın [UserVoice](https://visualstudio.uservoice.com/forums/121579).
* Ürün sorunları izleyebilir [Visual Studio Geliştirici topluluğu](https://developercommunity.visualstudio.com/), soru sorun ve yanıtlarını bulun.
* ABD ve diğer Visual Studio geliştiriciler aracılığıyla devreye bizim [Gitter topluluk Visual Studio konuşmada](https://gitter.im/Microsoft/VisualStudio).  (Bu seçenek gerektiren bir [GitHub](https://github.com/) hesabı.)

## <a name="see-also"></a>Ayrıca Bkz.
 * [Visual Studio'yu yükleyin](../install/install-visual-studio.md)
 * [Visual Studio’nun çevrimdışı yüklemesini oluşturma](../install/create-an-offline-installation-of-visual-studio.md)
