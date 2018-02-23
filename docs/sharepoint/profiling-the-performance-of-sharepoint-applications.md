---
title: "SharePoint uygulamalarını performans profili oluşturma | Microsoft Docs"
ms.custom: 
ms.date: 02/02/2017
ms.reviewer: 
ms.suite: 
ms.technology:
- office-development
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- VS.SharePointTools.Profiling.SilverlightWebPartOnly
- VS.SharePointTools.Profiling.DotNetTrustLevel
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- SharePoint development in Visual Studio, profiling
- performance testing [SharePoint development in Visual Studio]
- SharePoint development in Visual Studio, performance testing
- profiling [SharePoint development in Visual Studio]
author: TerryGLee
ms.author: tglee
manager: ghogen
ms.workload:
- office
ms.openlocfilehash: 44c2566a722794fea176100db144f09c6c010f6e
ms.sourcegitcommit: 36ab8429333b31f03992a9fe8fc669db8e09c968
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/21/2018
---
# <a name="profiling-the-performance-of-sharepoint-applications"></a>SharePoint Uygulamaları için Performans Profili Oluşturma
 
SharePoint uygulamaları yavaş veya inefficiently gerçekleştiriyorsanız sorunlu kod ve diğer öğeleri tanımlamak için Visual Studio profil özellikleri kullanabilirsiniz. Özellik sınama yük kullanarak, ne zaman çok sayıda kullanıcı uygulamaya aynı anda erişim gibi yük altında bir SharePoint uygulama gerçekleştirir belirleyebilirsiniz. Web performans testleri çalıştırarak uygulama Web'de nasıl gerçekleştireceğini ölçebilirsiniz. Kodlanmış UI testleri kullanarak kendi kullanıcı arabirimi dahil olmak üzere tüm SharePoint uygulama doğru şekilde işlev olup olmadığını doğrulayabilirsiniz. Bu testler birlikte kullanıldığında, bunlar Uygulamanızı dağıtmadan önce performans sorunları belirlemenize yardımcı olabilir.

## <a name="profiling-tools-overview"></a>Profil Araçlarına Genel Bakış

Profil oluşturma Gözlemleme ve çalışan uygulamanızın performansı davranışını kaydetme sürecini gösterir. Uygulamanızın profilini oluşturmanız, performans sorunlarını, verimsiz kodu ve uygulamaların yavaş çalışmasına veya çok fazla bellek kullanmasına neden bellek ayırma sorunları gibi sorunlara açığa. Örneğin, sık olarak adlandırılır ve uygulamanızın genel performansını yavaşlatabilir kod parçalarını olan etkin kodunuzda tanımlamak için profil oluşturma kullanabilirsiniz. Etkin noktalarına tanımladıktan sonra genellikle en iyi duruma getirme veya bunları ortadan kaldırmak.

Tanımlamak ve bu tür performans sorunları bulmak için tümleşik geliştirme ortamı (IDE) birkaç profil oluşturma araçları kullanabilirsiniz. Visual Studio projeleri diğer türleri için yaptığınız gibi bu araçlar SharePoint projeleri için aynı şekilde çalışır. Profil Araçları performans Sihirbazı belirttiğiniz testleri kullanan bir performans oturumu oluşturulmasını yol açar. Bir performans oturumu bir veya daha fazla profil çalıştırır sonuçlarını birlikte bir uygulamadan performans bilgilerini toplamak için kullanılan yapılandırma verilerini kümesidir. Performans oturumları proje klasöründe depolanır ve bunları görüntüleyebilirsiniz **performans Gezgini**. Daha fazla bilgi için bkz: [anlama performans koleksiyon yöntemleri](/visualstudio/profiling/understanding-performance-collection-methods).

