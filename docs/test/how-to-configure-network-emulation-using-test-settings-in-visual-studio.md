---
title: Visual Studio'da Test ayarlarını kullanarak ağ öykünmesini yapılandırma
ms.date: 10/03/2016
ms.topic: conceptual
helpviewer_keywords:
- test settings, network emulation
ms.assetid: ff275cfb-5df9-4710-9a91-9caabaaad34f
author: gewarren
ms.author: gewarren
manager: douge
ms.prod: visual-studio-dev15
ms.technology: vs-ide-test
ms.openlocfilehash: 66877397912fca0fbd3996c2dab146b040a047b3
ms.sourcegitcommit: e13e61ddea6032a8282abe16131d9e136a927984
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/26/2018
ms.locfileid: "31972426"
---
# <a name="how-to-configure-network-emulation-using-test-settings-in-visual-studio"></a>Nasıl Yapılır: Visual Studio'da Test Ayarlarını Kullanarak Ağ Öykünmesini Yapılandırma

Visual Studio'dan çeşitli ağ ortamları uygulamanızı test etmek için tanılama veri bağdaştırıcısı yapılandırabilirsiniz. Ayrıca, bir yapay bir ağ yükü ve performans sorunu, testlerinizi çalıştırdığınızda, test etmek için de yapılandırılabilir.

> [!WARNING]
> Öykünülen Ağ daha yavaş bir türde gerçek bir ağda testlerinizi çalıştırırsanız, test hala daha yavaş ağ hızında çalışır. Öykünme yalnızca ağ ortamını yavaş, değil hızlandırma.

 Aşağıdaki yordam, ağ öykünmesini yapılandırma düzenleyicisinden yapılandırmak açıklar. Her iki yapılandırma Düzenleyicisi'nde Microsoft Test Yöneticisi'ni ve Visual Studio için aşağıdaki adımları uygulayın.

> [!NOTE]
> Ağ öykünmesi tanılama veri bağdaştırıcısı yalnızca Visual Studio test ayarları için geçerlidir. Microsoft Test Yöneticisi'nde test ayarları için kullanılmaz.

Ağ öykünmesi için yönetici ayrıcalıklarına sahip bir hesap kullanılması gerekir. El ile testler çalıştıran yerel bir rol için ağ öykünmesi seçtiyseniz, yönetici ayrıcalıklarını kullanarak Microsoft Test Yöneticisi'ni başlatmanız gerekir. Diğer bir rol için ağ öykünmesi seçtiyseniz, test aracısı bu rol için makinenin administrators grubunun üyesi olan bir kullanıcı hesabı kullandığını doğrulamanız gerekir. Hesabı için test aracınızı ayarlama hakkında daha fazla bilgi için bkz: [yüklemek ve test aracılarını yapılandırma](../test/lab-management/install-configure-test-agents.md).

> [!NOTE]
> Test aracısı için varsayılan hesaptır, ağ hizmeti hesabı Yöneticiler grubunun bir üyesi değil.

 **Gerçek ağ öykünmesi**

 Visual Studio yazılım tabanlı gerçek ağ öykünmesini tüm test türleri için kullanır. Yük testleri içerir. Gerçek ağ öykünmesini ağ koşulları tarafından ağ paketlerinin doğrudan düzenlemesi benzetimini yapar. Gerçek ağ öykünücü Ethernet gibi güvenilir bir fiziksel bağlantıyı kullanarak hem kablolu hem de kablosuz ağların davranışını taklit edebilir. Aşağıdaki ağ öznitelikleri gerçek ağ öykünmesine dahil edilir:

-   Gidiş dönüş süresi (gecikme) ağ üzerinden

-   Kullanılabilir bant genişliği

-   Sıraya alma davranışı

-   Paket kaybı

-   Paketlerin yeniden sıralama

