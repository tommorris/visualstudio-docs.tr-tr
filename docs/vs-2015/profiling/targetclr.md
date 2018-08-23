---
title: TargetCLR | Microsoft Docs
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-debug
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: f9732480-287f-40f1-a4ff-b112e143b940
caps.latest.revision: 16
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 915ca4a859b4c80f785262f1c05698c4d34a683b
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/22/2018
ms.locfileid: "42634104"
---
# <a name="targetclr"></a>TargetCLR
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Bu konuda en son sürümünü şu yolda bulunabilir: [TargetCLR](https://docs.microsoft.com/visualstudio/profiling/targetclr).  
  
**TargetCLR** seçeneği bir uygulamada birden fazla CLR sürümü yüklendiğinde, ortak dil çalışma zamanı (CLR) sürümünü profiline belirtir.  
  
 Varsayılan olarak, [!INCLUDE[vsprvs](../includes/vsprvs-md.md)] profil oluşturma araçları hedef uygulama tarafından yüklenen CLR ilk sürümü.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
VSPerfCmd.exe {/Launch:AppName | /Attach:PID} /TargetCLR[:ClrVersion] [Options]   
```  
  
#### <a name="parameters"></a>Parametreler  
 `ClrVersion`  
 CLR sürüm numarası. Sürüm biçimi **vN.N.NNNNN**.  
  
## <a name="required-options"></a>Gerekli seçenekleri  
 **TargetCLR** seçeneği yalnızca kullanılabilir ile **başlatma** veya **iliştirme** seçenekleri.  
  
 **Başlat:** `AppName`  
 Belirtilen uygulamayı başlatır ve profile başlatır.  
  
 **Ekleme:** `PID`  
 Belirtilen işlem profili başlar.  
  
## <a name="example"></a>Örnek  
 Bu örnekte, TargetCLR seçeneği, CLR sürümü 4.0.11003 profili emin emin olmak için kullanılır.  
  
```  
VSPerfCmd.exe /Start:Sample /Output:TestApp.exe.vsp  
VSPerfCmd.exe /Launch:TestApp.exe /TargetCLR:v4.0.11003  
```



