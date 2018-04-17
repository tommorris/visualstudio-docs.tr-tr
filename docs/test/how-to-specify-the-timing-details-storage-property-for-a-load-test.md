---
title: Visual Studio'da çalıştırma ayarı ayrıntıları depolama özelliğini bir yük testi için zamanlama | Microsoft Docs
ms.date: 10/19/2016
ms.topic: conceptual
helpviewer_keywords:
- load tests, properties
- load tests, run settings
ms.assetid: 867a9c21-0909-4963-bc02-d41e9393008c
author: gewarren
ms.author: gewarren
manager: douge
ms.technology: vs-ide-test
ms.openlocfilehash: 73e800893fe9d923ff3f119f6741b496feac4fb6
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/16/2018
---
# <a name="how-to-specify-the-timing-details-storage-property-for-a-load-test-run-setting"></a>Nasıl yapılır: Bir Yük Testi Çalışma Ayarı için Zamanlama Ayrıntıları Depolama Özelliğini Belirtme

Yük testi ile oluşturduktan sonra **Yeni Yük Testi Sihirbazı**, kullanabileceğiniz **Yük Testi Düzenleyicisi** test gereksinimlerini ve hedeflerinizi karşılamak için ayarları değiştirmek için.

Bir çalışma ayarın düzenleyebilirsiniz **zamanlama ayrıntıları depolama** özellik değerine **özellikleri** penceresi. **Zamanlama ayrıntıları depolama** özelliği aşağıdaki seçeneklerden birini ayarlanabilir:

-   **Tüm Bireysel Ayrıntılar:** toplar ve her bir test, işlem ve test sırasında verilen sayfa için tek tek zamanlama verileri depolar.

    > [!NOTE]
    > **Tüm Bireysel Ayrıntılar** seçeneği, yük testi sonuçlarında sanal kullanıcı veri bilgilerini etkinleştirmek için seçilmesi gerekir. Daha fazla bilgi için bkz: [Ayrıntılar görünümünde sanal kullanıcı etkinliğini çözümleme](../test/analyze-load-test-virtual-user-activity-in-the-details-view.md).

-   **Hiçbiri:** tüm bireysel zamanlama ayrıntıları toplamaz. Ancak, ortalama değerler hala kullanılabilir durumdadır.

-   **Yalnızca istatistikleri:** bağımsız zamanlama verilerini sadece yüzdelik veriler depolar. Bu alanı kaynakları kaydeder.

 **Zamanlama Ayrıntıları Depolama özelliğini dikkate alınacak noktalar**

 Varsa **zamanlama ayrıntıları depolama** özelliğinin etkin olduğundan ve her bir bireysel test, işlem ve sayfa yük testi sırasında yürütme süresi yük testi sonuçları deposunda depolanır. Bu testler, işlemleri ve sayfalar tablolarda Yük Testi Çözümleyicisi gösterilecek 90 ve 95 yüzdelik veri sağlar.

 Varsa **zamanlama ayrıntıları depolama** özelliği etkinse, ya da değerini ayarlayarak **StatisticsOnly** veya **AllIndividualDetails**, tüm sayfaları, tek tek testlerin ve işlem zaman aşımına uğradı ve bireysel zamanlama verisinden yüzdelik veri hesaplanır. İle farktır **StatisticsOnly** seçeneğini yüzdelik veri hesaplandıktan sonra veri deposundan silinen bireysel zamanlama. Bu zamanlama ayrıntıları kullanıldığında, deposunda gereken alan miktarını azaltır. Ancak, bu durumda, SQL araçları kullanarak zamanlama ayrıntı verilerini diğer yollarla işlemek isteyebilirsiniz **AllIndividualDetails** zamanlama ayrıntı verileri bu işlem için kullanılabilir olmasını sağlamak seçeneği kullanılmalıdır. Ayrıca, özelliği ayarlamak, **AllIndividualDetails**, sonra da yük testi tamamlandıktan sonra Yük Testi Çözümleyicisi sanal kullanıcı etkinlik grafiğini kullanarak sanal kullanıcı etkinliğini çözümleyebilirsiniz. Daha fazla bilgi için bkz: [Ayrıntılar görünümünde sanal kullanıcı etkinliğini çözümleme](../test/analyze-load-test-virtual-user-activity-in-the-details-view.md).

 Zamanlama Ayrıntıları verileri depolamak için yük testi sonuçları deposunda gereken alan miktarını özellikle daha uzun yük testleri için çok büyük olabilir. Aynı zamanda depoya veriler yük testi çalıştırma, tamamlanana kadar bu veriler üzerinde yük test aracılarını saklandığından sonuçları deposundaki yük testi sonunda uzun yük testi bu verileri depolamak için de, geçen süre. **Zamanlama ayrıntıları depolama** özelliği varsayılan olarak etkindir. Sınama ortamınız için bir sorun varsa ayarlamak isteyebilirsiniz **zamanlama ayrıntıları depolama** için **hiçbiri**.

 Zamanlama Ayrıntıları verileri çalışması sırasında LoadTestItemResults.dat dosyasında depolanır ve yük testi tamamlandıktan sonra denetleyiciye geri gönderilir. Uzun bir süre için çalıştıran bir yük testi için dosya boyutu büyük. Aracı makine üzerinde yeterli disk alanı yoksa, bu bir sorun olacaktır.

 Visual Studio yükleme testi önceki bir sürümünden bir proje yükseltme yapıyorsanız, tam ayrıntılı toplamayı etkinleştirmek için aşağıdaki yordamı kullanın.

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