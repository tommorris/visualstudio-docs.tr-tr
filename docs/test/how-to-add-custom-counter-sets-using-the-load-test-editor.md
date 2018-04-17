---
title: Visual Studio'da Test yük için özel sayaç kümeleri ekleme | Microsoft Docs
ms.date: 10/19/2016
ms.topic: conceptual
helpviewer_keywords:
- counters, counter sets
- counter sets
- load tests, counter sets
ms.assetid: 499aca80-1069-408d-ac68-326da6a50645
author: gewarren
ms.author: gewarren
manager: douge
ms.technology: vs-ide-test
ms.openlocfilehash: f811ee784a0cb40fb1e5daf00f0ccf3c2ca16bfe
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/16/2018
---
# <a name="how-to-add-custom-counter-sets-using-the-load-test-editor"></a>Nasıl yapılır: Yük Testi Düzenleyicisini Kullanarak Özel Sayaç Kümeleri Ekleme

İle bir yük testi oluşturduğunuzda **Yeni Yük Testi Sihirbazı**, başlangıç sayaç kümesini ekleyin. Bu, yük testi için önceden tanımlanmış sayaç kümeleri kümesi sunar.

> [!NOTE]
> Yük testleri Uzak makinelerde dağıtılmışsa, denetleyici ve aracı sayaçları denetleyici ve aracı eşlenen sayaç. Yükleme testinizde uzak makineleri kullanma hakkında daha fazla bilgi için bkz: [Test denetleyicileri ve test aracıları](configure-test-agents-and-controllers-for-load-tests.md).

Sayaçlarınızın içinde yönetmek **Yük Testi Düzenleyicisi**. Teste zaten ekli sayaç kümelerini görünür **sayaç kümelerini** yük testi düğümü. Bir yük testi oluşturduktan sonra yeni özel sayaç kümeleri ekleyebilirsiniz.

![Özel sayaç kümesi](../test/media/loadtestcustomcounter.png "LoadTestCustomCounter")

## <a name="to-add-a-custom-counter-set-to-a-load-test"></a>Özel sayaç kümesi bir yük testine eklemek için

1.  Bir yük testi açın.

2.  Genişletme **sayaç kümelerini** düğümü. Yük testi eklenen tüm sayaç kümeleri görünür.

3.  Sağ **sayaç kümelerini** düğümü ve select **özel sayaç kümesi Ekle**.

    > [!NOTE]
    > Sayaç kümesi gibi bir varsayılan adı verilen **Custom1**. Kullanarak adı değiştirebilirsiniz **özellikleri** penceresi. Tuşuna basın, görüntülemek için F4 **özellikleri** penceresi.

4.  Sayaçları, özel sayaç kümesi, yeni sayaç kümesi sağ tıklayın ve ardından seçin eklemek için **Sayaç Ekle**. Sayaç ekleme hakkında daha fazla bilgi için bkz: [nasıl yapılır: sayaç kümelerine Sayaç Ekle](../test/how-to-add-counters-to-counter-sets-using-the-load-test-editor.md).

    > [!NOTE]
    > Varolan bir sayaç kümesini sağ tıklatıp, kopyala öğesini seçip ardından onu sayaç kümeleri düğümüne yapıştırarak da özel sayaç kümesi eklemek mümkündür. Kopyalanır, ancak gerekli değildir, ek sayaçlar silinebilir. Kullanarak yeni sayacın adını değiştirebilirsiniz **özellikleri** penceresi.

## <a name="see-also"></a>Ayrıca bkz.

- [Yük testindeki bilgisayarlar için sayaç kümelerini ve eşik kurallarını belirtme](../test/specify-counter-sets-and-threshold-rules-for-load-testing.md)
- [Yük testi çalıştırma ayarlarını yapılandırma](../test/configure-load-test-run-settings.md)