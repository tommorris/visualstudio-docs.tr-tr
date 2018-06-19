---
title: Visual Studio yükleme yanıt dosyası ile otomatikleştirme
description: Visual Studio yüklemenizin otomatikleştirmenize yardımcı olan bir JSON yanıt dosyası oluşturma hakkında bilgi edinin
ms.date: 08/14/2017
ms.technology: vs-acquisition
ms.prod: visual-studio-dev15
ms.topic: conceptual
helpviewer_keywords:
- response file
- automate
- installation
- command-line
author: TerryGLee
ms.author: tglee
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: ef060f77a7ac580cb93c93f8e48889b7f19e4fab
ms.sourcegitcommit: 4c0bc21d2ce2d8e6c9d3b149a7d95f0b4d5b3f85
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/20/2018
ms.locfileid: "31622061"
---
# <a name="how-to-define-settings-in-a-response-file"></a>Bir yanıt dosyası ayarları tanımlama

Visual Studio dağıtan Yöneticiler, bir yanıt dosyası kullanarak belirtebilirsiniz `--in` aşağıdaki örnekteki gibi parametre:

```cmd
vs_enterprise.exe --in customInstall.json
```

Yanıt dosyaları [JSON](http://json-schema.org/) içeriği yansıtmak komut satırı bağımsız değişkenleri dosyaları.  Bağımsız değişken içermeyen bir komut satırı parametresi sürerse, genel olarak, (örneğin, `--quiet`, `--passive`, vb.), yanıt dosyasındaki değer true/false olmalıdır.  Bağımsız değişken aldığı durumlarda (örneğin, `--installPath <dir>`), yanıt dosyasındaki değer bir dize olmalıdır.  Bir bağımsız değişken ve komut satırında birden çok kez yer alabilir (örneğin, `--add <id>`), bir dizeler dizisi olmalıdır.

Parametreleri birden çok girişi alırken, yanıt dosyasındaki komut satırı geçersiz kılma ayarları dışında belirtilen parametreler (örneğin, `--add`). Birden çok girişi sahip olduğunuzda, komut satırında girişleri yanıt dosyası ayarları ile birleştirilir.

## <a name="setting-a-default-configuration-for-visual-studio"></a>Visual Studio için varsayılan bir yapılandırma ayarı

Bir ağ düzeni önbellekle oluşturduysanız `--layout`, bir başlangıç `response.json` dosya düzende oluşturulur. Kısmi bir düzen oluşturursanız, bu yanıt dosyası düzende eklenmiş olan dilleri ve iş yükleri içerir.  Kurulum bu düzeninden otomatik olarak çalıştırarak düzende bileşenleri ve iş yükleri seçer bu response.json dosyası kullanır.  Kullanıcılar hala seçin veya Visual Studio yüklemeden önce tüm iş yükleri UI kurulumunda seçimini kaldırın.

Bir düzen oluşturma Yöneticiler değiştirebilirsiniz `response.json` Visual Studio düzenden yükledikleri zaman, kullanıcılar Bkz varsayılan ayarlarını denetlemek için Düzen dosyasında.  Örneğin, bir yönetici, belirli iş yükleri ve varsayılan olarak yüklü bileşenleri isterse, yapılandırabileceği `response.json` bunları eklemek için dosya.

Visual Studio kurulumunda bir düzen klasöründen çalıştırdığınızda, _otomatik olarak_ düzeni klasöründe yanıt dosyasını kullanır.  Kullanmak zorunda değilsiniz `--in` seçeneği.

Güncelleştirebilirsiniz `response.json` bu düzeninden yükleyen kullanıcılar için varsayılan ayar tanımlamak için bir çevrimdışı düzeni klasörde oluşturulan dosya.

> [!WARNING]
> Düzen oluşturulduğunda tanımlanmış olan mevcut özellikleri bırakın önemlidir.

Temel `response.json` ürün ve yüklemek istediğiniz kanal değeri içerir ancak bu bir düzen dosyasında aşağıdaki örnektekine benzer görünmelidir:

```json
{
  "installChannelUri": ".\\ChannelManifest.json",
  "channelUri": "https://aka.ms/vs/15/release/channel",
  "installCatalogUri": ".\\Catalog.json",
  "channelId": "VisualStudio.15.Release",
  "productId": "Microsoft.VisualStudio.Product.Enterprise"
}
```

Bir düzen oluştururken veya güncelleştirirken, response.template.json dosyası da oluşturulur.  Bu dosya tüm iş yükü, bileşen ve dil kullanılabilir kimliklerini içerir.  Bu dosya, hangi tümü için bir şablon özel bir yükleme içinde yer alan sağlanır.  Yöneticiler bu dosya için bir özel yanıt dosyasını bir başlangıç noktası olarak kullanabilirsiniz.  Yalnızca yükleme ve kendi yanıt dosyasına kaydetmek istiyor musunuz şeyler için kimlikleri kaldırın.  Response.template.json dosyasını özelleştirme değil veya düzeni güncelleştirildiğinde yaptığınız değişiklikler kaybolacak.

## <a name="example-layout-response-file-content"></a>Örnek düzeni yanıt dosyası içeriği

Aşağıdaki örnekte, altı ortak iş yükleri ve bileşenleri ve İngilizce ve Fransızca kullanıcı Arabirimi dilleri ile Visual Studio Enterprise yükler. Bu örnek bir şablon olarak kullanabilirsiniz; yalnızca iş yükleri ve bileşenlerini yüklemek istediğiniz o değiştirin:

```json
{
  "installChannelUri": ".\\ChannelManifest.json",
  "channelUri": "https://aka.ms/vs/15/release/channel",
  "installCatalogUri": ".\\Catalog.json",
  "channelId": "VisualStudio.15.Release",
  "productId": "Microsoft.VisualStudio.Product.Enterprise",

  "installPath": "C:\\VS2017",
  "quiet": false,
  "passive": false,
  "includeRecommended": true,
  "norestart": false,

  "addProductLang": [
    "en-US",
    "fr-FR"
    ],

    "add": [
        "Microsoft.VisualStudio.Workload.ManagedDesktop",
        "Microsoft.VisualStudio.Workload.Data",
        "Microsoft.VisualStudio.Workload.NativeDesktop",
        "Microsoft.VisualStudio.Workload.NetWeb",
        "Microsoft.VisualStudio.Workload.Office",
        "Microsoft.VisualStudio.Workload.Universal",
        "Component.GitHub.VisualStudio"
    ]
}
```

## <a name="get-support"></a>Destek alma

Bazı durumlarda, şeyler yanlış gidebilirsiniz. Visual Studio yüklemenizin başarısız olursa bkz [sorun giderme Visual Studio 2017 yükleme ve yükseltme sorunlarını](troubleshooting-installation-issues.md) sayfası. Sorun giderme adımlarını hiçbiri yardımcı, bize yükleme Yardımı (yalnızca İngilizce) için canlı sohbet tarafından başvurabilirsiniz. Ayrıntılar için bkz [Visual Studio destek sayfası](https://www.visualstudio.com/vs/support/#talktous).

Birkaç diğer destek seçenekleri şunlardır:

* Ürün sorunları bize bildirebilirsiniz [bir sorun bildirmek](../ide/how-to-report-a-problem-with-visual-studio-2017.md) hem Visual Studio Yükleyicisi ve Visual Studio IDE görünür aracı.
* Üzerinde bir ürün önerisi bizimle paylaşın [UserVoice](https://visualstudio.uservoice.com/forums/121579).
* Ürün sorunlarını izlemek ve yanıtlar bulmak [Visual Studio Geliştirici topluluğu](https://developercommunity.visualstudio.com/).
* ABD ve diğer Visual Studio geliştiriciler aracılığıyla devreye [Gitter topluluk Visual Studio konuşmada](https://gitter.im/Microsoft/VisualStudio). (Bu seçenek gerektiren bir [GitHub](https://github.com/) hesabı.)

## <a name="see-also"></a>Ayrıca bkz.

* [Visual Studio 2017 iş yükü ve Bileşen kimlikleri](workload-and-component-ids.md)
