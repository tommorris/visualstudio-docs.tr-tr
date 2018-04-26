---
title: Visual Studio IntelliTrace verilerini
ms.date: 10/13/2016
ms.topic: conceptual
helpviewer_keywords:
- IntelliTrace, configuring test settings
- Diagnostic Data Adapter, InteliTrace
- debugging [Visual Studio ALM], difficult issues using IntelliTrace
- Test Runner, InteliTrace
ms.assetid: 02b6716f-569e-4961-938a-e790a0c74b5c
author: gewarren
ms.author: gewarren
manager: douge
ms.prod: visual-studio-dev15
ms.technology: vs-ide-test
ms.openlocfilehash: c6b34993e011a8bf539b6ec2dd70beddf9c96caf
ms.sourcegitcommit: e13e61ddea6032a8282abe16131d9e136a927984
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/26/2018
---
# <a name="how-to-collect-intellitrace-data-to-help-debug-difficult-issues"></a>Nasıl yapılır: Hata Ayıklama Zorluklarını Çözmeye Yardımcı Olması için IntelliTrace Verilerini Toplama

Görsel Stdio belirli Tanılama izleme bilgileri toplamak IntelliTrace için tanılama veri bağdaştırıcısı yapılandırabilirsiniz. Testler bu bağdaştırıcıyı kullanabilir, test, uygulama için büyük miktarda tanılama olayları toplayabilir ve sonrasında bir geliştirici bu olayları, kodu izleyip bir hatanın nedenini bulmak üzere kullanabilir. IntelliTrace için tanılama veri bağdaştırıcısı el ile ya da otomatikleştirilmiş testler için kullanılabilir.

> [!NOTE]
> Yönetilen kod kullanılarak yazılan bir uygulama üzerinde IntelliTrace çalışır. Bir tarayıcı istemci olarak kullanan bir Web uygulamasını test ediyorsanız, yönetilen kod yok izleme için kullanılabilir olmadığından, IntelliTrace istemci için test ayarlarınızda etkinleştirmemeniz gerekir. Bu durumda, bir ortamı ayarlama ve Web sunucunuz üzerinde uzaktan IntelliTrace veri toplamak isteyebilirsiniz.

IntelliTrace verilerini .iTrace uzantısına sahip bir dosyada depolanır. Başarısız test ve bir test adımı çalıştırdığınızda, bir hata oluşturabilirsiniz. Tanılama bilgilerini içeren IntelliTrace dosyası otomatik olarak bu hataya eklenir.

> [!NOTE]
> Bir test geçişi başarılı olduğunda IntelliTrace için tanılama veri bağdaştırıcısı bir IntelliTrace dosyası oluşturmaz. Yalnızca başarısız bir test çalışması veya bir hata gönderdiğinizde dosya kaydeder.

 IntelliTrace dosyasında toplanan verileri yeniden oluşturun ve bir hata, kodunuzda tanımak için gerekli olan zamanı azaltarak hata ayıklama verimliliğini artırır. Ayrıca, kendi bilgisayarında yerel oturumunuza çoğaltabilirsiniz başka bir kişi ile IntelliTrace dosya paylaşımı için bir hatanın yeniden üretilebilir olmayan olacağını olasılığını azaltır.

> [!NOTE]
> Test ayarlarınızda IntelliTrace etkinleştirirseniz, kod kapsamı verilerini toplama çalışmaz.

> [!WARNING]
> IntelliTrace için tanılama veri bağdaştırıcısı test çalışması için testleri yüklendikten sonra gerçekleştirilmelidir yönetilen bir işlem kullanılarak çalışır. İzlemek istediğiniz işlem zaten başlatılmış olup olmadığını işlem zaten çalıştığından hiç IntelliTrace dosyaları toplanacak. Bunu aşmak için testler yüklenmeden önce işlemin durdurulduğundan emin olun. Ardından testleri yüklü olmadığından veya ilk test başladıktan sonra işlemi başlatın.

 Aşağıdaki yordam, toplamak istediğiniz IntelliTrace verilerini yapılandırmak açıklar. Visual Studio'da Microsoft Test Yöneticisi'ni ve Test Ayarları iletişim kutusunda her iki yapılandırma Düzenleyicisi için aşağıdaki adımları uygulayın.

> [!NOTE]
> Kullanıcı hesabı için IntelliTrace verilerini toplamak için kullanılan test aracısı Yöneticiler grubunun bir üyesi olması gerekir. Daha fazla bilgi için bkz: [yüklemek ve test aracılarını yapılandırma](../test/lab-management/install-configure-test-agents.md).

## <a name="configure-the-data-to-collect-with-the-intellitrace-diagnostic-data-adapter"></a>IntelliTrace Tanılama veri bağdaştırıcısı ile toplanacak verileri yapılandırma

Bu yordamdaki adımları gerçekleştirmeden önce Microsoft Test Yöneticisi'ni veya Visual Studio test ayarlarınızı açın ve seçmeniz gerekir **veri ve tanılama** sayfası.

### <a name="to-configure-the-data-to-collect-with-the-intellitrace-diagnostic-data-adapter"></a>IntelliTrace Tanılama veri bağdaştırıcısı ile toplanacak verileri yapılandırmak için

1.  IntelliTrace verilerini toplamak üzere kullanmak için rolü seçin.

2.  Seçin **IntelliTrace**.

