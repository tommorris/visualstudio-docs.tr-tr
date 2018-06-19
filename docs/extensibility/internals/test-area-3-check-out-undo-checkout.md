---
title: 'Test alanı 3: Onay dışarı kullanıma almayı geri | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- source control plug-ins, checkout
- source control plug-ins, undo checkout
- source control [Visual Studio SDK], checking out
- source control [Visual Studio SDK], undo checkout
ms.assetid: ce00c5a5-d472-4f45-8776-d77a1fbe9d37
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: 5d769fdc52ac92053c258a3f82fa53cec5c56fa7
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/16/2018
ms.locfileid: "31134971"
---
# <a name="test-area-3-check-outundo-checkout"></a>Test alanı 3: Kullanıma / kullanıma almayı geri al
Bu kaynak denetimi eklenti test alanını sürüm deposu düzenleme ve dönüştürülüyor öğelerinden kapsayan **kullanıma** ve **geri ödeme** komutları.  
  
 **Kullanıma**: işaretleri sürüm deposu içindeki bir öğeyi, teslim olarak değiştirir okuma/yazma için yerel bir kopya.  
  
 **Kullanıma almayı geri al**: sürüm deposu iade gibi bir öğeyi işaretler, yerel kopyası (Seçenekler) bağlı olarak kullanıma önce durumuna geri döner.  
  
## <a name="command-menu-access"></a>Komut menü erişimi  
 Aşağıdaki [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] tümleşik geliştirme ortamı menü yolları test çalışmaları kullanılır.  
  
##### <a name="check-out"></a>Kontrol etme:  
  
-   **Dosya**, **kaynak denetimi**, **kullanıma**.  
  
-   **Dosya**, **kullanıma**.  
  
-   Kısayol menüsünde **kullanıma**.  
  
-   Kullanıma almayı geri al: **dosya**, **kaynak denetimi**, **geri ödeme**.  
  
## <a name="common-expected-behavior"></a>Ortak beklenen bir davranış  
  
-   İşlemi kullanıma sonra hedef dosyalar ve/veya klasörleri sürüm Mağazası'nda kullanıma olarak işaretlenir.  
  
-   Sürüm deposu checkout için doğru kullanıcı öznitelikleri.  
  
-   Kullanıma alma tarihi ve saati (kullanıcının ayarları) doğru.  
  
## <a name="test-cases"></a>Test çalışmaları  
 Belirli test çalışmaları Checkout/geri ödeme test alanı için verilmiştir.  
  
### <a name="case-3a-check-out"></a>Case 3a: gözden geçirin  
 Bu bölüm kullanıma komutu işlemi üzerinde odaklanmıştır.  
  
|Eylem|Test adımları|Doğrulamak için beklenen sonuçları|  
|------------|----------------|--------------------------------|  
|Denetleme çıkışı özel (COE) istemci projesi|1.  Bir istemci projesi oluşturun.<br />2.  Çözümü kaynak denetimine ekleyin.<br />3.  Tüm projeyi özel olarak denetleyin (**dosya**, **kullanıma**).|Kullanıma oluşur.|  
|Bir dosya sistemi veya yerel IIS Web projesi (COE) özel kullanıma denetleyin|1.  Ayarlama paylaşımında dosyasına Web sunucusu bağlantısı **Araçları**, **seçenekleri**, **projeleri**, **Web ayarları**.<br />2.  Bir Web projesi oluşturun.<br />3.  Çözümü kaynak denetimine ekleyin.<br />4.  Tüm projeyi özel olarak denetleyin (**dosya**, **kaynak denetimi**, **kullanıma**).|Kullanıma oluşur.|  
|Çözüm Öğeleri bir çözümde (diğer dosyaları işlemek için yeni yöntemi) göz atın|1.  Boş bir çözüm oluşturun.<br />2.  Çözümü kaynak denetimine ekleyin.<br />3.  Çözüm denetleyin.<br />4.  Birkaç çözüm öğeleri ekleyin.<br />5.  Yeni eklenen tüm öğelerde denetleyin.<br />6.  Birden çok çözüm öğeleri seçin.<br />7.  Seçili öğeleri kullanıma (kısayol menüsünde **kullanıma**).|Seçili dosyaları teslim alınır.|  
|Denetleme çıkışı yerel (test altındaki eklenti bu özelliği destekliyorsa) sürümü|1.  Kullanıcı 1: bir istemci projesi oluşturun.<br />2.  Kullanıcı 1: kaynak denetimine çözüm ekleyin.<br />3.  2. kullanıcı: çözümü kaynak denetiminden başka bir konuma açın.<br />4.  Kullanıcı 2: bir dosyayı denetleyin.<br />5.  2. kullanıcı: dosyasını değiştirin.<br />6.  2. kullanıcı: dosyasını denetleyin.<br />7.  Kullanıcı 1: dosyanın yerel sürümünü denetleyin (denetleyin **yerel sürümü kullanıma** seçeneğinde Gelişmiş **kullanıma** iletişim kutusu).|Dosyanın yerel sürümünü kullanıma alınmış.<br /><br /> Kullanıcı 2 değişikliklerinden kullanıcı 1 dosyasına uygulanmaz.|  
  
