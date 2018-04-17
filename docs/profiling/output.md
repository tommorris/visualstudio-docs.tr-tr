---
title: Çıktı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-debug
ms.topic: conceptual
ms.assetid: 5e286e61-4548-42cf-a635-e608c5edbe2b
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 06d8518e6ea5e5cc4dbfbe3ae51d9fb1b06757a5
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/16/2018
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
  
 **Başlat:** `Method`  
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