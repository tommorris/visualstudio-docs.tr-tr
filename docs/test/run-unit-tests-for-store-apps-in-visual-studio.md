---
title: "Çalıştırmak, düzenlemek ve birim testleri Visual Studio'da hata ayıklama | Microsoft Docs"
ms.date: 11/04/2016
ms.technology: vs-devops-test
ms.tgt_pltfrm: 
ms.topic: article
ms.author: gewarren
manager: ghogen
ms.workload:
- multiple
author: gewarren
ms.openlocfilehash: d99b0ab4ce0b10a4a03f80c95a004df0a9facef5
ms.sourcegitcommit: e01ccb5ca4504a327d54f33589911f5d8be9c35c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/15/2018
---
# <a name="run-organize-and-debug-unit-tests"></a>Çalıştırmak, düzenlemek ve birim testleri hatalarını ayıklama

Bu konu, Microsoft Visual Studio Test Gezgini ile birim testleri çalıştırırken açıklar.

## <a name="unit-test-frameworks-and-test-projects"></a>Birim testi çerçevelerini ve test projeleri

Visual Studio yönetilen kod ve yerel C++ kodu için Microsoft birim test çerçevelerini içerir. Test Gezgini, bir çözümde birden çok test projelerden ve üretim kodu projeleri parçası olan test sınıflardan testleri çalıştırabilirsiniz. Visual C# ve Visual Basic birim test çerçevelerini veya testi projelerini Visual C++ herhangi bir bileşimini olabilir. .NET Framework için test altındaki kodun yazıldığında test projesinin hedef kod dilinin bağımsız olarak herhangi bir .NET Framework dil yazılabilir. Yerel C/C++ kod projeleri, C++ birim test çerçevesi kullanılarak test edilebilir.

## <a name="run-tests-in-test-explorer"></a>Test Gezgini testleri çalıştırma

Test projesi derlerken, testleri Test Gezgini'nde görünür. Test Gezgini görünür durumda değilse, seçin **Test** Visual Studio menüsünde, **Windows**ve ardından **Test Gezgini**.

![Birim Test Gezgini](../test/media/ute_failedpassednotrunsummary.png)

Test Gezgini çalıştırmak, yazma ve testleri yeniden çalıştırmak gibi sonuçları varsayılan gruplar halinde görüntülenir. **başarısız testler**, **testleri geçti**, **atlandı testleri** ve  **Testler değil**. Test Gezgini testlerinizi grupları şekilde değiştirebilirsiniz.

Bulma, düzenleme ve testleri Test Gezgini araç çubuğundan çalışan işin çoğunu gerçekleştirebilirsiniz.

![Test Gezgini araç çubuğundan testleri çalıştırma](../test/media/ute_toolbar.png)

### <a name="run-tests"></a>Testleri çalıştırma

Bir grup veya seçtiğiniz testleri kümesi tüm testleri Çözümdeki tüm testleri çalıştırın. Aşağıdakilerden birini yapın:

- Bir çözümde tüm testleri çalıştırmak için tercih **tümünü Çalıştır**.

- Bir varsayılan grubundaki tüm testleri çalıştırmak için tercih **Çalıştır...**  ve grubun menüsünde'i seçin.

- Seçilen testi için kısayol menüsünü açın ve ardından çalıştırmak istediğiniz tek tek testlerin seçin **seçili Testleri Çalıştır**.

Test Gezgini penceresinin üst geçişi/hata çubuğu Testleri Çalıştır animasyon eklenir. Tüm testleri geçirilen ya da herhangi bir test başarısız olursa kırmızı kapatır testi sonuç geçişi/hata çubuğu yeşil olur.

## <a name="view-test-results"></a>Test sonuçlarını görüntüleme

Test Gezgini çalıştırmak, yazma ve testleri yeniden çalıştırmak gibi sonuçları gruplar halinde görüntülenir. **başarısız testler**, **testleri geçti**, **atlandı testleri** ve **çalışmıyor Testleri**. Test Gezgini görüntüler altındaki ayrıntılar bölmesini test özetini çalıştırın.

### <a name="view-test-details"></a>Test ayrıntıları görüntüle

Bir test ayrıntılarını görüntülemek için test'i seçin.

Test Ayrıntılar bölmesinde aşağıdaki bilgileri görüntüler:

- Kaynak dosya adı ve test yöntemi satır sayısı.

- Test durumu.

- Test yöntemi sürdüğü geçen süre.

Sınama başarısız olursa, Ayrıntılar bölmesinde de görüntüler:

- Test için birim test çerçevesi tarafından döndürülen ileti.

- Yığın izleme testi başarısız zaman.

### <a name="view-the-source-code-of-a-test-method"></a>Bir test yönteminin kaynak kodu görüntüleme

Visual Studio Düzenleyicisinde test yöntemi için kaynak kodunu görüntülemek için test seçin ve ardından **açık Test** kısayol menüsü veya tuşuna **F12**.

## <a name="organize-the-test-list"></a>Test listesini düzenleme

### <a name="group-tests"></a>Grup testleri

Varsayılan olarak, Test Gezgini testlerinizi alt düğümleri olarak görüntüler **başarısız testler**, **testleri geçti**, **atlandı testleri** ve **testleri değil Çalıştır**.

|||
|-|-|
|![Test Gezgini grubu düğmesini](../test/media/ute_groupby_btn.png "UTE_GroupBy_btn")|Bunları yürütme süresini tarafından testlerinizi gruplamak için açık **Group By** listesinde ve seçin **süresi**. Seçin **Test sonucu** özgün gruplandırmasına geçiş yapmak için.|

### <a name="search-and-filter-the-test-list"></a>Arama ve filtre test listesi

Çok sayıda testleri olduğunda tarafından belirtilen dize listesini filtrelemek için Test Gezgini arama kutusuna yazabilirsiniz. Arama dizesini girin önce Filtre listeden seçerek belirli dizeleri türleri için filtre kısıtlayabilirsiniz.

![Arama filtresi kategorileri](../test/media/ute_searchfilter.png)

## <a name="debug-unit-tests"></a>Birim testleri hata ayıklama

Test Gezgini, testleriniz için hata ayıklama oturumu başlatmak için kullanabilirsiniz. Kodunuz Visual Studio hata ayıklayıcısı ile sorunsuz bir şekilde Adımlama, İleri ve geri birim testleri ve test altındaki proje arasında alır. Hata ayıklama başlatmak için:

1. Visual Studio Düzenleyicisi'nde hata ayıklamak istediğiniz bir veya daha fazla test yöntemler bir kesme noktası ayarlayın.

    > [!NOTE]
    > Test yöntemleri herhangi bir sırada çalıştığından hata ayıklamak istediğiniz tüm test yöntemler kesme noktalarını ayarlayın.

1. Test Gezgini test yöntemleri seçin ve ardından **seçili Testlerde Hata Ayıkla** kısayol menüsünde.

Hata ayıklayıcı hakkında daha fazla bilgi için bkz: [Visual Studio'da hata ayıklamayı](../debugger/debugging-in-visual-studio.md).
