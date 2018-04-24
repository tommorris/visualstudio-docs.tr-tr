---
title: 'Nasıl yapılır: izleme eklenmiş ikili dosyaları yeniden konumlandırma | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology: vs-ide-debug
ms.topic: conceptual
f1_keywords:
- vs.performance.property.binaries
helpviewer_keywords:
- binaries, instrumented
- instrumentation, instrumented binaries
- instrumented binaries and relocating
- profiling tools, instrumented binaries
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 1c138e8b823977d95f2630040a0690628396503d
ms.sourcegitcommit: 42ea834b446ac65c679fa1043f853bea5f1c9c95
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/19/2018
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
