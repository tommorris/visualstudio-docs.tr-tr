---
title: "Formlar arasında veri iletmek | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- walkthroughs [Windows Forms], data
- walkthroughs [Visual Studio], data
- data [Visual Studio], passing between forms
- forms, passing data between
- Windows Forms, walkthroughs
ms.assetid: 78bf038b-9296-4fbf-b0e8-d881d1aff0df
caps.latest.revision: "14"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.technology: vs-data-tools
ms.openlocfilehash: f401224657e64922fc9f6102a33eaf1cf824a556
ms.sourcegitcommit: ec1c7e7e3349d2f3a4dc027e7cfca840c029367d
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/07/2017
---
# <a name="pass-data-between-forms"></a>Formlar arasında veri geçirme
Bu kılavuz, verileri bir biçimden diğerine geçirmek için adım adım yönergeler sağlar. Northwind siparişleri tablolardan ve müşteriler kullanarak, bir form kullanıcıların bir müşteri seçmesine izin verir ve seçilen müşterinin siparişleri ikinci bir form görüntüler. Bu kılavuzda ilk formundan verileri alan ikinci form üzerinde bir yöntem oluşturulacağını gösterir.  
  
> [!NOTE]
>  Bu anlatımda formlar arasında veri iletmek için yalnızca bir şekilde gösterilir. Bir ortak özellik oluşturma verilerle ilk formundan ayarlanabilir veya bir forma veri almak için ikinci bir oluşturucu oluşturma dahil olmak üzere, veri geçirme için diğer seçenekleri vardır.  
  
 Bu örneklerde gösterilen görevler aşağıdakileri içerir:  
  
-   Yeni bir oluşturma **Windows Forms uygulaması** projesi.  
  
-   Oluşturma ve yapılandırma ile dataset [veri kaynağı Yapılandırma Sihirbazı](../data-tools/media/data-source-configuration-wizard.png).  
  
-   Öğelerden sürüklendiğinde form üzerinde oluşturulacak denetim seçme **veri kaynakları** penceresi. Daha fazla bilgi için bkz: [veri kaynakları penceresinden sürüklendiğinde oluşturulacak denetimini ayarlama](../data-tools/set-the-control-to-be-created-when-dragging-from-the-data-sources-window.md).  
  
-   Veri bağlama denetimi konumundan öğeleri sürükleyerek oluşturma **veri kaynakları** forma penceresi.  
  
-   İkinci bir form verileri görüntülemek için bir kılavuz oluşturuluyor.  
  
-   Belirli bir müşteri için siparişleri getirmek için bir TableAdapter sorgu oluşturma.  
  
-   Formlar arasında veri geçirme.  
  
## <a name="prerequisites"></a>Önkoşullar  
Bu kılavuzda, SQL Server Express LocalDB ve Northwind örnek veritabanı kullanılır.  
  
