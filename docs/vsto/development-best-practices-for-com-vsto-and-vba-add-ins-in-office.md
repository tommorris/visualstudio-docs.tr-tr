---
title: "En iyi geliştirme eklentilerinde Office COM, VSTO ve VBA yöntemler | Microsoft Docs"
ms.custom: 
ms.date: 07/25/2017
ms.reviewer: 
ms.suite: 
ms.technology: office-development
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: 
helpviewer_keywords: 
ms.assetid: 810a6648-fece-4b43-9eb6-948d28ed2158
caps.latest.revision: "33"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload: office
ms.openlocfilehash: 8985b3bb6e20b24b86174286104158c8830de971
ms.sourcegitcommit: 9357209350167e1eb7e50b483e44893735d90589
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/05/2018
---
# <a name="development-best-practices-for-com-vsto-and-vba--add-ins-in-office"></a>COM, VSTO ve VBA eklentilerinde Office için en iyi uygulamaları geliştirme
  COM, VSTO veya VBA eklentiler için Office geliştiriyorsanız, bu makalede açıklanan geliştirme en iyi uygulamaları izleyin.   Bu, olmanıza yardımcı olur:

-  Eklentilerinizi farklı sürümleri ve Office dağıtımlar arasında uyumluluk.
-  Azaltılan karmaşıklık eklenti dağıtım kullanıcılar ve BT yöneticileri için.
-  İstenmeyen yükleme veya çalışma zamanı hatalarının eklentiniz gerçekleşmez.

>Not: Kullanarak [Masaüstü köprüsü](/windows/uwp/porting/desktop-to-uwp-root) , COM hazırlamak için VSTO veya VBA eklentisi için Windows mağazası desteklenmiyor. COM, VSTO ve VBA eklentiler, Windows mağazası veya Office deposunda dağıtılamıyor. 
  
## <a name="do-not-check-for-office-during-installation"></a>Office için yükleme sırasında denetleme  
 Office eklentisini yükleme işlemi sırasında yüklenip yüklenmediğini belirle eklentinizi sahip öneririz yok. Office yüklü değilse, eklenti yükleyebilir ve kullanıcı Office yüklendikten sonra erişebilir. 
  
