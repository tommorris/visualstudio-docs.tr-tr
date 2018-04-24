---
title: 'Nasıl yapılır: ek izleme seçeneklerini belirtme | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology: vs-ide-debug
ms.topic: conceptual
f1_keywords:
- vs.performance.property.advanced
helpviewer_keywords:
- instrumentation, options
- profiling tools, session options
- performance sessions, options
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: dd5b18f4bcf3358592b191c2593fd020f99d4cf5
ms.sourcegitcommit: 42ea834b446ac65c679fa1043f853bea5f1c9c95
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/19/2018
---
# <a name="how-to-specify-additional-instrumentation-options"></a>Nasıl yapılır: Ek İzleme Seçeneklerini Belirtme

Visual Studio IDE kullanarak veya komut satırı araçlarını kullanarak ikili dosyaları işaretleyebilir. IDE içinden bir ikili izleme, izleme sırasında ek izleme seçeneklerini belirtme tarafından toplanan verilerin hacmi denetleyebilirsiniz [Vsınstr](../profiling/vsinstr.md) aracı. Bu seçenekler, oturumun veya hedef düzeyinde kullanılabilir. Örneğin, dahil etmek veya izleme işlemi sırasında belirli işlevleri dışlamak için hedef düzeyinde ek izleme seçeneği kullanın.

> [!IMPORTANT]
> Eklenen her araştırma biraz özgün programın davranışını değiştirir. Bu değişikliği analiz aynı anda ek yükü neden olur. Bu ek yükü yaklaşık çıkarılır olsa bile, yine birden çok iş parçacıklı uygulamalar üzerinde Zarif zamanlama etkilere sahiptir. [Vsınstr](../profiling/vsinstr.md) aracı profili oluşturma sırasında seçenekleri Yardım denetim veri koleksiyonu.

## <a name="to-specify-additional-instrumentation-option"></a>Ek izleme seçeneği belirtmek için

1. İçinde **performans Gezgini**seçin **Performans oturumunu** ve ardından sağ tıklatın ve seçin **özellikleri**.

2. İçinde **özellikler sayfalarına**, tıklatın **Gelişmiş** özellikleri.

3. Tür seçeneklerinde **ek izleme seçeneklerini** kutusu.

     Örneğin, /CONTROL:THREAD profil düzeyini belirtmek için kullanın. Seçenekler tam bir listesi için bkz: [Vsınstr](../profiling/vsinstr.md).

4. **Tamam**'ı tıklatın.

## <a name="see-also"></a>Ayrıca bkz.

[Performans oturumlarını yapılandırma](../profiling/configuring-performance-sessions.md)  
[Komut satırından profil oluşturma](../profiling/using-the-profiling-tools-from-the-command-line.md)