### <a name="case-3b-disconnected-check-out"></a>Case 3b: kullanıma bağlantısı kesildi  
 Bağlantısı kesilmiş modunda çalışırken, kullanıcıların belirli bir düzeyde doğrudan sürüm deposu için bağlı olmayan sürekli kaynak denetimi desteği sağlar. Bu kayıtlı çözüm ve projeleri ilgili tüm bilgileri yerel olarak önbelleğe alarak gerçekleştirilir.  
  
 Özel kullanıma alma işlemleri, yalnızca kaynak denetim deposunu bağlıyken oluşabilir. Paylaşılan kullanıma alma işlemleri, bağlantısı kesilmiş veya bağlı olup olmadığını herhangi bir zamanda ortaya çıkabilir. Bu nedenle, sürüm Mağazası'ndan yalnızca kesildiğinde **çıkışı denetleyin paylaşılan** (COS komut etkin). Bağlı değilken **geri ödeme** eski sürüm kullanıcı tarafından yapılan değişiklikleri değiştirmek için alınamadığından devre dışıdır.  
  
 Kullanıcı sürüme bağlandığında depolamak, tüm kayıtlı çözümlerinin checkout durumlarını ve projeleri eşitlenir. Bu kullanıcının gerçekleştirdiği kullanıma için gerekli güncelleştirmeleri deposuna yapar. Eşitleme gerçekleştirilmedi sonra kullanıcı (bağlı) normal şekilde çalışmaya devam edebilirsiniz.  
  
#### <a name="expected-behavior"></a>Beklenen bir davranış  
  
-   Kullanamazsınız **çıkışı özel olarak kontrol** sürüm Mağazası'ndan bağlı değilken komutu.  
  
-   Kullanamazsınız **geri ödeme** sürüm Mağazası'ndan bağlı değilken komutu.  
  
-   **Kullanıma paylaşılan** komut çalışır.  
  
|Eylem|Test adımları|Doğrulamak için beklenen sonuçları|  
|------------|----------------|--------------------------------|  
|Bağlı değilken bir dosyayı kullanıma ardından eşitleniyor için Bağlan|1.  Kaynak denetimini Değiştir iletişim kutusu kullanılarak denetimli bir proje kesin (**dosya**, **kaynak denetimi**, **değişiklik kaynak etkilenen sistemin tüm denetimini**l).<br />2.  Bir dosyayı gözden geçirin.<br />3.  (Uyarı iletişim kutusunda bağlantısı kesilmiş) kullanıma'ı tıklatın.<br />4.  Dosyayı düzenleyin.<br />5.  Kaynak denetimini Değiştir iletişim kutusunu kullanarak bağlanın.<br />6.  Düzenlenen dosyasının en son sürümünü alın.|Ortak beklenen bir davranış|  
  
### <a name="case-3c-query-editquery-save-qeqs"></a>Case 3c: Sorgu düzenleme/sorguyu kaydetmek (QEQS)  
 Kaynak denetimindeki öğeleri düzenlemeler, değişiklikleri izlenir ve kullanıcıların kolayca yardımcı olmak için kaydeder dosyalarına yönetin. "İade" denetimli bir öğe düzenlendiğinde QEQS denenen düzenleme durdurur ve düzenlemek için dosyayı kullanıma mı istediğini kullanıcıya sorar. Bağlı olarak **Araçları**, **seçenekleri** ayarları, kullanıcı olduğunu denetlemek için zorlanan düzenleme için dosyayı teslim veya bellekte bir kopyasını düzenlemek ve daha sonra kullanıma de izin verilir. Varsa kullanıcının **Araçları**, **seçenekleri** ayarı iletişim kutusunu kullanıma görüntülemek ve yalnızca onu denetlemek için ayarlı değil, sonra kullanıcı kendi düzenleme yapar, dosyayı otomatik olarak, mümkün olduğunda denetler.  
  
