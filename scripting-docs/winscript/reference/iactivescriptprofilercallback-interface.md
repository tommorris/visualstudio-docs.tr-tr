---
title: Iactivescriptprofilercallback arabirimi | Microsoft Docs
ms.custom: ''
ms.date: 01/18/2017
ms.prod: windows-script-interfaces
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
ms.assetid: 76f9164b-b086-4b29-ac79-76f9c76f1d11
caps.latest.revision: 13
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: f4dc4b9d4e3b1f83a37e64e3a85387fd378d3ca7
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2017
ms.locfileid: "24793460"
---
# <a name="iactivescriptprofilercallback-interface"></a>IActiveScriptProfilerCallback Arabirimi
Komut dosyası altyapısı tarafından olaylar gerçekleştiğinde bir profil oluşturucu nesnesi bildirmek için kullanılan yöntemleri sağlar. Bu arabirim profil oluşturucu nesnesi tarafından uygulanır.  
  
## <a name="methods"></a>Yöntemler  
  
|Yöntem|Açıklama|  
|------------|-----------------|  
|[IActiveScriptProfilerCallback::Initialize](../../winscript/reference/iactivescriptprofilercallback-initialize.md)|Bir komut dosyası altyapısı profil oluşturma başlatıldığında profil oluşturucu nesneyi başlatmak için çağrılır.|  
|[IActiveScriptProfilerCallback::Shutdown](../../winscript/reference/iactivescriptprofilercallback-shutdown.md)|Ücretsiz ve profil oluşturma bir komut dosyası altyapısı durduruldu her profil oluşturucu nesnesini serbest bırakma için çağrılır.|  
|[IActiveScriptProfilerCallback::ScriptCompiled](../../winscript/reference/iactivescriptprofilercallback-scriptcompiled.md)|Profil oluşturucu komut dosyası altyapısını nesne derlenmiş komut dosyası bildirir.|  
|[IActiveScriptProfilerCallback::FunctionCompiled](../../winscript/reference/iactivescriptprofilercallback-functioncompiled.md)|Profil oluşturucu komut dosyası altyapısını nesnesi, bir komut dosyası derlenirken bir işlev karşılaştı bildirir.|  
|[IActiveScriptProfilerCallback::OnFunctionEnter](../../winscript/reference/iactivescriptprofilercallback-onfunctionenter.md)|Komut dosyası altyapısı hakkında belge nesne modeli (DOM) içine çağrı olmayan bir işlev çağrısı yürütmek için profil oluşturucu nesne bildirir.|  
|[IActiveScriptProfilerCallback::OnFunctionExit](../../winscript/reference/iactivescriptprofilercallback-onfunctionexit.md)|Profil Oluşturucu nesne DOM çağrısını değil bir işlev yürütülürken tamamlanmış komut dosyası altyapısı çağrısı olduğunu bildirir.|  
  
## <a name="remarks"></a>Açıklamalar  
 İşlev çağrıları belge nesne modeli (DOM) içine bildirimi tarafından sağlanan [Iactivescriptprofilercallback2 arabirimi](../../winscript/reference/iactivescriptprofilercallback2-interface.md).  
  
> [!NOTE]
>  Bir komut dosyası çalıştırılırken profil oluşturmayı durdurmak ve başlatmak için özelliği eklemek için aşağıdaki yöntemleri çağırın. Bu yöntemleri kullanarak, tam çağrı yığını edinebilirsiniz [!INCLUDE[javascript](../../javascript/includes/javascript-md.md)] başlattığınızda veya profil oluşturmayı durdurmak çalışıyor.  
>   
>  -   Çağrı [IActiveScriptProfilerControl2::CompleteProfilerStart](../../winscript/reference/iactivescriptprofilercontrol2-completeprofilerstart.md) profil başlattığınız profil oluşturucu bildirmek için.  
> -   Çağrı [IActiveScriptProfilerControl2::PrepareProfilerStop](../../winscript/reference/iactivescriptprofilercontrol2-prepareprofilerstop.md) profil oluşturucu, yakında profil durduracağını bildirmek için.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Etkin komut dosyası profil oluşturucu arabirimleri](../../winscript/reference/active-script-profiler-interfaces.md)