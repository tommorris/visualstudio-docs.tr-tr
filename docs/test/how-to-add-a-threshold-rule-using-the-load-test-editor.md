---
title: "Visual Studio'da Test yük için bir eşik kuralı ekleme | Microsoft Docs"
ms.date: 10/19/2016
ms.topic: article
helpviewer_keywords:
- load tests, monitoring
- load tests, thresholds
- load tests, analyzing
- thresholds in load tests
ms.assetid: 3d8fac8f-426f-4155-9ced-f7cd4c79792c
author: gewarren
ms.author: gewarren
manager: ghogen
ms.technology: vs-ide-test
ms.openlocfilehash: b6a7551e269395fb3657aacf0c18e3212c62e53b
ms.sourcegitcommit: 900ed1e299cd5bba56249cef8f5cf3981b10cb1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/19/2018
---
# <a name="how-to-add-a-threshold-rule-using-the-load-test-editor"></a>Nasıl yapılır: Yük Testi Düzenleyicisini kullanarak bir eşik kuralı ekleme

Yük testlerindeki eşik kuralları bir performans sayacı değeri sabit bir değer veya başka bir performans sayacı değeri ile karşılaştırın.

## <a name="to-add-a-threshold-rule"></a>Bir eşik kuralı ekleme

1.  Bir yük testi açın.

2.  Yük Testi Düzenleyicisi'nde genişletin **sayaç kümelerini** düğümü.

3.  Aşağıdakilerden birini genişletin **sayacı kategorileri** sayaç kümelerini birinde. Örneğin, seçebileceğiniz **YüklemeTesti**. Düğümünü genişletin.

4.  Örneğin, sayaçları birine sağ tıklayın **kullanıcı yükü**altında **YüklemeTesti**. Seçin **eşik kuralı ekleme**.

     **Eşik Kuralı Ekle** iletişim kutusu görüntülenir.

5.  Kuralları iki türlerinden birini seçebilirsiniz: Sabiti Karşılaştır ve sayacı Karşılaştır. Uygun türü seçin ve değerlerini ayarlayın.

    > [!NOTE]
    > Ayarlama **uyarı üzerinden** özelliğine **True** bir Eşiği aşan bir sorun olduğunu belirtmek için veya **False** eşiğin altına dönmeden bir sorun olduğunu belirtmek için.

## <a name="see-also"></a>Ayrıca bkz.

- [Eşik kuralı ihlallerini çözümleme](../test/analyze-threshold-rule-violations-in-load-tests.md)
- [Yük testindeki bilgisayarlar için sayaç kümelerini ve eşik kurallarını belirtme](../test/specify-counter-sets-and-threshold-rules-for-load-testing.md)
- [Yük testi sonuçlarını çözümleme](../test/analyze-load-test-results-using-the-load-test-analyzer.md)
- [Yük testindeki bilgisayarlar için sayaç kümelerini ve eşik kurallarını belirtme](../test/specify-counter-sets-and-threshold-rules-for-load-testing.md)