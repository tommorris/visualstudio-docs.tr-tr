---
title: Bir eşzamanlılık özel durum işleme
ms.date: 09/11/2017
ms.topic: conceptual
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- concurrency control, exceptions
- datasets [Visual Basic], errors
- exception handling, concurrency issues
- data concurrency, walkthroughs
- updating datasets, errors
- concurrency control, walkthroughs
ms.assetid: 73ee9759-0a90-48a9-bf7b-9d6fc17bff93
author: gewarren
ms.author: gewarren
manager: douge
ms.technology: vs-data-tools
ms.workload:
- data-storage
ms.openlocfilehash: 26a52b082d447a2a4f14d0d09036c6b5df63656a
ms.sourcegitcommit: 42ea834b446ac65c679fa1043f853bea5f1c9c95
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/19/2018
---
# <a name="handle-a-concurrency-exception"></a>Bir eşzamanlılık özel durum işleme
Eşzamanlılık (<xref:System.Data.DBConcurrencyException>) iki kullanıcı aynı anda aynı verileri bir veritabanındaki değiştirmeye kalkıştığında ortaya çıkar. Bu kılavuzda, catch verilmektedir bir Windows uygulaması oluşturma bir <xref:System.Data.DBConcurrencyException>hataya satırı bulun ve onu nasıl ele alınacağını için bir strateji öğrenin.

 Bu kılavuz aşağıdaki süreci alır:

1.  Yeni bir **Windows Forms uygulaması** projesi.

2.  Northwind üzerinde dayalı yeni bir veri kümesi oluşturma `Customers` tablo.

3.  Bir form oluşturma bir <xref:System.Windows.Forms.DataGridView> verileri görüntülemek için.

4.  Bir veri kümesini verilerle doldurma `Customers` Northwind veritabanı tablosunda.

5.  Kullanım **tablo verileri Göster** özelliğini **Sunucu Gezgini** erişimi `Customers` tablonun veri ve değişikliği bir kaydı.

6.  Farklı bir değerle aynı kaydı değiştirmek, veri kümesi güncelleştirin ve değişiklikleri gerçekleştirilen bir eşzamanlılık hatası sonuçları veritabanına yazma girişimi.

7.  Hata yakalama sonra devam etmek ve veritabanını güncelleştirmek için ya da güncelleştirme iptal etmeye karar vermek kullanıcının kaydı, farklı sürümlerini görüntüler.

## <a name="prerequisites"></a>Önkoşullar
Bu kılavuzda, SQL Server Express LocalDB ve Northwind örnek veritabanı kullanılır.

