---
title: "Veri ile TableAdapter DBDirect yöntemleri Kaydet | Microsoft Docs"
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
- TableAdapters, walkthroughs
- data [Visual Studio], saving
- saving data, walkthroughs
- data [Visual Studio], TableAdapter
ms.assetid: 74a6773b-37e1-4d96-a39c-63ee0abf49b1
caps.latest.revision: "14"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.technology: vs-data-tools
ms.workload: data-storage
ms.openlocfilehash: 628a3cfc75f786ceb989145ada6e2f2579f349cd
ms.sourcegitcommit: 49aa031cbebdd9c7ec070c713afb1a97d1ecb701
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/23/2018
---
# <a name="save-data-with-the-tableadapter-dbdirect-methods"></a>Veri ile TableAdapter DBDirect yöntemleri kaydedin.
Bu kılavuz bir TableAdapter DBDirect yöntemleri kullanarak doğrudan bir veritabanında SQL deyimlerini çalıştırmak için ayrıntılı yönergeler sağlar. Veritabanı güncelleştirmelerinizi üzerinde denetim ayrıntılı bir düzeyde bir TableAdapter DBDirect yöntemleri sağlar. Bunları tek tek çağırarak belirli SQL deyimlerini ve depolanan yordamları çalıştırmak için kullanabileceğiniz `Insert`, `Update`, ve `Delete` , uygulamanız tarafından gerektiği şekilde yöntemleri (aşırı yüklenmiş aksine `Update` güncelleştirme gerçekleştirir yöntemi INSERT ve DELETE deyimlerinde tüm bir çağrı).  
  
 Bu gözden geçirme sırasında öğreneceksiniz nasıl yapılır:  
  
-   Yeni bir **Windows Forms uygulaması**.  
  
-   Oluşturma ve yapılandırma ile dataset [veri kaynağı Yapılandırma Sihirbazı](../data-tools/media/data-source-configuration-wizard.png).  
  
-   Formdaki öğelerinden sürüklendiğinde oluşturulması için denetimi seçin **veri kaynakları** penceresi. Daha fazla bilgi için bkz: [veri kaynakları penceresinden sürüklendiğinde oluşturulacak denetimini ayarlama](../data-tools/set-the-control-to-be-created-when-dragging-from-the-data-sources-window.md).  
  
-   Veri bağlama form konumundan öğeleri sürükleyerek oluşturma **veri kaynakları** forma penceresi.  
  
-   Doğrudan veritabanına erişmek ve ekler, güncelleştirmeleri ve silme gerçekleştirmek için yöntemler Ekle...  
  
## <a name="prerequisites"></a>Önkoşullar  
Bu kılavuzda, SQL Server Express LocalDB ve Northwind örnek veritabanı kullanılır.  
  
