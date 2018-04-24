---
title: Kaynak çakışması veri değerlerini anlama | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology: vs-ide-debug
ms.topic: conceptual
helpviewer_keywords:
- concurrency profiling method
- Profiling Tools, concurrency method
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: bdc41ee4c3c9f53d45245c6c305d7f8e221757f4
ms.sourcegitcommit: 42ea834b446ac65c679fa1043f853bea5f1c9c95
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/19/2018
---
# <a name="understanding-resource-contention-data-values"></a>Kaynak Çakışması Veri Değerlerini Anlama

Kaynak çakışması profil rakip iş parçacığı bir uygulamada bir paylaşılan kaynağa erişim için beklenecek zorlanır ayrıntılı çağrı yığını bilgileri her zaman toplar.

Kaynak çakışması raporları çekişmeleri ve modüller, İşlevler, kaynak kod satırlarını ve bekleme gerçekleştiği yönergeleri için bir kaynak için bekleyen harcanan toplam süreyi toplam sayısını görüntüler.

- Kapsayıcı değerleri toplam sayısını bir işlev tarafından kaynak çekişmeleri beklenecek zorunlu çekişmeleri ve işlevi beklenen toplam süreyi görüntüler.  İşlevin adı veriliyordu alt işlevleri neden çekişmeleri dahil değerleri dahil edilir.

- Özel değerler yalnızca beklenecek bir işlev zorlanan ve işlev gövdesine kodu tarafından neden çekişmeleri sayısını görüntüler. Alt işlevleri tarafından neden çekişmeleri dahil edilmez. Özel zaman işlevi için yalnızca işlev gövdesi deyimlerinde neden bekleme süresini de içerir.

Kaynak çakışması rapor görünümlerini de zaman içinde tek tek Çekişme olayları Göster zaman çizelgesi grafikleri içerir ve belirli olay oluşturulan çağrı yığınları gösterir. Daha fazla bilgi için aşağıdaki konulardan birine bakın:

- [İş parçacığı Ayrıntıları görünümü](../profiling/thread-details-view-contention-data.md)

- [Kaynak Ayrıntıları görünümü](../profiling/resource-details-view-contention-data.md)

Eşzamanlılık profili oluşturma ikinci modu hakkında daha fazla bilgi için bkz: [eşzamanlılık görselleştiricisi](../profiling/concurrency-visualizer.md).