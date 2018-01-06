---
title: TargetCLR | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: f9732480-287f-40f1-a4ff-b112e143b940
caps.latest.revision: "11"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.workload: multiple
ms.openlocfilehash: a69edb2730ff89a50dd45252258fc57e7205de3d
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/22/2017
---
# <a name="targetclr"></a>TargetCLR
**TargetCLR** seçeneği CLR birden fazla sürümünü bir uygulama yüklendiğinde bu ortak dil çalışma zamanı (CLR) sürümünü profiline belirtir.  
  
 Varsayılan olarak, [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] profil oluşturma araçları hedef uygulama tarafından yüklenen CLR ilk sürümü.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
VSPerfCmd.exe {/Launch:AppName | /Attach:PID} /TargetCLR[:ClrVersion] [Options]   
```  
  
#### <a name="parameters"></a>Parametreler  
 `ClrVersion`  
 CLR sürüm numarası. Sürüm biçimi kullanmak **vN.N.NNNNN**.  
  
## <a name="required-options"></a>Gerekli seçenekler  
 **TargetCLR** seçeneği yalnızca kullanılabilir ile **başlatma** veya **Attach** seçenekleri.  
  
 **Başlatma:**`AppName`  
 Belirtilen uygulamayı başlatır ve profiline başlatır.  
  
 **Ekle:**`PID`  
 Belirtilen işlem profilini başlatır.  
  
## <a name="example"></a>Örnek  
 Bu örnekte, TargetCLR seçeneği CLR sürüm 4.0.11003 profili emin olmak için kullanılır.  
  
```  
VSPerfCmd.exe /Start:Sample /Output:TestApp.exe.vsp  
VSPerfCmd.exe /Launch:TestApp.exe /TargetCLR:v4.0.11003  
```