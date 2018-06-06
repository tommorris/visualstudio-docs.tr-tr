---
title: Windows (ETW) raporu için olay izleme | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology: vs-ide-debug
ms.topic: conceptual
helpviewer_keywords:
- Event tracing for Windows profiling report
- ETW profiling report
ms.assetid: 81e88162-b88a-40b6-8b85-a232c8096a47
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 22307143f0044c6a3816534add9fe285ce8a9fd4
ms.sourcegitcommit: 4cd4aef53e7035d23e7d1d0f66f51ac8480622a1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/05/2018
ms.locfileid: "34764462"
---
# <a name="event-tracing-for-windows-etw-report"></a>Olay izleme için Windows (ETW) raporu
Olay izleme için Windows (ETW) raporu bir performans oturumda kaydedilmiş ETW olayları listeler [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] profil oluşturma araçları. ETW verilerini bir ikili toplanan (. *etl*) dosyası.  
  
> [!NOTE]
>  ETW raporlarda görüntüleyemiyor [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] arabirimi.  
  
-   ETW profil oluşturma Araçları'ndan kullanarak toplama hakkında bilgi için [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] arabirim için bkz: [nasıl yapılır: toplamak olay Windows için izleme (ETW) verileri](../profiling/how-to-collect-event-tracing-for-windows-etw-data.md).  
  
-   Kullanarak ETW veri toplama hakkında bilgi için [VSPerfCmd](../profiling/vsperfcmd.md) komut satırı araçları Bkz [olayları](../profiling/events-vsperfcmd.md).  
  
-   Kullanarak ETW raporu oluşturma **VSReport / özeti: ETW** komutu. Daha fazla bilgi için bkz: [VSPerfReport](../profiling/vsperfreport.md).  
  
|Sütun|Açıklama|  
|------------|-----------------|  
|**zaman damgası**|Olay oluştuğunda tanımlar.|  
|**İşlem kimliği**|Olayı oluşturan işlem tanımlar.|  
|**İş parçacığı kimliği**|Olayı oluşturan iş parçacığı tanımlar.|  
|**Açıklama**|Olay sağlayıcısı tanımlar.|  
|**Türü**|Olay türünü tanımlar.|  
|**Özellikler**|Olay Özellikleri. Her olay parantez içine alınmış bir virgülle ayrılmış, ad-değer çiftidir.|