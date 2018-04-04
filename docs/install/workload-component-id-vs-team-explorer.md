---
title: Visual Studio Takım Gezgini 2017 iş yükü ve Bileşen kimlikleri | Microsoft Docs
description: Sınayıcılar için genel bilgi sahibi tümleşik test araçları sağlamak için Visual Studio iş yükü ve Bileşen kimlikleri kullanın
keywords: ''
author: TerryGLee
ms.author: tglee
manager: douge
ms.date: 03/05/2018
ms.topic: reference
helpviewer_keywords:
- workload ID, Visual Studio
- component ID, Visual Studio
- install Visual Studio, administrator guide
ms.service: ''
ms.technology:
- vs-acquisition
ms.assetid: c6ef9a3b-d13d-49b4-9faa-51fa06b21e1f
ms.workload:
- multiple
ms.openlocfilehash: ab7bd672fdafb8a94904153278ca415294e94642
ms.sourcegitcommit: efd8c8e0a9ba515d47efcc7bd370eaaf4771b5bb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/03/2018
---
# <a name="visual-studio-team-explorer-2017-component-directory"></a>Visual Studio Takım Gezgini 2017 bileşen dizini

Bu sayfada tablolar Visual Studio komut satırını kullanarak yüklemek için kullanabileceğiniz kimliklerini listeler. Biz yayın güncelleştirmeler Visual Studio gibi ek bileşenleri ekleyeceğiz olduğunu unutmayın.

Ayrıca bu sayfa hakkında aşağıdakileri unutmayın:

* Her iş yükü iş yükü Kimliğini ve iş yükü için kullanılabilir olan bileşenleri tablosu arkasından kendi bölümü vardır.
* Varsayılan olarak, **gerekli** bileşenleri, iş yükü yüklediğinizde yüklenir. İsterseniz, ayrıca yükleyebilirsiniz **önerilen** ve **isteğe bağlı** bileşenleri.
* Herhangi bir iş yükü ile bağlı değil ek bileşenleri listeleyen bir bölüm de ekledik.

Bu kimlikleri kullanma hakkında daha fazla bilgi için bkz: [Visual Studio 2017 yüklemek için komut satırı parametrelerini kullanmak](use-command-line-parameters-to-install-visual-studio.md) sayfası. Ve iş yükü ve diğer ürünler için Bileşen kimlikleri listesi için bkz: [Visual Studio 2017 iş yükü ve Bileşen kimlikleri](workload-and-component-ids.md) sayfası.

## <a name="visual-studio-core-editor-included-with-visual-studio-team-explorer-2017"></a>Visual Studio çekirdek Düzenleyici (Visual Studio Takım Gezgini 2017 ile dahil)

**Kimliği:** Microsoft.VisualStudio.Workload.CoreEditor

**Açıklama:** sözdizimi algılayan kod düzenleme, dahil olmak üzere Visual Studio çekirdek Kabuk deneyimi kaynak kodu denetimi ve yönetim iş öğesi.

### <a name="components-included-by-this-workload"></a>Bu iş yükü tarafından bulunan bileşenler

Bileşen kimliği | Ad | Sürüm | Bağımlılık türü
--- | --- | --- | ---
Microsoft.VisualStudio.Component.CoreEditor | Visual Studio çekirdek Düzenleyicisi | 15.6.27309.0 | Gerekli
Microsoft.VisualStudio.Component.StartPageExperiment.Cpp | Visual Studio Başlangıç sayfası C++ kullanıcılar için | 15.0.27128.1 | İsteğe Bağlı

## <a name="unaffiliated-components"></a>Unaffiliated bileşenleri

Bu, herhangi bir iş yükü ile dahil değildir, ancak ayrı bir bileşen olarak seçilebilir bileşenleridir.

Bileşen kimliği | Ad | Sürüm
--- | --- | ---
yok | yok | yok

## <a name="get-support"></a>Destek alma
Bazı durumlarda, şeyler yanlış gidebilirsiniz. Visual Studio yüklemenizin başarısız olursa bkz [sorun giderme Visual Studio 2017 yükleme ve yükseltme sorunlarını](troubleshooting-installation-issues.md) sayfası. Sorun giderme adımlarını hiçbiri yardımcı, bize yükleme Yardımı (yalnızca İngilizce) için canlı sohbet tarafından başvurabilirsiniz. Ayrıntılar için bkz [Visual Studio destek sayfası](https://www.visualstudio.com/vs/support/#talktous).

Birkaç diğer destek seçenekleri şunlardır:
* Ürün sorunları bize bildirebilirsiniz [bir sorun bildirmek](../ide/how-to-report-a-problem-with-visual-studio-2017.md) hem Visual Studio Yükleyicisi ve Visual Studio IDE görünür aracı.
* Üzerinde bir ürün önerisi bizimle paylaşın [UserVoice](https://visualstudio.uservoice.com/forums/121579).
* Ürün sorunları izleyebilir [Visual Studio Geliştirici topluluğu](https://developercommunity.visualstudio.com/), soru sorun ve yanıtlarını bulun.
* ABD ve diğer Visual Studio geliştiriciler aracılığıyla devreye bizim [Gitter topluluk Visual Studio konuşmada](https://gitter.im/Microsoft/VisualStudio).  (Bu seçenek gerektiren bir [GitHub](https://github.com/) hesabı.)

## <a name="see-also"></a>Ayrıca bkz.

* [Visual Studio iş yükü ve bileşen kimlikleri](workload-and-component-ids.md)
* [Visual Studio Yönetici Kılavuzu](visual-studio-administrator-guide.md)
* [Komut satırı parametrelerini kullanarak Visual Studio'yu yükleme](use-command-line-parameters-to-install-visual-studio.md)
  * [Komut satırı parametresi örnekleri](command-line-parameter-examples.md)
* [Visual Studio’nun çevrimdışı yüklemesini oluşturma](create-an-offline-installation-of-visual-studio.md)
