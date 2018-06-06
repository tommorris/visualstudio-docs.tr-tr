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
ms.openlocfilehash: c06722e9270269ca674370d5bf8b1925d850ce00
ms.sourcegitcommit: 4cd4aef53e7035d23e7d1d0f66f51ac8480622a1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/05/2018
ms.locfileid: "34477411"
---
# <a name="understand-resource-contention-data-values"></a>Kaynak çakışması veri değerlerini anlama

Kaynak çakışması profil rakip iş parçacığı bir uygulamada bir paylaşılan kaynağa erişim için beklenecek zorlanır ayrıntılı çağrı yığını bilgileri her zaman toplar.

Kaynak çakışması raporları çekişmeleri ve modüller, İşlevler, kaynak kod satırlarını ve bekleme gerçekleştiği yönergeleri için bir kaynak için bekleyen harcanan toplam süreyi toplam sayısını görüntüler.

- Kapsayıcı değerleri toplam sayısını bir işlev tarafından kaynak çekişmeleri beklenecek zorunlu çekişmeleri ve işlevi beklenen toplam süreyi görüntüler.  İşlevin adı veriliyordu alt işlevleri neden çekişmeleri dahil değerleri dahil edilir.

- Özel değerler yalnızca beklenecek bir işlev zorlanan ve işlev gövdesine kodu tarafından neden çekişmeleri sayısını görüntüler. Alt işlevleri tarafından neden çekişmeleri dahil edilmez. Özel zaman işlevi için yalnızca işlev gövdesi deyimlerinde neden bekleme süresini de içerir.

Kaynak çakışması rapor görünümlerini de zaman içinde tek tek Çekişme olayları Göster zaman çizelgesi grafikleri içerir ve belirli olay oluşturulan çağrı yığınları gösterir. Daha fazla bilgi için aşağıdaki konulardan birine bakın:

- [İş parçacığı Ayrıntıları görünümü](../profiling/thread-details-view-contention-data.md)

- [Kaynak Ayrıntıları görünümü](../profiling/resource-details-view-contention-data.md)

Eşzamanlılık profili oluşturma ikinci modu hakkında daha fazla bilgi için bkz: [eşzamanlılık görselleştiricisi](../profiling/concurrency-visualizer.md).