---
title: CaptureCurrentFrame | Microsoft Docs
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-debug
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 4509311d-6fe2-4b65-9b4a-ff0522585d6a
caps.latest.revision: 8
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: b2fcb05d63370f8f40ab09f0978e0f49dbe7d6a3
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/22/2018
ms.locfileid: "42689633"
---
# <a name="capturecurrentframe"></a>CaptureCurrentFrame
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Bu konuda en son sürümünü şu yolda bulunabilir: [CaptureCurrentFrame](https://docs.microsoft.com/visualstudio/debugger/graphics/capturecurrentframe).  
  
Geçerli kare grafik günlük dosyasına geri kalanında yakalar.  
  
## <a name="syntax"></a>Sözdizimi  
  
```cpp  
void CaptureCurrentFrame();  
```  
  
## <a name="remarks"></a>Açıklamalar  
 Şu anda başka bir yakalama devam ediyor durumunda — tarafından başlatılan bir yakalama gibi `BeginCapture` işlevi — söz konusu yakalama tamamlandı ve ayrı bir kare olarak grafik günlüğüne kaydedilmiş. Daha sonra farklı bir çerçeve olarak da kaydedilir geçerli çerçeve geri kalanında yakalama grafik tanılama başlar hemen. Geçerli çerçevenin son sunmak için bir çağrı tarafından işaretlenir.  
  
 Bir kareyi yakalamak için yakalama ve grafik bilgilerini kaydetmek için uygulamanızı hazırlama — diğer bir deyişle, çağrısı yapmanız gerekir [Init](../debugger/init.md) örneği üzerinden `VsgDbg` çağırmadan önce sınıfı `CaptureCurrentFrame`.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Init](../debugger/init.md)   
 [BeginCapture](../debugger/begincapture.md)



