---
title: "Visual Studio Yönetici Kılavuzu | Microsoft Docs"
description: "Visual Studio bir kuruluş ortamında dağıtma hakkında daha fazla bilgi edinin."
ms.custom: 
ms.date: 05/15/2017
ms.reviewer: 
ms.suite: 
ms.technology: vs-acquisition
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- network installation, Visual Studio
- administrator guide, Visual Studio
- installing Visual Studio, administrator guide
ms.assetid: 4af353f5-6cfd-4ebe-bcfb-f42306e451a0
author: TerryGLee
ms.author: tglee
manager: ghogen
ms.workload: multiple
ms.openlocfilehash: c143456d71057071aa953605e2ee60c6aa9c77de
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/22/2017
---
# <a name="visual-studio-2017-administrator-guide"></a>Visual Studio 2017 Yönetici Kılavuzu

Kurumsal ortamlarda, sistem yönetim yazılımının kullanarak veya bir ağ paylaşımından yüklemeleri son kullanıcılara dağıtmak sistem yöneticileri için yaygın bir sorundur. Sistem yöneticileri yükleme işlemi sırasında ürün anahtarları dağıtmak için Yükleme varsayılanlarını önceden yapılandırmak için bir ağ yükleme konumu oluşturma olanağı izin vererek biz kurumsal dağıtım desteği için Visual Studio Kurulumu altyapısı tasarladık, ve sonra başarılı bir sunum ürün güncelleştirmeleri yönetebilirsiniz. Bu Yönetici Kılavuzu senaryo tabanlı ağa bağlı ortamlarda kurumsal dağıtım için yönergeler sağlar.

## <a name="deploying-visual-studio-2017-in-an-enterprise-environment"></a>Visual Studio 2017 bir kuruluş ortamında dağıtma

