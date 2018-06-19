---
title: 'Test alanı 1: Kaynak denetimi bağlantısı için Aç ekleme | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- source control [Visual Studio SDK], adding and opening solutions
- source control plug-ins, adding and opening solutions
ms.assetid: 5b3b5b08-5e9b-41be-ac72-c63957faed22
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: 6e95ef13a3d8f7a61c53c9938564479adf362a2c
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/16/2018
ms.locfileid: "31134740"
---
# <a name="test-area-1-add-toopen-from-source-control"></a>Test alanı 1: Kaynak denetiminden Aç / ekleyin
Bu kaynak denetimi eklenti test çözümleri veya kaynak denetimindeki projeleri yerleştirme ve kaynak denetiminden alma alanı kapsar.  
  
## <a name="command-menu-access"></a>Komut menü erişimi  
 Aşağıdaki [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] tümleşik geliştirme ortamı menü yolları test çalışmaları kullanılır:  
  
-   İçin [!INCLUDE[vsvss](../../extensibility/includes/vsvss_md.md)], açık kaynak denetiminden: **dosya**, **açmak**, **proje**/**çözüm**; arama içinde[!INCLUDE[vsvss](../../extensibility/includes/vsvss_md.md)] konumu.  
  
-   Diğer kaynak denetimi için eklentiler, kaynak denetiminden açın: **dosya**, **kaynak denetimi**, **kaynak denetiminden açmak**.  
  
-   Kaynak denetimine ekleyin: **dosya**, **kaynak denetimi**, **kaynak denetim dosyası Çözüm Ekle**, **kaynak denetimi**, **Ekle Kaynak denetimi projelerine seçili**.  
  
-   Kısayol menüsü (Proje/çözüm) **kaynak denetimine Çözüm Ekle**.  
  
-   Kaynak denetiminden Ekle: **dosya**, **kaynak denetimi**, **kaynak denetiminden Proje Ekle**.  
  
-   İçin [!INCLUDE[vsvss](../../extensibility/includes/vsvss_md.md)], ekleme kaynağından denetimi de kullanılabilir **dosya**, **Ekle**, **mevcut proje**; arama içinde [!INCLUDE[vsvss](../../extensibility/includes/vsvss_md.md)] konumu.  
  
    > [!NOTE]
    >  Yerel bir dosya veya yerel bir IIS (web sunucusu) bir yolu, bu test kullanılabilir.  
  
## <a name="expected-behavior"></a>Beklenen bir davranış  
  
-   Her desteklenen proje türü için bir kullanıcı "için Ekle" ve "dan kaynak denetimi açın" olmalıdır.  
  
-   Karşılık gelen bir kaynak denetimi için bir proje eklendiğinde \< *ProjectName*> .vspscc dosyası (Proje ipucu) oluşturulur. Dışlama dosya listesi ve bağlantı bilgilerini içerir. Projeye özel bilgiler içerdiği için bu dosyayı silmeyin.  
  
-   Karşılık gelen bir kaynak denetimi için bir çözüm eklendiğinde \< *SolutionName*> .vssscc (üçlü S) dosyası oluşturulur. Metin dosyası bağlantı bilgilerini ve bir proje ipucu dosyasına benzer çıkarma dosya listesi içerir. Bu dosya geçicidir ve yalnızca kaynak denetimi veritabanında yok.  
  
-   Kaynak denetiminden bir çözüm açıldığında bir \< *SolutionName*> yalnızca kaynak denetimi veritabanında, varolan .vsscc (çift S) dosyası yerel olarak geçici bir dosya oluşturulur. Bu dosya çözüm bağlantısı klasöründen çözüm dosyasının yolunu içerir. Bu dosya geçicidir ve "Açık kaynak denetimi" işlemi tamamlandıktan sonra yerel kopyayı silinir.  
  
-   Bir proje için kaynak denetimi eklendikten sonra (kullanıma, Get vb.) üzerindeki tüm kaynak denetim eylemleri gerçekleştirebilirsiniz.  
  
## <a name="test-cases"></a>Test çalışmaları  
 Belirli test çalışmaları ekleme şunlardır / kaynak denetimi test alanından açın.  
  
### <a name="case-1a-add-solution-to-source-control"></a>Case 1a: kaynak denetimine Çözüm Ekle  
 Bu test çalışması çözümleri kaynak denetimine ekleme odaklanır.  
  
|Eylem|Test adımları|Doğrulamak için beklenen sonuçları|  
|------------|----------------|--------------------------------|  
|Kaynak denetimi için istemci projeyi içeren çözüme ekleyin|1.  Bir istemci projesi oluşturun.<br />2.  Kaynak Denetimine Çözüm Ekle (**dosya**, **kaynak denetimi**, **kaynak denetimine Çözüm Ekle**).|Kaynak denetimi için çözüm/proje eklendi.|  
|İçeren bir dosya sistemi veya yerel IIS Web projesinin kaynak denetimine Çözüm Ekle|1.  Bir dosya sistemi veya yerel IIS Web projesi oluşturma (Proje konumuna; işaret etmek için Gözat düğmesini kullanın ne tür bir Web projesi oluşturulması yolu belirler).<br />2.  Kaynak Denetimine Çözüm Ekle (**dosya**, **kaynak denetimi**, **kaynak denetimine Çözüm Ekle**).|Kaynak denetimi için çözüm/proje eklendi.|  
|İçeren bir uzak Site Web projesi kaynak denetimine Çözüm Ekle|1.  Bir uzak Site Web projesi oluşturun.<br />2.  Kaynak Denetimine Çözüm Ekle (**dosya**, **kaynak denetimi**, **kaynak denetimine Çözüm Ekle**).<br />3.  Tıklatın **Tamam** FrontPage erişim uyarı iletişim kutusunda.|Çözüm için kaynak denetimi eklendi.<br /><br /> Uzak Site proje kaynak denetimi altında değil. (Uzak Site projeleri kendi IIS sunucusundan denetlenmesi gerekir.)|  
|Bir tek proje çözümü kullanarak kaynak denetimine ekleme **seçilen projelere kaynak denetimi ekleme**.|1.  Bir tek proje çözümü oluşturun.<br />2.  Kaynak denetimi seçim olarak yalnızca çözüm ekleyin (**dosya**, **kaynak denetimi**, **seçilen projelere kaynak denetimi ekleme**). Bu adım başarılı olursa, sonraki adıma geçin.<br />3.  Kaynak denetimi seçim olarak Ekle projesine (**dosya**, **kaynak denetimi**, **seçilen projelere kaynak denetimi ekleme**).<br />4.  Tıklatın **Evet** aynı konuma projesi eklemek için.<br />5.  Tıklatın **kullanıma** içinde **Check Out For Edit** iletişim kutusu.|`Result from Step 2:`<br /><br /> Proje ve proje içindeki tüm dosyalar kullanıma alınmış kaynak denetim göstergesi sahip ve araç ipucu "Değil. kaynak denetimi altında" görüntüler.<br /><br /> `Result from Step 5:`<br /><br /> Proje ve çözüm dosya kaynak denetimi aynı klasörde olan.|  
|Kaynak denetimi için bir çözüm eklemeyi iptal|1.  Bir tek proje çözümü oluşturun.<br />2.  Proje ve çözüm için kaynak denetimi eklemeyi deneyin. Bu adım başarılı olursa, sonraki adıma geçin.<br />3.  Kaynak denetim sistemi olduktan sonra iptal edin.|`Result from Step 2:`<br /><br /> Yalnızca bir kez kümesi proje konumu kaynak denetimi iletişim kutusu görüntülenir.<br /><br /> `Result from Step 3:`<br /><br /> Proje iptal edilmiş ekleyin, proje/çözüm kaynak denetiminde değildir ve tüm hala kullanılabilir olan denetim menüleri kaynak ekleyin.|  
  
### <a name="case-1b-open-solution-from-source-control"></a>Servis talebi 1b. Kaynak denetiminden çözümü Aç  
 Bu test çalışması kaynak denetiminden çözümleri açarken odaklanır.  
  
|Eylem|Test adımları|Doğrulamak için beklenen sonuçları|  
|------------|----------------|--------------------------------|  
|Kaynak denetiminden istemci projeyi içeren bir çözüm açın|1.  Bir istemci projesi oluşturun.<br />2.  Çözümü kaynak denetimine ekleyin.<br />3.  Çözümü kapatın.<br />4.  Çözümü kaynak denetiminden yeni bir konuma açın.|Çözüm/proje kaynak denetiminden açıldı.|  
|Bir yerel ya da kaynak denetiminden IIS Web projesi içeren bir çözüm açın|1.  Bir yerel veya IIS Web projesi oluşturun.<br />2.  Çözümü kaynak denetimine ekleyin.<br />3.  Çözümü kapatın.<br />4.  Çözümü kaynak denetiminden yeni bir konuma açın.|Çözüm/proje kaynak denetiminden açıldı.|  
|Kaynak denetiminden bir uzak Site Web projesi içeren bir çözüm açın|1.  Bir uzak Site Web projesi oluşturun.<br />2.  Çözümü kaynak denetimine ekleyin. Bu adım başarılı olursa, sonraki adıma geçin.<br />3.  Çözümü kapatın.<br />4.  Çözümü kaynak denetiminden yeni bir konuma açın.|`Result from Step 2:`<br /><br /> Uzak Site Web kaynak denetimi altında değil.<br /><br /> `Result from Step 4:`<br /><br /> Çözüm kaynak denetiminden açıldı.<br /><br /> Uzak Site proje yüklendi, ancak kaynak denetimi altında değil.|  
  
### <a name="case-1c-add-solution-from-source-control"></a>Case 1c: kaynak denetiminden çözüme ekleyin  
 Bu test çalışması çözümleri kaynak denetiminden ekleme odaklanır.  
  
|Eylem|Test adımları|Doğrulamak için beklenen sonuçları|  
|------------|----------------|--------------------------------|  
|Boş çözüme ekleyin — tek proje çözümü|1.  Bir tek proje çözümü oluşturun.<br />2.  Çözümü kaynak denetimine ekleyin.<br />3.  Çözümü kapatın.<br />4.  İkinci bir boş çözüm oluşturun.<br />5.  Kaynak denetiminden önceden denetimli çözüme ekleyin (**dosya**, **kaynak denetimi**, **kaynak denetiminden Proje Ekle**).|Eklenen project görünür **Çözüm Gezgini** ve iade edildi.|  
|Tek proje çözümüyle ekleyin — tek proje|1.  Bir çözümü ile tek bir proje oluşturun.<br />2.  Çözümü kaynak denetimine ekleyin.<br />3.  Çözümü kapatın.<br />4.  İkinci bir boş çözüm oluşturun.<br />5.  Kaynak denetiminden önceden denetimli çözüme ekleyin (**dosya**, **kaynak denetimi**, **kaynak denetiminden Proje Ekle**).|Eklenen project görünür **Çözüm Gezgini** ve iade edildi.|  
|Çözüme ekleyin — kaynak denetimine seçime göre eklenen çözümü|1.  Bir çözüm sahip bir proje oluşturun.<br />2.  Yalnızca çözüm için kaynak denetimi seçimi olarak ekleyin. Bu adım başarılı olursa, sonraki adıma geçin.<br />3.  Çözümü kapatın.<br />4.  Yeni bir çözüm oluşturun.<br />5.  Kaynak denetiminden önceden denetimli çözüme ekleyin (**dosya**, **kaynak denetimi**, **kaynak denetiminden Proje Ekle**).|`Result from Step 2:`<br /><br /> Proje kaynak denetimi altında değil.<br /><br /> `Result from Step 5:`<br /><br /> İlk çözüm çözüm öğeleri olsaydı değil görünmesi için bunlar kaynak denetiminden eklenemez.<br /><br /> İlk çözüm projeden kullanılamaz olarak görünür.|  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Kaynak Denetimi Eklentileri için Test Kılavuzu](../../extensibility/internals/test-guide-for-source-control-plug-ins.md)