Oluşturma ve bir profil analizi uygulamanızı çalıştırdıktan sonra bir rapor performansı hakkında ayrıntılar sağlar. Bu rapor, zaman, hiyerarşik işlevi çağrı yığını veya çağrı ağacı CPU kullanım grafiği gibi öğelerin dahil edebilirsiniz. Raporu tam içeriğini örnekleme veya araçları gibi çalışan test türüne bağlı olarak değişebilir. Daha fazla bilgi için bkz: [profil oluşturma Araçlar raporuna genel bakış](http://go.microsoft.com/fwlink/?LinkId=224689).

## <a name="performance-session-process"></a>Performans Oturum İşlemi

Bir uygulama profili için bir performans oturumu oluşturmak için Araçlar performans profili oluşturma Sihirbazı'nı kullanarak başlatın. Menü çubuğunda seçin **Çözümle**, **başlatma performans Sihirbazı**. Sihirbazı tamamlama gibi istediğiniz profili yöntemi ve profil oluşturmayı istediğiniz uygulama gibi performans oturumunuz için gereken bilgileri girin. Daha fazla bilgi için bkz: [nasıl yapılır: bir Web sitesi veya Web uygulaması kullanarak profil performans Sihirbazı](http://go.microsoft.com/fwlink/?LinkId=224692). Alternatif olarak, bir performans oturumunu ayarlama çalıştırıp komut satırı seçeneklerini kullanabilirsiniz. Daha fazla bilgi için bkz: [profil oluşturma araçları gelen kullanarak komut satırı](http://go.microsoft.com/fwlink/?LinkId=224703). Bir performans oturumu her yönüyle el ile yapılandırmak istiyorsanız, bkz: [nasıl yapılır: el ile oluşturmak performans oturumları profil oluşturma araçları](http://go.microsoft.com/fwlink/?LinkId=224691). Ayrıca bir performans oturumu birim testi tarafından de oluşturabilirsiniz **Test sonuçları** birim testi için kısayol menüsünü açarak ve ardından seçme penceresi **performans oturum Oluştur**.


Bir performans oturumu ayarladıktan sonra oturum yapılandırma kaydedilir, sunucunun profil oluşturma veri sağlayacak şekilde yapılandırılır ve uygulamayı çalıştırır. Siz uygulamayı kullanırken performans verileri bir günlük dosyasına yazılır. Performans oturumları içinde listelenen **performans Gezgini** altında **hedefleri** klasör. Bir performans oturumu bittikten sonra raporu görünür **raporları** klasöründe **performans Gezgini**. Raporu görüntülemek için de açmak **performans Gezgini**. Performans oturumunu özelliklerini görüntülemek veya yapılandırmak için kendi kısayol menüsünü açın **performans Gezgini**ve ardından **özellikleri**. Belirli bir performans oturum özellikleri hakkında daha fazla bilgi için bkz: [için profil oluşturma araçları performans oturumlarını yapılandırma](http://go.microsoft.com/fwlink/?LinkId=224694). Bir performans oturumu sonuçlarını yorumlama hakkında daha fazla bilgi için bkz: [profil oluşturma araçları verilerini analiz etme](http://go.microsoft.com/fwlink/?LinkId=224704).

## <a name="stress-testing"></a>Yük Testi

Yük testleri ve web performans testleri Visual Studio'da oluşturarak uygulamalarınızın stres performansını analiz edebilirsiniz. Visual Studio'da bir yük testi oluşturduğunuzda, uygulamanızı karşı test etmek için bir senaryo adlı faktörlerin birleşimine belirtin. Bu etkenler yük düzeni, test karışımı modeli, test karışımı, ağ karışımı ve web tarayıcısı karışımını içerir. Yük testi senaryolarını birim testleri ve web performans testleri içerebilir.

Şekil 1: Örnek yük testi sonuçları

![Çalışan yük testi grafik görünümü](../sharepoint/media/load-webgraphs.png "çalışan bir yük testine grafik görünümü")

Web performans testleri benzetimini yapmak bir son kullanıcı bir SharePoint uygulaması ile nasıl etkileşim. Web performans testleri tarayıcı oturumunda HTTP isteklerini kaydetme veya kullanarak oluşturabilirsiniz **Web Performans Testi Kaydedicisi**. Web isteklerini görünür **Web Performans Testi Düzenleyicisi** tarayıcı oturumu sona erdikten sonra. Sonuçlarda sonra ayıklayabilirsiniz **Web Performans Testi Sonuçları Görüntüleyicisi**. Web performans testleri kullanarak el ile de oluşturabilirsiniz **Web Performans Testi Düzenleyicisi**.

## <a name="testing-user-interfaces"></a>Kullanıcı Arabirimlerini Sınama

Kodlanmış UI testleri SharePoint uygulamanız kendi kullanıcı arabirimi (UI) üzerinden otomatik olarak sürücü. Bu testler, düğmeler ve düzgün şekilde çalıştıklarının doğrulamak için menüler gibi kullanıcı Arabirimi denetimlerini kapsar. Bu tür sınama doğrulama veya diğer mantığı kullanıcı Arabiriminde gibi bir web sayfasında gerçekleştirilirse özellikle yararlıdır. Kodlanmış UI testleri, el ile testleri otomatikleştirmek için de kullanabilirsiniz. Testleri uygulamalarının diğer türleri için oluştururken, oluşturma kodlanmış UI testleri SharePoint uygulamalarınız için aynı şekilde. Daha fazla bilgi için bkz: [kodlanmış UI testleriyle SharePoint 2010 uygulamalarını test etme](/visualstudio/test/testing-sharepoint-2010-applications-with-coded-ui-tests).

## <a name="related-topics"></a>İlgili Konular

|Başlık|Açıklama|
|-----------|-----------------|
|[İzlenecek Yol: SharePoint Uygulaması için Profil Oluşturma](../sharepoint/walkthrough-profiling-a-sharepoint-application.md)|Örnekleme profili bir SharePoint uygulama çözümlemesi gösterir.|
|[Performans testi uygulamanızı serbest bırakmadan önce](https://www.visualstudio.com/docs/test/performance-testing/run-performance-tests-app-before-release)|Stres testi SharePoint uygulamaları Yardım yük testleri oluşturmayı açıklar.|
|[Kodunuza Birim Testi Uygulama](/visualstudio/test/unit-test-your-code)|Birim testleri kullanarak kodunuzda mantık hataları bulmak açıklar.|
|[Kodlanmış UI Testleriyle SharePoint 2010 Uygulamalarını Test Etme](/visualstudio/test/testing-sharepoint-2010-applications-with-coded-ui-tests)|SharePoint uygulamaları kullanıcı arabirimini test edileceğini açıklar.|

## <a name="see-also"></a>Ayrıca bkz.

[SharePoint Çözümleri Oluşturma ve Hatalarını Ayıklama](../sharepoint/building-and-debugging-sharepoint-solutions.md)  
[Kod Kalitesini Geliştirme](/visualstudio/test/improve-code-quality)