---
title: "Visual Studio yük testlerini düzenleme | Microsoft Docs"
ms.date: 10/19/2016
ms.topic: article
helpviewer_keywords:
- Load Test Editor
- load tests, Load Test Editor
ms.assetid: ba16ed02-137e-40bf-a4cb-45d87d922d37
author: gewarren
ms.author: gewarren
manager: ghogen
ms.technology: vs-ide-test
ms.openlocfilehash: f8a6d4bbec460103f1e8db596fa5d8b523c1bd92
ms.sourcegitcommit: 900ed1e299cd5bba56249cef8f5cf3981b10cb1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/19/2018
---
# <a name="edit-load-tests"></a>Yük testleri Düzenle

Yük testleri Web performans testleri veya çok sayıda kullanıcı aynı anda bir sunucuya erişirken benzetimini yapmak için birim testleri çalıştırın. Bir yük testi için uygulama stres ve performans verilerini erişmenizi sağlar. Bir yük testi kullanıcı yükleri gibi çeşitli yük koşullarını taklit etmek ve ağ türleri için yapılandırılabilir.

> [!NOTE]
> Yük testi yalnızca Visual Studio 2017 Enterprise Edition'da kullanılabilir.

Bir yük testi tarafından tanımlanan *senaryoları*, *sayaç*, ve *çalışma ayarları*. Aşağıdaki çizimde arasındaki farklar açıklanmaktadır [senaryoları](../test/edit-load-test-scenarios.md), [sayaç](../test/specify-counter-sets-and-threshold-rules-for-load-testing.md), ve [çalışma ayarları](../test/load-test-run-settings-properties.md):

![Yük testi mimarisi](../test/media/load_test_editor.png)

## <a name="edit-load-test-scenario-settings"></a>Yük testi senaryosu ayarlarını Düzenle

Bir senaryo, bir kullanıcı grubuna bir sunucu uygulaması ile nasıl etkileşim kurduğu modellemek için kullanılır. Bir senaryo yük düzeni, bir test karışımı modeli, test karışımı, bir tarayıcı karışımı ve ağ karışımı oluşur. Bir yük testi birden fazla senaryosu olabilir ve tek bir senaryo Web performans testleri ve birim testleri içerebilir. Gruplandırma benzer ayarıyla birlikte, bir senaryo gruplamak ve bir yapıdaki birlikte testler için olanak sağlar.

Daha fazla bilgi için bkz: [yük testi senaryolarını düzenleme](../test/edit-load-test-scenarios.md) ve [yük testi senaryosu özellikleri](../test/load-test-scenario-properties.md).

## <a name="configure-and-manage-performance-counter-sets"></a>Yapılandırma ve performans sayaç kümelerini yönetme

Yük testleri performans sayacı verilerini analiz ederken kullanışlı olan teknoloji tarafından düzenlenen adlandırılmış sayaç kümeleri, sağlar. Sayaç kümeleri yük testi, IIS, ASP.NET ve SQL içerir. Yeni Yük Testi Sihirbazı ile bir yük testi oluşturduğunuzda, bir başlangıç önceden tanımlanmış ve önemli sayaç kümesi yük testine dahil etmek için belirttiğiniz bilgisayarlar için yapılandırılır. Yük Testi Düzenleyicisi'nde sayaçlarınızın yönetin.

Daha fazla bilgi için bkz: [sayaç kümelerini ve eşik kurallarını bilgisayarlar için bir yük testinde belirtme](../test/specify-counter-sets-and-threshold-rules-for-load-testing.md).

## <a name="configure-and-manage-load-test-run-settings"></a>Yapılandırma ve yük testi çalıştırma ayarlarını yönetme

Çalışma ayarları bir yük testi çalışma biçimini etkileyen özelliklerdir. Çalıştırma Ayarları Özellikleri penceresinde kategoriler halinde düzenlenir.

Daha fazla bilgi için bkz: [yük testi çalıştırma ayarları yapılandırma](../test/configure-load-test-run-settings.md) ve [yük testi çalıştırma ayarları özellikleri](../test/load-test-run-settings-properties.md).

## <a name="see-also"></a>Ayrıca bkz.

- [Yük testi sonuçlarını çözümleme](../test/analyze-load-test-results-using-the-load-test-analyzer.md)
- [Eşik kuralı ihlallerini çözümleme](../test/analyze-threshold-rule-violations-in-load-tests.md)