---
title: BeginCapture | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 9edbb52d-ee0b-4cc4-a382-972bcee067d3
caps.latest.revision: "5"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 8774b60f8791373b312437a3e554d17f9582f07f
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2017
---
# <a name="begincapture"></a>BeginCapture
İle sona erer yakalama aralığı başlar `EndCapture`.  
  
## <a name="syntax"></a>Sözdizimi  
  
```C++  
void BeginCapture();  
```  
  
## <a name="remarks"></a>Açıklamalar  
 Bir yakalama aralığı genellikle, yalnızca belirli bir tür çizim çağrı hakkında grafik bilgilerini yakalama istediğiniz zaman gibi bir çerçeve kümesini yayar. Yakalama aralığı sunmak için bir çağrı yayılırsa, grafik bilgilerini iki çerçeve yakalanır. İlk çerçeve çağrısı aralığını kapsayan `BeginCapture` ve sunmak için; çağrı ikinci çerçevesi sunmak için çağrısından sonra ilk Direct3D olay ve çağrısı aralığını kapsayan `EndCapture`.  
  
 Bir aralık yakalamak için yakalama ve grafik bilgilerini kaydetmek için uygulamanızı hazırlamak — diğer bir deyişle, aradığınız gerekir [Init](init.md) örneği üzerinden `VsgDbg` çağırmadan önce sınıf `BeginCapture` veya `EndCapture`.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [EndCapture](endcapture.md)   
 [CaptureCurrentFrame](capturecurrentframe.md)