1.  SQL Server Express LocalDB yoksa, araçtan yüklemek [SQL Server sürümleri indirme sayfasına](https://www.microsoft.com/en-us/server-cloud/Products/sql-server-editions/sql-server-express.aspx), aracılığıyla veya **Visual Studio yükleyicisi**. Visual Studio Yükleyicisi'nde, SQL Server Express LocalDB parçası olarak yüklenebilir **veri depolama ve işleme** iş yükü veya tek bir bileşen olarak.  
  
2.  Northwind örnek veritabanı, şu adımları izleyerek yükleyin:  

    1. Visual Studio'da açın **SQL Server Nesne Gezgini** penceresi. (SQL Server Nesne Gezgini parçası olarak yüklü **veri depolama ve işleme** Visual Studio yükleyicisi iş yükündeki.) Genişletme **SQL Server** düğümü. Yerel veritabanı örneğinde sağ tıklatıp **yeni sorgu...** .  

       Sorgu Düzenleyicisi penceresini açar.  

    2. Kopya [Northwind Transact-SQL betiği](https://github.com/MicrosoftDocs/visualstudio-docs/blob/master/docs/data-tools/samples/northwind.sql?raw=true) panonuza. Bu T-SQL betiği sıfırdan Northwind veritabanı oluşturur ve veri ile doldurur.  

    3. T-SQL betiği sorgu düzenleyicisine yapıştırın ve ardından **yürütme** düğmesi.  

       Kısa bir süre sonra sorgu yürütme tamamlandıktan ve Northwind veritabanı oluşturulur.  
  
## <a name="create-the-windows-forms-application"></a>Windows Forms uygulaması oluşturma  
  
#### <a name="to-create-the-new-windows-project"></a>Yeni Windows projesi oluşturmak için  
  
1. Visual Studio'da üzerinde **dosya** menüsünde, select **yeni**, **proje...** .  
  
2. Genişletin **Visual C#** veya **Visual Basic** sol bölmesinde, ardından **Windows Klasik Masaüstü**.  

3. Orta bölmede seçin **Windows Forms uygulaması** proje türü.  

4. Proje adı **PassingDataBetweenForms**ve ardından **Tamam**. 
  
     **PassingDataBetweenForms** projesi oluşturulur ve eklenen **Çözüm Gezgini**.  
  
## <a name="create-the-data-source"></a>Veri kaynağı oluşturun  
  
#### <a name="to-create-the-data-source"></a>Veri kaynağı oluşturmak için  
  
1.  Üzerinde **veri** menüsünde tıklatın **veri kaynaklarını Göster**.  
  
2.  İçinde **veri kaynakları** penceresinde, seçin **yeni veri kaynağı Ekle** başlatmak için **veri kaynağı yapılandırması** Sihirbazı.  
  
3.  Seçin **veritabanı** üzerinde **bir veri kaynağı türü seç** sayfasında ve ardından **sonraki**.  
  
4.  Üzerinde **bir veritabanı modeli seçin** sayfasında, **Dataset** belirtilir ve ardından **sonraki**.  
  
5.  Üzerinde **veri bağlantınızı seçin** sayfasında, aşağıdakilerden birini yapın:  
  
    -   Northwind örnek veritabanıyla kurulan veri bağlantısı aşağı açılan listede kullanılabilir durumdaysa bunu seçin.  
  
    -   Seçin **yeni bağlantı** başlatmak için **Ekle/Değiştir bağlantı** iletişim kutusu.  
  
6.  Veritabanınız bir parola gerektirir ve hassas verileri içerecek şekilde seçeneği etkinse, seçeneğini belirleyin ve ardından **sonraki**.  
  
7.  Üzerinde **bağlantı dizesi için uygulama yapılandırma dosyasını kaydetmek** sayfasında, **sonraki**.  
  
8.  Üzerinde **veritabanı nesnelerini seçin** sayfasında **tabloları** düğümü.  
  
9. Seçin **müşteriler** ve **siparişleri** tablolar ve ardından **son**.  
  
     **NorthwindDataSet** projenize, eklenen ve **müşteriler** ve **siparişleri** tabloları görünür **veri kaynakları** penceresi.  
  
## <a name="create-the-first-form-form1"></a>İlk form (Form1) oluşturun  
 Veri bağlama kılavuz oluşturabilirsiniz (bir <xref:System.Windows.Forms.DataGridView> denetimi), sürükleyerek **müşteriler** düğümden **veri kaynakları** forma penceresi.  
  
#### <a name="to-create-a-data-bound-grid-on-the-form"></a>Veri bağlama kılavuz formda oluşturmak için  
  
-   Ana sürükleyin **müşteriler** düğümden **veri kaynakları** penceresi üzerine **Form1**.  
  
     A <xref:System.Windows.Forms.DataGridView> ve araç şeridinde (<xref:System.Windows.Forms.BindingNavigator>) kayıtları gezinmek için görünür **Form1**. A [NorthwindDataSet](../data-tools/dataset-tools-in-visual-studio.md), TableAdapter, <xref:System.Windows.Forms.BindingSource>, ve <xref:System.Windows.Forms.BindingNavigator> bileşen tepsisinde görünür.  
  
## <a name="create-the-second-form-form2"></a>İkinci form (Form2) oluşturun  
  
#### <a name="to-create-a-second-form-to-pass-the-data-to"></a>Verileri geçirmek için ikinci bir form oluşturmak için  
  
1.  Gelen **proje** menüsünde seçin **Add Windows Form**.  
  
2.  Varsayılan adı bırakın **Form2**, tıklatıp **Ekle**.  
  
3.  Ana sürükleyin **siparişleri** düğümden **veri kaynakları** penceresi üzerine **Form2**.  
  
     A <xref:System.Windows.Forms.DataGridView> ve araç şeridinde (<xref:System.Windows.Forms.BindingNavigator>) kayıtları gezinmek için görünür **Form2**. A [NorthwindDataSet](../data-tools/dataset-tools-in-visual-studio.md), TableAdapter, <xref:System.Windows.Forms.BindingSource>, ve <xref:System.Windows.Forms.BindingNavigator> bileşen tepsisinde görünür.  
  
4.  Silme **OrdersBindingNavigator** bileşen gelen.  
  
     **OrdersBindingNavigator** kaybolur **Form2**.  
  
## <a name="add-a-tableadapter-query-to-form2-to-load-orders-for-the-selected-customer-on-form1"></a>TableAdapter sorgu siparişleri Form1 seçili müşteri için yüklenecek Form2 ekleyin  
  
#### <a name="to-create-a-tableadapter-query"></a>TableAdapter sorgu oluşturmak için  
  
1.  Çift **NorthwindDataSet.xsd** dosyasını **Çözüm Gezgini**.  
  
2.  Sağ **OrdersTableAdapter**seçip **Sorgu Ekle**.  
  
3.  Varsayılan seçeneğini bırakın **kullanım SQL deyimlerini**ve ardından **sonraki**.  
  
4.  Varsayılan seçeneğini bırakın **satırlar döndüren seçin**ve ardından **sonraki**.  
  
5.  WHERE yan tümcesi dönmek için sorguya eklemek `Orders` göre `CustomerID`. Sorgu aşağıdakine benzemelidir:  
  
    ```  
    SELECT OrderID, CustomerID, EmployeeID, OrderDate, RequiredDate, ShippedDate, ShipVia, Freight, ShipName, ShipAddress, ShipCity, ShipRegion, ShipPostalCode, ShipCountry  
    FROM Orders   
    WHERE CustomerID = @CustomerID  
    ```  
  
    > [!NOTE]
    >  Veritabanınız için doğru parametre sözdizimini doğrulayın. Örneğin, Microsoft Access'te WHERE yan tümcesi gibi görünür: `WHERE CustomerID = ?`.  
  
6.  
              **İleri**'ye tıklayın.  
  
7.  İçin **DataTableMethod ad girme**, türü `FillByCustomerID`.  
  
8.  Clear **DataTable dönmek** seçeneğini ve ardından **sonraki**.  
  
9. **Son**'a tıklayın.  
  
## <a name="create-a-method-on-form2-to-pass-data-to"></a>Verileri geçirmek için Form2 üzerinde bir yöntem oluşturma  
  
#### <a name="to-create-a-method-to-pass-data-to"></a>Verileri geçirmek için bir yöntem oluşturmak için  
  
1.  Sağ **Form2**seçip **görünümü kodu** açmak için **Form2** içinde **Kod düzenleyicisinde**.  
  
2.  Aşağıdaki kodu ekleyin **Form2** sonra `Form2_Load` yöntemi:  
  
     [!code-vb[VbRaddataDisplaying#1](../data-tools/codesnippet/VisualBasic/pass-data-between-forms_1.vb)]
     [!code-csharp[VbRaddataDisplaying#1](../data-tools/codesnippet/CSharp/pass-data-between-forms_1.cs)]  
  
## <a name="create-a-method-on-form1-to-pass-data-and-display-form2"></a>Veri iletmek ve Form2 görüntülemek için Form1 üzerinde bir yöntem oluşturma  
  
#### <a name="to-create-a-method-to-pass-data-to-form2"></a>Form2 için veri iletmek için bir yöntem oluşturmak için  
  
1.  İçinde **Form1**, müşteri verileri kılavuzunu sağ tıklatın ve ardından **özellikleri**.  
  
2.  İçinde **özellikleri** penceresinde tıklatın **olayları**.  
  
3.  Çift **CellDoubleClick** olay.  
  
     Kod Düzenleyicisi görüntülenir.  
  
4.  Aşağıdaki örnek eşleştirilecek yöntem tanımını güncelleştirin:  
  
     [!code-csharp[VbRaddataDisplaying#2](../data-tools/codesnippet/CSharp/pass-data-between-forms_2.cs)]
     [!code-vb[VbRaddataDisplaying#2](../data-tools/codesnippet/VisualBasic/pass-data-between-forms_2.vb)]  
  
## <a name="run-the-application"></a>Uygulamayı çalıştırın  
  
#### <a name="to-run-the-application"></a>Uygulamayı çalıştırmak için  
  
-   Uygulamayı çalıştırmak için F5 tuşuna basın.  
  
-   Bir müşteri kaydı çift tıklatarak **Form1** açmak için **Form2** müşterinin emirleriyle.  
  
## <a name="next-steps"></a>Sonraki Adımlar  
 Uygulama gereksinimlerinize bağlı olarak, verileri formlar arasında geçirme sonra gerçekleştirmek istediğinizi düşünelim birkaç adım vardır. Bu izlenecek yolda yapabileceğiniz bazı geliştirmeler şunlardır:  
  
-   Eklemek veya veritabanı nesnelerini kaldırmak için veri kümesi, düzenleme. Daha fazla bilgi için bkz: [oluşturma ve veri kümelerini yapılandırma](../data-tools/create-and-configure-datasets-in-visual-studio.md).  
  
-   Verileri veritabanına kaydetmek için işlevsellik ekleme. Daha fazla bilgi için bkz: [verileri veritabanına kaydetmek](../data-tools/save-data-back-to-the-database.md).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Visual Studio'da verilere Windows Forms denetimleri bağlama](../data-tools/bind-windows-forms-controls-to-data-in-visual-studio.md)