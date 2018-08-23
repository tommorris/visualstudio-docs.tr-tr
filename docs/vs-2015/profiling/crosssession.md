---
title: CrossSession | Microsoft Docs
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-debug
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: b9fcb9c3-7903-478c-9b7c-dbd94092fcba
caps.latest.revision: 15
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 45259d3a0605dde7164ec9fd98b7338b20c47122
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/22/2018
ms.locfileid: "42692626"
---
# <a name="crosssession"></a>CrossSession
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Bu konuda en son sürümünü şu yolda bulunabilir: [CrossSession](https://docs.microsoft.com/visualstudio/profiling/crosssession).  
  
VSPerfCmd.exe **CrossSession** seçeneği herhangi bir konsol oturumundan verileri toplamak profil oluşturucu sağlar. **CrossSession** seçeneği kullanılmalıdır **Başlat** seçeneği.  
  
 Kısaltması kullanabileceğiniz **CS** yerine **CrossSession**.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
VSPerfCmd.exe /Start:Method /CrossSession [Options]  
```  
  
#### <a name="parameters"></a>Parametreler  
 Yok.  
  
## <a name="valid-options"></a>Geçerli seçenekler şunlardır:  
 Başka bir oturumda oluşturmayı etkinleştirmek için **CrossSession** seçeneği belirtilmelidir **Başlat** seçeneği. **CrossSession** de birinde belirtilmelidir sonraki **VSPerfCmd ekleme** ve **ayırma** komutları.  
  
 **Başlat:** `Method`  
 **Başlat** seçeneği belirtilen profil oluşturma metodu için profil oluşturucuyu başlatır.  
  
 **Ekleme:** *PID*[**, *** PID*]  
 Belirtilen işlemler için profil oluşturma başlar.  
  
 **Ayırma**[**: *** PID*[,*PID*]]  
 Belirtilen işlemler profil oluşturmayı durdurur.  
  
## <a name="example"></a>Örnek  
 Bu örnekte, **CrossSession** seçeneği, başka bir konsol oturumu başlatılmasından bir uygulamaya eklemek için kullanılır.  
  
```  
VSPerfCmd.exe /Start:Sample /Output:TestApp.exe.vsp /CrossSession  
VSPerfCmd.exe /Attach:12345 /CS  
```  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [VSPerfCmd](../profiling/vsperfcmd.md)   
 [Bağımsız uygulamaların profilini oluşturma](../profiling/command-line-profiling-of-stand-alone-applications.md)   
 [ASP.NET Web uygulamalarında profil oluşturma](../profiling/command-line-profiling-of-aspnet-web-applications.md)   
 [Profil oluşturma hizmetleri](../profiling/command-line-profiling-of-services.md)