1.  SQL Server Express LocalDB yoksa, araçtan yüklemek [SQL Server Express indirme sayfası](https://www.microsoft.com/sql-server/sql-server-editions-express), aracılığıyla veya **Visual Studio yükleyicisi**. Visual Studio Yükleyicisi'nde, SQL Server Express LocalDB parçası olarak yüklenebilir **veri depolama ve işleme** iş yükü veya tek bir bileşen olarak.  
  
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
  
2. Genişletin **Visual C#** veya **Visual Basic** sol bölmesinde, ardından **Windows Klasik Masaüstü**.  

3. Orta bölmede seçin **Windows Forms uygulaması** proje türü.  

4. Proje adı **TableAdapterDbDirectMethodsWalkthrough**ve ardından **Tamam**. 
  
     **TableAdapterDbDirectMethodsWalkthrough** projesi oluşturulur ve eklenen **Çözüm Gezgini**.  
  
## <a name="create-a-data-source-from-your-database"></a>Veritabanından bir veri kaynağı oluşturun  
 Bu adımı kullanan **veri kaynağı Yapılandırma Sihirbazı** dayalı bir veri kaynağı oluşturmak için `Region` Northwind örnek veritabanı tablosunda. Northwind örnek veritabanı bağlantısı oluşturmak için erişimi olmalıdır. Northwind örnek veritabanı ayarlama hakkında daha fazla bilgi için bkz: [nasıl yapılır: örnek veritabanları yükleme](../data-tools/installing-database-systems-tools-and-samples.md).  
  
#### <a name="to-create-the-data-source"></a>Veri kaynağı oluşturmak için  
  
1.  Üzerinde **veri** menüsünde, select **veri kaynaklarını Göster**.  
  
2.  İçinde **veri kaynakları** penceresinde, seçin **yeni veri kaynağı Ekle** başlatmak için **veri kaynağı Yapılandırma Sihirbazı**.  
  
3.  Üzerinde **bir veri kaynağı türü seç** ekran, select **veritabanı**ve ardından **sonraki**.  
  
4.  Üzerinde **veri bağlantınızı seçin** ekranında, aşağıdakilerden birini yapın:  
  
    -   Northwind örnek veritabanıyla kurulan veri bağlantısı aşağı açılan listede kullanılabilir durumdaysa bunu seçin.  
  
         veya  
  
    -   Seçin **yeni bağlantı** başlatmak için **Ekle/Değiştir bağlantı** iletişim kutusu.  
  
5.  Veritabanınız bir parola gerektiriyorsa, hassas bilgileri Ekle ve ardından seçeneğini **sonraki**.  
  
6.  Üzerinde **bağlantı dizesi için uygulama yapılandırma dosyasını kaydetmek** ekran, select **sonraki**.  
  
7.  Üzerinde **veritabanı nesnelerini seçin** ekranında, **tabloları** düğümü.  
  
8.  Seçin `Region` tablo ve ardından **son**.  
  
     **NorthwindDataSet** projenize eklenir ve `Region` tablo görünür **veri kaynakları** penceresi.  
  
## <a name="add-controls-to-the-form-to-display-the-data"></a>Verileri görüntülemek için formu denetimleri ekleme  
 Verilere bağlı denetimler konumundan öğeleri sürükleyerek oluşturmak **veri kaynakları** formunuza penceresi.  
  
#### <a name="to-create-data-bound-controls-on-the-windows-form"></a>Bağlama denetimleri Windows formunda veri oluşturmak için  
  
-   Ana sürükleyin **bölge** düğümden **veri kaynakları** forma penceresi.  
  
     A <xref:System.Windows.Forms.DataGridView> denetimi ve araç şeridinde (<xref:System.Windows.Forms.BindingNavigator>) kayıtları gezinmek için form üzerinde görüntülenir. A [NorthwindDataSet](../data-tools/dataset-tools-in-visual-studio.md), `RegionTableAdapter`, <xref:System.Windows.Forms.BindingSource>, ve <xref:System.Windows.Forms.BindingNavigator> bileşen tepsisinde görünür.  
  
#### <a name="to-add-buttons-that-will-call-the-individual-tableadapter-dbdirect-methods"></a>Tek tek TableAdapter DbDirect yöntemleri çağırır düğmeleri eklemek için  
  
1.  Üç sürükleyin <xref:System.Windows.Forms.Button> gelen denetimleri **araç** üzerine **Form1** (aşağıda **RegionDataGridView**).  
  
2.  Aşağıdakileri ayarlayın **adı** ve **metin** her düğme özellikleri.  
  
    |Ad|Metin|  
    |----------|----------|  
    |`InsertButton`|**Ekle**|  
    |`UpdateButton`|**Güncelleştir**|  
    |`DeleteButton`|**Sil**|  
  
#### <a name="to-add-code-to-insert-new-records-into-the-database"></a>Veritabanına yeni kayıtlar eklemek üzere kod eklemek için  
  
1.  Seçin **InsertButton** click olayı için bir olay işleyicisi oluşturma ve formunuza Kod düzenleyicisinde açın.  
  
2.  Değiştir `InsertButton_Click` aşağıdaki kod ile olay işleyicisi:  
  
     [!code-vb[VbRaddataSaving#1](../data-tools/codesnippet/VisualBasic/save-data-with-the-tableadapter-dbdirect-methods_1.vb)]
     [!code-csharp[VbRaddataSaving#1](../data-tools/codesnippet/CSharp/save-data-with-the-tableadapter-dbdirect-methods_1.cs)]  
  
#### <a name="to-add-code-to-update-records-in-the-database"></a>Veritabanındaki kayıtlarını güncelleştirmek üzere kod eklemek için  
  
1.  Çift **UpdateButton** click olayı için bir olay işleyicisi oluşturma ve formunuza Kod düzenleyicisinde açın.  
  
2.  Değiştir `UpdateButton_Click` aşağıdaki kod ile olay işleyicisi:  
  
     [!code-vb[VbRaddataSaving#2](../data-tools/codesnippet/VisualBasic/save-data-with-the-tableadapter-dbdirect-methods_2.vb)]
     [!code-csharp[VbRaddataSaving#2](../data-tools/codesnippet/CSharp/save-data-with-the-tableadapter-dbdirect-methods_2.cs)]  
  
#### <a name="to-add-code-to-delete-records-from-the-database"></a>Kayıtlarını veritabanından silmek için kod eklemek için  
  
1.  Seçin **DeleteButton** click olayı için bir olay işleyicisi oluşturma ve formunuza Kod düzenleyicisinde açın.  
  
2.  Değiştir `DeleteButton_Click` aşağıdaki kod ile olay işleyicisi:  
  
     [!code-vb[VbRaddataSaving#3](../data-tools/codesnippet/VisualBasic/save-data-with-the-tableadapter-dbdirect-methods_3.vb)]
     [!code-csharp[VbRaddataSaving#3](../data-tools/codesnippet/CSharp/save-data-with-the-tableadapter-dbdirect-methods_3.cs)]  
  
## <a name="run-the-application"></a>Uygulamayı çalıştırın  
  
#### <a name="to-run-the-application"></a>Uygulamayı çalıştırmak için  
  
-   Seçin **F5** uygulamayı çalıştırın.  
  
-   Seçin **Ekle** düğmesine tıklayın ve yeni kayıt kılavuzda göründüğünden emin olun.  
  
-   Seçin **güncelleştirme** düğmesine tıklayın ve kayıt kılavuzda güncelleştirilir doğrulayın.  
  
-   Seçin **silmek** düğmesine tıklayın ve kayıt kılavuzdan kaldırıldığını doğrulayın.  
  
## <a name="next-steps"></a>Sonraki Adımlar  
 Uygulama gereksinimlerinize bağlı olarak, veri bağlama form oluşturduktan sonra gerçekleştirmek isteyebileceğiniz birkaç adım vardır. Bu izlenecek yolda yapabileceğiniz bazı geliştirmeler şunlardır:  
  
-   Arama işlevini formuna ekleme.  
  
-   Ek tablolar seçerek kümesine ekleme **veri kümesi Yapılandırma Sihirbazı ile** içinden **veri kaynakları** penceresi. Forma ilgili düğümleri sürükleyerek ilgili verileri görüntüleyen denetimler ekleyebilirsiniz. Daha fazla bilgi için bkz: [kümelerindeki ilişkiler](relationships-in-datasets.md).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Verileri yeniden veritabanına kaydetme](../data-tools/save-data-back-to-the-database.md)