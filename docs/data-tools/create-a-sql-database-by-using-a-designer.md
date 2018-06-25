---
title: Bir veritabanı dosyası oluşturma ve Visual Studio'da Tablo Tasarımcısı kullanma
ms.date: 11/03/2017
ms.topic: conceptual
helpviewer_keywords:
- database tables, creating
- database files, creating
- table designer
ms.assetid: 99c2b06f-47aa-414e-8057-a3453712fd23
author: gewarren
ms.author: gewarren
manager: douge
ms.prod: visual-studio-dev15
ms.technology: vs-data-tools
ms.workload:
- data-storage
ms.openlocfilehash: 5d21ba3f239bb4c5e3fdd1ba717b1288956b8550
ms.sourcegitcommit: 30f653d9625ba763f6b58f02fb74a24204d064ea
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/25/2018
ms.locfileid: "36756161"
---
# <a name="create-a-database-and-add-tables-in-visual-studio"></a>Bir veritabanı oluşturun ve Visual Studio'da tablolar ekleyin
Visual Studio oluşturmak ve SQL Server Express LocalDB yerel veritabanı dosyasında güncelleştirmek için kullanabilirsiniz. Transact-SQL deyimlerinde yürüterek bir veritabanı oluşturabilirsiniz **SQL Server Nesne Gezgini** Visual Studio'daki aracı. Bu konuda, oluşturacağız bir *.mdf* dosya ve Tablo Tasarımcısı kullanarak tablolar ile anahtarlar ekleyin.

## <a name="prerequisites"></a>Önkoşullar
Bu izlenecek yolu tamamlamak için isteğe bağlı olmalıdır **veri depolama ve işleme** Visual Studio'da yüklü iş yükü. Yüklemek için açık **Visual Studio yükleyicisi** ve **iş yükleri** sekmesi. Altında **Web ve bulut**, seçin **veri depolama ve işleme**. Seçin **Değiştir** iş yükü için Visual Studio eklemek için düğmeyi.

## <a name="create-a-project-and-a-local-database-file"></a>Proje ve bir yerel veritabanı dosyası oluşturma

### <a name="to-create-a-project-and-a-database-file"></a>Bir proje ve yerel veritabanı dosyası oluşturmak için
1.  Adlı bir Windows Forms projesi oluşturma `SampleDatabaseWalkthrough`.

2.  Menü çubuğunda seçin **proje** > **Yeni Öğe Ekle**.

3.  Öğe şablonları listesinde aşağı kaydırın ve seçin **hizmet tabanlı veritabanı**.

     ![Öğe şablonları iletişim kutusu](../data-tools/media/raddata-vsitemtemplates.png)

4.  Veritabanı adı **SampleDatabase**ve ardından **Ekle** düğmesi.

### <a name="to-add-a-data-source"></a>Bir veri kaynağı eklemek için
5.  Varsa **veri kaynakları** penceresi açık değilse, seçerek açın **Shift**+**Alt**+**D** anahtarları veya Menü çubuğunda, select **Görünüm** > **diğer pencereler** > **veri kaynakları**.

6.  İçinde **veri kaynakları** penceresinde, seçin **yeni veri kaynağı Ekle** bağlantı.

    **Veri kaynağı Yapılandırma Sihirbazı** açar.

7. Üzerinde **bir veri kaynağı türü seç** sayfasında, **veritabanı** ve ardından **sonraki**.

8. Üzerinde **bir veritabanı modeli seçin** sayfasında, **sonraki** varsayılan (veri kümesi) kabul etmek için.

9. Üzerinde **veri bağlantınızı** sayfasında, **SampleDatabase.mdf** aşağı açılan listede dosya ve ardından **sonraki**.

10. Üzerinde **bağlantı dizesini uygulama yapılandırma dosyasını Kaydet** sayfasında, **sonraki**.

11. Bir **veritabanı nesnelerini seçin** sayfası, veritabanı belirten bir ileti, tüm nesneler içermiyor göreceksiniz. Seçin **son**.

### <a name="to-view-properties-of-the-data-connection"></a>Veri bağlantısı özelliklerini görüntülemek için
Bağlantı dizesini görüntüleyebilirsiniz *SampleDatabase.mdf* veri bağlantısı Özellikler penceresini açarak dosyası:

-   Visual Studio'da seçin **Görünüm** > **SQL Server Nesne Gezgini** Bu pencere zaten açık değilse. Genişleterek Özellikler penceresini açmak **veri bağlantıları** için kısayol menüsünü açma düğümü *SampleDatabase.mdf*ve ardından seçerek **özellikleri**.

-   Alternatif olarak, seçebileceğiniz **Görünüm** > **Sunucu Gezgini**, bu pencereyi zaten açık değilse. Özellikler penceresini genişleterek açmak **veri bağlantıları** düğümü. Kısayol menüsünü açın *SampleDatabase.mdf*ve ardından **özellikleri**.

## <a name="create-tables-and-keys-by-using-table-designer"></a>Tablo Tasarımcısı kullanarak tablolar ile anahtarlar oluşturma
Bu bölümde, iki tablo, her bir tablo ve birkaç örnek veri satırı bir birincil anahtar oluşturmayı öğreneceksiniz. Ayrıca, bir tablodaki kayıtları kaydeder ve diğer tabloda nasıl karşılık belirtmek için yabancı anahtar oluşturacaksınız.

### <a name="to-create-the-customers-table"></a>Müşteriler tablosu oluşturmak için
1.  İçinde **Sunucu Gezgini** veya **SQL Server Nesne Gezgini**, genişletin **veri bağlantıları** düğümünü genişletin ve ardından **SampleDatabase.mdf**düğüm.

