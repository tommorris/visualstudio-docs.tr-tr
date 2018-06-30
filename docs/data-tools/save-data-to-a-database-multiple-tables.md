---
title: Bir veritabanına (birden çok tablo) veri kaydetme
ms.date: 11/04/2016
ms.topic: conceptual
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- updating datasets, walkthroughs
- data [Visual Studio], saving
- saving data, walkthroughs
- data [Visual Studio], updating
ms.assetid: 7ebe03da-ce8c-4cbc-bac0-a2fde4ae4d07
author: gewarren
ms.author: gewarren
manager: douge
ms.prod: visual-studio-dev15
ms.technology: vs-data-tools
ms.workload:
- data-storage
ms.openlocfilehash: 08a2d3a0f8d629e1110316c3cf18c348fa31f445
ms.sourcegitcommit: d9e4ea95d0ea70827de281754067309a517205a1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/29/2018
ms.locfileid: "37117049"
---
# <a name="save-data-to-a-database-multiple-tables"></a>Bir veritabanına (birden çok tablo) veri kaydetme
En yaygın senaryolar uygulama geliştirme, bir Windows uygulaması formunda veri görüntüleme, verileri düzenleme ve güncelleştirilmiş verileri veritabanına geri göndermek için biridir. Bu kılavuzda iki ilgili tablolarındaki verileri görüntüleyen ve kaydını düzenlemek ve değişiklikleri veritabanına kaydetmek gösterilmektedir bir form oluşturur. Bu örnekte `Customers` ve `Orders` Northwind örnek veritabanı tablolarından.

 Çağırarak uygulamanızda veritabanına veri kaydedebilirsiniz `Update` bir TableAdapter yöntemi. Tablodan sürüklediğinizde **veri kaynakları** forma, verileri kaydetmek için gerekli olan kod penceresi otomatik olarak eklenir. Forma eklenen ek tabloları bu kodu el ile eklenmesi gerekir. Bu kılavuz birden fazla tablodan güncelleştirmeleri kaydetmek üzere kod eklemek nasıl gösterir.

> [!NOTE]
>  İletişim kutuları ve menü komutlarını gördüğünüz açıklanana Yardımı'nda etkin ayarlarınızı veya kullanmakta olduğunuz edition bağlı olarak farklı olabilir. Ayarlarınızı değiştirmek için tercih **içeri ve dışarı aktarma ayarları** üzerinde **Araçları** menüsü. Daha fazla bilgi için bkz: [Visual Studio IDE'yi kişiselleştirme](../ide/personalizing-the-visual-studio-ide.md).

 Bu örneklerde gösterilen görevler aşağıdakileri içerir:

-   Yeni bir oluşturma **Windows Forms uygulaması** projesi.

-   Oluşturma ve uygulamanızda ile bir veri kaynağını yapılandırma [veri kaynağı Yapılandırma Sihirbazı](../data-tools/media/data-source-configuration-wizard.png).

-   İçindeki öğelerin denetimleri ayarlama [veri kaynakları penceresi](add-new-data-sources.md). Daha fazla bilgi için bkz: [veri kaynakları penceresinden sürüklendiğinde oluşturulacak denetimini ayarlama](../data-tools/set-the-control-to-be-created-when-dragging-from-the-data-sources-window.md).

-   Verilere bağlı denetimler konumundan öğeleri sürükleyerek oluşturma **veri kaynakları** formunuza penceresi.

-   Birkaç kayıt kümesindeki her tabloda değiştirme.

-   Güncelleştirilen verileri bir veri kümesini veritabanına geri göndermek için kod değiştirme.

## <a name="prerequisites"></a>Önkoşullar
Bu kılavuzda, SQL Server Express LocalDB ve Northwind örnek veritabanı kullanılır.

