---
title: QueryCounters | Microsoft Docs
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-debug
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 8059d4b2-af61-4a47-a6c2-8da5c0741c74
caps.latest.revision: 14
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: ff5cd703a323c93c479d69bbe956855106d80d80
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/22/2018
ms.locfileid: "42630297"
---
# <a name="querycounters"></a>QueryCounters
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Bu konuda en son sürümünü şu yolda bulunabilir: [QueryCounters](https://docs.microsoft.com/visualstudio/profiling/querycounters).  
  
**QueryCounters** seçeneği bilgisayarda kullanılabilir CPU (Donanım) performans sayaçları listeler.  
  
 **QueryCounters** yalnızca seçeneğin komut satırında olması gerekir.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
VSPerfCmd.exe /QueryCounters  
```  
  
#### <a name="parameters"></a>Parametreler  
 Yok.  
  
## <a name="remarks"></a>Açıklamalar  
 Araçlar yöntemini kullanırken, profil oluşturucu her veri koleksiyonu olayı, bir veya daha fazla CPU performans sayacı değerlerini toplayabilirsiniz. Örnekleme profili oluşturma yöntemi kullanırken, bir sayaç olay ve örnekleme aralığı kullanılacak olay oluşum sayısını belirtebilirsiniz.  
  
 Farklı bir işlemci, farklı bir CPU performans sayaçları kullanıma sunar. Profil Oluşturucu, neredeyse tüm işlemciler üzerinde kullanılabilir genel sayaçları kümesini tanımlar. **QueryCounters** seçeneği hem genel sayaçların adlarını ve işlemciye özgü sayaçların adlarını listeler.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [VSPerfCmd](../profiling/vsperfcmd.md)   
 [Bağımsız uygulamaların profilini oluşturma](../profiling/command-line-profiling-of-stand-alone-applications.md)   
 [ASP.NET Web uygulamalarında profil oluşturma](../profiling/command-line-profiling-of-aspnet-web-applications.md)   
 [Profil oluşturma hizmetleri](../profiling/command-line-profiling-of-services.md)