1.  SQL Server Express LocalDB yoksa, araçtan yüklemek [SQL Server Express indirme sayfası](https://www.microsoft.com/sql-server/sql-server-editions-express), aracılığıyla veya **Visual Studio yükleyicisi**. Visual Studio Yükleyicisi'nde, SQL Server Express LocalDB parçası olarak yüklenebilir **veri depolama ve işleme** iş yükü veya tek bir bileşen olarak.

2.  Northwind örnek veritabanı, şu adımları izleyerek yükleyin:

    1. Visual Studio'da açın **SQL Server Nesne Gezgini** penceresi. (SQL Server Nesne Gezgini parçası olarak yüklü **veri depolama ve işleme** Visual Studio yükleyicisi iş yükündeki.) Genişletme **SQL Server** düğümü. Yerel veritabanı örneğinde sağ tıklatıp **yeni sorgu...** .

       Sorgu Düzenleyicisi penceresini açar.

    2. Kopya [Northwind Transact-SQL betiği](https://github.com/MicrosoftDocs/visualstudio-docs/blob/master/docs/data-tools/samples/northwind.sql?raw=true) panonuza. Bu T-SQL betiği sıfırdan Northwind veritabanı oluşturur ve veri ile doldurur.

    3. T-SQL betiği sorgu düzenleyicisine yapıştırın ve ardından **yürütme** düğmesi.

       Kısa bir süre sonra sorgu yürütme tamamlandıktan ve Northwind veritabanı oluşturulur.

> [!NOTE]
>  İletişim kutuları ve menü komutlarını gördüğünüz açıklanana Yardımı'nda etkin ayarlarınızı veya kullanmakta olduğunuz edition bağlı olarak farklı olabilir. Ayarlarınızı değiştirmek için tercih **içeri ve dışarı aktarma ayarları** üzerinde **Araçları** menüsü. Daha fazla bilgi için bkz: [Visual Studio IDE'yi kişiselleştirme](../ide/personalizing-the-visual-studio-ide.md).

## <a name="create-a-new-project"></a>Yeni bir proje oluşturma
 Yeni bir Windows Forms uygulaması oluşturarak, izlenecek başlayın.

#### <a name="to-create-a-new-windows-forms-application-project"></a>Yeni bir Windows Forms uygulaması projesi oluşturmak için

1. Visual Studio'da üzerinde **dosya** menüsünde, select **yeni**, **proje...** .

2. Genişletin **Visual C#** veya **Visual Basic** sol bölmesinde, ardından **Windows Klasik Masaüstü**.

3. Orta bölmede seçin **Windows Forms uygulaması** proje türü.

4. Proje adı **ConcurrencyWalkthrough**ve ardından **Tamam**.

     **ConcurrencyWalkthrough** projesi oluşturulur ve eklenen **Çözüm Gezgini**, ve yeni bir form tasarımcısında açar.

## <a name="create-the-northwind-dataset"></a>Northwind veri kümesi oluşturma
 Bu bölümde, adlı bir veri kümesi oluşturma `NorthwindDataSet`.

#### <a name="to-create-the-northwinddataset"></a>NorthwindDataSet oluşturmak için

1.  Üzerinde **veri** menüsünde seçin **ekleme yeni veri kaynağı**.

     [Veri kaynağı Yapılandırma Sihirbazı](../data-tools/media/data-source-configuration-wizard.png) açar.

2.  Üzerinde **bir veri kaynağı türü seç** ekran, select **veritabanı**.

3.  Northwind örnek veritabanı için bir bağlantı kullanılabilir bağlantılar listesinden seçin. Bağlantı bağlantıları listesinde kullanılabilir durumda değilse, seçin **yeni bağlantı**

    > [!NOTE]
    >  Bir yerel veritabanı dosyasına bağlanıyorsanız seçin **Hayır** sorulduğunda isterseniz ister dosyayı projenize ekleyin.

4.  Üzerinde **bağlantı dizesini uygulama yapılandırma dosyasına kaydedin** ekran, select **sonraki**.

5.  Genişletme **tabloları** düğümü ve select `Customers` tablo. Veri kümesi için varsayılan adı olmalıdır `NorthwindDataSet`.

6.  Seçin **son** dataset projeye eklemek için.

## <a name="create-a-data-bound-datagridview-control"></a>Veri bağlama DataGridView denetimi oluşturma
 Bu bölümde, oluşturduğunuz bir <xref:System.Windows.Forms.DataGridView> sürükleyerek **müşteriler** gelen öğe **veri kaynakları** Windows formunuza penceresi.

#### <a name="to-create-a-datagridview-control-that-is-bound-to-the-customers-table"></a>Müşteriler tabloya bağlı DataGridView denetimi oluşturmak için

1.  Üzerinde **veri** menüsünde seçin **veri kaynaklarını Göster** açmak için **veri kaynakları penceresi**.

2.  İçinde **veri kaynakları** penceresinde genişletin **NorthwindDataSet** düğümünü ve ardından **müşteriler** tablo.

3.  Tablo düğümü üzerinde aşağı oku seçin ve ardından **DataGridView** aşağı açılan listesinde.

4.  Tablonun boş bir form alanının üzerine sürükleyin.

     A <xref:System.Windows.Forms.DataGridView> adlı Denetim `CustomersDataGridView` ve <xref:System.Windows.Forms.BindingNavigator> adlı `CustomersBindingNavigator` bağlı forma eklenen <xref:System.Windows.Forms.BindingSource>. Bu, içinde Aç bağlı `Customers` tablosundaki `NorthwindDataSet`.

## <a name="test-the-form"></a>Formun test
 Bu noktaya kadar beklendiği gibi davranır emin olmak için form artık test edebilirsiniz.

#### <a name="to-test-the-form"></a>Formu sınamak için

1.  Seçin **F5** uygulamayı çalıştırmak için

     Formun görünür bir <xref:System.Windows.Forms.DataGridView> verilerle doldurulur denetim üzerindeki `Customers` tablo.

2.  Üzerinde **hata ayıklama** menüsünde, select **durdurma hata ayıklama**.

## <a name="handle-concurrency-errors"></a>Eşzamanlılık hataları işleme
 Hataların nasıl işleneceğini uygulamanızı yöneten belirli iş kurallarını bağlıdır. Bu kılavuzda eşzamanlılık hatayı işlemeye ilişkin bir örnek olarak aşağıdaki stratejiyi kullanın.

 Uygulama kullanıcı kaydı üç sürümleriyle sunar:

-   Veritabanı geçerli kayıt

-   Veri kümesine yüklenen özgün kaydı

-   Veri kümesinde önerilen değişiklikleri

Kullanıcı daha sonra önerilen sürümüyle veritabanının üzerine yaz veya güncelleştirmeyi iptal eder ve veritabanından yeni değerlerle veri kümesini yenileyin.

#### <a name="to-enable-the-handling-of-concurrency-errors"></a>Eşzamanlılık hatalarının işlenmesini etkinleştirmek için

1.  Bir özel hata işleyicisi oluşturun.

2.  Seçimler kullanıcıya görüntüler.

3.  Kullanıcının yanıtını işleyin.

4.  Güncelleştirmeyi yeniden gönderin veya veri kümesindeki sıfırlayın.

### <a name="add-code-to-handle-the-concurrency-exception"></a>Eşzamanlılık özel durumu işlemek için kod ekleme
 Bir güncelleştirme gerçekleştirmeyi denedi ve bir özel durumu, genellikle özel durumu tarafından sağlanan bilgileri içeren bir şeyler istersiniz.

 Bu bölümde, veritabanını güncelleştirmek için çalışır kodu ekleyin. Herhangi bir de işlemek <xref:System.Data.DBConcurrencyException> oluşturuldu, yanı sıra diğer tüm özel durumlar.

> [!NOTE]
>  `CreateMessage` Ve `ProcessDialogResults` yöntemleri bu kılavuzda daha sonra eklenir.

##### <a name="to-add-error-handling-for-the-concurrency-error"></a>Hata işleme için eşzamanlılık hatası eklemek için

1.  Aşağıdaki kodu ekleyin `Form1_Load` yöntemi:

     [!code-csharp[VbRaddataConcurrency#1](../data-tools/codesnippet/CSharp/handle-a-concurrency-exception_1.cs)]
     [!code-vb[VbRaddataConcurrency#1](../data-tools/codesnippet/VisualBasic/handle-a-concurrency-exception_1.vb)]

2.  Değiştir `CustomersBindingNavigatorSaveItem_Click` çağrılacak yöntem `UpdateDatabase` yöntemi aşağıdaki gibi görünür:

     [!code-csharp[VbRaddataConcurrency#2](../data-tools/codesnippet/CSharp/handle-a-concurrency-exception_2.cs)]
     [!code-vb[VbRaddataConcurrency#2](../data-tools/codesnippet/VisualBasic/handle-a-concurrency-exception_2.vb)]

### <a name="display-choices-to-the-user"></a>Kullanıcı için görüntüleme seçenekleri
 Yeni kod yazdı çağrıları `CreateMessage` kullanıcıya hata bilgilerini görüntülemek için yordamı. Bu kılavuz için kayıt farklı sürümlerini kullanıcıya görüntülenecek bir ileti kutusu kullanın. Bu kullanıcının kaydı değişikliklerle üzerine veya düzenlemeyi iptal etmek isteyip istemediğinizi seçin sağlar. Kullanıcı bir seçenek (bir düğmeye tıklar) ileti kutusu seçtikten sonra yanıtı geçirilir `ProcessDialogResult` yöntemi.

##### <a name="to-create-the-message-to-display-to-the-user"></a>Kullanıcıya görüntülenecek iletiyi oluşturmak için

-   Aşağıdaki kodu ekleyerek iletiyi oluşturmak **Kod düzenleyicisinde**. Bu kodu aşağıya girin `UpdateDatabase` yöntemi.

     [!code-csharp[VbRaddataConcurrency#4](../data-tools/codesnippet/CSharp/handle-a-concurrency-exception_3.cs)]
     [!code-vb[VbRaddataConcurrency#4](../data-tools/codesnippet/VisualBasic/handle-a-concurrency-exception_3.vb)]

### <a name="process-the-users-response"></a>Kullanıcının yanıtı işlemi
 İleti kutusu kullanıcının yanıta işlemek için kod da gerekir. Veritabanı geçerli kayıt önerilen değişiklikle üzerine yaz'yı veya yerel değişiklikler abandon'yı ve veri tablosu veritabanında olan bir kayıtla Yenile seçeneklerdir. Evet, kullanıcı seçerse <xref:System.Data.DataTable.Merge%2A> yöntemi ile çağrılır *preserveChanges* değişkenini `true`. Bu kayıt özgün sürümü artık kaydını veritabanında eşleştiğinden başarılı olması güncelleştirme girişimi neden olur.

##### <a name="to-process-the-user-input-from-the-message-box"></a>Kullanıcı işlemek için ileti kutusundan Giriş

-   Önceki bölümde eklendi kod altına aşağıdaki kodu ekleyin.

     [!code-csharp[VbRaddataConcurrency#3](../data-tools/codesnippet/CSharp/handle-a-concurrency-exception_4.cs)]
     [!code-vb[VbRaddataConcurrency#3](../data-tools/codesnippet/VisualBasic/handle-a-concurrency-exception_4.vb)]

## <a name="test-the-form"></a>Formun test
 Artık formun beklendiği gibi davranır emin olmak için test edebilirsiniz. Bir eşzamanlılık ihlali benzetimini yapmak için NorthwindDataSet doldurduktan sonra veritabanındaki verileri değiştirmeniz gerekir.

#### <a name="to-test-the-form"></a>Formu sınamak için

1.  Seçin **F5** uygulamayı çalıştırın.

2.  Formun göründükten sonra çalışmasını bırakın ve Visual Studio IDE geçin.

3.  Üzerinde **Görünüm** menüsünde seçin **Sunucu Gezgini**.

4.  İçinde **Sunucu Gezgini**, uygulamanızı kullanarak ve ardından bağlantıyı genişletmek **tabloları** düğümü.

5.  Sağ **müşteriler** tablo ve ardından **Show Table Data**.

6.  İlk kaydındaki (`ALFKI`) değiştirme `ContactName` için `Maria Anders2`.

    > [!NOTE]
    >  Değişikliği kaydetmek için farklı bir satır gidin.

7.  Geçiş `ConcurrencyWalkthrough`form çalıştıran kullanıcının.

8.  Form ilk kaydında (`ALFKI`), değiştirme`ContactName` için `Maria Anders1`.

9. Seçin **kaydetmek** düğmesi.

     Eşzamanlılık hatası tetiklenir ve ileti kutusu görünür.

10. Seçme **Hayır** güncelleştirmeyi iptal eder ve şu anda veritabanında bulunan değerlere sahip veri kümesini güncelleştirir. Seçme **Evet** önerilen değeri veritabanına yazar.

## <a name="see-also"></a>Ayrıca bkz.

- [Verileri yeniden veritabanına kaydetme](../data-tools/save-data-back-to-the-database.md)