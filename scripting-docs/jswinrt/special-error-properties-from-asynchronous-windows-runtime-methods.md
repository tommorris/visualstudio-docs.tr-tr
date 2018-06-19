---
title: Zaman uyumsuz Windows çalışma zamanı yöntemleri özel hata özelliklerinden | Microsoft Docs
ms.custom: ''
ms.date: 01/18/2017
ms.prod: windows-client-threshold
ms.reviewer: ''
ms.suite: ''
ms.technology:
- javascript
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 45155584-06d8-4e7f-93a6-8564a93f643d
caps.latest.revision: 4
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 120d8f699c8bedd0fe5762300203c5d5ec18e73e
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2017
ms.locfileid: "24791744"
---
# <a name="special-error-properties-from-asynchronous-windows-runtime-methods"></a>Özel hata özelliklerinden zaman uyumsuz Windows çalışma zamanı yöntemleri
Çağrı yığınında yere derin gelen hata durum çünkü JavaScript, zaman uyumsuz Windows çalışma zamanı yöntemlerde hata ayıklaması zor olabilir. JavaScript `Error` nesnenin uygulama hata ayıklama modunda çalışırken, yalnızca hata olduğunda atılır zaman uyumsuz bir Windows çalışma zamanı yönteminden görünen ek özellikler vardır.  
  
## <a name="special-error-properties"></a>Özel hata özellikleri  
 Windows çalışma zamanı başarısız bir zaman uyumsuz işlem hata ayıklama modunda sonucu bir hata nesnesi özel özellikleri şunlardır:  
  
-   `asyncOpSource`(Nesne) Bir hata üretilen çağrı yapıldığı özgün konumuna hakkındaki bilgileri alır. Özellik `asyncOpSource.originatingCall` (dize) zaman uyumsuz işlemi kaynaklanan kullanıcının kodda konumu görüntüler.  
  
-   asyncOpType (dize) hataya neden zaman uyumsuz işlem türünün adını alır.  
  
 Zaman uyumsuz işlemleri hatalarla ilgili daha fazla bilgi için bkz:  
  
-   [İle hataların nasıl işleneceğini taahhüt eder](https://msdn.microsoft.com/en-us/library/windows/apps/hh700337.aspx)  
  
-   [Windows çalışma zamanı hataları giderme](http://msdn.microsoft.com/en-us/1ef7d7df-82ac-441d-8ad0-54ab1318de64)