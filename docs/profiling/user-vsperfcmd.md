---
title: Kullanıcı (VSPerfCmd) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology: vs-ide-debug
ms.topic: conceptual
ms.assetid: ee1a478e-374d-4f30-ae28-d260b9d4723a
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 5b774367120c9c33be57018fd8ea94674febfbf5
ms.sourcegitcommit: 42ea834b446ac65c679fa1043f853bea5f1c9c95
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/19/2018
---
# <a name="user-vsperfcmd"></a>Kullanıcı (VSPerfCmd)
**Kullanıcı** seçeneği profili işlemin sahibi olan hesabın etki alanı ve kullanıcı adını belirtir. Bu seçenek, yalnızca işlem oturum açan kullanıcının başka bir kullanıcı olarak çalışıyorsa gereklidir. İşlem sahibi, Windows Görev Yöneticisi'nin İşlemler sekmesinde kullanıcı adı sütununda listelenir.  
  
 **Kullanıcı** seçeneği de içeren bir komut satırında yalnızca belirtilebilir **Başlat** seçeneği.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
VSPerfCmd.exe /Start:Method /Output:FileName /User:[Domain\]UserName [Options]  
```  
  
#### <a name="parameters"></a>Parametreler  
 `Domain`  
 Kullanıcının etki alanı adı.  
  
 `UserName`  
 Kullanıcı adı.  
  
## <a name="required-options"></a>Gerekli seçenekler  
 **Kullanıcı** seçeneği yalnızca kullanılabilir ile **Başlat** seçeneği.  
  
 **Başlat:** `Method`  
 Belirtilen profil oluşturma yöntemi için profil oluşturucu başlatır.  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnek kullanımını gösteren **kullanıcı** seçeneği.  
  
```  
VSPerfCmd.exe /Start:Sample /Output:TestApp.exe.vsp /User:SYSTEM  
```  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [VSPerfCmd](../profiling/vsperfcmd.md)   
 [Bağımsız uygulamaların profilini oluşturma](../profiling/command-line-profiling-of-stand-alone-applications.md)   
 [ASP.NET Web uygulamalarında profil oluşturma](../profiling/command-line-profiling-of-aspnet-web-applications.md)   
 [Profil oluşturma hizmetleri](../profiling/command-line-profiling-of-services.md)