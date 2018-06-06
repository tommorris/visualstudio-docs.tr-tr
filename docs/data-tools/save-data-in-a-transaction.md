---
title: 'İzlenecek yol: Bir işlemde veri kaydetme'
ms.date: 09/08/2017
ms.topic: conceptual
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- System.Transactions namespace
- data [Visual Studio], saving in a transaction
- transactions, saving data
- Transactions namespace
- saving data
ms.assetid: 80260118-08bc-4b37-bfe5-9422ee7a1e4e
author: gewarren
ms.author: gewarren
manager: douge
ms.prod: visual-studio-dev15
ms.technology: vs-data-tools
ms.workload:
- data-storage
ms.openlocfilehash: c1f035fc56cd673f12ba694d6a94ec57aea1d93b
ms.sourcegitcommit: 58052c29fc61c9a1ca55a64a63a7fdcde34668a4
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/04/2018
ms.locfileid: "34745535"
---
# <a name="walkthrough-save-data-in-a-transaction"></a>İzlenecek yol: Bir işlemde veri kaydetme
Bu kılavuzu kullanarak bir işlemde veri kaydetme gösterilmiştir <xref:System.Transactions> ad alanı. Bu kılavuzda bir Windows Forms uygulaması oluşturacaksınız. Northwind örnek veritabanında iki tablo için bir veri kümesi oluşturmak için veri kaynağı Yapılandırma Sihirbazı'nı kullanacaksınız. Veri bağlama denetimleri için Windows formu ve bir TransactionScope içinde veritabanını güncelleştirmek BindingNavigator'ın Kaydet düğmesi için kod değiştireceksiniz ekleyeceksiniz.

## <a name="prerequisites"></a>Önkoşullar
Bu kılavuzda, SQL Server Express LocalDB ve Northwind örnek veritabanı kullanılır.

