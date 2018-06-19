---
title: JavaScript kullanarak Windows çalışma zamanı uygulamaları için hata kodları | Microsoft Docs
ms.custom: ''
ms.date: 05/10/2017
ms.prod: windows-client-threshold
ms.reviewer: ''
ms.suite: ''
ms.technology:
- javascript
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- JavaScript, Windows Runtime error codes
- VS.WebClient.Help.APPHOST9601
- VS.WebClient.Help.APPHOST9602
- VS.WebClient.Help.APPHOST9603
- VS.WebClient.Help.APPHOST9604
- VS.WebClient.Help.APPHOST9605
- VS.WebClient.Help.APPHOST9606
- VS.WebClient.Help.APPHOST9607
- VS.WebClient.Help.APPHOST9608
- VS.WebClient.Help.APPHOST9610
- VS.WebClient.Help.APPHOST9611
- VS.WebClient.Help.APPHOST9613
- VS.WebClient.Help.APPHOST9614
- VS.WebClient.Help.APPHOST9615
- VS.WebClient.Help.APPHOST9616
- VS.WebClient.Help.APPHOST9617
- VS.WebClient.Help.APPHOST9618
- VS.WebClient.Help.APPHOST9619
- VS.WebClient.Help.APPHOST9620
- VS.WebClient.Help.APPHOST9623
- VS.WebClient.Help.APPHOST9624
- VS.WebClient.Help.APPHOST9626
ms.assetid: 4c6d4e90-602a-4b56-ae74-3458929da442
caps.latest.revision: 1
author: erikadoyle
ms.author: edoyle
manager: jken
ms.openlocfilehash: 89b91a3246d0a6e2980459c2c35c7361168bccd4
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2017
ms.locfileid: "24792248"
---
# <a name="error-codes-for-windows-runtime-apps-using-javascript"></a>JavaScript kullanarak Windows çalışma zamanı uygulamaları için hata kodları
JavaScript kullanarak Windows çalışma zamanı uygulamaları geliştirirken Microsoft Visual Studio Konsolu tarafından görüntülenen hata kodları aşağıda verilmiştir.
  
