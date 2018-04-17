---
title: Başlatmış | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-debug
ms.topic: conceptual
ms.assetid: 4cd4fc0b-974a-4e61-9ea8-0aaa1a0c52ea
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 735eb1948acfb03a6aa1a70fb27f012c41bb097d
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/16/2018
---
# <a name="uninit"></a>UnInit
Grafik günlük dosyası sonlandırır kapatılır ve uygulama, etkin olarak grafik bilgilerini kaydetme sırasında kullanılan kaynakları serbest bırakır.  
  
## <a name="syntax"></a>Sözdizimi  
  
```C++  
void UnInit();  
```  
  
## <a name="remarks"></a>Açıklamalar  
 `UnInit` bir örneği olduğunda otomatik olarak çağrılır `VsgDbg` sınıfı yok. Varsa `VsgDbg` örneği etkin olarak kaydetmediğiniz grafik bilgilerini, bunun hiçbir etkisi olmaz.  
  
 Sonra `UnInit` bir örneği üzerinde çağrıldıktan `VsgDbg` sınıfı, yeni bir grafik günlük dosyası çağırarak oluşturulabilir `Init` ve çağırarak sonuçlandırılmış `UnInit`. Bu sayıda olarak aynı kullanmak istediğiniz yineleyebilirsiniz `VsgDbg` birkaç bağımsız grafik günlük dosyaları oluşturmak için örnek.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Init](init.md)