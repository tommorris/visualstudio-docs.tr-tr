---
title: 'Test alanı 8: Eklenti değiştirme | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- source control [Visual Studio SDK], switching plug-ins
- source control plug-ins, switching
ms.assetid: 01370792-b5da-4e46-9ce2-7dd326587141
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: 534bd9338181c5b682779b62a9c118a5ccaf8cda
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/16/2018
ms.locfileid: "31148866"
---
# <a name="test-area-8-plug-in-switching"></a>Test alanı 8: Eklenti değiştirme
[!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] Tümleşik geliştirme ortamı (IDE) eklentisi geçerli kaynak denetimi değiştirmek için kullanıcı arabirimi (UI) sahiptir. Bu test alan, hangi çözümün kaynak denetimi için kullanılacak eklentinin alma işlemi için test durumları sağlar.  
  
## <a name="command-menu-access"></a>Komut menü erişimi  
 Aşağıdaki [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] tümleşik geliştirme ortamı menü yolları test çalışmaları kullanılır.  
  
-   Eklenti geçerli kaynak denetimi: **Araçları** -> **seçenekleri** -> **kaynak denetimi** -> **eklentisi seçimi** .  
  
-   Değişiklik kaynak denetim bağlama: **dosya** -> **kaynak denetimi** -> **değişiklik kaynak denetimi**...  
  
## <a name="common-expected-behavior"></a>Ortak beklenen bir davranış  
 Kaynak denetimi için bir çözüm eklenti değiştirme Visual Studio çıkma veya çözümü yeniden mümkündür. Ayrıca, eklenti geçerli kaynak denetimi, bu çözüm yüklendiğinde bir çözüm tarafından kullanılan bir otomatik olarak değiştirir.  
  
## <a name="test-cases"></a>Test çalışmaları  
 Eklenti geçiş test alanı için belirli test durumları verilmiştir.  
  
### <a name="case-8a-automatic-change"></a>Case 8a: otomatik değiştirme  
  
#### <a name="expected-behavior"></a>Beklenen bir davranış  
 Kaynak denetimi altında bir çözüm kullanıcı yüklediğinde, çözüm otomatik olarak yüklenir ve uygun kaynak denetim eklentisi geçerli olarak seçilir.  
  
|Eylem|Test adımları|Doğrulamak için beklenen sonuçları|  
|------------|----------------|--------------------------------|  
|Otomatik kaynak denetim eklentisi değişikliği|1.  Select altında eklenti olarak geçerli test (**Araçları** -> **seçenekleri** -> **kaynak denetimi** -> **eklentisi Seçim**.)<br />2.  Yeni bir proje oluşturun.<br />3.  Çözümü kaynak denetimine ekleyin.<br />4.  Başka bir eklentiyi seçin (örneğin, [!INCLUDE[vsvss](../../extensibility/includes/vsvss_md.md)]).<br />5.  Yüklemeyi kaldırma çözümü isteğini kabul edin.<br />6.  Diskten çözümü kapatıp yeniden açın.|Çözüm açıldı.<br /><br /> Eklenti geçerli kaynak denetimi altında test eklentidir.|  
  
### <a name="case-8b-solution-based-change"></a>Case 8b: Çözüm tabanlı Değiştir  
  
#### <a name="expected-behavior"></a>Beklenen bir davranış  
 Çözüm değişti, ilişkili kaynak denetimi eklenti olabilir.  
  
|Eylem|Test adımları|Doğrulamak için beklenen sonuçları|  
|------------|----------------|--------------------------------|  
|Değişikliği bir çözüm eklentisi|1.  Select altında eklenti olarak geçerli test (**Araçları** -> **seçenekleri** -> **kaynak denetimi** -> **eklentisi Seçim**).<br />2.  Yeni proje ve çözüm oluşturun.<br />3.  Çözümü kaynak denetimine ekleyin.<br />4.  Kaynak denetiminden çözüm varsayılanın (kullanarak **değişiklik kaynak denetimi** iletişim kutusu).<br />5.  Başka bir eklentiyi seçin (örneğin, [!INCLUDE[vsvss](../../extensibility/includes/vsvss_md.md)]).<br />6.  Disk çözümden kaldırıldığında, yeniden yükleyin.<br />7.  Çözümü kaynak denetimine ekleyin.<br />8.  Kaynak denetiminden çözüm varsayılanın (kullanarak **değişiklik kaynak denetimi** iletişim kutusu).<br />9. Yeniden test altında eklenti'ı seçin.<br />10. Disk çözümden kaldırıldığında, yeniden yükleyin.<br />11. Özgün konuma çözümü bağlayın (kullanarak **değişiklik kaynak denetimi** iletişim kutusu).|Çözüm, seçili kullanarak kaynak denetimine eklenir eklentisi.|  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Kaynak Denetimi Eklentileri için Test Kılavuzu](../../extensibility/internals/test-guide-for-source-control-plug-ins.md)