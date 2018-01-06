---
title: "Test alanı 5: Kaynak denetimi değiştirme | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- source control [Visual Studio SDK], changing
- source control plug-ins, changing source control
ms.assetid: fdf09e00-108c-4d51-bbd5-72452d52a490
caps.latest.revision: "15"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload: vssdk
ms.openlocfilehash: ffe029ecf5839f03732a1e5162dd22da4fe0a18e
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/22/2017
---
# <a name="test-area-5-change-source-control"></a>Test alanı 5: Kaynak denetimini Değiştir
Bu kaynak denetimi eklenti test alanını kapsayan aracılığıyla kaynak denetimini değiştirme **değişiklik kaynak denetimi** komutu.  
  
 **Kaynak denetimi değiştirme** komutu, kullanıcı için dört temel işlevleri sağlar:  
  
-   **Bağlayın:**  
  
     Bir kullanıcının kurmak veya bir çözüm/proje ve sürüm deposu arasındaki kaynak denetimi bağlantıyı yeniden izin verir.  
  
-   **Bağlantı kesme:**  
  
     Bağlantı başına temelinde kaynak denetiminden bir proje/çözüm kaldırır.  
  
-   **Bağlan/bağlantısını kes:**  
  
 Bağlı veya çevrimdışı durumunu değiştirir alanı 3'te kapsanan denetimli çözümü. Daha fazla bilgi için bkz: [Test alanı 3: kullanıma / geri ödeme](../../extensibility/internals/test-area-3-check-out-undo-checkout.md).  
  
## <a name="command-menu-access"></a>Komut menü erişimi  
 Aşağıdaki [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] tümleşik geliştirme ortamı menü yolunu test çalışmaları kullanılır.  
  
 Kaynak denetimini Değiştir:**dosya**, **kaynak denetimi**, **değiştirmek kaynak denetimi**.  
  
## <a name="test-cases"></a>Test çalışmaları  
 Belirli test çalışmaları için şunlardır **değişiklik kaynak denetimi** test alanı komutu.  
  
### <a name="case-5a-bind"></a>Case 5a: bağlama  
 Bağ seçili projeler ve çözümler için kaynak kodu denetimi bilgisi eklemesine izin verir. Kullanıcı bir proje eklemek için bunlar kaynak denetiminde tanımlamak için genellikle sorulur. Kullanıcı bu işlemi (kaynak denetimine Ekle karşıtlığını) bir parçası olarak kaynak denetiminde yeni bir proje oluşturamazsınız.  
  
