---
title: İş Akışı Tasarımcısı'nda hata iletileri | Microsoft Docs
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- WFDErrorMessages.UI
- System.Activities.Presentation.ErrorActivity.UI
- System.Activities.Presentation.View.ErrorView.UI
ms.assetid: 4d8bbc2e-34fc-477f-9140-4adfd70c34a0
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: f4deecb6617e85263abc5eaad11dd829abecb05d
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/16/2018
---
# <a name="error-messages-in-workflow-designer"></a>İş Akışı Tasarımcısı'nda hata iletileri
Bu konu Windows iş akışı Tasarımcısı ile çalışırken karşılaşılan hata iletileri türleri açıklanmaktadır.

## <a name="situations-in-which-errors-in-the-workflow-designer-occur"></a>Hangi iş akışı Tasarımcısı'nda hatalar ortaya durumları
 Hataları [!INCLUDE[wfd2](../workflow-designer/includes/wfd2_md.md)] aşağıdaki durumlarda oluşur:

1.  Bir ifadede bir hata var.

2.  Doğrulama kısıtlamaları etkinliğin memnun değil.

3.  Bir etkinliğin yüklemek başarısız olmasına neden XAML dosyasındaki hataları vardır.

4.  İş akışını yüklemek başarısız olmasına neden XAML dosyasındaki hataları vardır.

 Geçersiz ifadeleri ve memnun doğrulama kısıtlamaları iş akışını oluşturmak başarısız olmasına neden olmaz. İş akışınızı oluşturma başarılı olur, ancak bir <xref:System.Activities.InvalidWorkflowException> çalışma zamanında atılır. XAML dosyada hatalar varsa derleme başarısız oluyor.

 İçinde [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)], bir iş akışı yüklendiğinde, hataları görüntülenen **hata listesi**. Hatanın kaynak etkinlik gitmek için hatayı çift tıklatın **hata listesi**.

### <a name="expression-errors"></a>İfade hataları
 Geçersiz bir ifade, kırmızı bir daire ifade yanındaki beyaz ünlem işaretiyle gösterilir. Bu simgenin üzerine gelerek veya onları hatanın kaynağını tanımlayan bir araç ipucu olarak görüntülenir. İçinde [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)], ifade kullanarak hatanın kaynağı altını çizer satırı görüntülemek için tıklatın. Çizgili metin görüntüler gelerek veya onları hatanın kaynağını tanımlayan bir araç ipucu.

### <a name="activity-validation-errors"></a>Etkinlik doğrulama hataları
 Doğrulama kısıtlamaları etkinliğin memnun değil, kırmızı bir daire beyaz ünlem işaretiyle etkinliği sağ üst köşesinde görüntülenir. Bu simgenin üzerine gelerek veya onları hatanın kaynağını tanımlayan bir araç ipucu olarak görüntülenir.

### <a name="xaml-load-errors"></a>XAML yükleme hataları
 Yüklemek bir etkinlik başarısız olduğunda metinle "etkinliği XAML hatalar nedeniyle yüklenemedi" kırmızı kutu görüntülenir. Bu genellikle, etkinliğin türü çözümlenemedi oluşur. Geçersiz Etkinlik Tasarımcısı'nda kırmızı kutu seçip silerek silinebilir.

### <a name="workflow-load-errors"></a>İş akışı yükleme hataları
 Yüklemek bir iş akışı başarısız olduğunda, "Belgenizi sorunlarla karşılaştı iş akışı Tasarımcısı" metin Tasarımcı yüzeyine yüklemek bir iş akışı hatasına neden oldu özel durum bilgileri ile birlikte görüntülenir. Bu genellikle, XAML dosyası ayrıştırılamıyor oluşur.