---
title: ToggleHUD | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 7261e01d-3c72-46ce-9fb3-5f33b2ddb901
caps.latest.revision: "5"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 5bf1e27b9385257203653f3bff5241f6c3875373
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2017
---
# <a name="togglehud"></a>ToggleHUD
Grafik tanılama değiştirir *HUD* (Head yukarı görüntüle) kaplama açıp kapatma.  
  
## <a name="syntax"></a>Sözdizimi  
  
```C++  
void ToggleHUD();  
```  
  
## <a name="remarks"></a>Açıklamalar  
 Grafik tanılama HUD grafik tanılama altında çalışan uygulama sol üst köşesinde görüntülenir. Çalışma zamanı grafik bilgilerini yakalama ve çağrılarak eklenir iletileri ve uygulama hakkında bilgi görüntüler [AddMessage](addmessage.md) üye işlevi.  
  
 HUD geçiş yapmak için etkin olarak grafik bilgilerini yakalama gerekmez — diğer bir deyişle, bir örneği üzerinden değiştirilebilir `VsgDbg` sınıfı, ancak [Init](init.md) üye işlevi ilk çağrılması gerekmez.