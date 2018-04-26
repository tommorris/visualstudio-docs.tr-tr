---
title: Microsoft Excel kullanarak Visual Studio Yük testi başarım raporları oluşturma
ms.date: 10/19/2016
ms.topic: conceptual
helpviewer_keywords:
- load tests, creating Excel reports
- load tests, reporting
ms.assetid: b87fb196-9973-4512-a924-088788def4ea
author: gewarren
ms.author: gewarren
manager: douge
ms.prod: visual-studio-dev15
ms.technology: vs-ide-test
ms.openlocfilehash: b82a35ed56c0930b8d9c0ff8ec7bfcbd008a7648
ms.sourcegitcommit: e13e61ddea6032a8282abe16131d9e136a927984
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/26/2018
---
# <a name="how-to-create-load-test-performance-reports-using-microsoft-excel"></a>Nasıl yapılır: Microsoft Excel Kullanarak Yük Testi Başarım Raporları Oluşturma

İki veya daha fazla test sonuçlarına bağlı Microsoft Excel yük testi raporları oluşturabilirsiniz. Yük testi raporları iki tür mevcuttur:

-   **Karşılaştırma çalıştırmak** bu tabloları ve çubuk grafikler kullanarak iki yük testi sonuçlarını verilerden karşılaştıran bir rapor kümesini oluşturur.

-   **Eğilim** eğilim analizi iki veya daha fazla yük testi sonuçlarını oluşturabilirsiniz. Çizgi grafikler kullanarak sonuçları görüntülenir, ancak veri pivot tablolarda kullanılabilir.

> [!TIP]
> Microsoft Word raporları, Özet görünümü, grafikler görünümünde ve Tablolar görünümünde veri kopyalama ve yapıştırma el ile de oluşturabilirsiniz. Bkz: [nasıl yapılır: Microsoft Word kullanılarak bir yük testi başarım raporunu el ile oluşturmanız](../test/how-to-manually-create-a-load-test-performance-report-using-microsoft-word.md).

 Her iki raporu Paydaşlar ile performans verileri paylaşabilir ve genel performans ve sistem durumunu mdan olup olmadığını daha iyi iletmek için kullanılan ya da daha da kötüsü.

 Rapor tanımları yük testi veritabanında depolanır. Bir rapor kaydedildiğinde, rapor tanımı veritabanına kaydedilir ve daha sonra yeniden kullanılabilir.

 Ayrıca, böylece Paydaşlar raporu görmek için veritabanına bağlanmak zorunda değilsiniz Excel çalışma kitabı Paydaşlar ile paylaşılabilir.

> [!NOTE]
> Excel çalışma kitabı paylaşabilirsiniz; Ancak, yalnızca Visual Studio'nun kendi makinede yüklü olan kullanıcıların elektronik tablolarda değiştirmek mümkün olacaktır. Diğer kullanıcıların görmezsiniz **yük testi raporu** Office Şerit seçeneğinde, ancak çalışma kitabını görüntülemek mümkün olacaktır.

 Aşağıdaki çizimde, Reddet işlem (güncelleştirme Sepeti) hız ve (% işlemci) sayacın degeneration arasında bir bağıntı gösteren bir rapor örneğidir. Bu, veritabanı veya ağ yerine uygulama kodundaki olası bir soruna işaret ve ASP.NET Profil Oluşturucu kullanarak tanılamak için iyi bir adaydır.

 ![Olası sorun uygulama kodundaki](../test/media/lt_excel.png "LT_Excel")

 Excel raporları ya da oluşturulabilir Yük Testi Çözümleyicisi kullanarak **Excel Raporu Oluştur** kullanarak düğmesi araç çubuğunda veya Excel'den **yük testi raporu** seçeneğini **yük testi**  Office Şerit sekmesi.

> [!NOTE]
> Bir yük testine açıklama eklerseniz, Excel raporunda görünürler. Daha fazla bilgi için bkz: [nasıl yapılır: yük testi tamamlandı Çözümleme sırasında açıklamaları ekleme](../test/how-to-add-comments-on-a-completed-load-test.md).

## <a name="to-generate-load-test-comparison-reports-using-excel"></a>Excel kullanarak yük testi karşılaştırma raporları oluşturmak için

1.  Rapor oluşturmadan önce bir yük testi çalıştırmanız gerekir.