## <a name="use-embedded-interop-types-nopia"></a>Katıştırılmış birlikte çalışma türlerini (NoPIA) kullanın  
Çözümünüzü daha sonra .NET 4.0 kullanır veya kullanıyorsanız katıştırılmış birlikte çalışma türleri (NoPIA) yerine Office birincil birlikte çalışma derlemeleri (PIA bağlı olarak) yeniden dağıtılabilir. Türü katıştırma kullanarak çözümünüzü yükleme boyutunu azaltır ve ileriye dönük uyumluluk sağlar. Office 2010 yeniden dağıtılabilir PIA birlikte gelen Office son sürümünü oluştu. Daha fazla bilgi için bkz: [izlenecek yol: Microsoft Office derlemelerinden tür bilgilerini katıştırma](https://msdn.microsoft.com/en-us/library/ee317478.aspx) ve [tür Eşdeğerliği ve katıştırılmış birlikte çalışma türlerini](/windows/uwp/porting/desktop-to-uwp-root).

Çözümünüzü .NET önceki bir sürümünü kullanıyorsa, .NET 4.0 veya sonraki sürümü kullanmak için çözümünüzün güncelleştirmenizi öneririz. .NET 4.0 veya sonraki sürümü kullanarak, daha yeni sürümlerinde Windows çalışma zamanı Önkoşullar azaltır.
  
## <a name="avoid-depending-on-specific-office-versions"></a>Bağlı olarak belirli Office sürümleri kaçının  
Çözümünüzü yalnızca Office, daha yeni sürümlerinde kullanılabilir olan işlevsellik kullanıyorsa, çalışma zamanında (örneğin, özel durum işleme veya sürüm denetleyerek kullanarak) özelliği (mümkünse, özellik düzeyinde) bulunduğunu doğrulayın. Nesne modelinde gibi desteklenen API'lerini kullanarak belirli sürümler yerine, en düşük sürümlerle doğrulamak [Application.Version özelliği](https://msdn.microsoft.com/en-us/library/office/microsoft.office.interop.excel._application.version.aspx). Bunlar yüklemeleri, ortamları ve sürümler arasında değişebildiğinden Office ikili meta verileri, yükleme yolları veya kayıt defteri anahtarlarını kullanan öneririz yok.

## <a name="enable-both-32-bit-and-64-bit-office-usage"></a>32 bit ve 64 bit Office kullanımı etkinleştir   
Yalnızca belirli verileri için kullanılabilir kitaplıkları çözümünüzü bağlıdır sürece varsayılan derleme hedefiniz hem 32 bit (x86) hem de 64 bit (x64) desteklemelidir. Office'in 64 bit sürümü özellikle büyük veri ortamlarda benimseme artmaktadır. Destek 32-bit ve 64-bit, Office'in 32 bit ve 64-bit sürümleri arasında geçiş için kullanıcılarınızın kolaylaştırır.

VBA kodu yazarken kullanmak için 64-bit güvenli deyimleri bildirme ve değişkenleri uygun olarak Dönüştür. Ayrıca, belgeler için her bit kodu sağlayarak Office 32 bit veya 64 bit sürümlerini çalıştıran kullanıcılar arasında paylaşılabilen emin olun. Daha fazla bilgi için bkz: [uygulamalarına genel bakış için 64-Bit Visual Basic](https://msdn.microsoft.com/en-us/library/office/gg264421.aspx).

## <a name="support-restricted-environments"></a>Kısıtlı ortamları desteği   
Çözümünüzü kullanıcı hesabı yükseltme veya yönetici ayrıcalıkları gerektirmemelidir. Buna ek olarak, çözümü ayarlama veya değiştirme bağlı olmaması gerekir:

- Geçerli çalışma dizini.
- DLL yükleme dizinleri.
- YOLU değişken.

## <a name="change-the-save-location-of-shared-data-and-settings"></a>Kaydetme değiştirmek konumunu paylaşılan veri ve ayarları
Çözümü bir eklenti ve Office harici bir işlem oluşuyorsa, exchange verileri veya eklenti ve dış işlem arasında ayarları için kullanıcının uygulama veri klasörü veya kayıt defteri kullanmayın. Bunun yerine, kullanıcının geçici klasör, Belgeler klasörünü veya çözümünüzün yükleme dizini kullanmayı düşünün.

## <a name="increment-the-version-number-with-each-update"></a>Her güncelleştirme sürüm numarasını Artır
İkili dosyalarının sürüm numarasını çözümünüzde ayarlayın ve her güncelleştirme ile artırın. Bu, sürümler arasındaki değişiklikleri tanımlamak ve uyumluluğu değerlendirmek kullanıcılar için daha kolay hale getirir.

## <a name="provide-support-statements-for-the-latest-versions-of-office"></a>En son Office sürümleri için destek bildirimleri sağlayın
Müşteriler kendi COM, VSTO ve VBA ofisinde çalıştırılan eklentileri için destek bildirimleri sağlamak için ISV istiyoruz. Office 365 ProPlus kullanarak açık destek deyimleri yardımcı müşterilerinizin listeleme hazırlık araçları destek anlayın. 

Office istemci uygulamaları (Word veya Excel gibi) için destek bildirimleri sağlamak için önce eklentilerinizi geçerli Office sürümü çalıştırın ve eklentinizi gelecekteki bir sürümde bozarsa güncelleştirmeleri sağlamayı Yürüt doğrulayın. Microsoft yeni bir yapı ya da Office için bir güncelleştirme yayımlandığında eklentilerinizi test etmek zorunda değildir. Microsoft Office COM, VSTO ve VBA genişletilebilirlik platform nadiren değişiklikleri ve bu değişiklikleri belgelendiğinden.

>Önemli: Microsoft hazır olma durumunu raporlar ve ISV kişi bilgileri için desteklenen eklentiler listesini tutar. Listelenen eklentiniz almak için bkz: [https://aka.ms/readyforwindows](https://aka.ms/readyforwindows).

## <a name="use-process-monitor-to-help-debug-installation-or-loading-issues"></a>İşlem İzleyicisi yükleme veya sorunları yüklenirken hata ayıklamaya yardımcı olması için kullanın
Eklentiniz uyumluluk sorunları yük veya yükleme sırasında varsa, bunlar dosya veya kayıt defteri erişim ile ilgili sorunlar için ilişkili. Kullanım [işlem İzleyicisi](/sysinternals/downloads/procmon) veya oturum ve sorunu belirlemeye yardımcı olmak için çalışma ortamını karşı davranışı karşılaştırmak için benzer bir hata ayıklama aracı.
