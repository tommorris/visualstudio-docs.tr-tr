---
title: "Masaüstü ile etkileşimi olan testleri çalıştırmak için Visual Studio Test Aracısı Yapılandırma | Microsoft Docs"
ms.date: 10/20/2016
ms.topic: article
helpviewer_keywords:
- agents, configuring for interaction with desktop
ms.assetid: 3a94dd07-6d17-402c-ae8f-7947143755c9
author: gewarren
ms.author: gewarren
manager: ghogen
ms.technology: vs-ide-test
ms.openlocfilehash: 6953466776872098315cf1b48036bf96d9e570ab
ms.sourcegitcommit: 900ed1e299cd5bba56249cef8f5cf3981b10cb1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/19/2018
---
# <a name="how-to-set-up-your-test-agent-to-run-tests-that-interact-with-the-desktop"></a>Nasıl yapılır: Masaüstü ile Etkileşimi Olan Testleri Çalıştırmak İçin Test Aracınızı Ayarlama

Masaüstü ile etkileşimde otomatikleştirilmiş testleri çalıştırmak istiyorsanız, bir hizmeti yerine bir işlem olarak çalıştırmak için aracınızı ayarlamanız gerekir. Örneğin, bir test denetleyicisi ve test aracısı Uzaktan kullanarak kodlanmış UI test çalıştırma veya video çalıştırdığınız zaman kaydı yakalama ve bir testi çalıştırmak istediğiniz istiyorsanız, aracınızı bir işlem olarak çalıştırmak için ayarlamanız gerekir. Visual Studio kullanarak test ayarlarınızda rollere aracılar atadığınızda ya da rollere aracılar için ortamınızda Microsoft Test Yöneticisi'ni kullanarak atadığınızda, kümesi masaüstü ile etkileşimde olması gereken rollere atanan tüm aracılar için ayarları değiştirmeniz gerekir.

> [!WARNING]
> Microsoft Test Yöneticisi'ni bir laboratuvar ortamı kurmanız için kullanırsanız, test aracısı yükler. Kodlanmış UI testleri çalıştırmak için roller birini yapılandırmak istediğiniz ortamı Oluşturma Sihirbazı'nda belirtebilirsiniz.

> [!IMPORTANT]
> Kodlanmış UI testleri çalıştırmak istediğiniz aracıyı çalıştıran bilgisayar kilitlenemez veya etkin bir ekran koruyucusu vardır.

Bir tarayıcı başlatmak kodlanmış UI testleri çalıştırıyorsanız, test aracısı için hizmet hesabı, tarayıcı başlatmak için kullanılır. Bu hizmet hesabı bu bilgisayarda etkin kullanıcı kullanıcı hesabı ile aynı olması gerekir. Aynı kullanıcı hesabı değilse, tarayıcı başlatılmaz.

> [!IMPORTANT]
> Yapı tanımının bir parçası tarayıcıyı başlatan kodlanmış bir UI testi çalıştırıyorsanız, yapı hizmeti için hizmet hesabı, tarayıcı başlatmak için kullanılır. Bu hizmet hesabı bu bilgisayarda etkin kullanıcı kullanıcı hesabı ile aynı olması gerekir. Aynı kullanıcı hesabı değilse, tarayıcı başlatılmaz.

 Masaüstü ile etkileşimine izin gerektiren bir görev gerçekleştiren bir role atanmış tüm aracıları ayarlamak için aşağıdaki yordamı kullanın.

## <a name="to-set-up-an-agent-to-run-as-a-process"></a>Bir işlem olarak çalıştırmak üzere bir aracıyı ayarlamak için

1.  Bir işlem olarak çalıştırmak için yüklediğiniz test aracısını yapılandırmak için şu adrese gidin **Başlat**, **tüm programlar**, **Microsoft Visual Studio**, **Microsoft Visual Studio Test Aracısı Yapılandırma Aracı**.

     **Test aracısını Yapılandır** iletişim kutusu görüntülenir.

2.  Bir işlem olarak çalıştırmayı seçme sayfasını görüntülemek için seçin **Çalıştırma Seçenekleri**.

     Aracı bir işlem veya bir hizmet çalıştırmak seçmenize olanak tanıyan sayfası görüntülenir.

3.  Seçin **etkileşimli işlem**. Test aracısı, bir hizmeti yerine bir işlem olarak başlatılacak. Seçin **sonraki**.

     Şimdi kullanıcının bir işlem ve diğer seçenekleri test aracısı başlattığınızda kullanmak Ayrıntılar girebilirsiniz.

    > [!NOTE]
    > İşlemi başlatmak için eklediğiniz kullanıcının, aynı zamanda bu aracı için test denetleyicisi için bilgisayarda TeamTestAgentService grubunun bir üyesi olarak eklenmelidir. Bu kullanıcıyı test denetleyicisi bilgisayarına eklediğinizde, bu kullanıcının geçerli kullanıcının ise, oturumu kapatın veya bu bilgisayarın yeniden başlatılması gerekir.