2.  Excel yük testi raporları iki yolla oluşturabilirsiniz:

    1.  İçinde bir yük testi tamamladıktan sonra **yük testi sonuçlarını** sayfasında, **Excel Raporu Oluştur** araç çubuğu düğmesi.

        > [!NOTE]
        > Varsa **Excel Raporu Oluştur** Web Performans Testi Sonuçları Görüntüleyicisi araç çubuğunda düğmesi devre dışı, Microsoft Excel'i çalıştırmak gerekebilir etkinleştirmeden önce zaman. Visual Studio Enterprise yük testi eklentisi bilgisayarınıza Visual Studio Enterprise yüklendiğinde, Microsoft Excel için kopyalanır; Ancak, Microsoft Excel eklenti için yükleme işlemini tamamlamak için çalıştırmanız gerekir.

     Microsoft Excel açılır **bir yük testi raporu oluşturmak** Sihirbazı.

     -veya-

    1.  Microsoft Excel'ni açın, **yük testi** sekmesinde Office şeritte ve ardından **yük testi raporu**.

         **Bir yük testi raporu oluşturmak** Sihirbazı görünür.

    2.  İçinde **yük testleri içeren veritabanı seçme** sayfasında **sunucu adı**, yük testi sonuçlarını içeren sunucunun adını yazın.

    3.  İçinde **Databasename** aşağı açılan listesinde, yük testi sonuçlarını içeren veritabanı seçin.

3.  İçinde **nasıl raporunuzu oluşturmak istiyorsunuz** sayfasında, **bir rapor oluşturmak** seçilir ve seçin **sonraki**.

4.  İçinde **oluşturmak istediğiniz rapor türünü** sayfasında, **karşılaştırma çalıştırmak** seçilir ve seçin **sonraki**.

5.  İçinde **Enter yük testi rapor ayrıntılarını** sayfasında, rapor için bir ad yazın **rapor adı**.

6.  İstediğiniz rapor oluşturmak ve seçmek için yük testi seçin **sonraki**.

7.  İçinde **raporunuz için çalıştırmaları seçin** sayfasında **seçmek için bir rapor eklemek için bir veya daha fazla çalıştığında**seçin iki yük seçin ve raporu karşılaştırması istediğiniz test sonuçları **İleri**.

    > [!NOTE]
    > Yalnızca iki yük testi sonuçlarını bir karşılaştırma raporu oluşturabilirsiniz. Ya da bir yük testi sonuç seçin veya ikiden daha fazla yük testi sonuçları, bir uyarı iletisi görüntülenir.

8.  İçinde **raporunuzun sayaçları seçin** sayfasında **seçin veya daha fazla sayaç rapora eklemek için** genişletilebilir bir sayaç listesi raporunuzu özelleştirmek kullanılabilir. Seçin ve raporu iki seçili test çalıştırmalarında karşılaştırmak istediğiniz sayaçları seçin **son**.

9. Excel çalışma kitabı raporu aşağıdaki elektronik tablo sekmeleriyle oluşturulur:

    -   **İçindekiler tablosu** - yük testi rapor adını görüntüler ve içindekiler tablosu rapordaki çeşitli sekmelere bağlantılar sağlar.

    -   **Çalışan -** üzerinde iki çalışması karşılaştırıldığı raporda ayrıntıları sağlar.

    -   **Test Karşılaştırması -** performans gerileme ve geliştirmeleri Karşılaştırılan iki çalıştırmaları arasında çubuk grafiği ayrıntıları sağlar.

    -   **Sayfa karşılaştırması -** çubuk grafik ve yüzdesi performans test çalıştırmalarında çeşitli sayfalarında iki çalıştırmaları arasında karşılaştırma verileri sağlar.

    -   **Makine karşılaştırması -** kullanılan makinelere göre iki çalıştırmaları arasında karşılaştırma verileri sağlar.

    -   **Hata karşılaştırması -** iki çalıştırır ve yineleme sayısı arasında karşılaşılan hata türleri karşılaştırır.

    > [!TIP]
    > Yük testleri ve daha zengin raporlar etkinleştir Web performans testleri daha iyi raporlar için çeşitli özellikler kullanılabilir. Sayfa isteği raporlarda sunulan iki özelliklere sahiptir: hedef ve raporlama adı. Sayfası yanıt sürelerini hedefe yönelik bildirilir ve raporlama adı raporlarında URL yerine kullanılır. Yük testi çalıştırma ayarları, sayaç kümelerini Yönet bilgisayar etiketleri özelliği rapor makina adlarında sunulur. Bu rapor, belirli bir makine rolü tanımlamak faydalıdır.

## <a name="to-generate-load-test-trend-reports-using-excel"></a>Excel kullanarak yük testi Eğilim raporları oluşturmak için