#### <a name="expected-behavior"></a>Beklenen bir davranış  
  
-   İşlemi kullanıma sonra hedef dosyalar ve/veya klasörleri sürüm Mağazası'nda kullanıma olarak işaretlenir.  
  
-   Sürüm deposu kullanıma için doğru kullanıcı öznitelikleri.  
  
-   Kullanıma tarih ve saat (kullanıcının ayarları) doğru.  
  
-   Hedef dosya veya klasörün yerel kopyasını yazılabilir.  
  
|Eylem|Test adımları|Doğrulamak için beklenen sonuçları|  
|------------|----------------|--------------------------------|  
|İade metin dosyasını düzenleyin|1.  Bir metin dosyasını içeren yeni bir proje oluşturun.<br />2.  Çözümü kaynak denetimine ekleyin.<br />3.  Ayarlama **Araçları**, **seçenekleri**, **kaynak denetimi**, **dosyaların salt okunur sırasında disk üzerinde düzenlenmesine izin ver** için işaretlenmemiş.<br />4.  Ayarlama **Araçları**, **seçenekleri**, **kaynak denetimi**, **kullanıma sor** içinde **işaretlendiğinde düzenlenendosyalar** birleşik giriş kutusu.<br />5.  Ayarlama **Araçları**, **seçenekleri**, **kaynak denetimi**, **kullanıma sor** içinde **işaretlendiğinde dosyalarıkaydedilir** birleşik giriş kutusu.<br />6.  Metin dosyasını düzenleyicisinde açın, yeni bir metin dosyasına yazın girişimi. Bu adım başarılı olursa, sonraki adıma geçin.<br />7.  Tıklatın **iptal** içinde **düzenleme için kullanıma** iletişim kutusu. Bu adım başarılı olursa, sonraki adıma geçin.<br />8.  Ayarlama **Araçları**, **seçenekleri**, **kaynak denetimi**, **dosyaların salt okunur sırasında disk üzerinde düzenlenmesine izin ver** için işaretlenmiş.<br />9. Proje dosyası düzenleyicide açın, yeni bir metin dosyasında yazın girişimi. Bu adım başarılı olursa, sonraki adıma geçin.<br />10. Tıklatın **Düzenle** içinde **düzenleme için kullanıma** iletişim kutusu. Bu adım başarılı olursa, sonraki adıma geçin.<br />11. Metin dosyasını düzenleyin ve kaydetmeyi deneyin.|`Result of step 6:`<br /><br /> Düzenleme iletişim kutusu görünür gözden geçirin.<br /><br /> `Result of step 7:`<br /><br /> Dosya değiştirilmez.<br /><br /> `Result of step 9:`<br /><br /> Düzenleme iletişim kutusu görünür gözden geçirin.<br /><br /> `Result of step 10:`<br /><br /> Bellek proje dosyasında düzenleyebilirsiniz.<br /><br /> `Result of step 11:`<br /><br /> Kaydet, kullanıma üzerinde Kaydet iletişim kutusu görünür.|  
|İade bir çözüm dosyasını düzenleyin|Önceki açıklanan adımları test ancak bir metin dosyasını değiştirerek yerine çözüm çözüm özelliklerini değiştirerek değişiklik yineleyin.|Önceki test aynı|  
|İade bir proje dosyası Düzenle|Önceki açıklanan adımları test ancak bir metin dosyasını değiştirerek yerine Proje proje özelliklerini değiştirerek değişiklik yineleyin.|Önceki test ile aynıdır.|  
  
### <a name="case-3d-silent-check-out"></a>3B case: Sessiz kullanıma  
 Bu senaryolar alt alan kapsar kullanıma nerede **kullanıma** iletişim kutusu, kullanıcı görünmez **Araçları**, **seçenekleri**, **kaynak denetim ayarları** .  
  
#### <a name="expected-behavior"></a>Beklenen bir davranış  
  
