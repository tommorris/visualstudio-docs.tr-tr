---
title: Çıkış | Microsoft Docs
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-debug
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 5e286e61-4548-42cf-a635-e608c5edbe2b
caps.latest.revision: 13
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: d08942b36fedab1f5c5535619bcb6c520093ff9b
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/22/2018
ms.locfileid: "42691773"
---
# <a name="output"></a>Çıkış
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Bu konuda en son sürümünü şu yolda bulunabilir: [çıkış](https://docs.microsoft.com/visualstudio/profiling/output).  
  
**Çıkış** seçeneği performans oturumu için profil oluşturma veri dosyasının adını belirtir. **Çıkış** ile birlikte kullanılmalıdır **Başlat** seçeneği.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
VSPerfCmd.exe /Start:Method /Output:FileName [Options]  
```  
  
#### <a name="parameters"></a>Parametreler  
 `FileName`  
 Veri dosyasının adı. Tam ve kısmi yollar kabul edilir. Bir yol belirtilmezse, dosyayı geçerli dizinde oluşturulur.  
  
## <a name="required-options"></a>Gerekli seçenekleri  
 **Çıkış** seçeneği kullanılmalıdır **Başlat** seçeneği.  
  
 **Başlat:** `Method`  
 Çıkış dosyası adını belirtir.  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnekte, profil oluşturma veri dosyasını geçerli dizinde oluşturulur.  
  
```  
VSPerfCmd.exe /Start:Sample /Output:TestApp.exe.vsp  
```  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [VSPerfCmd](../profiling/vsperfcmd.md)   
 [Bağımsız uygulamaların profilini oluşturma](../profiling/command-line-profiling-of-stand-alone-applications.md)   
 [ASP.NET Web uygulamalarında profil oluşturma](../profiling/command-line-profiling-of-aspnet-web-applications.md)   
 [Profil oluşturma hizmetleri](../profiling/command-line-profiling-of-services.md)



