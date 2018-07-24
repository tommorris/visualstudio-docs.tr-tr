---
title: Yük testi Visual Studio için sayaç kümesi eşlemeleri için bilgisayar etiketleri ekleme
ms.date: 10/19/2016
ms.topic: conceptual
helpviewer_keywords:
- load tests, counter set mappings, computer tags
ms.assetid: f52a73e1-036a-4b28-a6c8-848284bf4488
author: gewarren
ms.author: gewarren
manager: douge
ms.prod: visual-studio-dev15
ms.technology: vs-ide-test
ms.openlocfilehash: 96ce122c78c20b741613ed45820f585236a0383b
ms.sourcegitcommit: 36835f1b3ec004829d6aedf01938494465587436
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/23/2018
ms.locfileid: "39203673"
---
# <a name="how-to-add-computer-tags-to-counter-set-mappings-using-the-load-test-editor"></a>Nasıl yapılır: sayaç kümesi Yük Testi Düzenleyicisini kullanarak eşlemelerine bilgisayar etiketleri ekleme

Bilgisayar etiketleri bir kolayca tanımak ada sahip bir bilgisayar tanımlamanıza olanak sağlar. Etiketler görüntülenir **sayaç kümesi eşlemeleri** Yük Testi Düzenleyicisi'nde ağaç düğümü. Daha da önemlisi, etiketler yardımcı olan bilgisayar ve yük testinde sahip rolü proje katılımcılarını belirleme, Excel raporlarında görüntülenir. Örneğin, "Web Sunucu1 lab2 içinde" veya "SQL Server2 Phoenix Office". Daha fazla bilgi için [raporlama yük testleri için test karşılaştırmaları veya eğilim analizi sonuçları](../test/compare-load-test-results.md).

## <a name="to-add-a-tag-to-a-computer"></a>Bir bilgisayar için bir etiket eklemek için

1.  Bir yük testi açın.

2.  Seçin **sayaç kümelerini Yönet** düğmesi.

     – veya –

     Sağ **sayaç kümeleri** klasörü yük testi ağacında ve seçin **sayaç kümelerini Yönet**.

     **Sayaç kümelerini Yönet** iletişim kutusu görüntülenir.

3.  (İsteğe bağlı) İçinde **seçili bilgisayarlar ve sayaç kümeleri aşağıdaki çalışma ayarları altına eklenecek** liste kutusu, farklı bir çalışma ayarı seçin.

    > [!NOTE]
    > Bu, yalnızca yük testinize birden fazla çalışma ayarı varsa geçerlidir.

4.  Altında **bilgisayar ve sayaç kümeleri izlemek için**, etiketi uygulamak istediğiniz bilgisayarı seçin.

    > [!NOTE]
    > Bir bilgisayar ekleme hakkında daha fazla bilgi için bkz: [nasıl yapılır: sayaç kümelerini Yönet](../test/how-to-manage-counter-sets-using-the-load-test-editor.md).

5.  İçinde **bilgisayar etiketleri** metin kutusuna bilgisayarla ilişkilendirmek için bir etiket yazın. Örneğin, "TestMachine12 olarak lab3".

6.  Seçin **Tamam**.

## <a name="see-also"></a>Ayrıca bkz.

- [Eşik kuralı ihlallerini çözümleme](../test/analyze-threshold-rule-violations-in-load-tests.md)
- [Yük testi sonuçlarını çözümleme](../test/analyze-load-test-results-using-the-load-test-analyzer.md)
- [Sayaç kümelerini ve eşik kurallarını bilgisayarlar için bir yük testi içinde belirtin.](../test/specify-counter-sets-and-threshold-rules-for-load-testing.md)
- [Nasıl yapılır: sayaç kümelerini Yönet](../test/how-to-manage-counter-sets-using-the-load-test-editor.md)