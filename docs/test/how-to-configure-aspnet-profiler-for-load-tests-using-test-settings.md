---
title: Yük testleri için ASP.NET Profil Oluşturucu Visual Studio'da yapılandırın
ms.date: 10/13/2016
ms.topic: conceptual
helpviewer_keywords:
- test settings, ASP.NET
ms.assetid: 6832fe39-04d5-4d94-8a18-3e2730bad423
author: gewarren
ms.author: gewarren
manager: douge
ms.prod: visual-studio-dev15
ms.technology: vs-ide-test
ms.openlocfilehash: 8910ee5aa73e057849ad6b72b67c8b27ba9b0e6e
ms.sourcegitcommit: e13e61ddea6032a8282abe16131d9e136a927984
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/26/2018
---
# <a name="how-to-configure-aspnet-profiler-for-load-tests-using-test-settings-in-visual-studio"></a>Nasıl Yapılır: Visual Studio'da Test Ayarlarını Kullanarak Yük Testleri için ASP.NET Profil Oluşturucu'yu Yapılandırma

ASP.NET Profil Oluşturucu bilgi toplamak için ASP.NET Profil oluşturucu tanılama veri bağdaştırıcısı kullanabilirsiniz. Bu tanılama veri bağdaştırıcısı ASP.NET uygulamaları için performans verilerini toplar.

> [!NOTE]
> Bu tanılama veri bağdaştırıcısı Microsoft Test Yöneticisini kullanarak çalışan testler için kullanılamaz. ASP.NET Profil oluşturucu tanılama bağdaştırıcısı Visual Studio Enterprise gerektiren bir Web siteleri yalnızca kullanarak yük testleri ile kullanabilirsiniz.

ASP.NET Profil oluşturucu tanılama veri bağdaştırıcısı, bir yük testi çalıştırdığınızda, uygulama katmanı'ndan ASP.NET Profil Oluşturucu veri toplamanıza olanak sağlar. Uzun yükleme testleri, örneğin, bir saatten daha uzun yük testleri için profil oluşturucu çalıştırmamanız gerekir. Profil oluşturucu dosyası büyüyebilir olmasıdır belki de yüzlerce megabayt. Bunun yerine, performans sorunlarını derinlemesine tanılama yararı hala verecektir ASP.NET Profil Oluşturucu kullanarak daha kısa yük testleri çalıştırın.

> [!NOTE]
> ASP.NET Profil oluşturucu tanılama veri bağdaştırıcısı Internet Information Services (IIS) işlem profilleri. Bu nedenle, bir geliştirme Web sunucusuna karşı çalışmaz. Web sitesinin yükleme testinizde profilini için IIS çalıştıran makinede bir test aracısı yüklemeniz gerekir. Test aracısı yük oluşturmaz, ancak yalnızca koleksiyon için bir aracı olacaktır. Daha fazla bilgi için bkz: [yüklemek ve test aracılarını yapılandırma](../test/lab-management/install-configure-test-agents.md).

Daha fazla bilgi için bkz: [nasıl yapılır: Dağıtılmış yük testi için Test ayarı oluşturma](../test/how-to-create-a-test-setting-for-a-distributed-load-test.md).

Aşağıdaki yordam, ASP.NET Profil Oluşturucu için tanılama veri bağdaştırıcısı yapılandırmak açıklar.

## <a name="to-configure-the-aspnet-profiler-for-your-test-settings"></a>Test ayarlarınız için ASP.NET Profil Oluşturucu yapılandırmak için

Bu yordamdaki adımları gerçekleştirmeden önce Visual Studio'dan test ayarlarınızı açın ve seçmeniz gerekir **veri ve tanılama** sayfası.

### <a name="to-configure-the-aspnet-profiler-for-your-test-settings"></a>Test ayarlarınız için ASP.NET Profil Oluşturucu yapılandırmak için

1.  ASP.NET Profil Oluşturucu veri toplamak üzere kullanmak için rolü seçin.

    > [!WARNING]
    > Bu rol, bir Web sunucusu olması gerekir.

2.  Seçin **ASP.NET Profil Oluşturucu** ASP.NET profil oluşturma veri toplamayı etkinleştirmek ve ardından **yapılandırma**.

     ASP.NET profil oluşturma veri toplamayı yapılandırmak için iletişim kutusu görüntülenir.

3.  İçinde **profil oluşturucu örnekleme aralığı**, ASP.NET profil oluşturma örnekleri alma arasında beklenecek döngüleri saat kaç durdurulamaz harici CPU belirten bir değer girin.

4.  Katman etkileşim profil etkinleştirmek için seçin **etkinleştirmek katman etkileşim profil**.

     Etkileşimli sayıları profil oluşturma için her yapısı (örneğin, MyPage.aspx veya CompanyLogo.gif) Web sunucusuna gönderilen istek sayısı katmanı ve her bir isteğe hizmet için geçen süre. Ayrıca, katman etkileşim profil hangi ADO.NET bağlantıları sayfa isteği bir parçası olarak kullanılan ve kaç tane sorguları ve saklı yordam çağrıları bu isteğe hizmet parçası olarak yürütüldü toplar.

     İki farklı zamanlama bilgileri toplanır:

    -   Her web isteğini bakım için zamanlama bilgileri (Min, Max, ortalama ve toplam).

    -   Her sorguyu yürütmek için zamanlama bilgileri (Min, Max, ortalama ve toplam).

Test ortamında yapılandırılmış ASP.NET Profil oluşturucu tanılama veri bağdaştırıcısı ile ASP.NET profil oluşturma, ASP.NET Web uygulamanızın üzerinde verilerini toplayabilir.

## <a name="see-also"></a>Ayrıca bkz.

- [Test ayarlarını kullanarak tanılama bilgileri Topla](../test/collect-diagnostic-information-using-test-settings.md)
- [Nasıl yapılır: Dağıtılmış yük testi için Test ayarı oluşturma](../test/how-to-create-a-test-setting-for-a-distributed-load-test.md)
- [Test denetleyicileri ve test aracıları](configure-test-agents-and-controllers-for-load-tests.md)