|Eylem|Test adımları|Doğrulamak için beklenen sonuçları|  
|------------|----------------|--------------------------------|  
|Boş bir konuma bağlama|1.  Bir proje oluşturun.<br />2.  Çözümü kaynak denetimine ekleyin.<br />3.  Açık **değişiklik kaynak denetimi** iletişim kutusu (**dosya**, **kaynak denetimi**, **değişiklik kaynak denetimi**).<br />4.  Tıklatın **bağlantısını**.<br />5.  Uyarı iletişim kutusu görüntülenirse, kabul edin.<br />6.  Tüm öğeleri seçin.<br />7.  Tıklatın **bağlama**.<br />8.  Kaynak Denetim deposunu boş bir konuma göz atın.<br />9. Tıklatın **Tamam** kapatmak için **değişiklik kaynak denetimi** iletişim kutusu.<br />10. Tıklatın **bu bağlamaların devam** onay iletişim kutusunda.<br />11. Tıklatın **Tamam** görünürse uyarı iletişim kutusunda.<br />12. Her şeyi denetleyin. Bu adım başarılı olursa, sonraki adıma geçin.<br />13. Çözüm kaynak denetiminden yeni bir konuma açın.|`Result from Step 12:`<br /><br /> Çözüm ve proje bağlı ve sürüm deposuna yeni hedef yazılamaz.<br /><br /> Çözüm ve proje dosyaları iade edilir.<br /><br /> Sürüm deposu proje hiyerarşisi diskteki proje klasör hiyerarşisini eşleşir.<br /><br /> `Result from Step 13:`<br /><br /> Tüm proje öğeleri indirilir.|  
|İstemci ile eşitlenmemiş konuma bağlama|1.  Bir proje oluşturun.<br />2.  Çözümü kaynak denetimine ekleyin.<br />3.  Proje ve çözüm tekrarı sürüm deposunda oluşturun (paylaşabilir ve kullanıyorsanız dal [!INCLUDE[vsvss](../../extensibility/includes/vsvss_md.md)]).<br />4.  Açık **değişiklik kaynak denetimi** iletişim kutusu (**dosya**, **kaynak denetimi**, **değişiklik kaynak denetimi**).<br />5.  Tüm bağlantı kesme.<br />6.  Tıklatın **Tamam** kapatmak için **değişiklik kaynak denetimi** iletişim kutusu.<br />7.  Yeniden **değişiklik kaynak denetimi** iletişim kutusu.<br />8.  Tümünü seçin.<br />9. Tıklatın **bağlama**.<br />10. Proje ve çözüm dallı konumuna göz atın (adımından, 3)<br />11. Tıklatın **Tamam** kapatmak için **değişiklik kaynak denetimi** iletişim kutusu.<br />12. Tüm öğeler için en son yinelemeli olarak alın.|Get gibi get önce aynı tamamlandıktan sonra dosya içeriği.|  
|İstemci ile eşitlenmiş konumuna bağlama|1.  Bir proje oluşturun.<br />2.  Çözümü kaynak denetimine ekleyin.<br />3.  Proje ve çözüm tekrarı sürüm deposunda oluşturun (paylaşabilir ve kullanıyorsanız dal [!INCLUDE[vsvss](../../extensibility/includes/vsvss_md.md)]).<br />4.  Sürüm deposu dallı projede dosyaları değiştirin.<br />5.  Açık **değişiklik kaynak denetimi** iletişim kutusu (**dosya**, **kaynak denetimi**, **değişiklik kaynak denetimi**).<br />6.  Tüm bağlantı kesme.<br />7.  Tıklatın **Tamam** kapatmak için **değişiklik kaynak denetimi** iletişim kutusu.<br />8.  Yeniden **değişiklik kaynak denetimi** iletişim kutusu.<br />9. Tümünü seçin.<br />10. Tıklatın **bağlama**.<br />11. Dallandırılmış için çözüm ve proje konuma göz atın.<br />12. Tıklatın **Tamam** kapatmak için **değişiklik kaynak denetimi** iletişim kutusu.<br />13. Uyarı iletişim kutusu görüntülenirse, kabul edin.<br />14. En son özyinelemeli tüm öğeler için alın.|Adım 4'te değiştirilen dosyalar da yerel olarak değiştirilir.|  
|Hiç kaynak denetimi altında olan çözüm bağlama|1.  Kaynak denetiminde bir boş klasör oluşturun.<br />2.  Bir istemci projesi oluşturun.<br />3.  Açık **değişiklik kaynak denetimi** iletişim kutusu (**dosya**, **kaynak denetimi**, **değişiklik kaynak denetimi**).<br />4.  Kaynak denetimi boş konumda çözümü bağlar.<br />5.  Tıklatın **Tamam** kapatmak için **değişiklik kaynak denetimi** iletişim kutusu.<br />6.  Tıklatın **bu bağlamaların devam** onay iletişim kutusunda.<br />7.  Tıklatın **Tamam** görünürse uyarı iletişim kutusunda.|Çözüm için kaynak denetimi eklenir.<br /><br /> Çözüm ve proje kullanıma.|  
|İptal bağlama|1.  Bir proje oluşturun.<br />2.  Çözümü kaynak denetimine ekleyin.<br />3.  Kaynak denetimini Değiştir iletişim kutusunu açın.<br />4.  Tüm bağlantı kesme.<br />5.  Tıklatın **Tamam** düğmesi iletişim kutusunu kapatın. Bu adım başarılı olursa, sonraki adıma geçin.<br />6.  Yeniden **değişiklik kaynak denetimi** iletişim kutusu.<br />7.  İlişkisiz bir konuma bağlayın.<br />8.  Tıklatın **iptal**.|`Result from Step 5:`<br /><br /> Artık kaynak denetimi altında bir çözümdür<br /><br /> `Result from Step 8:`<br /><br /> Çözümdür altında hala olmayan kaynak denetimi.|  
  
### <a name="case-5b-unbind"></a>Case 5b: bağlantı kesme  
 Projeler ve kendi çözümünü kaldırır kaynak kodu denetimi bilgisi bağlantısını kesmek. Etkilenen proje ve çözüm kullanıcı seçimi ve kaynak denetimi öğelerin nasıl eklendiği bir karışımını dayanır.  
  
|Eylem|Test adımları|Doğrulamak için beklenen sonuçları|  
|------------|----------------|--------------------------------|  
|Bir dosya sistemi veya yerel IIS Web projesi ve bir istemci projesi içeren çözüm bağlantı kesme|1.  Bir dosya sistemi veya yerel IIS Web projesi oluşturun.<br />2.  Çözümü kaynak denetimine ekleyin.<br />3.  Yeni bir istemci proje çözüme ekleyin.<br />4.  Denetleme çıkışı çözümün istenirse kabul edin.<br />5.  Açık **değişiklik kaynak denetimi** iletişim kutusu.<br />6.  Tıklatın **bağlantısını**.<br />7.  İletişim kutusunu kapatmak için **Tamam** 'ı tıklatın.<br />8.  Çözüm, proje, çözüm öğeleri, proje öğelerini denetleme girişiminde bulunuldu.|Çözüm ve projeleri kaynak denetiminde değildir.<br /><br /> Kaynak denetimi menü komutlarını görünmez.|  
|İptal bağlantı kesme|1.  Bir proje oluşturun.<br />2.  Çözümü kaynak denetimine ekleyin.<br />3.  Açık **değişiklik kaynak denetimi** iletişim kutusu.<br />4.  Tıklatın **tüm bağlantısını**.<br />5.  Tıklatın **iptal**.|Kaynak denetimi altında bir çözümdür.|  
  
