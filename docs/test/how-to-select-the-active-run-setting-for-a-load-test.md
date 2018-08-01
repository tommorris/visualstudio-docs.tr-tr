---
title: Visual Studio Yük testi için çalıştırma ayarı seçme
ms.date: 10/19/2016
ms.topic: conceptual
helpviewer_keywords:
- load tests, run settings, active
ms.assetid: ed6ff546-acfa-4dd8-b3a2-6e7455930ca4
author: gewarren
ms.author: gewarren
manager: douge
ms.prod: visual-studio-dev15
ms.technology: vs-ide-test
ms.openlocfilehash: f5e7a56ff01e06c0d5046ab477ec78635f01f6c4
ms.sourcegitcommit: 495bba1d8029646653f99ad20df2f80faad8d58b
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/31/2018
ms.locfileid: "39381917"
---
# <a name="how-to-select-the-active-run-setting-for-a-load-test"></a>Nasıl yapılır: etkin çalışma yük testi için ayarı seçin

İle yükleme testinizi oluşturduktan sonra **Yeni Yük Testi Sihirbazı**, kullanabileceğiniz **Yük Testi Düzenleyicisi** test ihtiyaçlarınızı ve hedeflerinizi karşılayacak şekilde değiştirmek için.

Bir veya daha fazla yük testi içerebilir *çalıştırma ayarları* olan bir yük testinin çalışma biçimini etkileyen özellikler kümesi. Çalıştırma ayarları kategorilere göre düzenlenir **özellikleri** penceresi. Bir yük testi çalıştırdığınızda, şu anda etkin olarak ayarlanmış çalıştırma ayarını kullanır.

> [!NOTE]
> Çalıştırma ayarları özellikleri ve açıklamalarının tam listesi için bkz: [yük testi çalıştırma ayarları özellikleri](../test/load-test-run-settings-properties.md).

Yük testi çalışma ayarı yalnızca bir düğümünde içeriyorsa **çalıştırma ayarları** klasör, bu düğüm, her zaman etkin düğüme. Yük testi çalıştırma ayarları birden çok düğüm içeriyorsa, bir yük testi çalıştırdığınızda kullanılacak seçebilirsiniz. Bkz: [nasıl yapılır: bir yük testine ek çalışma ayarları ekleme](../test/how-to-add-additional-run-settings-to-a-load-test.md).

İçinde **Yük Testi Düzenleyicisi**, etkin çalışma ayarı "[etkin]" soneki ile tanımlanır.

## <a name="select-the-active-run-setting"></a>Etkin çalışma ayarını seçin

### <a name="to-select-the-active-run-setting-in-a-load-test"></a>Etkin bir yük testi çalışma ayarı seçmek için

1.  Bir yük testi açın.

2.  Genişletin **çalıştırma ayarları** klasör.

3.  Etkin düğüm olmasını ve ardından istediğiniz çalışma ayarları düğümünü sağ **etkin olarak ayarla**.

     İçinde **Yük Testi Düzenleyicisi**r, etkilenen çalışma ayarı düğümünü, "[etkin]" soneki ile güncelleştirilir.

     Seçili çalışma ayarı etkin hale gelir ve etkin olması için ayarı farklı bir seçene kadar etkin kalır çalıştırın.

> [!NOTE]
> Bir ortam değişkeni adlı etkin çalışma ayarını geçersiz kılabilirsiniz `Test.UseRunSetting=<run setting name>`. Komut satırından veya toplu iş dosyasından bir yük testi çalıştırdığınızda, bu yararlıdır. Bu farklı çalıştırma ayarları yük testinizi açmaya gerek kalmadan seçmenize olanak sağlar.

## <a name="specify-the-run-setting-to-use-from-the-command-line"></a>Komut satırından kullanmak için çalıştırma ayarını belirtin

Komut satırından bir ortam değişkenini ayarlayarak, yük testinde çalışma ayarları Varsayılanı geçersiz kılabilirsiniz:

**Test.UseRunSetting=PreProdEnvironment ayarlayın**

Ve testi çalıştırmak için:

**MSTest /testcontainer:loadtest1.loadtest**

## <a name="see-also"></a>Ayrıca bkz.

- [Yük testi çalıştırma ayarlarını yapılandırma](../test/configure-load-test-run-settings.md)
- [Sayaç kümelerini ve eşik kurallarını bilgisayarlar için bir yük testi içinde belirtin.](../test/specify-counter-sets-and-threshold-rules-for-load-testing.md)
- [Nasıl yapılır: bir yük testine ek çalışma ayarları ekleme](../test/how-to-add-additional-run-settings-to-a-load-test.md)