3.  Bir ASP.NET Web uygulaması veya Web istemci rolü için IntelliTrace ekliyorsanız, da seçmelisiniz **IntelliTrace ve Test etkisi için ASP.NET İstemci Proxy**.

     Bu proxy, IntelliTrace ve Test etkisi tanılama veri bağdaştırıcıları için bir Web sunucusu istemciden gelen http çağrıları hakkında bilgi toplamanıza olanak sağlar.

    > [!WARNING]
    > IntelliTrace verilerini toplamak istediğiniz yere Internet Information Server (IIS) üzerinde uygulama havuzu için kullanılan kimliği için özel bir hesap kullanmaya karar verirseniz, yerel kullanıcı profili özel hesap için IIS makinede, oluşturmanız gerekir kullanılıyor. Yerel olarak IIS makine için bir kez oturum açarak veya özel hesap kimlik bilgilerini kullanarak aşağıdaki komutu çalıştırarak özel hesap için yerel bir profil oluşturabilirsiniz:
    >
    > **runas /user:domain\name /profile cmd.exe**

4.  Seçin **yapılandırma** için **IntelliTrace** varsayılan IntelliTrace ayarlarını değiştirmek için.

     Toplanacak veri yapılandırmak için iletişim kutusu görüntülenir.

    > [!WARNING]
    > IntelliTrace veri toplama etkinleştirirseniz, kod kapsamı verilerini toplama çalışmaz.

5.  Seçin **genel** sekmesi. Seçin **yalnızca IntelliTrace olayları** test ettiğinizde performansı üzerinde en az etkisi olan önemli tanılama olaylarını kaydetmek için.

     **-** veya -

     Seçin **IntelliTrace olayları ve arama bilgileri** tanılama olayları ve yöntemi kaydetmek için izleme düzeyini çağrı bilgileri gösterir. Testlerinizi çalıştırdığınızda bu düzeyde bir izlemenin performans üzerinde etkisi olabilir.

6.  Internet Information Services üzerinde çalışan ASP.NET uygulamanızın veri toplamak için seçin **Internet Information Services üzerinde çalışan ASP.NET uygulamalardan veri toplamak**. Web sunucusu rolünde test aracınızı ayarlayın ve yapılandırın. Bkz: [yüklemek ve test aracılarını yapılandırma](../test/lab-management/install-configure-test-agents.md).

7.  Seçin **modülleri** sekmesi. Şunlardan birini seçin **aşağıdakiler dışında tüm modüllerdeki verileri toplama** ve **Ekle** modülleri listesine eklemek için ve **kaldırmak** modülü kaldırmak için. Bu seçenek, belirttiğiniz modüller dışında sistemde çalışan tüm modülleri dahil etmenizi sağlar.

     -veya-

     Seçin **yalnızca aşağıdaki modüllerden verileri toplama** ve **Ekle** modülleri listesine eklemek için ve **kaldırmak** modülü kaldırmak için. Bu seçenek tam olarak hangi modüllerin istediğinizi belirtmenize olanak sağlar.

    > [!NOTE]
    > Mümkünse, izlemek istediğiniz belirli işlemleri seçin. Bu en iyi performans için önerilir.

8.  Seçin **işlemleri** sekmesi. Seçin **aşağıdakiler dışında tüm işlemlerden verileri toplama** ve **Ekle** işlemler listesine eklemek için ve **kaldırmak** işlemi kaldırmak için. Bu seçenek, belirttiğiniz işlemler dışında sistemde çalışan tüm işlemleri dahil etmenizi sağlar.

     -veya-

     Seçin **verileri yalnızca belirtilen işlemlerini toplama** ve **Ekle** işlemler listesine eklemek için ve **kaldırmak** işlemi kaldırmak için. Bu seçenek tam olarak hangi işlemlerin istediğinizi belirtmenize olanak sağlar.

9. (İsteğe bağlı) Seçin **IntelliTrace olayları** sekmesi. Seçin veya eklemek veya tanılama olaylarını toplarken dışlamak istediğiniz her bir IntelliTrace olay kategorisi temizleyin.

10. (İsteğe bağlı) IntelliTrace olay kategorisini genişletin ve seçin veya eklemek veya IntelliTrace olayları dışlamak istediğiniz her belirli olay temizleyin.

11. (İsteğe bağlı) Seçin **Gelişmiş** sekmesi. Ardından, oku seçin **en fazla kayıt için disk alanı miktarı** ve IntelliTrace dosyası kullanmak etkinleştirmek istediğiniz maksimum boyutu seçin.

    > [!NOTE]
    > Kayıt boyutunu artırmak için bu kaydı ile birlikte test sonuçlarını kaydettiğinizde, zaman aşımı sorun oluşabilir. Tanılama veri bağdaştırıcıları için zaman aşımı değerlerini artırma hakkında daha fazla bilgi için bkz: [nasıl yapılır: tanılama veri bağdaştırıcıları zaman aşımlarını engellemek](../test/how-to-prevent-time-outs-for-diagnostic-data-adapters.md).

12. Microsoft Test Yöneticisi'ni kullanıyorsanız, seçin **kaydetmek**. Visual Studio kullanıyorsanız seçin **Tamam**. IntelliTrace ayarları şimdi yapılandırılmış ve test ayarlarınız için kaydedilir.

    > [!NOTE]
    > Bu tanılama veri bağdaştırıcısı için yapılandırmayı sıfırlamayı tercih **varsayılan yapılandırmaya sıfırlanır** Visual Studio için veya **Varsayılana Sıfırla** Microsoft Test Yöneticisi için.

## <a name="see-also"></a>Ayrıca bkz.

- [(VSTS) test ederken tanılama verisi toplama](/vsts/manual-test/collect-diagnostic-data)
- [El ile testlerde (VSTS) tanılama verisi toplama](/vsts/manual-test/mtm/collect-more-diagnostic-data-in-manual-tests)
- [Test ayarlarını kullanarak tanılama bilgileri Topla](../test/collect-diagnostic-information-using-test-settings.md)
- [IntelliTrace verilerini toplama](../test/how-to-collect-intellitrace-data-to-help-debug-difficult-issues.md)