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
ms.workload: multiple
ms.openlocfilehash: e1c7c0f57b919271c4880c9c1f2fbd8ca1dc964f
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/22/2017
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