Her hedef bilgisayar karşılıyorsa, Visual Studio 2017 istemci iş istasyonlarına dağıtabilirsiniz [minimum yükleme gereksinimlerini](https://www.visualstudio.com/en-us/productinfo/vs2017-system-requirements-vs). System Center gibi yazılım ya da bir toplu iş dosyası dağıtıyorsunuz olsun, genellikle aşağıdaki adımlarda size Git isteyeceksiniz:

1. [Visual Studio ürün dosyalarını içeren bir ağ paylaşımı oluşturmanız](create-a-network-installation-of-visual-studio.md) bir ağ konumuna.

2. [İş yükleri ve bileşenlerini seçin](workload-and-component-ids.md) yüklemek istediğiniz.

3. [Bir yanıt dosyası oluşturma](automated-installation-with-response-file.md) varsayılan yükleme seçenekleri içerir. Veya alternatif olarak, [bir yükleme komut dosyası derleme](use-command-line-parameters-to-install-visual-studio.md) yükleme denetlemek için komut satırı parametreleri kullanan.

4. İsteğe bağlı olarak, [bir toplu lisans ürün anahtarı geçerli](automatically-apply-product-keys-when-deploying-visual-studio.md) yüklemesinin bir parçası olarak kullanıcılar yazılım ayrı olarak etkinleştirmek gerekmemesi komut dosyası.

5. Ağ düzeni güncelleştirme [ürün güncelleştirmeleri kullanıcılarınıza zaman dağıtılır kontrol](controlling-updates-to-visual-studio-deployments.md).

6. İsteğe bağlı olarak ayarlanırsa kayıt defteri anahtarlarını [istemci iş istasyonlarında önbelleğe alınmış kontrol](set-defaults-for-enterprise-deployments.md).

7. Hedef Geliştirici istasyonlarında önceki adımda oluşturulan komut dosyası yürütme, dağıtım teknolojisi tercih kullanın.

8. [Son güncelleştirmeleri içeren ağ konumunuza yenileme](update-a-network-installation-of-visual-studio.md) içinde kullanılan komutunu çalıştırarak Visual Studio için güncelleştirilmiş bileşenleri eklemek için düzenli aralıklarla adım 1.

> [!IMPORTANT]
> Ağ üzerinden paylaşımı "kaynak konumu unutmayın" yüklemeleri bunlar geldiğini unutmayın. Bu, bir istemci makine onarımını istemci ilk olarak yüklenen ağ paylaşımı geri dönmek gerektiği anlamına gelir. Böylece, kuruluşunuzda çalışan Visual Studio 2017 istemcileri sahip olmayı beklediğiniz kullanım ömrü hizalar ağ konumunuzu dikkatle seçin.

## <a name="visual-studio-tools"></a>Visual Studio Araçları
Yardımcı olması kullanılabilen çeşitli araçlar sahibiz [algılamak ve yüklü Visual Studio Örnekleri yönetmek](tools-for-managing-visual-studio-instances.md) istemci makinelerde.

> [!TIP]
> Yönetici Kılavuzu'ndaki belgeleri ek olarak, iyi bir Visual Studio 2017 kurulumu hakkında bilgi kaynağıdır [sistem durumu Ilgaz'ın blogu](https://blogs.msdn.microsoft.com/heaths/tag/vs2017/).

## <a name="get-support"></a>Destek alma
Bazı durumlarda, şeyler yanlış gidebilirsiniz. Visual Studio yüklemenizin başarısız olursa bkz [sorun giderme Visual Studio 2017 yükleme ve yükseltme sorunlarını](troubleshooting-installation-issues.md) sayfası. Sorun giderme adımlarını hiçbiri yardımcı, bize yükleme Yardımı (yalnızca İngilizce) için canlı sohbet tarafından başvurabilirsiniz. Ayrıntılar için bkz [Visual Studio destek sayfası](https://www.visualstudio.com/vs/support/#talktous).

Birkaç diğer destek seçenekleri şunlardır:
* Ürün sorunları bize bildirebilirsiniz [bir sorun bildirmek](../ide/how-to-report-a-problem-with-visual-studio-2017.md) hem Visual Studio Yükleyicisi ve Visual Studio IDE görünür aracı.
* Üzerinde bir ürün önerisi bizimle paylaşın [UserVoice](https://visualstudio.uservoice.com/forums/121579).
* Ürün sorunları izleyebilir [Visual Studio Geliştirici topluluğu](https://developercommunity.visualstudio.com/), soru sorun ve yanıtlarını bulun.
* ABD ve diğer Visual Studio geliştiriciler aracılığıyla devreye bizim [Gitter topluluk Visual Studio konuşmada](https://gitter.im/Microsoft/VisualStudio).  (Bu seçenek gerektiren bir [GitHub](https://github.com/) hesabı.)

## <a name="see-also"></a>Ayrıca bkz.
* [Visual Studio 2017 yükleyin](install-visual-studio.md)
* [Visual Studio 2017 yüklemek için komut satırı parametreleri kullanın](use-command-line-parameters-to-install-visual-studio.md)
  * [Komut satırı parametresi örnekleri](command-line-parameter-examples.md)
  * [İş yükü ve bileşen kimliği başvurusu](workload-and-component-ids.md)
* [Visual Studio ağ tabanlı yüklemesini oluşturma](create-a-network-installation-of-visual-studio.md)
  * [Visual Studio çevrimdışı yükleme için gerekli sertifikaları yükleyin](install-certificates-for-visual-studio-offline.md)
* [Visual Studio ile bir yanıt dosyası otomatikleştirme](automated-installation-with-response-file.md)
* [Visual Studio’yu dağıtırken ürün anahtarlarını otomatik olarak uygulama](automatically-apply-product-keys-when-deploying-visual-studio.md)
* [Visual Studio kuruluş dağıtımları için varsayılanları ayarlama](set-defaults-for-enterprise-deployments.md)
* [Paket önbelleğini devre dışı bırakma veya taşıma](disable-or-move-the-package-cache.md)
* [Visual Studio ağ tabanlı yüklemesini güncelleştirme](update-a-network-installation-of-visual-studio.md)
* [Visual Studio dağıtımlarına yönelik güncelleştirmeleri denetleme](controlling-updates-to-visual-studio-deployments.md)
* [Visual Studio örneklerini algılamaya ve yönetmeye yönelik araçlar](tools-for-managing-visual-studio-instances.md)