2.  Kısayol menüsünü açın **tabloları**ve ardından **Yeni Tablo Ekle**.

     **Tablo Tasarımcısı** açılır ve oluşturmakta olduğunuz tablo tek bir sütunda temsil eden bir varsayılan satır içeren bir kılavuz gösterir. Kılavuza satırlar ekleyerek, tabloda sütunlar ekleyeceksiniz.

3.  Kılavuzda, aşağıdaki girişlerin her biri için bir satır ekleyin:

    |Sütun adı|Veri türü|Null'lere izin ver|
    |-----------------|---------------|-----------------|
    |`CustomerID`|`nchar(5)`|False (işaretsiz)|
    |`CompanyName`|`nvarchar(50)`|False (işaretsiz)|
    |`ContactName`|`nvarchar (50)`|True (seçili)|
    |`Phone`|`nvarchar (24)`|True (seçili)|

4.  Kısayol menüsünü açın `CustomerID` satır ve ardından **birincil anahtarı ayarlama**.

5.  Varsayılan satır için kısayol menüsünü açın ve ardından **silmek**.

6.  Betik bölmesindeki ilk satırı aşağıdaki örnekle eşleşecek şekilde değiştirerek Müşteriler tablosunu adlandırın:

    ```sql
    CREATE TABLE [dbo].[Customers]
    ```

    Şöyle bir şey görmeniz gerekir:

    ![Tablo Tasarımcısı](../data-tools/media/raddata-table-designer.png)

7.  Sol üst köşesindeki **Tablo Tasarımcısı**seçin **güncelleştirme** düğmesi.

8.  İçinde **Önizleme veritabanı güncelleştirmeleri** iletişim kutusunda **güncelleştirme veritabanı** düğmesi.

    Değişiklikleriniz yerel veritabanı dosyasına kaydedildi.

### <a name="to-create-the-orders-table"></a>Siparişler tablosu oluşturmak için
1.  Başka bir tablo ekleyin ve sonra aşağıdaki tabloda her giriş için bir satır ekleyin:

    |Sütun adı|Veri türü|Null'lere izin ver|
    |-----------------|---------------|-----------------|
    |`OrderID`|`int`|False (işaretsiz)|
    |`CustomerID`|`nchar(5)`|False (işaretsiz)|
    |`OrderDate`|`datetime`|True (seçili)|
    |`OrderQuantity`|`int`|True (seçili)|

2.  Ayarlama **OrderID** birincil anahtar ve ardından Sil'i varsayılan satır olarak.

3.  Betik bölmesindeki ilk satırı aşağıdaki örnekle eşleşecek şekilde değiştirerek Siparişler tablosunu adlandırın:

    ```sql
    CREATE TABLE [dbo].[Orders]
    ```

4.  Sol üst köşesindeki **Tablo Tasarımcısı**seçin **güncelleştirme** düğmesi.

5.  İçinde **Önizleme veritabanı güncelleştirmeleri** iletişim kutusunda **güncelleştirme veritabanı** düğmesi.

    Değişiklikleriniz yerel veritabanı dosyasına kaydedildi.

### <a name="to-create-a-foreign-key"></a>Yabancı anahtar oluşturmak için
1.  Izgaranın sağ tarafındaki içerik bölmesinde için kısayol menüsünü açın **yabancı anahtarlar**ve ardından **yeni yabancı anahtar Ekle**, aşağıdaki çizimde gösterildiği gibi.

     ![Tablo Tasarımcısı'nda bir yabancı anahtar ekleme](../data-tools/media/foreignkey.png)

2.  Görüntülenen metin kutusunda, yerine **ToTable** ile `Customers`.

3.  T-SQL bölmesinde aşağıdaki örnekle eşleşmesi için son satırında güncelleştirin:

    ```sql
    CONSTRAINT [FK_Orders_Customers] FOREIGN KEY ([CustomerID]) REFERENCES [Customers]([CustomerID])
    ```

4.  Sol üst köşesindeki **Tablo Tasarımcısı**seçin **güncelleştirme** düğmesi.

5.  İçinde **Önizleme veritabanı güncelleştirmeleri** iletişim kutusunda **güncelleştirme veritabanı** düğmesi.

    Değişiklikleriniz yerel veritabanı dosyasına kaydedildi.

## <a name="populate-the-tables-with-data"></a>Tabloları verilerle doldurma

### <a name="to-populate-the-tables-with-data"></a>Tabloları veriyle doldurmak için

1.  İçinde **Sunucu Gezgini** veya **SQL Server Nesne Gezgini**, örnek veritabanı düğümünü genişletin.

2.  Kısayol menüsünü açın **tabloları** düğümü, select **yenileme**, genişletin ve ardından **tabloları** düğümü.

3.  Müşteriler tablosu için kısayol menüsünü açın ve ardından **Show Table Data**.

4.  Bazı müşteriler için istediğiniz veriyi ekleyin.

    Müşteri kimliklerini beş karakterli olarak istediğiniz gibi belirtebilirsiniz, ancak en azından bu yordamda daha sonra kullanmak üzere hatırlayabileceğiniz bir kimlik olmalıdır.

5.  Siparişler tablosundaki için kısayol menüsünü açın ve ardından **Show Table Data**.

6.  Bazı siparişler için verileri ekleyin.

    > [!IMPORTANT]
    > Tüm sipariş kimlikleri ve sipariş miktarları tamsayılar olduğunu ve her müşteri kimliği içinde belirtilen bir değerle eşleşen olun **CustomerID** müşteriler tablosunun sütun.

7.  Menü çubuğunda seçin **dosya** > **Tümünü Kaydet**.

## <a name="see-also"></a>Ayrıca bkz.

- [Visual Studio'da verilere erişime](accessing-data-in-visual-studio.md)