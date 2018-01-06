---
title: "Anlık görüntü hata ayıklama hakkında SSS | Microsoft Docs"
ms.date: 11/07/2017
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: debugger
ms.assetid: 944f1eb0-a74b-4d28-ae2b-a370cd869add
caps.latest.revision: "1"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.workload: multiple
ms.openlocfilehash: fd2ca2bf48c50b0ea5b44654d0711ba162313f04
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/22/2017
---
# <a name="frequently-asked-questions-for-snapshot-debugging-in-visual-studio"></a>Sık sorulan anlık görüntü Visual Studio'da hata ayıklama ile ilgili sorular

Burada, anlık görüntü hata ayıklayıcıyı kullanma Canlı Azure uygulamalarını hata ayıklama sırasında gelebilir yukarı soruları listesi verilmiştir.

#### <a name="what-is-the-performance-cost-of-taking-a-snapshot"></a>Bir anlık görüntü alma performans maliyeti nedir?

Anlık görüntü hata ayıklayıcı uygulamanızı görüntüsünü yakalar, uygulamanın işlem forking ve forked kopyalama askıya alınıyor. Bir anlık görüntü hata ayıklarken işlemi forked kopyası üzerinde ayıkladığınız. Bu işlem yalnızca 10-20 milisaniye alır ancak uygulamanın tam yığın kopyalamaz; Bunun yerine, yalnızca sayfa tablosu kopyalar ve yazma kopyalamak için sayfaları ayarlar. Yığın değişiklik uygulamanızın nesnelerde bazıları, kendi ilgili sayfalar sonra kopyalanır. Her anlık görüntü, bu nedenle çok küçük bir bellek içi maliyeti (terabayt kilobayt çoğu uygulamalar için yüzlerce) sahiptir. 

#### <a name="what-happens-if-i-have-a-scaled-out-azure-app-service-multiple-instances-of-my-app"></a>Ölçeklendirilen Azure App Service (Uygulamam birden çok örneğini) varsa ne olur?

Uygulamanız birden çok örneği varsa, her tek örnekli snappoints uygulanacağını. Belirtilen koşul ile İsabet yalnızca ilk snappoint bir anlık görüntüsü oluşturur. Birden çok snappoints varsa, sonraki anlık ilk anlık görüntüyü oluşturulan aynı örnek gelir. Uygulama günlüklerini gönderilen logpoints her örneğinden iletileri gönderirken çıkış penceresine gönderilen Logpoints yalnızca bir örnek, gelen iletileri göster. 

#### <a name="how-does-the-snapshot-debugger-load-symbols"></a>Anlık görüntü hata ayıklayıcı simgeleri nasıl yüklenmesi?

Anlık görüntü hata ayıklayıcı eşleşen simgeler, uygulamanız için ya da yerel olarak yüklü veya (katıştırılmış pdb şu anda desteklenmiyor), Azure App Service'e dağıtılan gerektirir. Anlık görüntü hata ayıklayıcı simgeleri Azure uygulama hizmetiniz otomatik olarak yükler. Visual Studio 2017 itibariyle de Azure App Service'e dağıtma sürüm 15.2, uygulamanızın simgeleri dağıtır.

#### <a name="does-the-snapshot-debugger-work-against-release-builds-of-my-application"></a>Anlık görüntü hata ayıklayıcı Uygulamam yayın derlemeleri karşı çalışır?

Evet - sürüm derlemeleri karşı çalışmak için anlık görüntü hata ayıklayıcı yöneliktir. Bir snappoint bir işlevde yerleştirildiğinde işlevi debuggable yapmadan geri bir hata ayıklama sürümü için derlenmiştir. Anlık görüntü hata ayıklayıcı durdurduğunuzda, İşlevler için yayın derlemesi döndürülür. 

#### <a name="can-logpoints-cause-side-effects-in-my-production-application"></a>Logpoints yan etkileri üretim uygulamamda neden olabilir mi?

Hayır - uygulamanıza eklediğiniz herhangi bir günlük iletisi neredeyse değerlendirilir. Bunlar, uygulamanızda herhangi yan etkileri neden olamaz. Ancak, yerel bazı özellikler logpoints ile erişilebilir olmayabilir. 

#### <a name="does-the-snapshot-debugger-work-if-my-server-is-under-load"></a>Anlık görüntü hata ayıklayıcı sunucum yük altında olduğunda çalışır?

Anlık görüntü hata ayıklama, yük altında sunucuları için Evet, çalışabilir. Anlık görüntü hata ayıklayıcı kısıtlar ve anlık görüntüleri durumlarda yakalamaz düşük boş bellek miktarı, sunucunuzdaki olduğu.

#### <a name="how-do-i-uninstall-the-snapshot-debugger"></a>Anlık görüntü hata ayıklayıcı nasıl kaldırabilirim?

Uygulama hizmetiniz aşağıdaki adımlarla üzerinde anlık görüntü hata ayıklayıcı site uzantısı kaldırabilirsiniz:

1. Uygulama hizmeti kapatmak bulut Gezgini'nde Visual Studio ya da Azure Portal aracılığıyla.
1. Uygulama hizmetinizin Kudu sitesine gidin (diğer bir deyişle, yourappservice. **SCM**. azurewebsites.net) gidin **Site uzantıları**.
1. Anlık görüntü hata ayıklayıcı site uzantısı kaldırmak için X'i tıklatın.

## <a name="see-also"></a>Ayrıca bkz.

[Visual Studio'da hata ayıklama](../debugger/index.md)  
[Anlık görüntü hata ayıklayıcı kullanarak canlı ASP.NET uygulamaları hata ayıklama](../debugger/debug-live-azure-applications.md)  
[Anlık görüntü hata ayıklama için sorun giderme ve bilinen sorunlar](../debugger/debug-live-azure-apps-troubleshooting.md)
