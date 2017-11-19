---
title: "Çıktı | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 5e286e61-4548-42cf-a635-e608c5edbe2b
caps.latest.revision: "8"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 6ead4ac1f7b420ac59fc58f87d4351498148c161
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2017
---
# <a name="output"></a>Çıkış
**Çıkış** seçeneği performans oturumu için profil oluşturma veri dosyası adını belirtir. **Çıktı** ile birlikte kullanılmalıdır **Başlat** seçeneği.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
VSPerfCmd.exe /Start:Method /Output:FileName [Options]  
```  
  
#### <a name="parameters"></a>Parametreler  
 `FileName`  
 Veri dosyası adı. Tam ve kısmi yollar kabul edilir. Bir yol belirtilmezse, dosya geçerli dizinde oluşturulur.  
  
## <a name="required-options"></a>Gerekli seçenekler  
 **Çıkış** seçeneği kullanılan, ile **Başlat** seçeneği.  
  
 **Başlangıç:**`Method`  
 Çıktı dosyası adını belirtir.  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnekte, profil oluşturma veri dosyası geçerli dizinde oluşturulur.  
  
```  
VSPerfCmd.exe /Start:Sample /Output:TestApp.exe.vsp  
```  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [VSPerfCmd](../profiling/vsperfcmd.md)   
 [Bağımsız uygulamaların profilini oluşturma](../profiling/command-line-profiling-of-stand-alone-applications.md)   
 [ASP.NET Web uygulamalarında profil oluşturma](../profiling/command-line-profiling-of-aspnet-web-applications.md)   
 [Profil oluşturma hizmetleri](../profiling/command-line-profiling-of-services.md)