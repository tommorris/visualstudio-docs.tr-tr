---
title: "FxCopCmd hataları | Microsoft Docs"
ms.custom: 
ms.date: 10/19/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- vs-ide-code-analysis
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- FxCopCmd errors
ms.assetid: bb614ed0-1b7c-4b56-99ae-da50ef6cfef9
caps.latest.revision: 
ms.author: gewarren
author: gewarren
manager: ghogen
ms.workload:
- multiple
ms.openlocfilehash: 48b082f5b00f260d2f8e2519a4551fab23dc1011
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/22/2017
---
# <a name="fxcopcmd-errors"></a>FxCopCmd Hataları
FxCopCmd önemli olması için tüm hataların dikkate almaz. FxCopCmd kısmi analiz gerçekleştirmek için yeterli bilgiye sahip oluştu analiz ve raporları hataları gerçekleştirir. Bir 32 bit tamsayı ise, hata kodu hataları karşılık gelen sayısal değerlerin Bitsel bir birleşimi içerir.  
  
 Aşağıdaki tabloda FxCopCmd tarafından döndürülen hata kodları açıklanmaktadır:  
  
|Hata|Sayısal değer|  
|-----------|-------------------|  
|Hiçbir hata|0x0|  
|Çözümleme hatası|0x1|  
|Kural özel durumları|0x2|  
|Proje yükleme hatası|0x4|  
|Derleme yükleme hatası|0x8|  
|Kural kitaplığı yükleme hatası|0x10|  
|İçeri aktarma rapor yükleme hatası|0x20|  
|Çıkış hatası|0x40|  
|Komut satırı anahtarı hatası|0x80|  
|Başlatma hatası|0x100|  
|Derleme başvuruları hata|0x200|  
|BuildBreakingMessage|0x400|  
|Bilinmeyen hata|0x1000000|  
  
 Çözümleme hatası için önemli hatalar döndürülür. Analiz tamamlanamadı belirtir. Uygun olduğunda, hata kodu önemli hatanın temel nedenini de içerir. Aşağıdaki koşullar önemli hatalar oluşturur:  
  
-   Analiz yetersiz girişi tarafından nedeniyle gerçekleştirilemedi.  
  
-   Analiz FxCopCmd tarafından işlenmemiş bir özel durum oluşturdu.  
  
-   Belirtilen proje dosyası bulunamadı veya bozuk olabilir.  
  
-   Output seçeneği belirtilmedi veya dosya yazılmadı.  
  
    > [!NOTE]
    >  FxCopCmd dönüş kodu "Hata bütünleştirilmiş koduna başvuruyor" kendisi tarafından 0x200 olan bir hata yerine bir uyarı. Bu dönüş kodu eksik dolaylı başvuru bulundu ancak FxCopCmd bunları işleyebilen gösterir. Bazı çözümleme sonuçlarını geçirildiğini olduğunu olasılığı olduğunu belirten bir uyarı var. Diğer dönüş kodu ile birleştirildiğinde "Hata bütünleştirilmiş koduna başvuruyor" dönüş kodu hata olarak göz önünde bulundurun.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Kod Çözümleme Uygulama Hataları](../code-quality/code-analysis-application-errors.md)