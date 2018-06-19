---
title: Visual Studio'da Test yük sayaç kümesi eşlemeleri için bilgisayar etiketleri ekleme
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
ms.openlocfilehash: d6b14ef4ae42ef978c449f7cb4bafaa08bf8a1a6
ms.sourcegitcommit: e13e61ddea6032a8282abe16131d9e136a927984
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/26/2018
ms.locfileid: "31968141"
---
# <a name="how-to-add-computer-tags-to-counter-set-mappings-using-the-load-test-editor"></a>Nasıl yapılır: Yük Testi Düzenleyicisini Kullanılarak Sayaç Kümesi Eşlemelerine Bilgisayar Etiketleri Ekleme

Bilgisayar etiketleri tanımak kolay ada sahip bir bilgisayar tanımlamanıza olanak sağlar. Etiketler görüntülenir **sayaç kümesi eşlemeleri** Yük Testi Düzenleyicisi'nde ağaç düğümü. Daha da önemlisi, etiketler hangi Yardım paydaşları yük testinde bilgisayarında hangi rolü belirleyin Excel raporlarında görüntülenir. Örneğin, "içinde Web Server1 lab2" veya "Phoenix ofisi içinde SQL Server2". Daha fazla bilgi için bkz: [Test karşılaştırmaları veya eğilim analizleri için yük testleri sonuçlarını raporlama](../test/compare-load-test-results.md).

## <a name="to-add-a-tag-to-a-computer"></a>Bir bilgisayara bir etiket eklemek için

1.  Bir yük testi açın.

2.  Seçin **sayaç kümelerini Yönet** düğmesi.

     – veya –

     Sağ **sayaç kümelerini** yükleme klasöründe test ağacı ve seçin **sayaç kümelerini Yönet**.

     **Sayaç kümelerini Yönet** iletişim kutusu görüntülenir.

3.  (İsteğe bağlı) İçinde **seçili bilgisayarlar ve sayaç kümelerini eklenecek aşağıdaki çalışma ayarlarının altında** liste kutusunda, farklı bir çalışma ayarı seçin.

    > [!NOTE]
    > Bu, yalnızca yük testinde birden fazla çalışma ayarı varsa geçerlidir.

4.  Altında **bilgisayar ve sayaç ayarlar izlemek için**, etiket için uygulamak istediğiniz bilgisayarı seçin.

    > [!NOTE]
    > Bir bilgisayar ekleme hakkında daha fazla bilgi için bkz: [nasıl yapılır: sayaç kümelerini Yönet](../test/how-to-manage-counter-sets-using-the-load-test-editor.md).

5.  İçinde **bilgisayar etiketleri** metin kutusuna bilgisayarla ilişkilendirmek için bir etiket yazın. Örneğin, "TestMachine12 olarak lab3".

6.  Seçin **Tamam**.

## <a name="see-also"></a>Ayrıca bkz.

- [Eşik kuralı ihlallerini çözümleme](../test/analyze-threshold-rule-violations-in-load-tests.md)
- [Yük testi sonuçlarını çözümleme](../test/analyze-load-test-results-using-the-load-test-analyzer.md)
- [Yük testindeki bilgisayarlar için sayaç kümelerini ve eşik kurallarını belirtme](../test/specify-counter-sets-and-threshold-rules-for-load-testing.md)
- [Nasıl yapılır: sayaç kümelerini yönetme](../test/how-to-manage-counter-sets-using-the-load-test-editor.md)