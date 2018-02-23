---
title: IntelliTrace | Microsoft Docs
ms.custom: 
ms.date: 07/18/2017
ms.reviewer: 
ms.suite: 
ms.technology:
- vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- vs.historicaldebug.overview
helpviewer_keywords:
- debugger, recording execution history
- debugging, recording execution history
- IntelliTrace [Visual Studio ALM]
- IntelliTrace, debugging applications
- debugger, (See also IntelliTrace [Visual Studio ALM])
- debugging, (See also IntelliTrace [Visual Studio ALM])
- IntelliTrace, collecting data from Test Manager
- IntelliTrace
- Test Manager, debugging with IntelliTrace
- IntelliTrace, debugging after a crash
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.workload:
- multiple
ms.openlocfilehash: 07afad8b464e266477c4edbb97ffc3eb3d8436e4
ms.sourcegitcommit: 36ab8429333b31f03992a9fe8fc669db8e09c968
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/21/2018
---
# <a name="intellitrace"></a>IntelliTrace

IntelliTrace kaydetmek ve kodunuzu 's yürütme geçmişini izlemek için kullandığınızda uygulamanızın hatalarını ayıklama daha az zaman harcayabilir. IntelliTrace izin verdiğinden, hataları kolayca bulabilirsiniz:

- Kayıt belirli olayları

     İlgili kod, görüntülenen verileri incelemek **Yereller** penceresi sırasında hata ayıklayıcı olayları ve işlev çağrısı bilgisi

- Yeniden zor veya dağıtımında gerçekleşen hataları hata ayıklama

Visual Studio Enterprise edition (ancak değil Professional veya topluluk sürümleri), IntelliTrace kullanabilirsiniz.

## <a name="what-do-you-want-to-do"></a>Ne yapmak istiyorsunuz?