4.  Adı yazın **kullanıcı adı**.

5.  Parolayı yazın **parola**.

     **Önemli kullanıcı hesabı bilgileri:**

    -   Null parolalar kullanıcı hesapları için desteklenmez.

    -   IntelliTrace veya ağ öykünmesi veri ve tanılama bağdaştırıcısını kullanmak istiyorsanız, kullanıcı hesabını Administrators grubunun bir üyesi olması gerekir. Test aracısı çalıştıran makinede en az ayrıcalıklı kullanıcı hesabı olan bir işletim sistemi çalıştırıyorsa, çalıştırmak yönetici olarak da sahip (yükseltilmiş). Aracı kullanıcı adı aracı hizmetinde değilse, bunu, eklemek test denetleyicisi izinleri gerektiren dener.

    -   Test denetleyicisi kullanmayı deneyen kullanıcı test denetleyicisinin kullanıcı hesabında olmalıdır veya bunlar denetleyiciye karşı testleri çalıştırmak mümkün olmaz.

6.  Test aracısı olan bir bilgisayarı yeniden başlatmadan sonra testleri çalıştırabilirsiniz emin olmak için bilgisayarı otomatik olarak test aracısı kullanıcısı olarak oturum açmak için ayarlayabilirsiniz. Seçin **otomatik olarak oturum açma**. Bu kullanıcı adı ve parola kayıt defterinde şifrelenmiş biçimde depolar.

    > [!NOTE]
    > Uzak Masaüstü veya konuk tabanlı bağlantısı kullanarak Laboratuvar ortamına bağlandığında, karşılaşabileceğiniz sık, beklenmeyen bağlantısını keser. Olası bir nedeni de bağlantı kaybı makine otomatik olarak ağ oturum açmak için yapılandırılmış olmasıdır.

7.  Bu masaüstü ile etkileşimde olması gereken otomatikleştirilmiş testleri engelleyebilmesi yüzünden ekran koruyucusu devre dışı bırakıldığından emin olmak için seçin **olun ekran koruyucusu devre dışı**.

    > [!WARNING]
    > Otomatik olarak oturum açın veya ekran koruyucusu devre dışı bırakırsanız güvenlik riskleri vardır. Otomatik oturum açmayı etkinleştirerek, diğer kullanıcıların bu bilgisayarı başlatmak için ve otomatik oturum açan hesap kullanabilmek için etkinleştirin. Ekran koruyucu devre dışı bırakırsanız, bilgisayarda oturum açmak bir kullanıcı için bilgisayarın kilidini açmak için istemeyebilir. Bu bilgisayara fiziksel erişimi bilgisayara erişmek herhangi bir kişi sağlar. Bu özellikler bir bilgisayarda etkinleştirirseniz, bu bilgisayarların fiziksel olarak güvenli olduğundan emin olun. Örneğin, bu bilgisayarların fiziksel olarak güvenli bir laboratuar ortamında bulunur. Silerseniz **olun ekran koruyucusu devre dışı**, ekran koruyucusu etkinleştirmez.

     Aracıyı geri bir hizmet olarak çalıştırmak için bu aracı kullanabilirsiniz ve seçin **hizmet**.

8.  Değişikliklerinizi uygulamak için tercih **ayarlarını uygula**.

     A **Yapılandırma Özeti** iletişim kutusu her test aracınızı yapılandırmak için gereken adımları durumunu gösteren görüntülenir.

9. Kapatmak için **Yapılandırma Özeti** iletişim kutusunda, seçin **kapatmak**. Ardından **kapatmak** Test Aracısı Yapılandırma aracı kapatın.

    > [!NOTE]
    > Bir işlem olarak çalışan bir test aracısı için bilgisayar üzerinde çalışan bir bildirim alanı simgesini yoktur. Test aracısı durumunu gösterir. Başlatma, durdurma veya bu aracı kullanarak bir işlem olarak çalışıyorsa, aracıyı yeniden başlatın. Test aracısı çalışır durumda değilse bir işlem olarak başlatmak için tercih **Başlat**, **tüm programlar**, **Microsoft Visual Studio**, **Microsoft Visual Studio Test Aracı**.

     Bu test aracısı için test denetleyicisi Team Foundation Server ile kayıtlı değilse, etkileşimli bir işlem olarak çalışan bir test aracısı durumunu görüntülenen **denetleyicileri** görünümünde **Laboratuvar Merkezi**Microsoft Test Yöneticisi için. Etkileşimli bir işlem olarak çalıştığını göstermek için bir önceki yıldız simgesiyle listelenir. Bu test aracısını yeniden başlatmak için test aracısı için bilgisayar üzerinde çalışan aracını kullanın ve **denetleyicileri** görünümü.

## <a name="see-also"></a>Ayrıca bkz.

- [Test aracılarını yükleme ve yapılandırma](../test/lab-management/install-configure-test-agents.md)