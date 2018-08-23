---
title: Kapatma | Microsoft Docs
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-debug
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: a1e37500-4ad1-4670-9737-3d9a20536386
caps.latest.revision: 13
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: e7e351050859a96ca95c267bdcbe34ee19e7f87f
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/22/2018
ms.locfileid: "42693132"
---
# <a name="shutdown"></a>Kapat
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Bu konuda en son sürümünü şu yolda bulunabilir: [kapatma](https://docs.microsoft.com/visualstudio/profiling/shutdown).  
  
**Kapatma** seçeneği bekler herhangi şu anda son veya ayırmak için işlem profili ve ardından profil oluşturucuyu devre dışı bırakır ve profil oluşturma veri dosyasını kapatır. **Kapatma** seçeneği, bir profil oluşturma, son komut olması gerekir.  
  
 Bir zaman aşımı parametresi belirtilmezse **kapatma** seçeneği süresiz olarak bekleyecek. Seçeneği bir zaman aşımı parametresi belirtilirse, belirtilen sayıda saniye geçtikten sonra profil oluşturucuyu kapatmak veya veri dosyasını kapatmadan döndürür.  
  
 **Kapatma** seçeneği, komut satırında belirtilen tek seçenek olması gerekir.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
VSPerfCmd.exe /Shutdown[:Timeout]  
```  
  
#### <a name="parameters"></a>Parametreler  
 `Timeout`  
 -   (İsteğe bağlı) Belirtilmişse seçeneği belirtilen sayıda saniye geçtikten sonra profil oluşturucuyu kapatmak veya profil oluşturma veri dosyasını kapatmadan döndürür.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [VSPerfCmd](../profiling/vsperfcmd.md)   
 [Bağımsız uygulamaların profilini oluşturma](../profiling/command-line-profiling-of-stand-alone-applications.md)   
 [ASP.NET Web uygulamalarında profil oluşturma](../profiling/command-line-profiling-of-aspnet-web-applications.md)   
 [Profil oluşturma hizmetleri](../profiling/command-line-profiling-of-services.md)