|||
|-|-|
|**Uygulamam IntelliTrace ile hata ayıklama:**<br /><br /> -Geçmişteki olayları göster.<br />-Beni Ara geçmiş olaylar bilgilerle gösterir.<br />-IntelliTrace Oturumum kaydedin.<br />-Denetim IntelliTrace topladığı veriler.|- [İzlenecek yol: IntelliTrace'i kullanma](../debugger/walkthrough-using-intellitrace.md)<br />- [IntelliTrace özellikleri](../debugger/intellitrace-features.md)<br />- [Geçmiş hata ayıklama](../debugger/historical-debugging.md)<br />- [IntelliTrace adım geri kullanarak görünüm anlık görüntüler](../debugger/how-to-use-intellitrace-step-back.md)|
|**Test Yöneticisi'nde testi oturumu sırasında IntelliTrace verilerini toplama**|- [El ile testlerde daha fazla tanılama verisi toplama](/vsts/manual-test/mtm/collect-more-diagnostic-data-in-manual-tests)|
|**Dağıtılan uygulamalarından IntelliTrace verilerini toplama**|- [IntelliTrace tek başına toplayıcıyı kullanma](../debugger/using-the-intellitrace-stand-alone-collector.md)|
|**IntelliTrace günlük dosyasından (.iTrace dosyası) hata ayıklamayı Başlat.**|- [Kaydedilen IntelliTrace verilerini kullanma](../debugger/using-saved-intellitrace-data.md)|

## <a name="IntelliTraceSupport"></a> Hangi uygulamaların ı IntelliTrace ile hata ayıklayabilirim?

|||
|-|-|
|Desteklenen|-.NET Framework 2.0 veya daha sonraki sürümler kullanın Visual Basic ve Visual C# uygulamalar.<br/>ASP.NET, Microsoft Azure, Windows Forms, WCF, WPF, Windows iş akışı, SharePoint 2010, SharePoint 2013 ve 64-bit uygulamalar dahil olmak üzere çoğu uygulamayı ayıklayabilirsiniz.<br/>SharePoint uygulamaları IntelliTrace ile hata ayıklamak için bkz: [izlenecek yol: bir SharePoint uygulaması kullanarak IntelliTrace ile hata ayıklama](../sharepoint/walkthrough-debugging-a-sharepoint-application-by-using-intellitrace.md).<br/> Microsoft Azure uygulamaları IntelliTrace ile hata ayıklamak için bkz: [yayımlanan bir bulut hizmeti IntelliTrace ve Visual Studio ile hata ayıklama](/azure/vs-azure-tools-intellitrace-debug-published-cloud-services).|
|**Sınırlı destek**|-.NET core ve ASP.NET Core uygulamaları yalnızca olayları desteklenen<br />-F # uygulamaları Deneysel düzenli olarak<br />-Yalnızca olayları desteklenen UWP uygulamaları|
|Desteklenmiyor|-C++ diğer dillere ve komut dosyası<br />-Windows Hizmetleri, Silverlight, Xbox veya [!INCLUDE[winmobile](../debugger/includes/winmobile_md.md)] uygulamalar|

> [!NOTE]
> Zaten çalışan işlemde hata ayıklamak istiyorsanız, yalnızca IntelliTrace olayları (çağrı bilgileri) toplayabilir. Bir 32 bit veya 64-bit işlem yalnızca yerel makinedeki ekleyebilirsiniz. İşleme iliştirilemiyor önce gerçekleşen olaylara toplanmadı.

##  <a name="IntelliTraceVSTraditional"></a> Neden IntelliTrace ile hata ayıklama?

Geleneksel veya *canlı* hata ayıklama yalnızca uygulamanızın geçerli durumu, son olaylar hakkında sınırlı verilerle gösterir. Ya da uygulamanın geçerli durumuna göre bu olayları Infer gerekir veya bu olayları, uygulamanızın yeniden çalıştırarak yeniden oluşturmanız gerekir.

IntelliTrace bu zamanlardaki belirli olayları ve verileri kaydederek bu geleneksel hata ayıklama deneyimini genişletir. Bu, özellikle hata olduğu geçmiş adım uygulamanızda, yeniden başlatmadan ne görmenizi sağlar. IntelliTrace geleneksel hata ayıklama işlemi sırasında varsayılan olarak açıktır ve görünmez ve otomatik olarak veri toplar. Bu, geleneksel hata ayıklama ve IntelliTrace hata ayıklama arasında kaydedilen bilgileri görmek için kolayca geçiş yapmanızı sağlar. Bkz: [IntelliTrace özellikleri](../debugger/intellitrace-features.md) ve [hangi verilerin IntelliTrace Topla?](#WhatData)

IntelliTrace yeniden oluşturulması zor olan veya dağıtımda gerçekleşen hataları ayıklamaya da yardımcı olabilir. IntelliTrace verisi toplayabilir ve bir IntelliTrace günlük dosyasına (.iTrace dosyası) kaydedebilirsiniz. Bir .iTrace dosyası özel durumlar, performans olayları, Web istekleri, test verileri, iş parçacıkları, modüller ve diğer sistem bilgileri ile ilgili ayrıntıları içerir. Visual Studio kuruluşta bu dosyayı açın, bir öğe seçin ve IntelliTrace ile hata ayıklama başlatılamıyor. Bu, dosyanın herhangi bir olay gidin ve uygulamanızı zamandaki o noktada hakkında belirli diğer ayrıntıları görmek sağlar.

Bu kaynaklardan IntelliTrace verisi kaydedebilirsiniz:

- Visual Studio 2017 Enterprise, Visual Studio 2015 Enterprise ya da Visual Studio Ultimate önceki sürümlerini IntelliTrace oturumu.

- Microsoft Test Yöneticisi'nde bir test oturumu

- IIS'de barındırılan ASP.NET web uygulamaları ya da Microsoft Monitoring Agent kullandığınızda dağıtımda tek başına ya da System Center 2012 ile birlikte çalışan SharePoint 2010 ve SharePoint 2013 uygulamaları. Bkz: [IntelliTrace tek başına toplayıcıyı kullanma](../debugger/using-the-intellitrace-stand-alone-collector.md) ve [Microsoft Monitoring Agent ile izleme](http://technet.microsoft.com/library/dn465153.aspx).

 IntelliTrace'in hata ayıklamada yardımcı olması ile ilgili bazı örnekler aşağıdadır:

- Uygulamanızı bir veri dosyası bozuk, ancak bu olay yapıldığı tanımadığınız.

     IntelliTrace olmadan tüm olası dosya erişimler bulmak için bu erişim sırasında kesme noktaları put kodlarda bakmanız ve sorun yapıldığı bulmak için uygulamanızın yeniden çalıştırın. Her olayın meydana geldiği zaman IntelliTrace ile tüm toplanan dosya erişimi olayları ve belirli Ayrıntılar uygulamanız hakkında görebilirsiniz.

- Bir özel durum gerçekleşir.

     IntelliTrace olmadan bir özel durum hakkında bir ileti alır ancak özel durumu öncülük olaylar hakkında daha bilgi yok. Özel durumu öncülük çağrı zincirine görmek için çağrı yığını inceleyebilirsiniz, ancak bu çağrılar sırasında gerçekleşen olayların sırası göremez. IntelliTrace ile özel durumdan önce meydana gelen olayları inceleyebilirsiniz.

- Uygulamanızı test bilgisayarında çöküyor ancak başarılı bir şekilde geliştirme bilgisayar üzerinde çalışır.

     Microsoft Test Yöneticisi'nden IntelliTrace verisi toplayabilir, verileri .iTrace dosyasına kaydedebilir ve bu dosyayı daha sonra incelemek için Team Foundation Server çalışma öğesine ekleyebilirsiniz. Bkz: [el ile testlerde daha fazla tanılama verisi toplama](/vsts/manual-test/mtm/collect-more-diagnostic-data-in-manual-tests) ve [kaydedilmiş IntelliTrace verilerini kullan](../debugger/using-saved-intellitrace-data.md).

- Bir hata ya da kilitlenme dağıtılan bir uygulama olur.

     Uygulamayı yayımlamadan önce Microsoft Azure tabanlı uygulamalar için IntelliTrace verilerini toplama yapılandırabilirsiniz. Uygulamanızı çalışırken IntelliTrace verilerini bir .iTrace dosyasına kaydeder. Bkz: [IntelliTrace ve Visual Studio ile yayımlanan bulut hizmetinde hata ayıklama](http://go.microsoft.com/fwlink/?LinkID=262248).

     IIS 7.0, 7.5 ve 8.0'da barındırılan ASP.NET web uygulamaları ve SharePoint 2010 ya da SharePoint 2013 uygulamalarında, IntelliTrace verisini bir .iTrace dosyasına kaydetmek için Microsoft İzleme Aracısı'nı tek başına ya da System Center 2012 ile birlikte kullanın.

     Bu, dağıtımdaki uygulamalarla ilgili sorunları tanılamak istediğinizde kullanışlıdır. Bkz: [IntelliTrace tek başına toplayıcıyı kullanma](../debugger/using-the-intellitrace-stand-alone-collector.md).

##  <a name="WhatData"></a> Hangi verilerin IntelliTrace topluyor?

**Olay bilgilerini toplama**

Varsayılan olarak, IntelliTrace yalnızca IntelliTrace olayları kaydeder: hata ayıklayıcı olayları, özel durumlar, .NET Framework olaylar ve hata ayıklamaya yardımcı olabilecek diğer sistem olayları. Hata ayıklayıcı olayları ve her zaman toplanan özel durumlar dışında toplamak istediğiniz IntelliTrace olaylarının türlerini seçebilirsiniz. Bkz: [IntelliTrace özellikleri](../debugger/intellitrace-features.md).

- **Hata ayıklayıcı olayları**

     IntelliTrace her zaman Visual Studio hata ayıklayıcıda gerçekleşen olayları kaydeder. Örneğin, uygulamanızın başlangıç bir hata ayıklayıcı olayıdır. Diğer hata ayıklayıcı olayları yürütme ayırmak, uygulamanızın neden olayları duruyor. Örneğin, programınızı bir kesme noktası isabet, bir tracepoint isabetler veya yürüten bir **adım** komutu.

     Varsayılan olarak, performans ile yardımcı olması için IntelliTrace hata ayıklayıcı olayı için olası her değer kaydetmez. Bunun yerine, bu değerleri kaydeder:

    - Değerler **Yereller** penceresi. Tutmak **Yereller** penceresi bu değerleri görmek için açık.

    - Değerler **otomobiller** penceresi yalnızca IF **otomobiller** penceresini açın

    - Kaynak penceresinde değerini görmek için bir değişkenin üzerine fare işaretçisini getirdiğinizde görüntülenen DataTips değerleri. IntelliTrace sabitlenmiş DataTips değerlerini toplamaz.

    IntelliTrace olayları ve anlık görüntü modu etkinleştirildiğinde, IntelliTrace her hata ayıklayıcı uygulama işlemi bir anlık görüntüsünü **kesme noktası** ve **adım** olay. Bu değerleri kaydedilecek **Yereller**, **otomobiller**, ve **izleme** windows, windows veya açık olup ne olursa olsun. Tüm sabit veri ipuçları değerleri de toplanacaktır.

- **Özel Durumlar**

     IntelliTrace özel durum türünü ve iletisini bu tür özel durumlar için kaydeder:

    - Özel durumun ortaya çıktığı ve yakalandığı yönetilen özel durumlar

    - Yönetilmeyen özel durumlar

- **.NET framework olayları**

     Varsayılan olarak, IntelliTrace en sık görülen .NET Framework olaylarını kaydeder. Örneğin:

    - Bir Onay Kutusu Denetimi olayında IntelliTrace onay kutusunun durumunu ve metnini toplar.

- **SharePoint 2010 ve SharePoint 2013 uygulama olayları**

     Kullanıcı profili olayları ve SharePoint 2010 ile Visual Studio dışında çalışan 2013 uygulamaları için birleşik Günlük Kaydetme Sistemi (ULS) olaylarının alt kümesini kaydedebilirsiniz. Bu olayları bir .iTrace dosyasına kaydedebilirsiniz. Visual Studio Enterprise 2017, Visual Studio Enterprise 2015, Visual Studio Ultimate, bir önceki sürümünü gerektirir veya [Microsoft İzleme Aracısı](http://go.microsoft.com/fwlink/?LinkId=320384) çalışır durumda **izleme** modu.

     .iTrace dosyasını açtığınızda, eşleşen web isteğini bulmak için bir SharePoint bağıntı kimliği girin, kayıtlı olayları görüntüleyin ve belirli bir olaydan hata ayıklamaya başlayın. Dosya işlenmeyen özel durumlar içeriyorsa, bir bağıntı kimliği seçerek bir özel durumu hata ayıklamaya başlayabilirsiniz.

     Bkz.

    - [IntelliTrace tek başına toplayıcıyı kullanma](../debugger/using-the-intellitrace-stand-alone-collector.md)

    - [Kayıtlı IntelliTrace verilerini kullanma](../debugger/using-saved-intellitrace-data.md)

    - [İzlenecek yol: IntelliTrace'i Kullanarak SharePoint Uygulamasında Hata Ayıklama](../sharepoint/walkthrough-debugging-a-sharepoint-application-by-using-intellitrace.md)

**Anlık görüntüleri yakalama**

IntelliTrace anlık görüntüleri her kesme noktasındaki yakalamak ve adım olay hata ayıklayıcı için yapılandırabilirsiniz. IntelliTrace karmaşık değişkenleri görüntülemek ve ifadeler değerlendirmek için verir her anlık görüntü konumundaki tam uygulama durumunu kaydeder.

Bkz: [görüntülemek IntelliTrace adım geri kullanarak anlık görüntüyü](../debugger/how-to-use-intellitrace-step-back.md).

**İşlev çağrısı bilgisi toplama**

İşlev çağrı bilgilerini toplamak için IntelliTrace'i yapılandırabilirsiniz. Bu bilgiler çağrı yığını geçmişini görmenizi sağlar ve koddaki çağrılarda geri veya ileri hareket edebilmenize izin verir. Her işlev çağrısı için IntelliTrace bu verileri kaydeder:

- İşlev adı
- İşlev giriş noktalarında parametre olarak gönderilen ve işlev çıkış noktalarında döndürülen temel veri türlerinin değerleri
- Okunduklarında veya değiştirildiklerinde otomatik özelliklerin değerleri
- Birinci düzey alt nesnelerin işaretçileri, ancak değerleri yalnızca boş veya değil şeklinde verilir

> [!NOTE]
> IntelliTrace yalnızca dizilerdeki ilk 256 nesneyi ve dizelerdeki ilk 256 karakteri toplar.

Bkz: [geçmiş hata ayıklama ile uygulamanızı incelemek](../debugger/historical-debugging-inspect-app.md).

**Modül bilgilerini toplama**

IntelliTrace'in ne kadar çağrı bilgisi topladığını denetlemek için, yalnızca istediğiniz modülleri belirtin. Bu toplama sırasında uygulamanızın performansını artırmaya yardımcı olabilir. Bölümüne bakın [ne kadar bilgi IntelliTrace toplar kontrol](../debugger/intellitrace-features.md#ControlCallData) IntelliTrace özellikleri.

## <a name="AffectPerformance"></a> Uygulamam yavaş olacak IntelliTrace?

Varsayılan olarak, IntelliTrace yalnızca seçili IntelliTrace olaylarının verilerini toplar. Bu olabilir veya yapısı ve kod organizasyonu bağlı olarak, uygulamayı yavaşlatabilir değil. Örneğin, IntelliTrace genellikle bir olay kaydeder, bu uygulamanızın yavaşlatabilir. Bu ayrıca, uygulamanızı yeniden düzenleme göz önünde bulundurun yapabilir.

Toplama çağrı bilgileri uygulamanızı önemli ölçüde yavaşlatabilir. Diske kaydettiğiniz IntelliTrace herhangi bir günlük dosyasının (.iTrace dosyaları) boyutunu da artırabilir. Bu etkileri en aza indirmek için yalnızca ilginiz dahilinde olan modüller için çağrı bilgilerini toplayın.  .İTrace dosyaları en büyük boyutunu değiştirmek için gidin **Araçları**, **seçenekleri**, **IntelliTrace**, **Gelişmiş**. 

## <a name="in-this-section"></a>Bu bölümde

[IntelliTrace özellikleri](../debugger/intellitrace-features.md)
[dağıtımdan sonra sorunları tanılama](../debugger/diagnose-problems-after-deployment.md)
[kaydedilmiş IntelliTrace verilerini kullan](../debugger/using-saved-intellitrace-data.md)

### <a name="blogs"></a>Bloglar

[Visual Studio ALM + Team Foundation Server](http://go.microsoft.com/fwlink/?LinkID=201340)

### <a name="forums"></a>Forumlar

[Visual Studio tanılama](http://go.microsoft.com/fwlink/?LinkId=262263)