---
title: "Başlatmış | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 4cd4fc0b-974a-4e61-9ea8-0aaa1a0c52ea
caps.latest.revision: "4"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 285cfb5a68055612fc7d77022b8f9d1d61067ded
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2017
---
# <a name="uninit"></a>UnInit
Grafik günlük dosyası sonlandırır kapatılır ve uygulama, etkin olarak grafik bilgilerini kaydetme sırasında kullanılan kaynakları serbest bırakır.  
  
## <a name="syntax"></a>Sözdizimi  
  
```C++  
void UnInit();  
```  
  
## <a name="remarks"></a>Açıklamalar  
 `UnInit`bir örneği olduğunda otomatik olarak çağrılır `VsgDbg` sınıfı yok. Varsa `VsgDbg` örneği etkin olarak kaydetmediğiniz grafik bilgilerini, bunun hiçbir etkisi olmaz.  
  
 Sonra `UnInit` bir örneği üzerinde çağrıldıktan `VsgDbg` sınıfı, yeni bir grafik günlük dosyası çağırarak oluşturulabilir `Init` ve çağırarak sonuçlandırılmış `UnInit`. Bu sayıda olarak aynı kullanmak istediğiniz yineleyebilirsiniz `VsgDbg` birkaç bağımsız grafik günlük dosyaları oluşturmak için örnek.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Init](init.md)