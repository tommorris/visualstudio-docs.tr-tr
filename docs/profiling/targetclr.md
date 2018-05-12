---
title: TargetCLR | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology: vs-ide-debug
ms.topic: conceptual
ms.assetid: f9732480-287f-40f1-a4ff-b112e143b940
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 5f8ea5bd3f1ec16f6deeae8365cc90541bc8b958
ms.sourcegitcommit: 046a9adc5fa6d6d05157204f5fd1a291d89760b7
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/11/2018
---
# <a name="targetclr"></a>TargetCLR
**TargetCLR** seçeneği CLR birden fazla sürümünü bir uygulama yüklendiğinde bu ortak dil çalışma zamanı (CLR) sürümünü profiline belirtir.  
  
 Varsayılan olarak, [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] profil oluşturma araçları hedef uygulama tarafından yüklenen CLR ilk sürümü.  
  
## <a name="syntax"></a>Sözdizimi  
  
```cmd  
VSPerfCmd.exe {/Launch:AppName | /Attach:PID} /TargetCLR[:ClrVersion] [Options]   
```  
  
#### <a name="parameters"></a>Parametreler  
 `ClrVersion`  
 CLR sürüm numarası. Sürüm biçimi kullanmak **vN.N.NNNNN**.  
  
## <a name="required-options"></a>Gerekli seçenekler  
 **TargetCLR** seçeneği yalnızca kullanılabilir ile **başlatma** veya **Attach** seçenekleri.  
  
 **Başlat:** `AppName`  
 Belirtilen uygulamayı başlatır ve profiline başlatır.  
  
 **Ekle:** `PID`  
 Belirtilen işlem profilini başlatır.  
  
## <a name="example"></a>Örnek  
 Bu örnekte, TargetCLR seçeneği CLR sürüm 4.0.11003 profili emin olmak için kullanılır.  
  
```cmd  
VSPerfCmd.exe /Start:Sample /Output:TestApp.exe.vsp  
VSPerfCmd.exe /Launch:TestApp.exe /TargetCLR:v4.0.11003  
```