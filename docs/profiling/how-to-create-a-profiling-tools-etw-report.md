---
title: 'Nasıl yapılır: profil oluşturma araçları ETW raporu oluşturma | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-debug
ms.topic: conceptual
ms.assetid: bf5547b3-f6c7-4989-9d47-2fe4f1261444
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 06877736e2672b6eb1f58c6ea606c701f84d4719
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/16/2018
---
# <a name="how-to-create-a-profiling-tools-etw-report"></a>Nasıl yapılır: Profil Oluşturma Araçları ETW Raporu Oluşturma
Olay izleme için Windows (ETW) raporu bir performans oturumda kaydedilir ETW olayları listeler [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] profil oluşturma araçları. ETW verilerini bir ikili (.etl) dosyasında toplanır. Bu rapor hakkında daha fazla bilgi için bkz: [olay izleme için Windows (ETW) raporu](../profiling/event-tracing-for-windows-etw-report.md).  
  
> [!NOTE]
>  Arabirimdeki ETW raporları görüntüleyemez [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)].  
  
-   Arabirimi kullanarak ETW veri toplama hakkında bilgi için [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)], bkz: [nasıl yapılır: toplamak olay Windows için izleme (ETW) verileri](../profiling/how-to-collect-event-tracing-for-windows-etw-data.md).  
  
-   Bir komut isteminden ETW veri toplama hakkında daha fazla bilgi için bkz: [VSPerfCmd](../profiling/vsperfcmd.md) ve [olayları](../profiling/events-vsperfcmd.md).  
  
 Kullanarak ETW raporu oluşturma **VSReport / özeti: etw** komutu. ETW verilerini içeren .etl profil oluşturma veri (.vsp veya .vsps) dosyası ile aynı dizinde olmalıdır. Varsayılan olarak, rapor bir virgülle ayrılmış değer (.csv) dosyası olarak oluşturulur. Daha fazla bilgi için bkz: [VSPerfReport](../profiling/vsperfreport.md).  
  
### <a name="to-generate-an-etw-report"></a>ETW raporu oluşturmak için  
  
-   İçinde bir **komut istemi** penceresinde aşağıdaki komutu yazın:  
  
     *ToolsPath* **VSPerfReport** *VSPFile***/Summary:ETW [/ XML]**   
  
    |||  
    |-|-|  
    |*ToolsPath*|Profil oluşturma araçları yardımcı programı yolu. Daha fazla bilgi için bkz: [komut satırı araçları yolunu belirtme](../profiling/specifying-the-path-to-profiling-tools-command-line-tools.md).|  
    |*VSPFile*|Profil oluşturma veri (.vsp veya .vsps) dosyası. Tam ve kısmi yollar kabul edilir.|  
    |Xml|XML'de biçimlendirilmiş bir rapor oluşturur.|