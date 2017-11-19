---
title: AddMessage | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 102a0404-a00c-4566-93f3-01bc8df63280
caps.latest.revision: "5"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 5b0050f5022b31020879b45e45da48546e5a7caa
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2017
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