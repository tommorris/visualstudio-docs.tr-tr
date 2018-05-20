---
title: C++ kaynak dosya ve üstbilgi dosyası arasındaki bağımlılıkları bakın
ms.date: 05/16/2018
ms.topic: conceptual
author: gewarren
ms.author: gewarren
manager: douge
ms.prod: visual-studio-dev15
ms.technology: vs-ide-modeling
ms.workload:
- multiple
ms.openlocfilehash: d274241700dfdac393544f554f7025ea4d0bcb46
ms.sourcegitcommit: 209c2c068ff0975994ed892b62aa9b834a7f6077
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/17/2018
---
# <a name="code-maps-for-c-projects"></a>C++ projeleri için kod eşlemeleri

C++ projeleri için daha kapsamlı eşlemeleri oluşturmak isterseniz, Gözat bilgi derleyici seçeneği ayarlayın (**/FR**) o projelerde. Aksi durumda, bir ileti görüntülenir ve bu seçeneği ayarlamanızı ister. Seçerseniz **Tamam**, bu seçeneği yalnızca geçerli eşlemesi için ayarlar. Tüm sonraki eşlemeleri için iletisini gizlemek seçebilirsiniz.

Visual C++ projeleri içeren bir çözümü açtığınızda, IntelliSense veritabanını güncelleştirmek biraz zaman alabilir. Bu süre boyunca, üstbilgi için kod haritalarını oluşturmak mümkün olmayabilir (*.h* veya `#include`) IntelliSense veritabanı güncelleştirme tamamlanana kadar dosyaları. Visual Studio durum çubuğunda güncelleştirme ilerleme durumunu izleyebilirsiniz.

- Tüm kaynak dosya ve üstbilgi dosyası çözümünüzdeki arasındaki bağımlılıkları görmek için seçin **mimarisi** > **oluşturmak grafik dahil dosyaların**.

   ![Yerel kod için bağımlılık grafiği](../modeling/media/dependencygraphgeneral_nativecode.png)

- Şu anda açık dosya ile ilgili kaynak dosyaları ve başlık dosyaları arasındaki bağımlılıkları görmek için kaynak dosya veya üst bilgi dosyasını açın. Herhangi bir yere dosyası içindeki dosya kısayol menüsünü açın. Seçin **dosyaları Ekle grafiği oluşturmak**.

   ![Birinci düzey bağımlılık grafiğinin .h dosyası için](../modeling/media/dependencygraph_native_firstlevel.png)

## <a name="troubleshoot-code-maps-for-c-and-c-code"></a>C ve C++ kodu için kod haritalarını sorun giderme

Bu öğeler için C ve C++ kodu desteklenmez:

- Taban türleri üst hiyerarşiyi içeren eşlemeleri görünmüyor.

- Çoğu **Göster** menü öğeleri C ve C++ kodu için kullanıma sunulmaz.

C ve C++ kodu için kod haritalarını oluşturduğunuzda, bu sorunları ortaya çıkabilir:

|**Sorunu**|**Olası neden**|**Çözümleme**|
|---------------|------------------------|--------------------|
|Kod Haritası oluşturma başarısız oldu.|Çözümdeki hiçbir proje başarıyla oluşturulmadı.|Oluştu derleme hataları düzeltin ve harita yeniden oluşturun.|
|Kod eşlemesinden oluşturmaya çalıştığınızda Visual Studio yanıt veremez duruma **mimarisi** menüsü.|Program veritabanı (.pdb) dosyası bozulmuş olabilir.<br /><br /> .pdb dosyası; tür, yöntem ve kaynak dosya bilgileri gibi hata ayıklama bilgilerini depolar.|Çözümü yeniden oluşturun ve tekrar deneyin.|
|IntelliSense göz atma veritabanı için belirli ayarlar devre dışı bırakılır.|Visual Studio'da belirli IntelliSense ayarları devre dışı bırakılabilir **seçenekleri** iletişim kutusu.|Bunları etkinleştirmek için ayarları etkinleştirin.<br /><br /> Bkz: [seçenekler, metin düzenleyici, C/C++, Gelişmiş](../ide/reference/options-text-editor-c-cpp-advanced.md).|
|İleti **bilinmeyen yöntemleri** yöntemi düğümünde görünür.<br /><br /> Yöntemin adı çözümlenemediği için bu sorun oluşur.|İkili dosya temel konum değişikliği tablosuna sahip olmayabilir.|Aç **/FIXED:NO** bağlayıcı seçeneği.|
||Program veritabanı (.pdb) dosyası oluşturulmamış olabilir.<br /><br /> .pdb dosyası; tür, yöntem ve kaynak dosya bilgileri gibi hata ayıklama bilgilerini depolar.|Aç **/DEBUG** bağlayıcı seçeneği.|
||.pdb dosyasını beklenen konumda açamıyor veya bulamıyor.|.pdb dosyasının beklenen konumlarda var olduğundan emin olun.|
||Hata ayıklama bilgileri, .pdb dosyasından çıkarıldı.|Varsa **/PDBSTRIPPED** seçeneği bağlayıcı kullanıldı, bunun yerine tam .pdb dosyasını içerir.|
||Arayan bir işlev değildir ve ikili dosyada bir dönüştürücü ya da veri bölümünde bir işaretçidir.|Çağıran bir dönüştürücü olduğunda kullanmayı deneyin `_declspec(dllimport)` dönüştürücü önlemek için.|

## <a name="see-also"></a>Ayrıca bkz.

- [Kod haritaları ile bağımlılıkları eşleme](../modeling/map-dependencies-across-your-solutions.md)