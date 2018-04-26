---
title: Visual Studio'da Test yük sanal kullanıcılar için tüm ayrıntıları toplamak
ms.date: 10/19/2016
ms.topic: conceptual
helpviewer_keywords:
- load tests, virtual user activity chart, configuring
- virtual user activity chart, configuring
ms.assetid: cb22e43b-af4d-4e09-9389-3c3fa00786f7
author: gewarren
ms.author: gewarren
manager: douge
ms.prod: visual-studio-dev15
ms.technology: vs-ide-test
ms.openlocfilehash: cac171d6f0e1bcd91a89be799497b84dc15fc5a5
ms.sourcegitcommit: e13e61ddea6032a8282abe16131d9e136a927984
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/26/2018
---
# <a name="how-to-configure-load-tests-to-collect-full-details-to-enable-virtual-user-activity-in-test-results"></a>Nasıl yapılır: Test Sonuçlarında Sanal Kullanıcı Etkinliğini Etkinleştirmek için Tüm Ayrıntıları Toplamak Üzere Yük Testlerini Yapılandırma

Yük testi için Sanal Kullanıcı Etkinlik Grafiği kullanmak için tüm ayrıntıları toplamak üzere yük testlerini yapılandırmanız gerekir. Bunu yapmak için yük testi yapılandırmak için seçin **Tüm Bireysel Ayrıntılar** ayarını **zamanlama ayrıntıları depolama** yük testi ile ilişkili özelliği. Bu modda, yük testi her test, sayfa ve işlem hakkında ayrıntılı bilgi toplar.

 Visual Studio yükleme testi önceki bir sürümünden bir proje yükseltme yapıyorsanız, tam ayrıntılı toplamayı etkinleştirmek için aşağıdaki yordamda adımları kullanın.

 **Tüm Bireysel Ayrıntılar** ayarını **zamanlama ayrıntıları depolama** özelliği aşağıdaki seçeneklerden birini ayarlanabilir:

-   **Tüm Bireysel Ayrıntılar:** toplar ve her bir test, işlem ve test sırasında verilen sayfa için tek tek zamanlama verileri depolar.

    > [!NOTE]
    > **Tüm Bireysel Ayrıntılar** seçeneği, yük testi sonuçlarında sanal kullanıcı veri bilgilerini etkinleştirmek için seçilmesi gerekir.

-   **Hiçbiri:** tüm bireysel zamanlama ayrıntıları toplamaz. Ancak, ortalama değerler hala kullanılabilir durumdadır.

-   **Yalnızca istatistikleri:** bağımsız zamanlama verilerini sadece yüzdelik veriler depolar. Bu alanı kaynakları kaydeder.

## <a name="to-configure-the-timing-details-storage-property-in-a-load-test"></a>Bir yük testinde zamanlama ayrıntıları depolama özelliğini yapılandırmak için

1.  Bir yük testi Yük Testi Düzenleyicisi'nde açın.

2.  Genişletme **çalıştırma ayarları** yük testi düğümünde.

3.  Örneğin, yapılandırmak istediğiniz çalıştırma ayarlarını seçin **çalıştırma Ayarları1 [etkin]**.

4.  Özellikler penceresini açın. Üzerinde **Görünüm** menüsünde, select **Özellikler penceresini**.

5.  Altında **sonuçları** kategorisi seçin **zamanlama ayrıntıları depolama** özelliği ve select **Tüm Bireysel Ayrıntılar**.

     Yapılandırdıktan sonra **Tüm Bireysel Ayrıntılar** ayarını **zamanlama ayrıntıları depolama** özelliği, yük testlerini çalıştırın ve Sanal Kullanıcı Etkinlik Grafiği görüntüleyin. Daha fazla bilgi için bkz: [nasıl yapılır: çözümleme ne sanal kullanıcıların olan yapılması sırasında bir yük testi](../test/how-to-analyze-virtual-user-activity-during-a-load-test.md).

## <a name="see-also"></a>Ayrıca bkz.

- [Ayrıntılar görünümünde sanal kullanıcı etkinliğini çözümleme](../test/analyze-load-test-virtual-user-activity-in-the-details-view.md)
- [İzlenecek yol: sorunları yalıtmak için sanal kullanıcı etkinlik grafiğini kullanma](../test/walkthrough-use-the-virtual-user-activity-chart-to-isolate-issues.md)