Hata | Açıklamalar
----- | -------
APPHOST9601: "yüklenemiyor *remoteURI*. Bir uygulama Uzak web içeriği yerel bağlamında yüklenemiyor." | Web bağlamında izin verilen hakkında daha fazla bilgi için bkz: [özellikler ve kısıtlamalar bağlamı ile](https://msdn.microsoft.com/en-us/library/windows/apps/xaml/hh465373.aspx).
APPHOST9602: "'javascript:' geçersiz bir öznitelik değeri olan ve yok sayılacak. Kullanmayan ' javascript:' yerel bağlamdaki URI'ler. " | Güvenlik nedenleriyle kullanamazsınız ' javascript:' yerel bağlamdaki URI. Yerel bağlamında izin verilen hakkında daha fazla bilgi için bkz: [özellikler ve kısıtlamalar bağlamı ile](https://msdn.microsoft.com/en-us/library/windows/apps/xaml/hh465373.aspx).
APPHOST9603: "sınıf kimliği olan ActiveX Eklenti yüklenemiyor *ClassID*.  Uygulamaları ActiveX denetimlerini yüklenemiyor." | JavaScript kullanarak Windows çalışma zamanı uygulamaları özel Microsoft ActiveXcontrols desteklemez. UI denetim gerekiyorsa, bir standart web denetimi denetimler kitaplığı kullanabilir veya kendi özel denetim oluşturabilirsiniz. Özel mantık gerçekleştirmeniz gerekirse, bunun yerine özel bir Windows çalışma zamanı nesnesi oluşturun. Diğer HTML, CSS ve JavaScript farklar hakkında daha fazla bilgi için bkz: [HTML, CSS ve JavaScript özellikleri ve farkları](https://msdn.microsoft.com/en-us/library/windows/apps/xaml/hh465380.aspx).
APPHOST9604: "için gidemezsiniz *URI* çünkü bir geçersiz karakter kodlamasını kullanır.  Bir uygulamayı yalnızca UTF8 olarak kodlanmış dosyalar için gidebilirsiniz." | Tüm HTML, JavaScript ve Windows çalışma zamanı tarafından erişilen CSS 8 bit Unicode dönüştürme biçimi (UTF-8) kodlanmış olmalıdır. Diğer HTML, CSS ve JavaScript farklar hakkında daha fazla bilgi için bkz: [HTML, CSS ve JavaScript özellikleri ve farkları](https://msdn.microsoft.com/en-us/library/windows/apps/xaml/hh465380.aspx).
APPHOST9605: "için gidemezsiniz *Hedefuri* gelen *sourceURI* hedef daha yüksek güvenlik bölgesinde URI'si olduğundan. Bölgeden alt güvenliği ile bir bölgeye ile daha yüksek güvenlik sürece bir web içeriği URI yerel bir bağlamı URI gezinme ve MSApp.addPublicLocalApplicationUri yöntemiyle yerel bağlam URI kayıtlı gidemezsiniz." | Daha fazla bilgi için bkz: [MSApp.addPublicLocalApplicationUri](https://msdn.microsoft.com/en-us/library/windows/apps/xaml/hh465759.aspx).
APPHOST9606: "yüklenemiyor *URI* çünkü bir HTTP bağlantısı kullanır ve ms-https-bağlantıları-yalnızca meta öğesi yok. Ms https-bağlantıları-salt meta öğesi kullandığınızda yalnızca HTTPS bağlantılarına izin verilir. Bir HTTPS bağlantısı kullanabilir veya güvenli bir bağlantı ihtiyaç duymuyorsanız meta öğeyi kaldırın." | Daha fazla bilgi için bkz: [bir HTTPS bağlantısı gerektirecek şekilde nasıl](https://msdn.microsoft.com/en-us/library/windows/apps/xaml/hh452771.aspx).
APPHOST9607: "uygulama URI'de başlatamazlar *URI* bu hata nedeniyle: *failureCode*." | Bu hatanın sık karşılaşılan nedenleri şunlardır eksik kaynak ya da geçersiz bir dosya.
APPHOST9608: "uygulamasına gidin uygulanamadı hakkında: Bu hata nedeniyle boş sayfa: *errorCode*." | 
APPHOST9610: "uygulama bir özel hata sayfasına gitmek hazırlanırken bir hata bulundu: *errorCode*." |
APPHOST9611: "uygulamasına bir özel hata sayfası için bu hata nedeniyle gidin uygulanamadı: *errorCode*." |
APPHOST9613: "uygulamasına gidin uygulanamadı * URI * bu hata nedeniyle: *errorCode*." | 
APPHOST9614: "istenen IFRAME belgede *requestedDocMode* belge modu, ancak sistem zorlar *currentDocMode* belge modu. IFRAME kullanacağı *currentDocMode* belge modu. " | Uzak web içeriği görüntüleme hakkında daha fazla bilgi için bkz: [dış web sayfalarına bağlanmak nasıl](https://msdn.microsoft.com/en-us/library/windows/apps/xaml/hh780594.aspx).
APPHOST9615: "uygulama dosyasını karşıdan yükleyemiyor *URI* program aracılığıyla yerel bağlamı dışında çağrıldı çünkü." | Web içeriği içeriğinde program aracılığıyla dosya indirme denediğinde oluşur.
APPHOST9616: "Bu URI coğrafi konuma API'leri kullanamazsınız.  Coğrafi konuma API'leri paketinin parçası olan veya bildirim ApplicationContentUris öğesinde bulunan bir URI çağrılabilir." | Web bağlamında izin verilen hakkında daha fazla bilgi için bkz: [özellikler ve kısıtlamalar bağlamı ile](https://msdn.microsoft.com/en-us/library/windows/apps/xaml/hh465373.aspx).
APPHOST9617: "Bu URI Pano API'leri kullanamazsınız.  Pano API'leri paketinin parçası olan veya bildirim ApplicationContentUris öğesinde bulunan bir URI çağrılabilir." | Web bağlamında izin verilen hakkında daha fazla bilgi için bkz: [özellikler ve kısıtlamalar bağlamı ile](https://msdn.microsoft.com/en-us/library/windows/apps/xaml/hh465373.aspx).
APPHOST9618: "Bu URI window.close kullanamazsınız.  Window.close yöntemi ile bir ms-appx URI şeması ile yüklenen paket içeriğini çağrılabilir." | Web bağlamında izin verilen hakkında daha fazla bilgi için bkz: [özellikler ve kısıtlamalar bağlamı ile](https://msdn.microsoft.com/en-us/library/windows/apps/xaml/hh465373.aspx).
APPHOST9619: "uygulama için gidemezsiniz *URI* web içerik sayfasında uygulamanın üst düzey belge olamayacağı için. IFRAME sayfasında yerine yükleyin." | Üst düzey sayfanızı uzak bir web sayfasına gidilemiyor ancak uygulamanızı bir web sayfasında görüntüleyebilirsiniz bir [IFRAME](https://msdn.microsoft.com/en-us/library/ms535258(v=vs.85).aspx). Uzak web içeriği görüntüleme hakkında daha fazla bilgi için bkz: [dış web sayfalarına bağlanmak nasıl](https://msdn.microsoft.com/en-us/library/windows/apps/xaml/hh780594.aspx).
APPHOST9620: "Bu uygulama bir HTTP bağlantısı kullanılan ve ms-https-bağlantıları-yalnızca meta öğesi mevcut olduğundan kapatıldı. Ms https-bağlantıları-salt meta öğesi kullandığınızda yalnızca HTTPS bağlantılarına izin verilir. Bir HTTPS bağlantısı kullanabilir veya güvenli bir bağlantı gerektirmeyen meta öğesi kaldırın." | Daha fazla bilgi için bkz: [bir HTTPS bağlantısı gerektirecek şekilde nasıl](https://msdn.microsoft.com/en-us/library/windows/apps/xaml/hh452771.aspx).
APPHOST9623: "uygulama çözümleyemedik *url* bu hata nedeniyle: *errorCode*." | Bu hatanın ortak bir nedeni eksik bir dosyadır.  
APPHOST9624: "uygulamayı yüklemek için komut dosyası kullanamazsınız *url* url için başka bir uygulama URL'si başlatılır. Yalnızca doğrudan kullanıcı etkileşimi başka bir uygulama başlatabilirsiniz." | Uygulamaların diğer uygulamalar doğrudan başlatılamıyor. Uygulamayı belirli sözleşmeleri uygular, diğer uygulamalar kullanıcı tarafından başlatılabilir. Daha fazla bilgi için bkz: [uygulama sözleşmeleri ve uzantıları](https://msdn.microsoft.com/en-us/library/windows/apps/xaml/hh464906.aspx).
APPHOST9626: "kaynak dosyasını doğrudan bir başvuru `ms-appx://1d33240b-0b00-40e4-a416-a4750c48787f/ja-jp\images\logo.scale-140.png` algılandı. Bu başvuru hata ayıklama ortamı dışında kullanıldığında hatalarına neden oluyor." | Dosya yolunu nedeniyle `logo.scale-140.png`, bu PNG dosyası yerelleştirilmiş kaynaklar doğrudan başvurulamaz, hataya neden olan bir yerelleştirilmiş kaynak olarak kabul edilir. Bkz: [uygulamanızı (HTML) Genelleştirme](https://msdn.microsoft.com/en-us/library/windows/apps/xaml/hh465006.aspx) bu dosyayı bir dil kaynak olarak kullanmak istiyorsanız. Aksi takdirde, sorunlu dizini yeniden adlandırmayı deneyin.
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Windows çalışma zamanı JavaScript kullanma](../jswinrt/using-the-windows-runtime-in-javascript.md)