---
title: Visual Studio Yük testi çalışma ayarı seçin
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
ms.openlocfilehash: 8566964ab8dd3fbfa1fca15ce8362218c99c27e6
ms.sourcegitcommit: e13e61ddea6032a8282abe16131d9e136a927984
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/26/2018
---
# <a name="how-to-select-the-active-run-setting-for-a-load-test"></a>Nasıl yapılır: Yük Testi için Etkin Çalışma Ayarını Seçme

Yük testi ile oluşturduktan sonra **Yeni Yük Testi Sihirbazı**, kullanabileceğiniz **Yük Testi Düzenleyicisi** senaryoları özelliklerini test gereksinimlerini ve hedeflerinizi karşılayacak şekilde değiştirmek için.

Bir yük testi bir veya daha fazla içerebilir *çalışma ayarları* olan bir yük testi çalışma biçimini etkileyen özellikler kümesi. Çalıştırma Ayarları Özellikleri penceresinde kategoriler halinde düzenlenir. Bir yük testi çalıştırdığınızda, şu anda etkin olarak ayarlanmış çalışma ayarı kullanır.

> [!NOTE]
> Çalışma ayarları özelliklerini ve açıklamalarının tam listesi için bkz: [yük testi çalıştırma ayarları özellikleri](../test/load-test-run-settings-properties.md).

Yük testi çalışma ayarı düğümü altında yalnızca bir düğüm içeriyorsa **çalıştırma ayarları** , o düğümün klasördür her zaman etkin düğüm. Yük testi birden çok çalışma ayarları düğümü içeriyorsa, bir yük testi çalıştırdığınızda kullanmak için birini seçebilirsiniz. Bkz: [nasıl yapılır: bir yük testine ek çalışma ayarları ekleme](../test/how-to-add-additional-run-settings-to-a-load-test.md).

Yük Testi Düzenleyicisi'nde etkin çalışma ayarı "[etkin]" soneki ile tanımlanır.

## <a name="selecting-the-active-run-setting"></a>Etkin çalışma ayarını seçme

### <a name="to-select-the-active-run-setting-in-a-load-test"></a>Etkin bir yük testi çalışma ayarı seçmek için

1.  Bir yük testi açın.

2.  Genişletme **çalıştırma ayarları** klasör.

3.  Etkin düğüm olmasını ve ardından istediğiniz çalışma ayarları düğümünü sağ tıklatın **etkin olarak ayarla**.

     İçinde **Yük Testi Düzenleyicisi**r, etkilenen çalışma ayarı düğümü "[etkin]" soneki ile güncelleştirilir.

     Seçili çalışma ayarı etkin hale gelir ve ayarın etkin olması için farklı bir seçene kadar etkin kalır çalıştırın.

> [!NOTE]
> Bir ortam değişkeni adlı etkin çalışma ayarını geçersiz kılabilirsiniz `Test.UseRunSetting=<run setting name>`. Komut satırından veya toplu iş dosyasından bir yük testi çalıştırdığınızda, bu yararlıdır. Bu yük testlerini açmadan farklı çalışma ayarları seçmenize olanak sağlar.


## <a name="specifying-the-run-setting-to-use-from-the-command-line"></a>Çalıştırma ayarını kullanmak için komut satırından belirtme
 Komut satırından bir ortam değişkeni ayarlayarak yük testinde çalışma ayarları Varsayılanı geçersiz kılabilirsiniz:

 **Test.UseRunSetting=PreProdEnvironment ayarlama**

 Ve test çalıştırın:

 **mstest'i /testcontainer:loadtest1.loadtest**

## <a name="see-also"></a>Ayrıca bkz.

- [Yük testi çalıştırma ayarlarını yapılandırma](../test/configure-load-test-run-settings.md)
- [Yük testindeki bilgisayarlar için sayaç kümelerini ve eşik kurallarını belirtme](../test/specify-counter-sets-and-threshold-rules-for-load-testing.md)
- [Nasıl yapılır: bir yük testine ek çalışma ayarları ekleme](../test/how-to-add-additional-run-settings-to-a-load-test.md)