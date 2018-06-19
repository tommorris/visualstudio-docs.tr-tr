---
title: Jsruntimehandle tür | Microsoft Docs
ms.custom: ''
ms.date: 01/18/2017
ms.prod: windows-client-threshold
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
ms.assetid: 69e59bfd-9b0e-4710-9aa8-fbd6844171bc
caps.latest.revision: 6
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: d3c0344e203c58691048c55ba4080c6c86c1c643
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2017
ms.locfileid: "24788513"
---
# <a name="jsruntimehandle-typedef"></a>JsRuntimeHandle Tür Tanımı
Chakra çalışma zamanı için bir tanıtıcı.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
typedef void *JsRuntimeHandle;  
```  
  
## <a name="remarks"></a>Açıklamalar  
 Her bir Chakra çalışma zamanının kendi bağımsız yürütme alt yapısı, JIT derleyicisi ve atık toplanma yığını vardır. Bu nedenle her bir çalışma zamanı, diğer çalışma zamanlarından tamamen ayrı tutulur.  
  
 Çalışma zamanları herhangi bir iş parçacığı üzerinde kullanılabilir, ancak yalnızca bir iş parçacığı herhangi bir zamanda çalışma zamanına çağırılabilir.  
  
> [!WARNING]
>  Chakra barındırma API'lerindeki diğer nesne başvurularından farklı olarak bir JsRuntimeHandle, atık toplama yığınını kendisini içerdiğinden atık toplama işlemi gerçekleşmez. Bir çalışma zamanı, JsDisposeRuntime çağrılana kadar var olmaya devam eder.  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** jsrt.h  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Başvuru (JavaScript çalışma zamanı)](../chakra-hosting/reference-javascript-runtime.md)