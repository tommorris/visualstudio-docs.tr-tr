---
title: AddMessage | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-debug
ms.topic: conceptual
ms.assetid: 102a0404-a00c-4566-93f3-01bc8df63280
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 0f58f716aca83cce9f2e04129d45a9cf9c97df50
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/16/2018
---
# <a name="addmessage"></a>AddMessage
Grafik tanılama için özel bir ileti ekler *HUD* (Head yukarı görüntüle).  
  
## <a name="syntax"></a>Sözdizimi  
  
```C++  
void AddMessage(  
  wchar_t const * szMessage  
);  
```  
  
#### <a name="parameters"></a>Parametreler  
 `szMessage`  
 HUD eklenecek ileti.  
  
## <a name="remarks"></a>Açıklamalar  
 Grafik tanılama HUD grafik tanılama altında çalışan uygulama sol üst köşesinde görüntülenir. Çalışma zamanı grafik bilgilerini yakalama ve bu işlevini çağırarak eklenen iletileri ve uygulama hakkında bilgi görüntüler.  
  
 Bir ileti HUD eklemek için etkin olarak grafik bilgilerini yakalama gerekmez — diğer bir deyişle, bir ileti örneği eklenebilir `VsgDbg` sınıfı, ancak [Init](init.md) üye işlevi mu ilk çağrılmasına değil. Yalnızca HUD görüntülenen iletiler, grafik günlük dosyasında kaydedilmez.