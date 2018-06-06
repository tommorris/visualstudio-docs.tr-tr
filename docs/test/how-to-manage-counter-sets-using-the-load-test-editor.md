---
title: Visual Studio Yük Testi Sayaç kümeleri
ms.date: 10/19/2016
ms.topic: conceptual
f1_keywords:
- vs.test.load.dialog.countersetmapping
helpviewer_keywords:
- counters, counter sets
- performance counters
- counter sets
- load tests, counter sets
ms.assetid: 64315c2f-a0b2-4378-be16-0774b99beef5
author: gewarren
ms.author: gewarren
manager: douge
ms.prod: visual-studio-dev15
ms.technology: vs-ide-test
ms.openlocfilehash: 27a1cdd3390d6f068947bfcb0daef76eb93fd026
ms.sourcegitcommit: 58052c29fc61c9a1ca55a64a63a7fdcde34668a4
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/04/2018
ms.locfileid: "34751994"
---
# <a name="how-to-manage-counter-sets-using-the-load-test-editor"></a>Nasıl yapılır: Yük Testi Düzenleyicisini Kullanılarak Sayaç Kümelerini Yönetme

İle bir yük testi oluşturduğunuzda **Yeni Yük Testi Sihirbazı**, başlangıç sayaç kümesini ekleyin. Bu, yük testi için önceden tanımlanmış sayaç kümeleri kümesi sunar.

> [!NOTE]
> Yük testleri Uzak makinelerde dağıtılmışsa, denetleyici ve aracı sayaçları denetleyici ve aracı eşlenen sayaç. Yükleme testinizde uzak makineleri kullanma hakkında daha fazla bilgi için bkz: [Test denetleyicileri ve test aracıları](configure-test-agents-and-controllers-for-load-tests.md).

Sayaç kümelerini yönetme, performans verileri toplamak istediğiniz bilgisayarlar kümesi seçme ve her bir bilgisayardan toplamak için sayaç kümelerini kümesi atama içerir. Sayaçlarınızın içinde yönetmek **Yük Testi Düzenleyicisi**.

![Sayaç kümelerini yönetme](../test/media/loadtestmanagecountersets.png)

## <a name="to-manage-counter-sets"></a>Sayaç kümeleri yönetmek için

1.  Bir yük testi açın.

2.  Seçin **sayaç kümelerini Yönet** düğmesi.

     – veya –

     Sağ **sayaç kümelerini** yükleme klasöründe test ağacı ve seçin **sayaç kümelerini Yönet**.

     **Sayaç kümelerini Yönet** iletişim kutusu görüntülenir.

3.  (İsteğe bağlı) İçinde **seçili bilgisayarlar ve sayaç kümelerini eklenecek aşağıdaki çalışma ayarlarının altında** liste kutusunda, farklı bir çalışma ayarı seçin.

    > [!NOTE]
    > Bu, yalnızca yük testinde birden fazla çalışma ayarı varsa geçerlidir.

4.  (İsteğe bağlı) Seçin **bilgisayar Ekle** izlemek için yeni bir bilgisayar eklemek için. İçin bir ad istenir. Bir bilgisayarın adını yazın ve düğümleri yeni girdi altındaki görürsünüz. Örneğin **ASP.NET**, **IIS**, **SQL**ve diğerleri. Seçmek istediğiniz düğümleri önünde onay kutularını seçin. Yeni sayaçları görünür **Önizleme seçimleri** bölmesi.

5.  (İsteğe bağlı) İçinde **bilgisayar etiketleri** metin kutusuna bilgisayarla ilişkilendirmek için bir etiket yazın. Örneğin, "TestMachine12 olarak lab3".

     Bilgisayar etiketleri tanımak kolay ada sahip bir bilgisayar tanımlamanıza olanak sağlar.

     Etiketler görüntülenir **sayaç kümesi eşlemeleri** Yük Testi Düzenleyicisi'nde ağaç düğümü. Daha da önemlisi, etiketler hangi Yardım paydaşları yük testinde bilgisayarında hangi rolü belirleyin Excel raporlarında görüntülenir. Örneğin, "içinde Web Server1 lab2" veya "Phoenix ofisi içinde SQL Server2". Daha fazla bilgi için bkz: [Test karşılaştırmaları veya eğilim analizleri için yük testleri sonuçlarını raporlama](../test/compare-load-test-results.md).

6.  Seçin **Tamam**.

## <a name="see-also"></a>Ayrıca bkz.

- [Test denetleyicileri ve test aracıları](configure-test-agents-and-controllers-for-load-tests.md)
- [Yük testindeki bilgisayarlar için sayaç kümelerini ve eşik kurallarını belirtme](../test/specify-counter-sets-and-threshold-rules-for-load-testing.md)
- [Yük testi çalıştırma ayarlarını yapılandırma](../test/configure-load-test-run-settings.md)