### <a name="case-5c-rebind"></a>Case 5c: yeniden bağlayın  
 Yeniden bağlamasını birleşimidir yalnızca Ciltten Çıkar ve bağ — bir proje/daha önce kaynak denetimi altında ve ilişkisiz şeklindeydi çözümü yeniden bağlama işlemi.  
  
|Eylem|Test adımları|Doğrulamak için beklenen sonuçları|  
|------------|----------------|--------------------------------|  
|Çözüm ve projeleri kapatmadan rebind **değişiklik kaynak denetimi** iletişim kutusu|1.  Bir proje oluşturun.<br />2.  Çözümü kaynak denetimine ekleyin.<br />3.  Açık **değişiklik kaynak denetimi** iletişim kutusu.<br />4.  Tıklatın **bağlantısını**.<br />5.  Tüm satırları seçin.<br />6.  Tıklatın **bağlama**.<br />7.  Tıklatın **Tamam** kapatmak için **değişiklik kaynak denetimi** iletişim kutusu.<br />8.  Checkout istenirse kabul edin.|Çözüm ve proje kaynak denetimi altında olan.|  
|Proje yalnızca kapatmadan rebind **değişiklik kaynak denetimi** iletişim kutusu|1.  Bir proje oluşturun.<br />2.  Kullanarak kaynak denetimine yalnızca projeye ekleyin (Dosya -> kaynak denetimi -> kaynak denetimi için seçilen projeleri ekleyin.<br />3.  Kaynak denetimini Değiştir iletişim kutusunu açın.<br />4.  Yalnızca proje bağlantısını kesmek.<br />5.  Yalnızca proje bağlayın.|Çözüm denetlenmeyen kalır.<br /><br /> Proje denetimli kalır.|  
|Çözüm yalnızca kapatmadan rebind **değişiklik kaynak denetimi** iletişim kutusu|1.  Bir proje oluşturun.<br />2.  Yalnızca çözüm kullanarak kaynak denetimine ekleme (**dosya**, **kaynak denetimi**, **seçilen projelere kaynak denetimi ekleme**.<br />3.  Açık **değişiklik kaynak denetimi** iletişim kutusu.<br />4.  Yalnızca çözüm varsayılanın (kapatmayın **değişiklik kaynak denetimi** iletişim kutusu.)<br />5.  Yalnızca çözüm bağlayın.<br />6.  İletişim kutusunu kapatmak için **Tamam** 'ı tıklatın.<br />7.  Çözüm ve çözüm öğeleri çıkış (varsa) denetleyin|Çözüm denetimli kalır.<br /><br /> Proje denetlenmeyen kalır.|  
|Çözüm/project yalnızca aynı dizinde zaman yeniden bağlayın|1.  Bir proje oluşturun.<br />2.  Kullanarak kaynak denetimine yalnızca projeye ekleyin (**dosya**, **kaynak denetimi**, **seçilen projelere kaynak denetimi ekleme**.<br />3.  Çözümü kapatın.<br />4.  Yeni bir çözüm, en az iki projelerle oluşturun.<br />5.  Çözümü kaynak denetimine ekleyin.<br />6.  Kaynak denetiminden 1. adımda oluşturduğunuz projeye ekleyin.<br />7.  Çözüm checkout istenirse kabul edin.<br />8.  Çözümün tamamında denetleyin.<br />9. Açık **değişiklik kaynak denetimi** iletişim kutusu.<br />10. Eklenen projeden (6. adım) seçin ve tıklatın **Ciltten Çıkar**.<br />11. İletişim kutusunu kapatmak için **Tamam** 'ı tıklatın.<br />12. Kullanıma alma istenirse kabul edin.<br />13. Yeniden **değişiklik kaynak denetimi** iletişim kutusu.<br />14. Eklenen projeden (6. adım) seçin ve tıklatın **bağlama**.<br />15. Özgün konumu seçin.|Çözüm ve projeleri denetimli kalır.|  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Kaynak Denetimi Eklentileri için Test Kılavuzu](../../extensibility/internals/test-guide-for-source-control-plug-ins.md)