-   Hata yayma.

 Gerçek ağ öykünmesini Ayrıca ağ paketlerini IP adresleri veya TCP, UDP ve ICMP gibi protokollere göre filtreleme esneklik sağlar.

 Gerçek ağ öykünmesini ağ tabanlı geliştiriciler ve sınayıcılar tarafından istenen bir sınama ortamına öykünmek, performansını değerlendirmek, değişikliğin etkilerini öngörmek veya teknoloji iyileştirmesi hakkında kararlar için kullanılabilir. Donanım test yataklarıyla karşılaştırıldığında, gerçek ağ öykünmesini daha ucuz ve daha esnek bir çözüm değildir.

## <a name="configure-network-emulation-for-your-test-settings"></a>Ağ öykünmesi için Test ayarlarınızı yapılandırın
 Bu yordamdaki adımları gerçekleştirmeden önce Visual Studio'dan test ayarlarınızı açın ve ardından gerekir **veri ve tanılama** sayfası.

### <a name="to-configure-network-emulation-for-your-test-settings"></a>Ağ öykünmesi için test ayarları yapılandırmak için

1.  Belirli bir ağ benzetmek için kullanılacak rolü seçin.

    > [!NOTE]
    > Ağ öykünmesi bağdaştırıcısı yalnızca istemci rol veya sunucu rolü yapılandırmanız gerekir. Her iki rollerinde bağdaştırıcıyı kullanmak zorunda değil. Böylece hem kullanmak zorunda değil bağdaştırıcı hem rolleri arasındaki iletişim etkiler ağ gürültü öykünür. Gerekli olmadığı sürece, sunucu rolü ek yükü önlemek ağ öykünmesi bağdaştırıcısı için bir istemci rolü seçmeniz gerekir.

2.  Seçin **ağ öykünmesini** ve ardından **yapılandırma**.

     Ağ öykünmesi yapılandırmak için iletişim kutusu görüntülenir.

3.  Oku seçin **kullanmak için ağ profilini seçin**ve bir testi çalıştırdığınızda taklit etmek istediğiniz ağ türünü seçin (örneğin, **Kablo DSL 768Kps**).

    > [!WARNING]
    > Öykünülen Ağ daha yavaş bir türde gerçek bir ağda testlerinizi çalıştırırsanız, test hala daha yavaş ağ hızında çalışır. Öykünme yalnızca ağ ortamını yavaş, değil hızlandırma.

4.  Ağ öykünmesi tanılama veri bağdaştırıcısı test ayarlarında içerir ve yerel makinenizde kullanmayı planlıyorsanız, daha sonra aynı zamanda ağ öykünmesi sürücüsü makinenizin ağ bağdaştırıcılarından birine bağlamanız gerekir. Ağ öykünmesi sürücüsü ağ öykünmesi tanılama veri bağdaştırıcısı çalışması için gereklidir. Ağ öykünmesi sürücüsü yüklenir ve bağdaştırıcınızı iki yolla bağlı:

    -   **Microsoft Visual Studio Test Aracısı ile yüklenmiş ağ öykünme sürücüsü:** Microsoft Visual Studio Test aracısı, hem uzak makineleri hem de yerel makinenize kullanılabilir. Visual Studio Test aracısı yüklediğinizde, yükleme işlemi ağ öykünmesi sürücüsü ağ kartınıza bağlayan bir yapılandırma adımı içerir. Daha fazla bilgi için bkz: [yüklemek ve test aracılarını yapılandırma](../test/lab-management/install-configure-test-agents.md).

    -   **Microsoft Visual Studio Test Professional ile yüklenmiş ağ öykünme sürücüsü:** ağ öykünmesini ilk kez kullandığınızda, bir ağ kartı ağ öykünmesi sürücüsü bağlamanız istenir.

    > [!TIP]
    > Ayrıca ağ öykünmesi sürücüsü komut satırından yerel makinenizde aşağıdaki komutu kullanarak Visual Studio test aracısı yüklemeden yükleyebilirsiniz: **da VSTestConfig NETWORKEMULATION/install**

## <a name="see-also"></a>Ayrıca bkz.

- [Test ayarlarını kullanarak tanılama bilgileri Topla](../test/collect-diagnostic-information-using-test-settings.md)
- [(VSTS) el ile testleri çalıştırma](/vsts/manual-test/getting-started/run-manual-tests)