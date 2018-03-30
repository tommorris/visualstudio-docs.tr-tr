---
title: Visual Studio dağıtımları için güncelleştirmeleri denetlemek | Microsoft Docs
description: '{{PLACEHOLDER}}'
ms.date: 08/14/2017
ms.reviewer: tims
ms.suite: ''
ms.technology:
- vs-acquisition
ms.tgt_pltfrm: ''
ms.topic: conceptual
helpviewer_keywords:
- '{{PLACEHOLDER}}'
- '{{PLACEHOLDER}}'
ms.assetid: 35C7AB05-07D5-4B38-BCAC-AB88444E7368
author: tglee
ms.author: tglee
manager: ghogen
ms.workload:
- multiple
ms.openlocfilehash: 2dd91af67a3e9ef06e1090b14be9f28afd842327
ms.sourcegitcommit: 064f8678f4a918e1dce60285090a9803d37dc34b
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/30/2018
---
# <a name="control-updates-to-network-based-visual-studio-deployments"></a>Visual Studio dağıtımları ağ tabanlı denetim güncelleştirmeleri

Kuruluş yöneticileri genellikle bir düzeni oluşturmak ve bunların son kullanıcılara dağıtmak için bir ağ dosya paylaşımında bir ana bilgisayar.

## <a name="controlling-where-visual-studio-looks-for-updates"></a>Visual Studio için güncelleştirmeleri burada görünür denetleme
Varsayılan olarak, Visual Studio yükleme bir ağ paylaşımından dağıtılan olsa bile güncelleştirmeleri çevrimiçi aramaya devam eder. Bir güncelleştirme varsa, kullanıcı bunu yükleyebilir. Çevrimdışı düzeninde bulunamadı herhangi güncelleştirilmiş içerik Web'den indirilir.

Visual Studio için güncelleştirmeleri burada görünür üzerinde doğrudan denetim isterseniz, nerede görünüyor konumunu değiştirebilirsiniz. Kullanıcılarınız için güncelleştirilmiş sürümü de denetleyebilirsiniz. Bunu yapmak için aşağıdaki adımları izleyin:

 1. Çevrimdışı bir düzen oluşturun:
    ```
    vs_enterprise.exe --layout C:\vs2017offline --lang en-US
    ```
 2. Da barındırmak istediğiniz dosya paylaşımına kopyalayın:
    ```
    xcopy /e C:\vs2017offline \\server\share\VS2017
    ```
 3. Düzen ve değişiklik response.json dosyasında değişiklik `channelUri` yönetici denetimleri channelManifest.json kopyaya işaret edecek şekilde değeri.

  Aşağıdaki örnekte olduğu gibi değeri ters eğik çizgi kaçış emin olun:

  ```json
    "channelUri":"\\\\server\\share\\VS2017\\ChannelManifest.json"
  ```

 Artık son kullanıcıların Visual Studio'yu yüklemek için bu paylaşımından Kurulum çalıştırabilirsiniz.
    ```
    \\server\share\VS2017\vs_enterprise.exe
    ```

Kuruluş Yöneticisi zamanı için Visual Studio'nun daha yeni bir sürüme güncelleştirmek, kullanıcılar belirlediğinde yapabilir [düzeni konumunu güncelleştirmesi](update-a-network-installation-of-visual-studio.md) güncelleştirilmiş dosyaları gibi içerecek şekilde.

 1. Aşağıdaki komutu benzer bir komutu kullanın:
    ```
    vs_enterprise.exe --layout \\server\share\VS2017 --lang en-US
    ```
 2. Güncelleştirilmiş düzeni response.json dosyasında hala özelleştirmelerinizi, özellikle channelUri değiştirme gibi içerdiğinden emin olun:
    ```json
    "channelUri":"\\\\server\\share\\VS2017\\ChannelManifest.json"
    ```
 Mevcut Visual Studio yükler bu güncelleştirmeleri düzeni arayın gelen `\\server\share\VS2017\ChannelManifest.json`. Visual Studio channelManifest.json kullanıcı yüklü olduğu daha yeniyse bir güncelleştirme kullanıma hazır kullanıcıyı uyarır.

 Yeni yüklemeler otomatik olarak doğrudan düzeninden Visual Studio güncelleştirilmiş sürümünü yükleyin.

