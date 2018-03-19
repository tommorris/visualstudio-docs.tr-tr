---
title: "Test aracıları yapılandırma ve test denetleyicileri yükleme testleri için Visual Studio'da | Microsoft Docs"
ms.date: 10/19/2016
ms.topic: article
helpviewer_keywords:
- load tests, test agents and controllers
author: gewarren
ms.author: gewarren
manager: ghogen
ms.technology: vs-ide-test
ms.openlocfilehash: 3ed020e6cef6dfb27901b6f72ba29c7c838cf8de
ms.sourcegitcommit: 900ed1e299cd5bba56249cef8f5cf3981b10cb1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/19/2018
---
# <a name="configure-test-agents-and-test-controllers-for-running-load-tests"></a>Test aracıları yapılandırma ve test denetleyicileri yükleme testlerini çalıştırmak için

Visual Studio kullanarak uygulamanız için fiziksel benzetilmiş yük ya da sanal makineleri oluşturabilirsiniz. Bu makinelerin tek bir test denetleyicisi ve bir veya daha fazla test aracılarını ayarlanması gerekir. Test denetleyicisi ve test aracıları, tek bir bilgisayar başına oluşturabilir daha çok yükleme oluşturmak için kullanabilirsiniz.

> [!NOTE]
> Aynı zamanda, web sitesine erişen çok sayıda kullanıcı yük oluşturmak sanal makineler sağlamak için bulut tabanlı yük testi de kullanabilirsiniz. Bulut tabanlı yük testi hakkında daha fazla bilgi [VSTS kullanarak çalışma yük testleri](/vsts/load-test/get-started-simple-cloud-load-test).

## <a name="load-simulation-architecture"></a>Yükleme Benzetimi Mimarisi

Visual Studio istemcisi, test denetleyicisi ve test aracılarını yükleme benzetimi mimarisi oluşur.

-   İstemci, testleri geliştirmek, testleri çalıştırmak ve test sonuçlarını görüntülemek için kullanılır.

-   Test denetleyicisi ve test sonuçlarını toplamak test aracıları yönetmek için kullanılır.

-   Test aracıları, sistem bilgileri ve profil oluşturma verilerini test ayarında tanımlanan ASP.NET dahil olmak üzere veri toplamak ve testleri çalıştırmak için kullanılır.

Bu mimari, aşağıdaki avantajları sağlar:

-   Test denetleyicisine ek test aracıları ekleyerek yükleme oluşturma ölçeklenme olanağı.

-   İstemci yüklemek için esneklik test denetleyicisi ve aynı veya farklı bilgisayarlarda aracı yazılım sınayın. Örneğin:

     **Yerel yapılandırma:**

    -   Makine1: Visual Studio, denetleyici, aracı.

     ![Denetleyici ve aracı kullanarak yerel makine](./media/load-test-configa.png)

     **Tipik Uzaktan yapılandırma:**

    -   Makine1 ve 2: Visual Studio (birden çok test eden aynı denetleyicisi kullanabilir).

    -   Makine3: Denetleyici (aracılar da olabilir).

    -   Machine4-n: aracı veya MAKİNE3 denetleyicisinde ile ilişkilendirilmiş tüm aracılar.

     ![Uzak makine denetleyicisi ve aracıları kullanma](./media/load-test-configb.png)

Test denetleyicisi genellikle birkaç test aracılarını yönetir olsa da, bir aracı yalnızca tek bir denetleyici ile ilişkili olabilir. Her test aracısı geliştiriciler ekibi tarafından paylaşılabilir. Bu mimari, böylece daha büyük yükleri oluşturma, test aracılarını sayısını artırmak kolaylaştırır.

## <a name="test-agent-and-test-controller-interaction"></a>Test aracısı ve Test denetleyicisi etkileşimi

Test denetleyicisi testleri çalıştırmak için test aracılarını bir dizi yönetir. Test aracıları başlangıç testleri, Dur testleri, test aracı durumunu izlemek ve test sonuçlarını toplamak için test denetleyicisi ile iletişim kurar.

### <a name="test-controller"></a>Test denetleyicisi

Test denetleyicisi testleri çalıştırmak için genel bir mimari sağlar ve yük testleri çalıştırmak için özel özellikler içerir. Tüm test aracılarını test başlatana kadar test denetleyicisi yük testi tüm test aracılarını ve bekler gönderir. Tüm test aracılarını hazır olduğunuzda, test denetleyicisi testi başlatmak için test aracılarını bir ileti gönderir.

### <a name="test-agent"></a>Test Aracısı

Test aracısı, yeni bir test başlatmak için test denetleyicisinden isteklerini dinleyen bir hizmet olarak çalışır. Test aracısı bir istek aldığında, test aracısı hizmeti testleri çalıştırmak için bir işlem başlatır. Her test aracısı aynı yük testi çalıştırır.

 Yük testi aracısının ağırlıklı göre dağıtılır ve test aracılarını ağırlık yönetici tarafından atanır. Test Aracısı 2 700 sanal kullanıcıların benzetimini yapar ancak örneğin, test aracısı 1 30 ağırlığa sahip ve test aracısı 2 70 ağırlığa sahip ve yük 1000 kullanıcılara ayarlamak, ardından test aracısı 1 300 sanal kullanıcıların benzetimini yapar. Bkz: [Test denetleyicileri ve Test aracıları Visual Studio ile yönetme](../test/manage-test-controllers-and-test-agents.md).

 Test aracısı testleri kümesi ve benzetim parametreleri kümesini girdi olarak alır. Anahtar kavram testleri burada çalıştıran bir bilgisayardan bağımsız olmasıdır.

## <a name="test-controller-and-test-agent-connection-points"></a>Test denetleyicisi ve Test aracısı bağlantı noktaları

Aşağıdaki çizimde test denetleyicisi, test aracısı ile istemci arasındaki bağlantı noktalarını gösterir. Bu, bu bağlantı noktalarına kullanılan güvenlik kısıtlamaları yanı sıra gelen ve giden bağlantılar için hangi bağlantı noktalarının kullanılacağını açıklar.

 ![Contoller ve test aracısı bağlantı noktaları ve güvenlik](./media/test-controller-agent-firewall.png)

 Daha fazla bilgi için bkz: [Test denetleyicileri ve Test aracıları için bağlantı noktalarını yapılandırma](../test/configure-ports-for-test-controllers-and-test-agents.md).

## <a name="test-controller-and-agent-installation-information"></a>Test denetleyicisi ve aracı yükleme bilgileri

Yüklemeden ve ortamınız için en iyi performans, yapılandırma yordamları test denetleyicileri ve test aracıları için donanım ve yazılım gereksinimleri hakkında önemli bilgiler için bkz: [yüklemek ve test aracılarınıyapılandırın](../test/lab-management/install-configure-test-agents.md).

## <a name="using-the-test-controller-and-test-agent-with-unit-tests"></a>Test denetleyicisi ve Test Aracısı ile birim testleri kullanma

Bir test denetleyicisi ve bir ya da daha fazla aracı yükledikten sonra, yük testleriniz için test ayarında test denetleyicisi ile bir uzaktan yürütme kullanılıp kullanılmayacağını belirtebilirsiniz. Ayrıca, veri ve test ayarı aracıları ile ilişkili rol ile kullanılacak tanılama bağdaştırıcılarını belirtebilirsiniz.

## <a name="see-also"></a>Ayrıca bkz.

- [Test aracılarını yükleme ve yapılandırma](../test/lab-management/install-configure-test-agents.md)