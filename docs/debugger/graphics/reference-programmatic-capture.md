---
title: "Başvuru (programlı yakalama) | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: ef60eb8d-1ac2-4e3a-9b4b-f6da0bdd9da8
caps.latest.revision: "5"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 899211452a776931e3d0d9742e499ed8ba78a652
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2017
---
# <a name="reference-programmatic-capture"></a>Başvuru (Programlı Yakalama)
Grafik tanılama yakalama özelliklerini programlı yakalama API aracılığıyla programlı denetime destekler. Bu API, geçiş ve iletiler grafik tanılama HUD (Head yukarı görüntüle) eklemek, başlatmak ve grafik günlük dosyalarını oluşturmak ve grafik bilgilerini yakalama için kullanabilirsiniz.  
  
## <a name="programmatic-capture-apis"></a>Programlı yakalama API'leri  
  
### <a name="classes"></a>Sınıflar  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[VsgDbg sınıfı](vsgdbg-class.md)|Üzerinden grafik tanılama uygulama bileşeninin program aracılığıyla denetlenir arabirimi temsil eder.|  
  
### <a name="preprocessor-symbols"></a>Önişlemci sembolleri  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[DONT_SAVE_VSGLOG_TO_TEMP](dont-save-vsglog-to-temp.md)|Grafik günlük dosyası için kullanıcının geçici dosyalar dizini kaydedilip kaydedilmediğini tarafından varlığını tanımlar.|  
|[VSG_DEFAULT_RUN_FILENAME](vsg-default-run-filename.md)|Grafik günlük dosyası varsayılan dosya adını tanımlar.|  
|[VSG_NODEFAULT_INSTANCE](vsg-nodefault-instance.md)|Varsayılan örneği olup olmadığını, varlığı tanımlayan `VsgDbg` sınıfı sağlanır.|  
  
## <a name="related-articles"></a>İlgili Makaleler  
  
|Başlık|Açıklama|  
|-----------|-----------------|  
|[Grafik bilgilerini yakalama](capturing-graphics-information.md)|Böylece kullanabileceğiniz DirectX tabanlı uygulamanızdan grafik bilgilerini yakalama gösterilmektedir [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] işleme sorunları tanılamak için grafik tanılama araçları.|  
|[Genel bakış](overview-of-visual-studio-graphics-diagnostics.md)|Grafik tanılama DirectX oyunları ve uygulamaları işleme hataları hata ayıklama nasıl yardımcı olabileceğini gösterir.|