1.  Rapor oluşturmadan önce bir yük testi çalıştırmanız gerekir.

2.  Excel yük testi raporları iki yolla oluşturabilirsiniz:

    1.  İçinde bir yük testi tamamladıktan sonra **yük testi sonuçlarını** sayfasında, **Excel Raporu Oluştur** araç çubuğu düğmesi.

        > [!NOTE]
        > Varsa **Excel Raporu Oluştur** Web Performans Testi Sonuçları Görüntüleyicisi araç çubuğunda düğmesi devre dışı, Microsoft Excel'i çalıştırmak gerekebilir etkinleştirmeden önce zaman. Visual Studio Enterprise yük testi eklentisi bilgisayarınıza Visual Studio Enterprise yüklendiğinde, Microsoft Excel için kopyalanır; Ancak, Microsoft Excel eklenti için yükleme işlemini tamamlamak için çalıştırmanız gerekir.

     Microsoft Excel açılır **bir yük testi raporu oluşturmak** Sihirbazı.

     -veya-

    1.  Microsoft Excel'ni açın, **yük testi** sekmesinde Office şeritte ve ardından **yük testi raporu**.

         **Bir yük testi raporu oluşturmak** Sihirbazı görünür.

    2.  İçinde **yük testleri içeren veritabanı seçme** sayfasında **sunucu adı**, yük testi sonuçlarını içeren sunucunun adını yazın.

    3.  İçinde **Databasename** aşağı açılan listesinde, yük testi sonuçlarını içeren veritabanı seçin.

3.  İçinde **nasıl raporunuzu oluşturmak istiyorsunuz** sayfasında, **bir rapor oluşturmak** seçilir ve seçin **sonraki**.

4.  İçinde **oluşturmak istediğiniz rapor türünü** sayfasında, **eğilim** seçilir ve seçin **sonraki**.

5.  İçinde **Enter yük testi rapor ayrıntılarını** sayfasında, rapor için bir ad yazın **rapor adı**.

6.  İstediğiniz rapor oluşturmak ve seçmek için yük testi seçin **sonraki**.

7.  İçinde **raporunuz için çalıştırmaları seçin** sayfasında **seçmek için bir rapor eklemek için bir veya daha fazla çalıştığında**, seçin ve raporu karşılaştırması istediğiniz yük testi sonuçlarını seçin **İleri**.

8.  İçinde **raporunuzun sayaçları seçin** sayfasında **seçin veya daha fazla sayaç rapora eklemek için**, Genişletilebilir bir sayaç listesi raporunuzu özelleştirmek kullanılabilir. Eğilim analizi için karşılaştırır ve seçmek istediğiniz sayaçları seçin **son**.

10. Rapor raporda oluşturulan çeşitli Excel çalışma kitabı sekmelerine bağlantılara sahip olan bir içindekiler tablosu ile oluşturulur. Bağlantılar eğilimi rapor için seçilen sayaçları temel alır. 7. adımda seçilen varsayılan sayaçları bırakılırsa, örneğin, ardından raporu sunulan veri 7. adımda listelenen her sayaç için Excel'de ayrı sekmeler oluşturur. Her sayaç için oluşturulan veri eğilimi stili grafiklerde sunulur.

    > [!TIP]
    > Yük testleri ve daha zengin raporlar etkinleştir Web performans testleri daha iyi raporlar için çeşitli özellikler kullanılabilir. Sayfa isteği raporlarda sunulan iki özelliklere sahiptir: hedef ve raporlama adı. Sayfası yanıt sürelerini hedefe yönelik bildirilir ve raporlama adı raporlarında URL yerine kullanılır. Yük testi çalıştırma ayarları, sayaç kümelerini Yönet bilgisayar etiketleri özelliği rapor makina adlarında sunulur. Bu rapor, belirli bir makine rolü tanımlamak faydalıdır.

## <a name="net-framework-security"></a>.NET Framework Güvenliği

Yük testi sonuçları ve raporları bilgisayarınıza veya ağınıza yönelik bir saldırı oluşturmak için kullanılabilecek olası hassas bilgileri içerir. Yük testi sonuçları ve raporları bilgisayar adları ve bağlantı dizeleri içerir. Ne zaman bunun farkında olmalıdır yük testi raporları diğer kişilerle paylaşın.

## <a name="see-also"></a>Ayrıca bkz.

- [Yük testi sonuçlarını raporlama Test karşılaştırmaları veya eğilim analizleri için](../test/compare-load-test-results.md)