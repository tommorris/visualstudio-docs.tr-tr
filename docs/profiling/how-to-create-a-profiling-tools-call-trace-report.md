---
title: "Nasıl yapılır: profil oluşturma araçları çağrı izleme raporu oluşturma | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- performance tools, viewing ETW data
- ETW [Visual Studio ALM], viewing data
ms.assetid: 7640520a-7d3c-456c-b184-872a5d2f82f3
caps.latest.revision: "19"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 1daf97ee7de7a0deea9b3b1c8a9a17529edfe9b4
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2017
---
# <a name="how-to-create-a-profiling-tools-call-trace-report"></a>Nasıl yapılır: Profil Oluşturma Araçları Çağrı İzleme Raporu Oluşturma
*Çağrı izleme raporu* için [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] profil oluşturma araçları her giriş ve çıkış noktası, uygulamanızın işlevlere ve diğer işlevleri işlevinizi tarafından her çağrı için zamanlama bilgilerini listeler. Çağrı izleme raporları yalnızca araçları yöntemi ile toplanan, profil oluşturma verilerini için kullanılabilir.  
  
> [!NOTE]
>  Çağrı izleme raporlarında görüntüleyemiyor [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)]. Kullanmalısınız **VSPerfReport** bir virgülle ayrılmış değer (.csv) veya Xml dosyasını oluşturmak için komut satırı aracı. Bu araç hakkında daha fazla bilgi için bkz: [VSPerfReport](../profiling/vsperfreport.md).  
  
### <a name="to-create-a-call-trace-report"></a>Çağrı izleme raporu oluşturmak için  
  
1.  Açık bir **komut istemi**çizgi penceresi.  
  
2.  Komut satırında, aşağıdaki komutu yazın:  
  
     *ToolsPath* **VSPerfReport** *VSPFile***/CallTrace [/ XML]**   
  
    |||  
    |-|-|  
    |*ToolsPath*|Profil oluşturma araçları komut satırı araçları yolu. Daha fazla bilgi için bkz: [komut satırı araçları yolunu belirtme](../profiling/specifying-the-path-to-profiling-tools-command-line-tools.md).|  
    |*VSPFile*|Profil oluşturma veri (.vsp veya .vsps) dosyası. Tam ve kısmi yollar kabul edilir.|  
    |Xml|Biçimlendirilmiş Xml raporunu oluşturur.|  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Nasıl yapılır: Windows (ETW) toplamak için olay izleme](../profiling/how-to-collect-event-tracing-for-windows-etw-data.md)   
 [Profil Araçları API'leri](../profiling/profiling-tools-apis.md)