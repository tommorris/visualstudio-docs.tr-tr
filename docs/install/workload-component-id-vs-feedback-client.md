---
title: Visual Studio geri bildirim istemcisi 2017 iş yükü ve Bileşen kimlikleri
description: Visual Studio Team Services veya Team Foundation Server için zengin geri bildirim sağlamak için Visual Studio iş yükü ve Bileşen kimlikleri kullanın
keywords: ''
author: TerryGLee
ms.author: tglee
manager: douge
ms.date: 05/07/2018
ms.topic: reference
helpviewer_keywords:
- workload ID, Visual Studio
- component ID, Visual Studio
- install Visual Studio, administrator guide
ms.service: ''
ms.technology: vs-acquisition
ms.prod: visual-studio-dev15
ms.assetid: 7392a100-100c-458c-9394-828695109015
ms.workload:
- multiple
ms.openlocfilehash: acdadad76c9cbf833003e5b0652c06b563a0d551
ms.sourcegitcommit: 33c954fbc8e05f7ba54bfa2c0d1bc1f9bbc68876
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/07/2018
---
# <a name="visual-studio-feedback-client-2017-component-directory"></a>Visual Studio geri bildirim istemcisi 2017 bileşen dizini

Tablolar bu sayfa listede kimlikleri, Visual Studio komut satırını kullanarak yüklemek için kullanabileceğiniz veya bağımlılık VSIX bildirim olarak belirtebilirsiniz. Biz yayın güncelleştirmeler Visual Studio gibi ek bileşenleri ekleyeceğiz olduğunu unutmayın.

Ayrıca sayfa hakkında aşağıdakileri unutmayın:

* Her iş yükü iş yükü Kimliğini ve iş yükü için kullanılabilir olan bileşenleri tablosu arkasından kendi bölümü vardır.
* Varsayılan olarak, **gerekli** bileşenleri, iş yükü yüklediğinizde yüklenir.
* İsterseniz, ayrıca yükleyebilirsiniz **önerilen** ve **isteğe bağlı** bileşenleri.
* Herhangi bir iş yükü ile bağlı değil ek bileşenleri listeleyen bir bölüm de ekledik.

VSIX bildiriminizi bağımlılıkları ayarladığınızda, Bileşen kimlikleri yalnızca belirtmeniz gerekir. Bizim minimum Bileşen bağımlılıkları belirlemek için bu sayfadaki tabloları kullanın. Bazı senaryolarda bu bir iş yükü yalnızca bir bileşenden belirttiğiniz anlamına gelebilir. Diğer senaryolarda, tek bir iş yükünü birden çok bileşenlerini veya birden çok iş yükünün birden çok bileşenlerini belirtin gelebilir. Daha fazla bilgi için bkz: [nasıl yapılır: Visual Studio 2017 genişletilebilirlik projelerine geçirmek](../extensibility/how-to-migrate-extensibility-projects-to-visual-studio-2017.md) sayfası.

Bu kimlikleri kullanma hakkında daha fazla bilgi için bkz: [Visual Studio 2017 yüklemek için komut satırı parametrelerini kullanmak](use-command-line-parameters-to-install-visual-studio.md) sayfası. Ve iş yükü ve diğer ürünler için Bileşen kimlikleri listesi için bkz: [Visual Studio 2017 iş yükü ve Bileşen kimlikleri](workload-and-component-ids.md) sayfası.

## <a name="feedback-client"></a>Geribildirim İstemcisi

**Kimliği:** Microsoft.VisualStudio.Workload.FeedbackClient

**Açıklama:** geri bildirim istemcisi Visual Studio Team Services veya Team Foundation Server için zengin geri bildirim sağlamak üzere proje katılımcılarına sağlar.

### <a name="components-included-by-this-workload"></a>Bu iş yükü tarafından bulunan bileşenler

Bileşen kimliği | Ad | Sürüm | Bağımlılık türü
--- | --- | --- | ---
Microsoft.VisualStudio.Component.TestTools.FeedbackClient | Microsoft Geri Bildirim İstemcisi | 15.6.27406.0 | Gerekli

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
* Ürün sorunlarını izlemek ve yanıtlar bulmak [Visual Studio Geliştirici topluluğu](https://developercommunity.visualstudio.com/).
* ABD ve diğer Visual Studio geliştiriciler aracılığıyla devreye [Gitter topluluk Visual Studio konuşmada](https://gitter.im/Microsoft/VisualStudio). (Bu seçenek gerektiren bir [GitHub](https://github.com/) hesabı.)

## <a name="see-also"></a>Ayrıca bkz.

* [Visual Studio iş yükü ve bileşen kimlikleri](workload-and-component-ids.md)
* [Visual Studio Yönetici Kılavuzu](visual-studio-administrator-guide.md)
* [Komut satırı parametrelerini kullanarak Visual Studio'yu yükleme](use-command-line-parameters-to-install-visual-studio.md)
  * [Komut satırı parametresi örnekleri](command-line-parameter-examples.md)
* [Visual Studio’nun çevrimdışı yüklemesini oluşturma](create-an-offline-installation-of-visual-studio.md)
