---
title: IActiveScriptProfilerControl::StartProfiling | Microsoft Docs
ms.custom: ''
ms.date: 01/18/2017
ms.prod: windows-script-interfaces
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
apiname:
- IActiveScriptProfilerControl.StartProfiling
apilocation:
- scrobj.dll
ms.assetid: 56a7b3b7-8c21-43d0-9d8b-53bbc19fabb9
caps.latest.revision: 8
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: d5362eaba439ff7a645a8323c4eed5d9496f6d88
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2017
ms.locfileid: "24793562"
---
# <a name="iactivescriptprofilercontrolstartprofiling"></a>IActiveScriptProfilerControl::StartProfiling
Komut dosyası altyapısı profil başlatır. Komut dosyası altyapısı yapılan bir çağrı yaparak profil oluşturucu nesnesinin örneği oluşturur [CoCreateInstance](http://msdn.microsoft.com/en-us/7295a55b-12c7-4ed0-a7a4-9ecee16afdec).  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
HRESULT StartProfiling(  
    [in] REFCLSID clsidProfilerObject,  
    [in] DWORD dwEventMask,  
    [in] DWORD dwContext);  
```  
  
#### <a name="parameters"></a>Parametreler  
 `clsidProfilerObject`  
 [in] Oluşturulacak profil oluşturucu nesnesinin tanımlayıcısını (CLSID) sınıfı.  
  
 `dwEventMask`  
 [in] Olay türlerini belirtir 4-bayt bit maskesi. BITS tanımlanan [profıler_event_mask numaralandırması](../../winscript/reference/profiler-event-mask-enumeration.md).  
  
 `dwContext`  
 [in] Profil Oluşturucu nesnesine geçirilen 4-bayt değeri.  
  
## <a name="return-value"></a>Dönüş Değeri  
 HRESULT döndürür. Olası değerler aşağıdaki gibidir:  
  
|Dönüş Değeri|Açıklama|  
|------------------|-------------|  
|`S_OK`|Yöntem başarılı oldu.|  
|`ACTIVPROF_E_PROFILER_PRESENT`|Profil oluşturma zaten etkin.|  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Iactivescriptprofilercontrol arabirimi](../../winscript/reference/iactivescriptprofilercontrol-interface.md)