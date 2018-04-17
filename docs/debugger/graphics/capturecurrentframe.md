---
title: CaptureCurrentFrame | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-debug
ms.topic: conceptual
ms.assetid: 4509311d-6fe2-4b65-9b4a-ff0522585d6a
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 3863cabe07d6b3f061e0eeecded88d39d00596ad
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/16/2018
---
# <a name="capturecurrentframe"></a>CaptureCurrentFrame
Grafik günlük dosyası için geçerli çerçeve kalanı yakalar.  
  
## <a name="syntax"></a>Sözdizimi  
  
```C++  
void CaptureCurrentFrame();  
```  
  
## <a name="remarks"></a>Açıklamalar  
 Şu anda başka bir yakalama devam ediyor durumunda — tarafından başlatılan bir yakalama gibi `BeginCapture` işlevi — bu yakalama tamamlandı ve ayrı bir kare olarak grafik günlüğüne kaydedilir. Daha sonra farklı bir çerçeve olarak da kaydedilir geçerli çerçeve kalanı yakalama grafik tanılama başlar hemen. Geçerli çerçevenin son sunmak için bir çağrı tarafından işaretlenir.  
  
 Bir çerçeve yakalamak için yakalama ve grafik bilgilerini kaydetmek için uygulamanızı hazırlamak — diğer bir deyişle, aradığınız gerekir [Init](init.md) örneği üzerinden `VsgDbg` çağırmadan önce sınıf `CaptureCurrentFrame`.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Init](init.md)   
 [BeginCapture](begincapture.md)