1.  SQL Server Express LocalDB yoksa, araçtan yüklemek [SQL Server Express indirme sayfası](https://www.microsoft.com/sql-server/sql-server-editions-express), aracılığıyla veya **Visual Studio yükleyicisi**. Visual Studio Yükleyicisi'nde, SQL Server Express LocalDB parçası olarak yüklenebilir **veri depolama ve işleme** iş yükü veya tek bir bileşen olarak.

2.  Northwind örnek veritabanı, şu adımları izleyerek yükleyin:

    1. Visual Studio'da açın **SQL Server Nesne Gezgini** penceresi. (SQL Server Nesne Gezgini parçası olarak yüklü **veri depolama ve işleme** Visual Studio yükleyicisi iş yükündeki.) Genişletme **SQL Server** düğümü. Yerel veritabanı örneğinde sağ tıklatıp **yeni sorgu**.

       Sorgu Düzenleyicisi penceresini açar.

    2. Kopya [Northwind Transact-SQL betiği](https://github.com/MicrosoftDocs/visualstudio-docs/blob/master/docs/data-tools/samples/northwind.sql?raw=true) panonuza. Bu T-SQL betiği sıfırdan Northwind veritabanı oluşturur ve veri ile doldurur.

    3. T-SQL betiği sorgu düzenleyicisine yapıştırın ve ardından **yürütme** düğmesi.

       Kısa bir süre sonra sorgu yürütme tamamlandıktan ve Northwind veritabanı oluşturulur.

## <a name="create-the-windows-forms-application"></a>Windows Forms uygulaması oluşturma
 İlk adım oluşturmaktır bir **Windows Forms uygulaması**. Proje için bir ad atama sırasında bu adım isteğe bağlıdır, ancak projeye daha sonra kaydetmeniz çünkü biz bunu bir ad verin.

#### <a name="to-create-the-new-windows-forms-application-project"></a>Yeni Windows forms uygulaması projesi oluşturmak için

1. Visual Studio'da üzerinde **dosya** menüsünde, select **yeni** > **proje**.

2. Genişletin **Visual C#** veya **Visual Basic** sol bölmesinde, ardından **Windows Masaüstü**.

3. Orta bölmede seçin **Windows Forms uygulaması** proje türü.

4. Proje adı **UpdateMultipleTablesWalkthrough**ve ardından **Tamam**.

     **UpdateMultipleTablesWalkthrough** projesi oluşturulur ve eklenen **Çözüm Gezgini**.

## <a name="create-the-data-source"></a>Veri kaynağı oluşturun
 Bu adımı kullanarak Northwind veritabanı bir veri kaynağı oluşturur **veri kaynağı Yapılandırma Sihirbazı**. Northwind örnek veritabanı bağlantısı oluşturmak için erişimi olmalıdır. Northwind örnek veritabanı ayarlama hakkında daha fazla bilgi için bkz: [nasıl yapılır: örnek veritabanları yükleme](../data-tools/installing-database-systems-tools-and-samples.md).

#### <a name="to-create-the-data-source"></a>Veri kaynağı oluşturmak için

1.  Üzerinde **veri** menüsünde, select **veri kaynaklarını Göster**.

2.  İçinde **veri kaynakları** penceresinde, seçin**yeni veri kaynağı Ekle** başlatmak için **veri kaynağı Yapılandırma Sihirbazı**.

3.  Üzerinde **bir veri kaynağı türü seç** ekran, select **veritabanı**ve ardından **sonraki**.

4.  Üzerinde **veri bağlantınızı seçin** aşağıdakilerden birini ekran yapın:

    -   Northwind örnek veritabanıyla kurulan veri bağlantısı aşağı açılan listede kullanılabilir durumdaysa bunu seçin.

         veya

    -   Seçin **yeni bağlantı** açmak için **Ekle/Değiştir bağlantı** iletişim kutusu.

5.  Veritabanınız bir parola gerektiriyorsa, hassas bilgileri Ekle ve ardından seçeneğini **sonraki**.

6.  Üzerinde **bağlantı dizesi için uygulama yapılandırma dosyasını kaydetmek**seçin **sonraki**.

7.  Üzerinde **veritabanı nesnelerini seçin**ekranında, **tabloları** düğümü.

8.  Seçin **müşteriler** ve **siparişleri** tablolar ve ardından **son**.

     **NorthwindDataSet** projenize, eklenen ve tabloları görüntülenmesini **veri kaynakları** penceresi.

## <a name="set-the-controls-to-be-created"></a>Oluşturulması için denetimleri ayarlama
 Bu kılavuz, verileri `Customers` tablo bir **ayrıntıları** burada veri görüntülenir her denetim düzeni. Verileri `Orders` tablo bir **kılavuz** görüntülenen düzeni bir <xref:System.Windows.Forms.DataGridView> denetim.

#### <a name="to-set-the-drop-type-for-the-items-in-the-data-sources-window"></a>Veri kaynakları penceresinden öğeleri için açılan türünü ayarlamak için

1.  İçinde **veri kaynakları** penceresinde genişletin **müşteriler** düğümü.

2.  Üzerinde **müşteriler** düğümü, select **ayrıntıları** denetimi değiştirmek için Denetim listesinden **müşteriler** ayrı ayrı denetimler tabloya. Daha fazla bilgi için bkz: [veri kaynakları penceresinden sürüklendiğinde oluşturulacak denetimini ayarlama](../data-tools/set-the-control-to-be-created-when-dragging-from-the-data-sources-window.md).

## <a name="create-the-data-bound-form"></a>Veri bağlama formu oluşturma
 Verilere bağlı denetimler konumundan öğeleri sürükleyerek oluşturabileceğiniz **veri kaynakları** formunuza penceresi.

#### <a name="to-create-data-bound-controls-on-the-form"></a>Form üzerinde veri bağlama denetimleri oluşturmak için

1.  Ana sürükleyin **müşteriler** düğümden **veri kaynakları** penceresi üzerine **Form1**.

     Verilere bağlı denetimler tanımlayıcı etiketlerle görünür formdaki bir aracı Şerit birlikte (<xref:System.Windows.Forms.BindingNavigator>) kayıtları gezinme. A [NorthwindDataSet](../data-tools/dataset-tools-in-visual-studio.md), `CustomersTableAdapter`, <xref:System.Windows.Forms.BindingSource>, ve <xref:System.Windows.Forms.BindingNavigator> bileşen tepsisinde görünür.

2.  İlgili sürükleyin **siparişleri** düğümden **veri kaynakları** penceresi üzerine **Form1**.

    > [!NOTE]
    >  İlgili **siparişleri** düğümü altında bulunan **faks** sütun ve bir alt düğüm **müşteriler** düğümü.

     A <xref:System.Windows.Forms.DataGridView> denetimi ve araç şeridinde (<xref:System.Windows.Forms.BindingNavigator>) kayıtları gezinmek için form üzerinde görüntülenir. Bir `OrdersTableAdapter` ve <xref:System.Windows.Forms.BindingSource> bileşen tepsisinde görünür.

## <a name="add-code-to-update-the-database"></a>Veritabanını güncelleştirmek için kodu ekleyin
 Veritabanı çağırarak güncelleştirebilirsiniz `Update` yöntemlerinin **müşteriler** ve **siparişleri** TableAdapters. Varsayılan olarak, bir olay işleyicisi için **kaydetmek** düğmesine<xref:System.Windows.Forms.BindingNavigator> veritabanına güncelleştirmeleri göndermek için formun kodu eklenir. Bu yordamı doğru sırayla güncelleştirmeleri göndermek için kod değiştirir. Bu başvuru bütünlüğü hataları oluşturma olasılığını ortadan kaldırır. Kod Ayrıca güncelleştirme çağrısında bir try-catch bloğu içinde kaydırma tarafından işleme hatası uygular. Uygulamanızın gereksinimlerine uyacak şekilde kodu değiştirebilirsiniz.

> [!NOTE]
>  Daha anlaşılır olması için bu kılavuzu bir işlem kullanmaz. Ancak, iki güncelleştiriliyor veya daha fazla ilişkili tablo, bir işlem içinde tüm güncelleştirme mantığını içerir. Bir işlem, tüm değişiklikler kaydedilmeden önce tüm ilgili değişiklikleri veritabanına başarılı sağlar bir işlemdir. Daha fazla bilgi için bkz: [işlemleri ve eşzamanlılık](/dotnet/framework/data/adonet/transactions-and-concurrency).

#### <a name="to-add-update-logic-to-the-application"></a>Uygulama güncelleştirme mantığı eklemek için

1.  Seçin **kaydetmek** düğmesini <xref:System.Windows.Forms.BindingNavigator>. Kod Düzenleyicisi açılır `bindingNavigatorSaveItem_Click` olay işleyicisi.

2.  Çağrılacak olay işleyicisi kodla `Update` ilgili TableAdapters yöntemleri. Aşağıdaki kod önce her kullanıcının güncelleştirilmiş bilgilerini tutmak için üç geçici veri tabloları oluşturur <xref:System.Data.DataRowState> (<xref:System.Data.DataRowState.Deleted>, <xref:System.Data.DataRowState.Added>, ve <xref:System.Data.DataRowState.Modified>). Daha sonra güncelleştirmeleri doğru sırada çalıştırılır. Kod aşağıdaki gibi görünmelidir:

     [!code-vb[VbRaddataSaving#10](../data-tools/codesnippet/VisualBasic/save-data-to-a-database-multiple-tables_1.vb)]
     [!code-csharp[VbRaddataSaving#10](../data-tools/codesnippet/CSharp/save-data-to-a-database-multiple-tables_1.cs)]

## <a name="test-the-application"></a>Uygulamayı test etme

#### <a name="to-test-the-application"></a>Uygulamayı test etmek için

1.  Seçin **F5**.

2.  Bir veya daha fazla kayıt her tabloda veri bazı değişiklikler yapın.

3.  Seçin **kaydetmek** düğmesi.

4.  Değişiklikler kaydedildi doğrulamak için veritabanında değerlerini denetleyin.


## <a name="see-also"></a>Ayrıca bkz.

- [Verileri yeniden veritabanına kaydetme](../data-tools/save-data-back-to-the-database.md)