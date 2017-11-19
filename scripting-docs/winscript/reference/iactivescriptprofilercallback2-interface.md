---
title: Iactivescriptprofilercallback2 arabirimi | Microsoft Docs
ms.custom: 
ms.date: 01/18/2017
ms.prod: windows-script-interfaces
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: reference
helpviewer_keywords: IActiveScriptProfilerCallback2 interface
ms.assetid: 8f2e62e4-c232-4dc3-a2c0-54dd06298306
caps.latest.revision: "11"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 2dc9fcd8ca4afec0fb474c0f3a7317b608c7c9f6
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2017
---
# <a name="iactivescriptprofilercallback2-interface"></a>IActiveScriptProfilerCallback2 Arabirimi
Komut dosyası altyapısı tarafından belge nesne modeli (DOM) olaylar gerçekleştiğinde bir profil oluşturucu nesnesi bildirmek için kullanılan yöntemleri sağlar. Bu arabirim profil oluşturucu nesnesi tarafından uygulanır.  
  
## <a name="methods"></a>Yöntemler  
  
|Yöntem|Açıklama|  
|------------|-----------------|  
|[IActiveScriptProfilerCallback2::OnFunctionEnterByName](../../winscript/reference/iactivescriptprofilercallback2-onfunctionenterbyname.md)|Komut dosyası altyapısı DOM işlev çağrısı çalışmasına olmaya profil oluşturucu nesne bildirir.|  
|[IActiveScriptProfilerCallback2::OnFunctionExitByName](../../winscript/reference/iactivescriptprofilercallback2-onfunctionexitbyname.md)|Profil oluşturucu komut dosyası altyapısını nesne DOM işlev çağrısı çalıştıran tamamlandı bildirir.|  
  
## <a name="remarks"></a>Açıklamalar  
 `IActiveScriptProfilerCallback2` İlk Internet Explorer 9 ile yayımlanan arabirimi.  
  
 DOM çağrılarını olmayan işlev çağrılarını bildirimi tarafından sağlanan [Iactivescriptprofilercallback arabirimi](../../winscript/reference/iactivescriptprofilercallback-interface.md).  
  
> [!NOTE]
>  Bir komut dosyası çalıştırılırken profil oluşturmayı durdurmak ve başlatmak için özelliği eklemek için aşağıdaki yöntemleri çağırın. Bu yöntemleri kullanarak, tam çağrı yığını edinebilirsiniz [!INCLUDE[javascript](../../javascript/includes/javascript-md.md)] başlattığınızda veya profil oluşturmayı durdurmak çalışıyor.  
>   
>  -   Çağrı [IActiveScriptProfilerControl2::CompleteProfilerStart](../../winscript/reference/iactivescriptprofilercontrol2-completeprofilerstart.md) profil başlattığınız profil oluşturucu bildirmek için.  
> -   Çağrı [IActiveScriptProfilerControl2::PrepareProfilerStop](../../winscript/reference/iactivescriptprofilercontrol2-prepareprofilerstop.md) profil oluşturucu, yakında profil durduracağını bildirmek için.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Etkin komut dosyası profil oluşturucu arabirimleri](../../winscript/reference/active-script-profiler-interfaces.md)