---
title: EndCapture | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 06084c3b-e065-49b6-968e-d578762fb871
caps.latest.revision: "6"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.workload: multiple
ms.openlocfilehash: 6f717d8b1e95531f0b758a88db48b610b343ee60
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/22/2017
---
# <a name="endcapture"></a>EndCapture
Başlatıldığı yakalama zaman aralığı sona `BeginCapture`.  
  
## <a name="syntax"></a>Sözdizimi  
  
```C++  
void EndCapture();  
```  
  
## <a name="remarks"></a>Açıklamalar  
 Bir yakalama aralığı genellikle, yalnızca belirli bir tür çizim çağrı hakkında grafik bilgilerini yakalama istediğiniz zaman gibi bir çerçeve kümesini yayar. Yakalama aralığı sunmak için bir çağrı yayılırsa, grafik bilgilerini iki çerçeve yakalanır. İlk çerçeve çağrısı aralığını kapsayan `BeginCapture` ve sunmak için; çağrı ikinci çerçevesi sunmak için çağrısından sonra ilk Direct3D olay ve çağrısı aralığını kapsayan `EndCapture`.  
  
 Bir aralık yakalamak için yakalama ve grafik bilgilerini kaydetmek için uygulamanızı hazırlamak — diğer bir deyişle, aradığınız gerekir [Init](init.md) örneği üzerinden `VsgDbg` çağırmadan önce sınıf `BeginCapture` veya `EndCapture`.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [BeginCapture](begincapture.md)   
 [CaptureCurrentFrame](capturecurrentframe.md)