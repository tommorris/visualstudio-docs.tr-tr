---
title: Visual Studio'da Test yük Adım yük düzeni için Adım Rampa Süresi | Microsoft Docs
ms.date: 10/19/2016
ms.topic: conceptual
helpviewer_keywords:
- load tests, load patterns
ms.assetid: 4a69e857-f93b-4907-9a01-fd1b66291205
author: gewarren
ms.author: gewarren
manager: douge
ms.technology: vs-ide-test
ms.openlocfilehash: 0ed9a9ec360072c45ea2f59483e031dfe856b8e5
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/16/2018
---
# <a name="how-to-specify-the-step-ramp-time-property-for-a-step-load-pattern"></a>Nasıl yapılır: Adım Yük Düzeni için Adım Rampa Süresi Özelliğini Belirtme

Yük testi ile oluşturduktan sonra **Yeni Yük Testi Sihirbazı**, kullanabileceğiniz **Yük Testi Düzenleyicisi** senaryoları özelliklerini test gereksinimlerini ve hedeflerinizi karşılayacak şekilde değiştirmek için. Daha fazla bilgi için bkz: [izlenecek yol: oluşturma ve bir yük testi çalıştırma](../test/walkthrough-create-and-run-a-load-test.md).

> [!NOTE]
> Yük testi senaryosu özellikleri ve açıklamalarının tam listesi için bkz: [yük testi senaryosu özellikleri](../test/load-test-scenario-properties.md).

**Adım Rampa Süresi** özelliği Özellikler penceresinde ayarlanır. Yük Testi Düzenleyicisi'nde yük testi senaryosu özellikleri düzenleyin.

**Adım Rampa Süresi** özelliği yalnızca bir adım yük düzeni ile kullanılır. Daha fazla bilgi için bkz: [modeli sanal kullanıcı etkinlikleri için yük desenlerini düzenleme](../test/edit-load-patterns-to-model-virtual-user-activities.md).

Adım yük düzeni, sunucu veya sunucularda yük kullanıcı yük arttıkça performansın nasıl değişeceğini görebileceğiniz şekilde yük testi olarak artırmak için kullanılır. Örneğin, 2.000 kullanıcılara kullanıcı yükü olarak sunucu veya sunucularda nasıl gerçekleştirmek görmek için aşağıdaki özelliklere sahip bir adım yük düzeni kullanarak 10 saat yük testi çalıştırabilirsiniz:

-   İlk kullanıcı sayısı: 100

-   En fazla kullanıcı sayısı: 2000

-   Adım Süresi (saniye): 1800

-   Adım Rampa Süresi (saniye): 20

-   Adım kullanıcı sayısı: 100

Bu ayarlar kullanıcı yükleri 100, 200, 300, 2.000 kullanıcılar kadar 30 dakika (1800 saniye olarak) çalıştıran yük testi olması.

> [!NOTE]
> **Adım Rampa Süresi** Yeni Yük Testi Sihirbazı'nda seçmek kullanılabilir değil yalnızca bu özelliklerden biri bir özelliktir.

**Adım Rampa Süresi** özelliği aşamalı yerine hemen olacak şekilde tek bir adımda artışın sonrakine (örneğin 100 200 kullanıcıya) sağlar. Örnekte, kullanıcı yükü 20 saniye döneminde 100 ila 200'e yükseltilmiştir (artışı 5 kullanıcıların her saniye).

## <a name="to-edit-the-step-ramp-time-property-for-a-step-load-pattern"></a>Adım yük düzeni için Adım Rampa Süresi özelliğini düzenlemek için

1.  Bir yük testi açın.

     **Yük Testi Düzenleyicisi** görüntülenir. Yük testi ağacı görüntülenir.

2.  Ağaçları yük testi **senaryoları** Adım Rampa belirtmek istediğiniz senaryo düğümünü zaman klasörünü açın.

3.  Seçin **Adım yük düzeni** düğümü.

    > [!NOTE]
    > Yük düzeni senaryo için Adım yük düzeni olması gerekir. Değilse, yük düzeni şu anda senaryoyla ilişkili yük düzeni türünü görüntüler. Daha fazla bilgi için bkz: [modeli sanal kullanıcı etkinlikleri için yük desenlerini düzenleme](../test/edit-load-patterns-to-model-virtual-user-activities.md).

4.  Üzerinde **Görünüm** menüsünde, select **Özellikler penceresini**.

     Senaryonun kategoriler ve Özellikler Özellikler penceresinde görüntülenir.

5.  Değeri ayarlanamıyor **Adım Rampa Süresi** özelliği tarafından belirtilen kullanıcıların her adımda kademeli olarak geçen saniye eklemek için bir sayı girerek **adım kullanıcı sayısı** özelliği.

6.  Özelliği değiştirmeyi bitirdikten sonra seçin **kaydetmek** üzerinde **dosya** menüsü. Ardından yeni kullanarak yük testlerini çalıştırabilirsiniz **Adım Rampa Süresi** değeri.

## <a name="see-also"></a>Ayrıca bkz.

- [Yük testi senaryolarını düzenleme](../test/edit-load-test-scenarios.md)
- [Test denetleyicileri ve test aracıları](configure-test-agents-and-controllers-for-load-tests.md)
- [Yük testi senaryosu özellikleri](../test/load-test-scenario-properties.md)
- [Sanal kullanıcı etkinlikleri modellemek için yük desenlerini düzenleme](../test/edit-load-patterns-to-model-virtual-user-activities.md)