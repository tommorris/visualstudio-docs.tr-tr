---
title: "Veri aramak için bir Windows formu oluşturma | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Windows Forms, searching data
- Windows Forms, displaying data
- parameters, displaying filtered data
- data [Visual Studio], parameterizing queries
- data [Visual Studio], searching
ms.assetid: 65ca79a9-7458-466c-af55-978cd24c549e
caps.latest.revision: "28"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.technology: vs-data-tools
ms.openlocfilehash: 2799e2425ec9748075fc082881243658c363e327
ms.sourcegitcommit: ec1c7e7e3349d2f3a4dc027e7cfca840c029367d
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/07/2017
---
# <a name="create-a-windows-form-to-search-data"></a>Veri aramak için bir Windows formu oluşturma
Sık rastlanan bir uygulama senaryosu seçilen verileri form üzerinde görüntülemektir. Örneğin, belirli bir müşterinin siparişlerini veya belirli bir siparişin ayrıntılarını görüntülemek isteyebilirsiniz. Bu senaryoda, kullanıcı bilgileri forma girer ve sonra kullanıcının girişi parametre olarak kullanılarak bir sorgu yürütülür; diğer bir deyişle veriler parametreli bir sorgu temel alınarak seçilir. Sorgu sadece kullanıcı tarafından girilen ölçütleri karşılayan verileri getirir. Bu kılavuzda, belirli bir şehirdeki müşterileri getiren bir sorgu oluşturma ve kullanıcı arabirimini kullanıcıların şehir adı girip bir düğmeye basarak sorguyu çalıştırabilecekleri şekilde değiştirme işlemleri gösterilmiştir.  
  
 Parametreli sorgular kullanılması, veritabanının kayıtları hızla filtreleyerek işini en iyi şekilde yapmasını sağlayarak uygulamanızın verimli çalışmasına yardımcı olur. Buna karşılık, tüm veritabanı tablosu isteği, ağ üzerinden aktar ve ardından istediğiniz kayıtları bulmak için uygulama mantığını kullanın, uygulamanızın yavaş ve verimsiz olabilir.  
  
 Parametreli sorgular herhangi TableAdapter (ve denetimler için parametre değerlerini kabul etmek ve sorguyu yürütmek için) kullanarak ekleyebilirsiniz **arama ölçütleri Oluşturucu** iletişim kutusu. Seçerek iletişim kutusunu açmak **Sorgu Ekle** komutunu **veri** menü (veya herhangi bir TableAdapter akıllı etiket).  
  
 Bu örneklerde gösterilen görevler aşağıdakileri içerir:  
  
-   Yeni bir Windows Forms uygulaması projesi oluşturma.  
  
-   Oluşturma ve veri kaynağı ile uygulamanızda yapılandırma **veri kaynağı yapılandırması** Sihirbazı.  
  
-   Ayar öğelerinin bırakma türü **veri kaynakları**penceresi.  
  
-   Konumundan öğeleri sürükleyerek verileri görüntüleyen denetimler oluşturma **veri kaynakları** forma penceresi.  
  
-   Formdaki verileri görüntülemek için denetimler ekleme.  
  
-   Tamamlanıyor **arama ölçütleri Oluşturucu** iletişim kutusu.  
  
-   Forma parametreleri girerek ve Parametreli sorgu yürütülürken.  
  
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
 İlk adım oluşturmaktır bir **Windows Forms uygulaması**. Proje için bir ad atama sırasında bu adım isteğe bağlıdır, ancak daha sonra projeyi kaydedin çünkü bir ad verin.  
  
#### <a name="to-create-the-new-windows-forms-application-project"></a>Yeni Windows Forms uygulaması projesi oluşturmak için  
  
1. Visual Studio'da üzerinde **dosya** menüsünde, select **yeni**, **proje...** .  
  
2. Genişletin **Visual C#** veya **Visual Basic** sol bölmesinde, ardından **Windows Klasik Masaüstü**.  

3. Orta bölmede seçin **Windows Forms uygulaması** proje türü.  

4. Proje adı **WindowsSearchForm**ve ardından **Tamam**. 
  
     **WindowsSearchForm** projesi oluşturulur ve eklenen **Çözüm Gezgini**.  
  
## <a name="create-the-data-source"></a>Veri kaynağı oluşturun  
Bu adım bir veri kaynağı kullanarak bir veritabanı oluşturur **veri kaynağı yapılandırması** Sihirbazı.  
  
#### <a name="to-create-the-data-source"></a>Veri kaynağı oluşturmak için  
  
1.  Üzerinde **veri** menüsünde tıklatın **veri kaynaklarını Göster**.  
  
2.  İçinde **veri kaynakları** penceresinde, seçin **yeni veri kaynağı Ekle** başlatmak için **veri kaynağı yapılandırması** Sihirbazı.  
  
3.  Seçin **veritabanı** üzerinde **bir veri kaynağı türü seç** sayfasında ve ardından **sonraki**.  
  