-   İşlemi kullanıma sonra hedef dosyalar ve/veya klasörleri sürüm Mağazası'nda kullanıma olarak işaretlenir.  
  
-   Sürüm deposu kullanıma için doğru kullanıcı öznitelikleri.  
  
-   Kullanıma tarih ve saat (kullanıcının ayarları) doğru.  
  
-   Hedef dosya veya klasörün yerel kopyasını yazılabilir.  
  
|Eylem|Test adımları|Doğrulamak için beklenen sonuçları|  
|------------|----------------|--------------------------------|  
|Bir dosya için sessiz alma|1.  Ayarlama **Araçları**, **seçenekleri**, **kaynak denetimi** için **checkout dosyaları otomatik olarak Düzenle**.<br />2.  Yeni bir proje sahip bir dosya oluşturun.<br />3.  Çözümü kaynak denetimine ekleyin.<br />4.  Dosyasını kontrol edin.|Dosya kullanıma sessizce (kullanıcı Arabirimi yok).|  
|Bir proje için sessiz alma|1.  Ayarlama **Araçları**, **seçenekleri**, **kaynak denetimi** için **checkout dosyaları otomatik olarak Düzenle**.<br />2.  Yeni bir proje oluşturun.<br />3.  Çözümü kaynak denetimine ekleyin.<br />4.  Projeyi denetleyin.|Dosya kullanıma sessizce (kullanıcı Arabirimi yok).|  
  
### <a name="case-3e-undo-check-out"></a>Case 3e: kullanıma almayı geri al  
 **Teslim almayı geri** durumu kontrol bir dosyanın iptal etmek ve dosyasında yapılan değişiklikleri iade önlemek için kullanılır.  
  
#### <a name="expected-behavior"></a>Beklenen bir davranış  
  
-   Kullanıcının varsayılan temel **yerel sürümünü denetleme** ayarı. Out yerel sürümünü denetlemek kullanıcı tarafından seçilir, ardından kullanıma almayı geri al için her zaman kullanıma sürümüne geri dönmek için varsayılandır.  
  
-   Simgeleri geri almayı kabul bağlı **Çözüm Gezgini** etkilenen güncelleştirilmiş dosyaları ve öğe kaldırılır **Bekleyen İadeler** penceresi.  
  
|Eylem|Test adımları|Doğrulamak için beklenen sonuçları|  
|------------|----------------|--------------------------------|  
|Özel olarak kullanıma alınmış tek bir dosya kullanıma almayı geri al|1.  Bir istemci projesi oluşturun.<br />2.  Çözümü kaynak denetimine ekleyin.<br />3.  Bir dosyanın özel olarak denetleyin.<br />4.  Dosyasını değiştirin.<br />5.  Kullanıma almayı geri al (**dosya**, **kaynak denetimi**, **geri ödeme**).|Ortak beklenen davranıştır.|  
|Paylaşılan denetlenir tek bir dosya kullanıma almayı geri al|1.  Bir istemci projesi oluşturun.<br />2.  Çözümü kaynak denetimine ekleyin.<br />3.  Paylaşılan bir dosyalarını inceleyin.<br />4.  Dosyasını değiştirin.<br />5.  Kullanıma almayı geri al (**dosya**, **kaynak denetimi**, **geri ödeme**).|Ortak beklenen davranıştır.|  
|Proje dosyaları ekledikten sonra bir proje kullanıma almayı geri al|1.  Yeni bir proje oluşturun ve kaynak denetimine ekleyin.<br />2.  Projeyi denetleyin.<br />3.  Bir dosya projeye ekleyin.<br />4.  Proje kullanıma almayı geri alın.|Çözüm Gezgini'nde projeye eklenen dosya kaldırılır.<br /><br /> Proje artık kullanıma alınmış.|  
|Projeden dosyaları sildikten sonra bir proje kullanıma almayı geri al|1.  Yeni bir proje oluşturun ve kaynak denetimine ekleyin.<br />2.  Projeyi denetleyin.<br />3.  Bir dosyayı projeden silin.<br />4.  Proje kullanıma almayı geri alın.|Silinen dosya, Çözüm Gezgini'nde projeye altında görünür.<br /><br /> Proje artık kullanıma alınmış.|  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Kaynak Denetimi Eklentileri için Test Kılavuzu](../../extensibility/internals/test-guide-for-source-control-plug-ins.md)