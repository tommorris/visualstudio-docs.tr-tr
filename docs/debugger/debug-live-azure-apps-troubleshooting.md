---
title: Anlık görüntü hata ayıklama için sorun giderme ve bilinen sorunlar | Microsoft Docs
ms.date: 11/07/2017
ms.technology: vs-ide-debug
ms.topic: conceptual
helpviewer_keywords:
- debugger
ms.assetid: 511a0697-c68a-4988-9e29-8d0166ca044a
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 7340b5f6ce7e9f8cbcbb0e2673b22712b3ab45a3
ms.sourcegitcommit: 3d10b93eb5b326639f3e5c19b9e6a8d1ba078de1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/18/2018
---
# <a name="troubleshooting-and-known-issues-for-snapshot-debugging-in-visual-studio"></a>Anlık görüntü Visual Studio'da hata ayıklama için sorun giderme ve bilinen sorunlar

Bu konuda açıklanan adımlar sorunu çözmezse başvurun snaphelp@microsoft.com.

## <a name="issue-snappoint-does-not-turn-on"></a>Sorun: Snappoint açılmıyor

Bir uyarı simgesi görürseniz ![Snappoint uyarı simgesi](../debugger/media/snapshot-troubleshooting-snappoint-warning-icon.png "Snappoint uyarı simgesi") normal snappoint simgesi yerine, snappoint ile sonra snappoint açık değil.

![Snappoint değil Aç](../debugger/media/snapshot-troubleshooting-dont-turn-on.png "Snappoint değil Aç")

Aşağıdaki adımları gerçekleştirin:

1. Derleme ve, app.isua1 dağıtmak için kullanılan kaynak kodu aynı sürümüne sahip olduğunuzdan emin olun. Dağıtımınız için doğru simgeleri yüklenen emin olun. Bunu yapmak için görüntülemek **modülleri** penceresi açıkken anlık görüntü hata ayıklama ve simge dosyası sütun .pdb dosyasını ayıkladığınız modülü için yüklenen gösterir doğrulayın. Anlık görüntü hata ayıklayıcı otomatik olarak karşıdan yükle ve dağıtımınız için simgeler kullanmayı deneyecek unutmayın.

## <a name="issue-symbols-do-not-load-when-i-open-a-snapshot"></a>Sorun: bir anlık görüntü açtığınızda simgeleri yüklenmez

Pencere görürseniz, simgeler yüklemedi.

![Yüklenmemesi simgeleri](../debugger/media/snapshot-troubleshooting-symbols-wont-load.png "yüklenmemesi semboller")

Aşağıdaki adımları gerçekleştirin:

- Tıklatın **Simge Ayarları Değiştir...** Bu sayfada bağlayın. İçinde **hata ayıklama > Sembol** ayarlarını, bir simge önbelleği dizini ekleyin. Simge yolu ayarlandıktan sonra anlık görüntü hata ayıklamayı yeniden başlatın.

   Simge veya .pdb dosyaları, projenize kullanılabilir, App Service dağıtımınızda eşleşmesi gerekir. Çoğu dağıtımda (Visual Studio, CI/CD VSTS veya Kudu, dağıtımıyla vb.), simge dosyaları boyunca uygulama hizmetiniz yayımlayacak. Simge önbelleği dizini ayarı bu simgeleri kullanmak Visual Studio sağlar.

   ![Simge Ayarları](../debugger/media/snapshot-troubleshooting-symbol-settings.png "simge ayarları")

- Alternatif olarak, kuruluşunuz bir simge sunucusu kullanan veya farklı bir yolda simgeleri bırakır, dağıtımınız için doğru simgeleri yüklemek için simge ayarlarını kullanın.

## <a name="issue-i-cannot-see-the-attach-snapshot-debugger-option-in-the-cloud-explorer"></a>Sorun: "Anlık görüntü hata ayıklayıcı Ekle" seçeneğini Cloud Explorer'da göremiyorum

Aşağıdaki adımları gerçekleştirin:

- Anlık görüntü hata ayıklayıcı bileşeni yüklü olduğundan emin olun. Visual Studio Yükleyicisi'ni açın ve denetleme **anlık görüntü hata ayıklayıcı** Azure yükündeki bileşen.
- Uygulamanızı desteklenen emin olun. Şu anda, yalnızca ASP.NET (4.6.1+) ve ASP.NET Core (2.0 +) uygulamaları için Azure App Services dağıtılan desteklenir.

## <a name="issue-i-only-see-throttled-snapshots-in-the-diagnostic-tools"></a>Sorun: yalnızca anlık görüntüleri tanılama araçları kısıtlanan görüyorum

![Throttled snappoint](../debugger/media/snapshot-troubleshooting-throttled-snapshots.png "snappoint kısıtlanan")

Aşağıdaki adımları gerçekleştirin:

- Anlık görüntüler çok az bellek alanı dolduracaktır ancak yürütme ücrete tabi. Anlık görüntü hata ayıklayıcı sunucunuz yoğun bellek yük altında olduğu algılarsa, anlık görüntüleri olmayacaktır. Zaten yakalanan anlık görüntüler, anlık görüntü hata ayıklayıcı oturum durdurma ve yeniden deneme silebilirsiniz.

## <a name="known-issues"></a>Bilinen Sorunlar

- Aynı uygulama hizmeti karşı birden çok Visual Studio istemcilerle anlık görüntü hata ayıklama şu anda desteklenmiyor.
- Roslyn IL iyileştirmeler ASP.NET Core projelerinde tam olarak desteklenmez. Bazı ASP.NET Core projeleri için bazı değişkenler görmek veya bazı değişkenler koşullu ifadeler kullanmak mümkün olmayabilir. 
- Özel değişkenler gibi *$FUNCTION* veya *$CALLER*, koşullu ifadeleri veya ASP.NET Core projeleri için logpoints değerlendirilemez.
- Anlık görüntü hata ayıklama uygulama hizmetleri üzerinde sahip çalışmıyor [yerel önbelleğe alma](/azure/app-service/app-service-local-cache) açık.
- Hata ayıklama API uygulamaları anlık görüntü şu anda desteklenmiyor.

## <a name="site-extension-upgrade"></a>Site uzantısı yükseltme

Anlık görüntü hata ayıklama ve Application Insights site sürecine yükler ve dosya kilitleme sorunları yükseltme sırasında neden olan bir ICorProfiler bağlıdır. Hiçbir kapalı kalma süresi, üretim sitenize olduğundan emin olun. Bu işlem öneririz.

- Oluşturma bir [dağıtım yuvası](/azure/app-service/web-sites-staged-publishing) App Service içinde ve sitenizi yuvaya dağıtabilirsiniz.
- Visual Studio bulut Gezgini'nden veya Azure Portal üretim yuvasıyla takas.
- Yuva sitesini durdurun. Bu site w3wp.exe işleminin tüm örnekleri kapalı sonlandırmak için birkaç saniye sürer.
- Kudu site veya Azure portalından yuvası site uzantısı yükseltme (*uygulama hizmeti dikey > Geliştirme araçları > uzantılar > güncelleştirme*).
- Yuva sitesini başlatın. Yeniden sıcak için siteyi ziyaret öneririz.
- Üretim yuvasıyla takas.

## <a name="see-also"></a>Ayrıca bkz.

[Visual Studio’da hata ayıklama](../debugger/index.md)  
[Anlık görüntü hata ayıklayıcı kullanarak canlı ASP.NET uygulamaları hata ayıklama](../debugger/debug-live-azure-applications.md)  
[Anlık görüntü hatalarını ayıklama hakkında SSS](../debugger/debug-live-azure-apps-faq.md)  
