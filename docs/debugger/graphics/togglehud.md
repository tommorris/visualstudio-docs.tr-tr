---
title: ToggleHUD | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-debug
ms.topic: conceptual
ms.assetid: 7261e01d-3c72-46ce-9fb3-5f33b2ddb901
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 8839e41048a68adf09380e6fa428087299a12801
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/16/2018
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