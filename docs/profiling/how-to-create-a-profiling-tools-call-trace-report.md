---
title: 'Nasıl yapılır: profil oluşturma araçları çağrı izleme raporu oluşturma | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-debug
ms.topic: conceptual
helpviewer_keywords:
- performance tools, viewing ETW data
- ETW [Visual Studio ALM], viewing data
ms.assetid: 7640520a-7d3c-456c-b184-872a5d2f82f3
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 5fd16cb73778aecfca9b85a48161146a18d8714f
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/16/2018
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