1.  SQL Server Express LocalDB yoksa, araçtan yüklemek [SQL Server Express indirme sayfası](https://www.microsoft.com/sql-server/sql-server-editions-express), aracılığıyla veya **Visual Studio yükleyicisi**. Visual Studio Yükleyicisi'nde, SQL Server Express LocalDB parçası olarak yüklenebilir **.NET masaüstü geliştirme** iş yükü veya tek bir bileşen olarak.

2.  Northwind örnek veritabanı, şu adımları izleyerek yükleyin:

    1. Visual Studio'da açın **SQL Server Nesne Gezgini** penceresi. (SQL Server Nesne Gezgini parçası olarak yüklü **veri depolama ve işleme** Visual Studio yükleyicisi iş yükündeki.) Genişletme **SQL Server** düğümü. Yerel veritabanı örneğinde sağ tıklatıp **yeni sorgu...** .

       Sorgu Düzenleyicisi penceresini açar.

    2. Kopya [Northwind Transact-SQL betiği](https://github.com/MicrosoftDocs/visualstudio-docs/blob/master/docs/data-tools/samples/northwind.sql?raw=true) panonuza. Bu T-SQL betiği sıfırdan Northwind veritabanı oluşturur ve veri ile doldurur.

    3. T-SQL betiği sorgu düzenleyicisine yapıştırın ve ardından **yürütme** düğmesi.

       Kısa bir süre sonra sorgu yürütme tamamlandıktan ve Northwind veritabanı oluşturulur.

## <a name="create-a-windows-forms-application"></a>Bir Windows Forms uygulaması oluşturma
 İlk adım oluşturmaktır bir **Windows Forms uygulaması**.

#### <a name="to-create-the-new-windows-project"></a>Yeni Windows projesi oluşturmak için

1. Visual Studio'da üzerinde **dosya** menüsünde, select **yeni**, **proje...** .

2. Genişletin **Visual C#** veya **Visual Basic** sol bölmesinde, ardından **Windows Masaüstü**.

3. Orta bölmede seçin **Windows Forms uygulaması** proje türü.

4. Proje adı **SavingDataInATransactionWalkthrough**ve ardından **Tamam**.

     **SavingDataInATransactionWalkthrough** projesi oluşturulur ve eklenen **Çözüm Gezgini**.

## <a name="create-a-database-data-source"></a>Veritabanı veri kaynağı oluşturma
 Bu adımı kullanan **veri kaynağı Yapılandırma Sihirbazı** dayalı bir veri kaynağı oluşturmak için `Customers` ve `Orders` Northwind örnek veritabanı tablolarında.

#### <a name="to-create-the-data-source"></a>Veri kaynağı oluşturmak için

1.  Üzerinde **veri** menüsünde, select **veri kaynaklarını Göster**.

2.  İçinde **veri kaynakları** penceresinde, seçin **yeni veri kaynağı Ekle** başlatmak için **veri kaynağı Yapılandırma Sihirbazı**.

3.  Üzerinde **bir veri kaynağı türü seç** ekran, select **veritabanı**ve ardından **sonraki**.

4.  Üzerinde **veri bağlantınızı seçin** aşağıdakilerden birini ekran yapın:

    -   Northwind örnek veritabanıyla kurulan veri bağlantısı aşağı açılan listede kullanılabilir durumdaysa bunu seçin.

         veya

    -   Seçin **yeni bağlantı** başlatmak için **Ekle/Değiştir bağlantı** iletişim kutusuna ve Northwind veritabanına bağlantı oluşturun.

5.  Veritabanınız bir parola gerektiriyorsa, hassas bilgileri Ekle ve ardından seçeneğini **sonraki**.

6.  Üzerinde **bağlantı dizesi için uygulama yapılandırma dosyasını kaydetmek** ekran, select **sonraki**.

7.  Üzerinde **veritabanı nesnelerini seçin** ekranında, **tabloları** düğümü.

8.  Seçin `Customers` ve `Orders` tablolar ve ardından **son**.

     **NorthwindDataSet** projenize eklenir ve `Customers` ve `Orders` tabloları görünür **veri kaynakları** penceresi.

## <a name="add-controls-to-the-form"></a>Forma denetimler ekleme
 Verilere bağlı denetimler konumundan öğeleri sürükleyerek oluşturabileceğiniz **veri kaynakları** formunuza penceresi.

#### <a name="to-create-data-bound-controls-on-the-windows-form"></a>Bağlama denetimleri Windows formunda veri oluşturmak için

-   İçinde **veri kaynakları** penceresinde genişletin **müşteriler** düğümü.

-   Ana sürükleyin **müşteriler** düğümden **veri kaynakları** penceresi üzerine **Form1**.

     A <xref:System.Windows.Forms.DataGridView> denetimi ve araç şeridinde (<xref:System.Windows.Forms.BindingNavigator>) kayıtları gezinmek için form üzerinde görüntülenir. A [NorthwindDataSet](../data-tools/dataset-tools-in-visual-studio.md), `CustomersTableAdapter`, <xref:System.Windows.Forms.BindingSource>, ve <xref:System.Windows.Forms.BindingNavigator> bileşen tepsisinde görünür.

-   İlgili sürükleyin **siparişleri** düğümü (ana **siparişleri** düğümü, ancak aşağıdaki ilgili alt tablo düğümü **faks** sütun) form üzerine  **CustomersDataGridView**.

     A <xref:System.Windows.Forms.DataGridView> formda görünür. Bir `OrdersTableAdapter` ve <xref:System.Windows.Forms.BindingSource> bileşen tepsisinde görünür.

## <a name="add-a-reference-to-the-systemtransactions-assembly"></a>System.Transactions derlemesine başvuru ekleyin
 İşlemleri kullanma <xref:System.Transactions> ad alanı. Bu nedenle onu elle eklemeniz gerekir system.transactions derleme proje başvurusu varsayılan olarak eklenmez.

#### <a name="to-add-a-reference-to-the-systemtransactions-dll-file"></a>System.Transactions DLL dosyasının bir başvuru eklemek için

1.  Üzerinde **proje** menüsünde, select **Başvuru Ekle**.

2.  Seçin **System.Transactions** (üzerinde **.NET** sekmesinde) ve ardından **Tamam**.

     Bir başvuru **System.Transactions** projeye eklenir.

## <a name="modify-the-code-in-the-bindingnavigators-saveitem-button"></a>BindingNavigator'ın saveItem düğmesi kodda değiştirme
 Formunuza bırakılan ilk tablo için varsayılan olarak kod eklenir `click` olayı Kaydet düğmesine <xref:System.Windows.Forms.BindingNavigator>. Ek tabloları güncelleştirmek için kod el ile eklemeniz gerekir. Bu kılavuzda, biz kodun dışına kaydet Kaydet varolan yeniden düzenle düğmesine tıklama olay işleyicisi. Ayrıca olup satır eklendiğinde veya silindiğinde uygun olarak belirli bir güncelleştirmeyi işlevselliği sağlamak için birkaç daha fazla yöntem oluşturuyoruz.

#### <a name="to-modify-the-auto-generated-save-code"></a>Otomatik olarak oluşturulan kodu kaydetme değiştirmek için

1.  Seçin **kaydetmek** düğmesini **CustomersBindingNavigator** (disket simgesiyle düğme).

2.  Değiştir `CustomersBindingNavigatorSaveItem_Click` aşağıdaki kod ile yöntemi:

     [!code-vb[VbRaddataSaving#4](../data-tools/codesnippet/VisualBasic/save-data-in-a-transaction_1.vb)]
     [!code-csharp[VbRaddataSaving#4](../data-tools/codesnippet/CSharp/save-data-in-a-transaction_1.cs)]

Değişiklikleri ilgili verileri için karşılaştırma sırasını aşağıdaki gibidir:

-   Alt kayıtları silin. (Bu durumda, kayıtlardan silme `Orders` tablo.)

-   Üst kayıtları silin. (Bu durumda, kayıtlardan silme `Customers` tablo.)

-   Üst kayıtlar ekleyin. (Bu durumda, kayıtları eklemek `Customers` tablo.)

-   Alt kayıtlar ekleyin. (Bu durumda, kayıtları eklemek `Orders` tablo.)

#### <a name="to-delete-existing-orders"></a>Varolan siparişleri silmek için

-   Aşağıdakileri ekleyin `DeleteOrders` yönteme **Form1**:

     [!code-vb[VbRaddataSaving#5](../data-tools/codesnippet/VisualBasic/save-data-in-a-transaction_2.vb)]
     [!code-csharp[VbRaddataSaving#5](../data-tools/codesnippet/CSharp/save-data-in-a-transaction_2.cs)]

#### <a name="to-delete-existing-customers"></a>Var olan müşteriler silmek için

-   Aşağıdakileri ekleyin `DeleteCustomers` yönteme **Form1**:

     [!code-vb[VbRaddataSaving#6](../data-tools/codesnippet/VisualBasic/save-data-in-a-transaction_3.vb)]
     [!code-csharp[VbRaddataSaving#6](../data-tools/codesnippet/CSharp/save-data-in-a-transaction_3.cs)]

#### <a name="to-add-new-customers"></a>Yeni müşteriler eklemek için

-   Aşağıdakileri ekleyin `AddNewCustomers` yönteme **Form1**:

     [!code-vb[VbRaddataSaving#7](../data-tools/codesnippet/VisualBasic/save-data-in-a-transaction_4.vb)]
     [!code-csharp[VbRaddataSaving#7](../data-tools/codesnippet/CSharp/save-data-in-a-transaction_4.cs)]

#### <a name="to-add-new-orders"></a>Yeni siparişleri eklemek için

-   Aşağıdakileri ekleyin `AddNewOrders` yönteme **Form1**:

     [!code-vb[VbRaddataSaving#8](../data-tools/codesnippet/VisualBasic/save-data-in-a-transaction_5.vb)]
     [!code-csharp[VbRaddataSaving#8](../data-tools/codesnippet/CSharp/save-data-in-a-transaction_5.cs)]

## <a name="run-the-application"></a>Uygulamayı çalıştırın

#### <a name="to-run-the-application"></a>Uygulamayı çalıştırmak için

-   Seçin **F5** uygulamayı çalıştırın.

## <a name="see-also"></a>Ayrıca bkz.

- [Nasıl yapılır: bir işlemi kullanarak veri kaydetme](../data-tools/save-data-by-using-a-transaction.md)
- [Verileri yeniden veritabanına kaydetme](../data-tools/save-data-back-to-the-database.md)