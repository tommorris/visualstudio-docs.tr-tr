---
title: "Nasıl yapılır: izleme eklenmiş ikili dosyaları yeniden konumlandırma | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- vs.performance.property.binaries
helpviewer_keywords:
- binaries, instrumented
- instrumentation, instrumented binaries
- instrumented binaries and relocating
- profiling tools, instrumented binaries
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.workload:
- multiple
ms.openlocfilehash: 364d6695738cb646397895cead518d640497652f
ms.sourcegitcommit: 36ab8429333b31f03992a9fe8fc669db8e09c968
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/21/2018
---
# <a name="how-to-relocate-instrumented-binaries"></a>Nasıl yapılır: Araç Haline Getirilmiş İkili Dosyaları Yeniden Konumlandırma

İzleme sırasında araştırmalar uygulama performansını ölçmek için ikili olarak eklenir. İzleme eklenmiş ikili taşıyabilir seçerek, özgün ikili bir kopyasını işaretlenir ve belirtilen konuma yerleştirin. Bu seçenek, özgün ikili dosyanız yeniden adlandırmak için profil oluşturucu istemiyorsanız yararlıdır. İkili yeniden konumlandırılmasını değil, ikili özgün sürümünün üzerine yazılır.

## <a name="to-relocate-instrumented-binary"></a>İzleme eklenmiş ikili konumunu değiştirmek için

1. İçinde **performans Gezgini**, performans oturumu sağ tıklatın ve ardından **özellikleri**.

2. İçinde **özellik sayfaları**, tıklatın **ikili** özellikleri.

3. Seçin **izleme eklenmiş ikili dosyaları yeniden konumlandırma** onay kutusu.

4. İzleme eklenmiş ikili dosya konumunu belirtin.

## <a name="see-also"></a>Ayrıca bkz.

[Performans oturumlarını yapılandırma](../profiling/configuring-performance-sessions.md)  
[VSInstr](../profiling/vsinstr.md)
