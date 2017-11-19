---
title: CrossSession | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: b9fcb9c3-7903-478c-9b7c-dbd94092fcba
caps.latest.revision: "10"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 196107019a43f8f76beeb55cde6a56034375b9d9
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2017
---
# <a name="crosssession"></a>CrossSession
VSPerfCmd.exe **CrossSession** seçeneğini herhangi bir konsol oturumundan verileri toplamak profil oluşturucu etkinleştirir. **CrossSession** seçeneği kullanılan, ile **Başlat** seçeneği.  
  
 Kısaltması kullanabilirsiniz **CS** yerine **CrossSession**.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
VSPerfCmd.exe /Start:Method /CrossSession [Options]  
```  
  
#### <a name="parameters"></a>Parametreler  
 Yok.  
  
## <a name="valid-options"></a>Geçerli seçenekleri  
 Başka bir oturumda profil oluşturmayı etkinleştirmek için **CrossSession** seçeneği belirtilen, ile **Başlat** seçeneği. **CrossSession** birinde de belirtilmelidir sonraki **VSPerfCmd Attach** ve **ayırma** komutları.  
  
 **Başlangıç:**`Method`  
 **Başlat** seçeneği belirtilen profil oluşturma yöntemi için profil oluşturucu başlatır.  
  
 **Ekle:** *PID*[**,***PID*]  
 Belirtilen işlemler profil başlar.  
  
 **Detach**[**:***PID*[,*PID*]]  
 Profil oluşturma belirtilen işlemleri durdurur.  
  
## <a name="example"></a>Örnek  
 Bu örnekte, **CrossSession** seçeneği, başka bir konsol oturumunda başlatılmasından bir uygulama eklemek için kullanılır.  
  
```  
VSPerfCmd.exe /Start:Sample /Output:TestApp.exe.vsp /CrossSession  
VSPerfCmd.exe /Attach:12345 /CS  
```  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [VSPerfCmd](../profiling/vsperfcmd.md)   
 [Bağımsız uygulamaların profilini oluşturma](../profiling/command-line-profiling-of-stand-alone-applications.md)   
 [ASP.NET Web uygulamalarında profil oluşturma](../profiling/command-line-profiling-of-aspnet-web-applications.md)   
 [Profil oluşturma hizmetleri](../profiling/command-line-profiling-of-services.md)