## <a name="controlling-notifications-in-the-visual-studio-ide"></a>Visual Studio IDE bildirimlerini denetleme
Daha önce açıklandığı gibi Visual Studio içinden, bir ağ paylaşımına veya herhangi bir güncelleştirme olup olmadığını görmek için Internet gibi yüklenmiş olduğu konumu denetler. Bir güncelleştirme kullanıma hazır olduğunda, Visual Studio pencerenin sağ üst köşesinde bir bildirim bayrağı ile kullanıcıyı uyarır.

 ![Güncelleştirmeleri için bildirim bayrağı](media/notification-flag.png)

Son kullanıcıları, güncelleştirmelerinin bildirilmesini için istemiyorsanız bildirimleri devre dışı bırakabilirsiniz. (Örneğin, bir merkezi yazılım dağıtım mekanizması güncelleştirmeleri gönderirseniz bildirimleri devre dışı bırakmak isteyebilirsiniz.)

İçin Visual Studio 2017 [kayıt defteri girdileri özel bir kayıt defterinde depolar](tools-for-managing-visual-studio-instances.md#editing-the-registry-for-a-visual-studio-instance), normal şekilde kayıt defterini doğrudan düzenleyemezsiniz. Ancak, Visual Studio içeren bir `vsregedit.exe` Visual Studio ayarlarını değiştirmek için kullanabileceğiniz yardımcı programı. Aşağıdaki komutla bildirimleri devre dışı bırakabilirsiniz:

```cmd
vsregedit.exe set "C:\Program Files (x86)\Microsoft Visual Studio\2017\Enterprise" HKCU ExtensionManager AutomaticallyCheckForUpdates2Override dword 0
```
(Dizin düzenlemek istediğiniz yüklü örneği eşleşecek şekilde değiştirdiğinizden emin olun.)

> [!TIP]
> Kullanım [vswhere.exe](tools-for-managing-visual-studio-instances.md#detecting-existing-visual-studio-instances) istemci iş istasyonunda Visual Studio belirli bir örneği bulunamıyor.

## <a name="get-support"></a>Destek alma
Bazı durumlarda, şeyler yanlış gidebilirsiniz. Visual Studio yüklemenizin başarısız olursa bkz [sorun giderme Visual Studio 2017 yükleme ve yükseltme sorunlarını](troubleshooting-installation-issues.md) sayfası. Sorun giderme adımlarını hiçbiri yardımcı, bize yükleme Yardımı (yalnızca İngilizce) için canlı sohbet tarafından başvurabilirsiniz. Ayrıntılar için bkz [Visual Studio destek sayfası](https://www.visualstudio.com/vs/support/#talktous).

Birkaç diğer destek seçenekleri şunlardır:
* Ürün sorunları bize bildirebilirsiniz [bir sorun bildirmek](../ide/how-to-report-a-problem-with-visual-studio-2017.md) hem Visual Studio Yükleyicisi ve Visual Studio IDE görünür aracı.
* Üzerinde bir ürün önerisi bizimle paylaşın [UserVoice](https://visualstudio.uservoice.com/forums/121579).
* Ürün sorunları izleyebilir [Visual Studio Geliştirici topluluğu](https://developercommunity.visualstudio.com/), soru sorun ve yanıtlarını bulun.
* ABD ve diğer Visual Studio geliştiriciler aracılığıyla devreye bizim [Gitter topluluk Visual Studio konuşmada](https://gitter.im/Microsoft/VisualStudio).  (Bu seçenek gerektiren bir [GitHub](https://github.com/) hesabı.)

## <a name="see-also"></a>Ayrıca bkz.
* [Visual Studio'yu yükleyin](install-visual-studio.md)
* [Visual Studio Yönetici Kılavuzu](visual-studio-administrator-guide.md)
* [Komut satırı parametrelerini kullanarak Visual Studio'yu yükleme](use-command-line-parameters-to-install-visual-studio.md)
* [Visual Studio Örnekleri yönetmek için Araçlar](tools-for-managing-visual-studio-instances.md)