4.  Üzerinde **veri bağlantınızı seçin** sayfasında aşağıdakilerden birini yapın:  
  
    -   Northwind örnek veritabanıyla kurulan veri bağlantısı aşağı açılan listede kullanılabilir durumdaysa bunu seçin.  
  
    -   Seçin **yeni bağlantı** başlatmak için **Ekle/Değiştir bağlantı** iletişim kutusu.  
  
5.  Veritabanınız bir parola gerektiriyorsa, hassas bilgileri Ekle ve ardından seçeneğini **sonraki**.  
  
6.  Üzerinde **bağlantı dizesi için uygulama yapılandırma dosyasını kaydetmek** sayfasında, **sonraki**.  
  
7.  Üzerinde **veritabanı nesnelerini seçin** sayfasında **tabloları** düğümü.  
  
8.  Seçin **müşteriler** tablo ve ardından **son**.  
  
     **NorthwindDataSet** projenize, eklenen ve **müşteriler** tablo görünür **veri kaynakları** penceresi.  
  
## <a name="create-the-form"></a>Formu oluşturma  
 Verilere bağlı denetimler konumundan öğeleri sürükleyerek oluşturabileceğiniz **veri kaynakları** formunuza penceresi.  
  
#### <a name="to-create-data-bound-controls-on-the-form"></a>Form üzerinde veri bağlama denetimleri oluşturmak için  
  
1.  Genişletme **müşteriler** düğümünde **veri kaynakları** penceresi.  
  
2.  Sürükleme **müşteriler** düğümden **veri kaynakları** formunuza penceresi.  
  
     A <xref:System.Windows.Forms.DataGridView> ve araç şeridinde (<xref:System.Windows.Forms.BindingNavigator>) kayıtları gezinmek için form üzerinde görüntülenir. A [NorthwindDataSet](../data-tools/dataset-tools-in-visual-studio.md), TableAdapter, <xref:System.Windows.Forms.BindingSource>, ve <xref:System.Windows.Forms.BindingNavigator> bileşen tepsisinde görünür.  
  
## <a name="add-parameterization-search-functionality-to-the-query"></a>Sorguya parametrelemeyi (arama işlevini) ekleyin  
 Özgün kullanarak sorgu WHERE yan tümcesi ekleyebilirsiniz **arama ölçütleri Oluşturucu** iletişim kutusu.  
  
#### <a name="to-create-a-parameterized-query-and-controls-to-enter-the-parameters"></a>Parametreleri girmek üzere parametreli sorgu ve denetimler oluşturmak için  
  
1.  Seçin <xref:System.Windows.Forms.DataGridView> denetlemek ve ardından **Sorgu Ekle** üzerinde **veri** menüsü.  
  
2.  Tür `FillByCity` içinde **yeni sorgu adı** alanı **arama ölçütleri Oluşturucu** iletişim kutusu.  
  
3.  Ekleme `WHERE City = @City` sorguya **sorgu metni** alanı.  
  
     Sorgu aşağıdakine benzemelidir:  
  
     ```sql
     SELECT CustomerID, CompanyName, ContactName, ContactTitle,  
          Address, City, Region, PostalCode, Country, Phone, Fax  
     FROM Customers
     WHERE City = @City  
     ```
  
    > [!NOTE]
    >  Erişim ve OLE DB veri kaynaklarını kullanmak soru işareti ('? ') parametrelerini belirtmek için bu nedenle WHERE yan tümcesi şuna benzeyebilir: `WHERE City = ?`.  
  
4.  Tıklatın **Tamam** kapatmak için **arama ölçütleri Oluşturucu** iletişim kutusu.  
  
     A **FillByCityToolStrip** forma eklenir.  
  
## <a name="testing-the-application"></a>Uygulamayı test etme  
 Uygulamanın çalıştırılması formunuzu giriş olarak parametreyi almaya hazır olarak açar.  
  
#### <a name="to-test-the-application"></a>Uygulamayı test etmek için  
  
1.  Uygulamayı çalıştırmak için F5 tuşuna basın.  
  
2.  Tür **Londra** içine **Şehir** metin kutusuna ve ardından **FillByCity**.  
  
     Veri Kılavuzu ölçütlere uyan müşterilerle doldurulur. Bu örnekte, veri kılavuzu yalnızca değerine sahip müşteriler görüntüler **Londra** içinde kendi **Şehir** sütun.  
  
## <a name="next-steps"></a>Sonraki Adımlar  
 Uygulama gereksinimlerinize bağlı olarak, parametreli form oluşturduktan sonra gerçekleştirmek isteyebileceğiniz birkaç adım vardır. Bu izlenecek yolda yapabileceğiniz bazı geliştirmeler şunlardır:  
  
-   İlgili verileri görüntüleyen denetimler ekleme. Daha fazla bilgi için bkz: [kümelerindeki ilişkiler](relationships-in-datasets.md).  
  
-   Veritabanı nesneleri eklemek veya çıkarmak için veri kümesini düzenleme. Daha fazla bilgi için bkz: [oluşturma ve veri kümelerini yapılandırma](../data-tools/create-and-configure-datasets-in-visual-studio.md).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Visual Studio'da verilere Windows Forms denetimleri bağlama](../data-tools/bind-windows-forms-controls-to-data-in-visual-studio.md)