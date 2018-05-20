---
title: 'İzlenecek yol: sunucudaki çalışma kitabından önbelleğe alınmış verileri alma'
ms.custom: ''
ms.date: 02/02/2017
ms.technology:
- office-development
ms.topic: conceptual
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- workbooks [Office development in Visual Studio], retrieving data
- datasets [Office development in Visual Studio], accessing on server
- server-side data access [Office development in Visual Studio]
- data [Office development in Visual Studio], accessing on server
- documents [Office development in Visual Studio], server-side data access
author: TerryGLee
ms.author: tglee
manager: douge
ms.workload:
- office
ms.openlocfilehash: b9b9296bd57e7f3057dfbca86c16b1ac41418ba0
ms.sourcegitcommit: 209c2c068ff0975994ed892b62aa9b834a7f6077
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/17/2018
---
# <a name="walkthrough-retrieve-cached-data-from-a-workbook-on-a-server"></a>İzlenecek yol: sunucudaki çalışma kitabından önbelleğe alınmış verileri alma
  Bu kılavuz, Microsoft Office Excel çalışma kitabında kullanarak Excel'i başlatmadan önbelleğe alınmış bir veri kümesinden veri almak gösterilmiştir <xref:Microsoft.VisualStudio.Tools.Applications.ServerDocument> sınıfı.  
  
 [!INCLUDE[appliesto_xlalldoc](../vsto/includes/appliesto-xlalldoc-md.md)]  
  
 Bu izlenecek yol aşağıdaki görevleri gösterir:  
  
-   Verileri içeren bir veri kümesini tanımlama *AdventureWorksLT* veritabanı.  
  
-   Veri kümesi örneklerini Excel çalışma kitabı ve konsol uygulama projesi oluşturma.  
  
-   Oluşturma bir <xref:Microsoft.Office.Tools.Excel.ListObject> çalışma kitabındaki veri kümesine bağlı ve doldurma <xref:Microsoft.Office.Tools.Excel.ListObject> çalışma kitabı açıldığında verilerle.  
  
-   Veri kümesi çalışma kitabında veri önbelleğine ekleme.  
  
-   Excel başlatmadan konsol uygulamasındaki veri kümesine önbelleğe alınmış veri kümesinden veri okunurken.  
  
 Bu kılavuzda geliştirme bilgisayarınızda kodu çalıştığını varsayar ancak bu izlenecek yol tarafından gösterilen kodu Excel yüklü olmayan bir sunucu üzerinde kullanılabilir.  
  
> [!NOTE]  
>  Bilgisayarınız, aşağıdaki yönergelerde yer alan Visual Studio kullanıcı arabirimi öğelerinden bazıları için farklı adlar veya konumlar gösterebilir. Sahip olduğunuz Visual Studio sürümü ve kullandığınız ayarlar bu öğeleri belirler. Daha fazla bilgi için bkz: [Visual Studio IDE'yi kişiselleştirme](../ide/personalizing-the-visual-studio-ide.md).  
  
## <a name="prerequisites"></a>Önkoşullar  
 Bu izlenecek yolu tamamlamak için aşağıdaki bileşenlere ihtiyacınız vardır:  
  
-   [!INCLUDE[vsto_vsprereq](../vsto/includes/vsto-vsprereq-md.md)]  
  
-   [!INCLUDE[Excel_15_short](../vsto/includes/excel-15-short-md.md)] veya [!INCLUDE[Excel_14_short](../vsto/includes/excel-14-short-md.md)].  
  
-   Microsoft SQL Server ya da Microsoft SQL Server ekli AdventureWorksLT örnek veritabanı olan Express çalışan örneğine erişim. AdventureWorksLT veritabanından indirebilirsiniz [CodePlex Web sitesi](http://go.microsoft.com/fwlink/?linkid=87843). Veritabanı ekleme hakkında daha fazla bilgi için aşağıdaki konulara bakın:  
  
    -   SQL Server Management Studio veya SQL Server Management Studio Express kullanarak veritabanı eklemek için bkz: [nasıl yapılır: bir veritabanını (SQL Server Management Studio)](http://msdn.microsoft.com/en-us/b4efb0ae-cfe6-4d81-a4b4-6e4916885caa).  
  
    -   Komut satırını kullanarak bir veritabanı eklemek için bkz: [nasıl yapılır: SQL Server Express için bir veritabanı dosyası ekleme](http://msdn.microsoft.com/en-us/0f8e42b5-7a8c-4c30-8c98-7d2bdc8dcc68).  
  
## <a name="create-a-class-library-project-that-defines-a-dataset"></a>Bir veri kümesini tanımlayan bir sınıf kitaplığı projesi oluşturma  
 Excel çalışma kitabı ve bir konsol uygulaması aynı veri kümesini kullanmak için her ikisi de bu projeler tarafından başvurulan ayrı bir derleme dataset tanımlamanız gerekir. Bu kılavuz için bir sınıf kitaplığı projesinde veri kümesini tanımlayın.  
  
#### <a name="create-the-class-library-project"></a>Sınıf kitaplığı proje oluşturma  
  
1.  Başlat [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)].  
  
2.  Üzerinde **dosya** menüsündeki **yeni**ve ardından **proje**.  
  
3.  Şablonlar bölmesinde **Visual C#** veya **Visual Basic**ve ardından **Windows**.  
  
4.  Proje şablonları listesinde seçin **sınıf kitaplığı**.  
  
5.  İçinde **adı** kutusuna **AdventureWorksDataSet**.  
  
6.  Tıklatın **Gözat**, gidin, *%UserProfile%\My belgeleri* (Windows XP ve önceki sürümler için) veya *%UserProfile%\Documents* (için Windows Vista) klasörünü ve ardından **Klasör Seç**.  
  
7.  İçinde **yeni proje** iletişim kutusunda **çözüm için dizin oluştur** onay kutusu seçilmez.  
  
8.  **Tamam**'ı tıklatın.  
  
     [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)] ekler **AdventureWorksDataSet** için proje **Çözüm Gezgini** ve açılır *Class1.cs* veya *Class1.vb'ye* kod dosyası.  
  
9. İçinde **Çözüm Gezgini**, sağ *Class1.cs* veya *Class1.vb'ye*ve ardından **silmek**. Bu kılavuz için bu dosyayı gerekmez.  
  
## <a name="define-a-dataset-in-the-class-library-project"></a>Sınıf kitaplığı projesinde bir veri kümesini tanımlayın  
 SQL Server 2005 için AdventureWorksLT veritabanından veri içeren yazılmış bir veri kümesi tanımlayın. Bu kılavuzda daha sonra bu veri kümesi Excel çalışma kitabı ve konsol uygulama projesi başvurur.  
  
 Veri kümesi bir *yazılan veri kümesi* AdventureWorksLT veritabanının ürün tablosundaki verileri temsil eden. Yazılan veri kümeleri hakkında daha fazla bilgi için bkz: [Visual Studio'da veri kümesi Araçları](/visualstudio/data-tools/dataset-tools-in-visual-studio).  
  
#### <a name="define-a-typed-dataset-in-the-class-library-project"></a>Sınıf kitaplığı projesinde türü belirtilmiş veri kümesi tanımlayın  
  
1.  İçinde **Çözüm Gezgini**, tıklatın **AdventureWorksDataSet** projesi.  
  
2.  Varsa **veri kaynakları** pencere görünür değil, bunu, menü çubuğu seçme görüntülemek **Görünüm** > **diğer pencereler**  >   **Veri kaynakları**.  
  
3.  Seçin **yeni veri kaynağı Ekle** başlatmak için **veri kaynağı Yapılandırma Sihirbazı**.  
  
4.  Tıklatın **veritabanı**ve ardından **sonraki**.  
  
5.  AdventureWorksLT veritabanını varolan bir bağlantınız varsa bu bağlantıyı seçin ve tıklatın **sonraki**.  
  
     Aksi takdirde, tıklatın **yeni bağlantı**ve **Bağlantı Ekle** yeni bir bağlantı oluşturmak için iletişim kutusu. Daha fazla bilgi için bkz: [yeni bağlantılar eklemek](../data-tools/add-new-connections.md).  
  
6.  İçinde **bağlantı dizesini uygulama yapılandırma dosyasını Kaydet** sayfasında, **sonraki**.  
  
7.  İçinde **veritabanı nesnelerinizi** sayfasında **tabloları** seçip **ürün (SalesLT)**.  
  
8.  **Son**'a tıklayın.  
  
     *AdventureWorksLTDataSet.xsd* dosya eklenen **AdventureWorksDataSet** projesi. Bu dosya, aşağıdaki öğeleri tanımlar:  
  
    -   Adlı bir türü belirtilmiş veri `AdventureWorksLTDataSet`. Bu veri kümesi AdventureWorksLT veritabanının ürün tablosunun içeriğini temsil eder.  
  
    -   Adlı bir TableAdapter `ProductTableAdapter`. Bu TableAdapter okumak ve veri yazmak için kullanılan `AdventureWorksLTDataSet`. Daha fazla bilgi için bkz: [TableAdapter genel bakışı](../data-tools/fill-datasets-by-using-tableadapters.md#tableadapter-overview).  
  
     Bu kılavuzda daha sonra bu nesnelerin her ikisi de kullanır.  
  
9. İçinde **Çözüm Gezgini**, sağ **AdventureWorksDataSet** tıklatıp **yapı**.  
  
     Projenin hatasız oluşturulduğunu doğrulayın.  
  
## <a name="create-an-excel-workbook-project"></a>Bir Excel çalışma kitabı projesi oluşturma  
 Arabirimi için verileri bir Excel çalışma kitabı oluşturun. Bu kılavuzda daha sonra oluşturacağınız bir <xref:Microsoft.Office.Tools.Excel.ListObject> verileri görüntüleyen ve çalışma kitabının veri önbelleğindeki veri kümesi örneğini ekleyeceksiniz.  
  
#### <a name="create-the-excel-workbook-project"></a>Excel çalışma kitabı projesi oluşturma  
  
1.  İçinde **Çözüm Gezgini**, sağ **AdventureWorksDataSet** çözüm, noktasına **Ekle**ve ardından **yeni proje**.  
  
2.  Şablonlar bölmesinde **Visual C#** veya **Visual Basic**, genişletin ve ardından **Office/SharePoint**.  
  
3.  Genişletilmiş altında **Office/SharePoint** düğümü, select **Office eklentileri** düğümü.  
  
4.  Proje şablonları listesinde seçin **Excel 2010 Çalışma kitabı** veya **Excel 2013 çalışma kitabı** projesi.  
  
5.  İçinde **adı** kutusuna **AdventureWorksReport**. Konumunu değiştirmeyin.  
  
6.  **Tamam**'ı tıklatın.  
  
     **Office Proje Sihirbazı için Visual Studio Araçları** açar.  
  
7.  Emin **bir yeni belge oluşturun** seçilir ve tıklatın **Tamam**.  
  
     [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)] açılır **AdventureWorksReport** çalışma kitabı Tasarımcısı'nda ve ekler **AdventureWorksReport** için proje **Çözüm Gezgini**.  
  
## <a name="add-the-dataset-to-data-sources-in-the-excel-workbook-project"></a>Excel çalışma kitabı projesindeki veri kaynaklarına veri kümesi ekleyin  
 Excel çalışma kitabında veri kümesi görüntülemeden önce Excel çalışma kitabı projesindeki veri kaynaklarına ilk veri kümesi eklemeniz gerekir.  
  
1.  İçinde **Çözüm Gezgini**, çift *Sheet1.cs* veya *Sheet1.vb* altında **AdventureWorksReport** projesi.  
  
     Çalışma kitabı tasarımcıda açılır.  
  
2.  Üzerinde **veri** menüsünde tıklatın **yeni veri kaynağı Ekle**.  
  
     **Veri kaynağı Yapılandırma Sihirbazı** açar.  
  
3.  Tıklatın **nesne**ve ardından **sonraki**.  
  
4.  İçinde **bağlamak istediğiniz nesne seçin** sayfasında, tıklatın **Başvuru Ekle**.  
  
5.  Üzerinde **projeleri** sekmesini tıklatın, **AdventureWorksDataSet** ve ardından **Tamam**.  
  
6.  Altında **AdventureWorksDataSet** ad alanı **AdventureWorksDataSet** bütünleştirilmiş tıklatın **AdventureWorksLTDataSet** ve ardından **son** .  
  
     **Veri kaynakları** penceresi açılır ve **AdventureWorksLTDataSet** veri kaynakları listesine eklendi.  
  
## <a name="create-a-listobject-that-is-bound-to-an-instance-of-the-dataset"></a>Veri kümesi örneğine bağlanan ListObject oluşturma  
 Çalışma kitabındaki veri kümesini görüntülemek için Oluştur bir <xref:Microsoft.Office.Tools.Excel.ListObject> dataset örneğine bağlı. Denetimlere veri bağlama hakkında daha fazla bilgi için bkz: [Office çözümlerinde denetimlere veri bağlama](../vsto/binding-data-to-controls-in-office-solutions.md).  
  
1.  İçinde **veri kaynakları** penceresinde genişletin **AdventureWorksLTDataSet** düğümü altında **AdventureWorksDataSet**.  
  
2.  Seçin **ürün** düğümünde görünür ve seçin açılan oka **ListObject** aşağı açılan listesinde.  
  
     Aşağı açılan okunu görünmüyorsa, çalışma kitabını tasarımcıda açık olduğundan emin olun.  
  
3.  Sürükleme **ürün** hücre A1 tablo.  
  
     A <xref:Microsoft.Office.Tools.Excel.ListObject> adlı Denetim `productListObject` çalışma A1 hücresinde başlayarak oluşturulur. Aynı anda, adında bir veri kümesi nesnesi `adventureWorksLTDataSet` ve <xref:System.Windows.Forms.BindingSource> adlı `productBindingSource` projeye eklenir. <xref:Microsoft.Office.Tools.Excel.ListObject> Bağlı <xref:System.Windows.Forms.BindingSource>, sırayla bağlı veri kümesi nesnesi.  
  
## <a name="add-the-dataset-to-the-data-cache"></a>Veri kümesi veri önbelleğine ekleme  
 Çalışma kitabındaki veri kümesine erişebilmesi için Excel çalışma kitabı proje dışındaki kodu etkinleştirmek için veri kümesi veri önbelleğine eklemeniz gerekir. Veri önbelleği hakkında daha fazla bilgi için bkz: [belge düzeyi özelleştirmelerinde verileri önbelleğe](../vsto/cached-data-in-document-level-customizations.md) ve [veriyi önbelleğe](../vsto/caching-data.md).  
  
1.  Tasarımcısı'nda tıklayın **adventureWorksLTDataSet**.  
  
2.  İçinde **özellikleri** penceresindeki ayarlayın **değiştiricileri** özelliğine **ortak**.  
  
3.  Ayarlama **CacheInDocument** özelliğine **doğru**.  
  
## <a name="initialize-the-dataset-in-the-workbook"></a>Çalışma kitabındaki veri kümesi başlatma  
 Konsol uygulaması kullanarak önbelleğe alınmış veri kümesinden veri almadan önce önbelleğe alınmış veri kümesini verilerle doldurmanız gerekir.  
  
1.  İçinde **Çözüm Gezgini**, sağ *Sheet1.cs* veya *Sheet1.vb* dosya ve tıklayın **görünümü kodu**.  
  
2.  Değiştir `Sheet1_Startup` aşağıdaki kod ile olay işleyicisi. Bu kod örneği kullanan `ProductTableAdapter` tanımlanan sınıfı **AdventureWorksDataSet** şu anda boş ise önbellekteki veri kümesini verilerle doldurmak için proje.  
  
     [!code-csharp[Trin_CachedDataWalkthroughs#8](../vsto/codesnippet/CSharp/AdventureWorksDataSet/AdventureWorksReport/Sheet1.cs#8)]
     [!code-vb[Trin_CachedDataWalkthroughs#8](../vsto/codesnippet/VisualBasic/AdventureWorksDataSet/AdventureWorksReport/Sheet1.vb#8)]  
  
## <a name="checkpoint"></a>Denetim noktası  
 Derleme ve derler ve hatasız çalışır emin olmak için Excel çalışma kitabı projesi çalıştırma. Bu işlem ayrıca önbellekteki veri kümesini doldurur ve çalışma kitabını verileri kaydeder.  
  
#### <a name="build-and-run-the-project"></a>Projesini derlemeyi ve çalıştırmayı  
  
1.  İçinde **Çözüm Gezgini**, sağ **AdventureWorksReport** projesi, seçin **hata ayıklama**ve ardından **başlangıç yeni örnek**.  
  
     Proje oluşturulur ve çalışma kitabını Excel'de açar. Aşağıdakileri doğrulayın:  
  
    -   <xref:Microsoft.Office.Tools.Excel.ListObject> Verileri ile doldurur.  
  
    -   Değer **ListPrice** ilk satırında sütun <xref:Microsoft.Office.Tools.Excel.ListObject> 1431.5. Bu kılavuzda daha sonra bir konsol uygulaması değerleri değiştirmek için kullanacağınız **ListPrice** sütun.  
  
2.  Çalışma kitabını kaydedin. Dosya adı veya çalışma kitabının konumunu değiştirmeyin.  
  
3.  Excel'i kapatın.  
  
## <a name="create-a-console-application-project"></a>Bir konsol uygulama projesi oluşturma  
 Çalışma kitabı önbelleğe alınmış veri kümesindeki veriler değiştirmek için kullanılacak bir konsol uygulama projesi oluşturun.  
  
1.  İçinde **Çözüm Gezgini**, sağ **AdventureWorksDataSet** çözüm, noktasına **Ekle**ve ardından **yeni proje**.  
  
2.  İçinde **proje türleri** bölmesini genişletin **Visual C#** veya **Visual Basic**ve ardından **Windows**.  
  
3.  İçinde **şablonları** bölmesinde, **konsol uygulaması**.  
  
4.  İçinde **adı** kutusuna **DataReader**. Konumunu değiştirmeyin.  
  
5.  **Tamam**'ı tıklatın.  
  
     [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)] ekler **DataReader** için proje **Çözüm Gezgini** ve açılır *Program.cs* veya *Module1.vb* kod dosyası.  
  
## <a name="retrieve-data-from-the-cached-dataset-by-using-the-console-application"></a>Konsol uygulaması kullanarak önbelleğe alınmış veri kümesinden veri alma  
 Kullanım <xref:Microsoft.VisualStudio.Tools.Applications.ServerDocument> yerel verileri okumak için konsol uygulaması sınıfında `AdventureWorksLTDataSet` nesnesi. Yerel veri kümesi önbelleğe alınmış veri kümesini verilerle başlatıldı onaylamak için uygulama yerel veri kümesinde satır sayısını görüntüler.  
  
#### <a name="retrieve-data-from-the-cached-dataset"></a>Önbelleğe alınmış veri kümesinden veri alma  
  
1.  İçinde **Çözüm Gezgini**, sağ **DataReader** proje ve tıklatın **Başvuru Ekle**.  
  
2.  Üzerinde **.NET** sekmesinde, Microsoft.VisualStudio.Tools.Applications.ServerDocument'a seçin.  
  
3.  **Tamam**'ı tıklatın.  
  
4.  İçinde **Çözüm Gezgini**, sağ **DataReader** proje ve tıklatın **Başvuru Ekle**.  
  
5.  Üzerinde **projeleri** sekmesine **AdventureWorksDataSet**, tıklatıp **Tamam**.  
  
6.  Açık *Program.cs* veya *Module1.vb* Kod düzenleyicisinde dosya.  
  
7.  Aşağıdakileri ekleyin **kullanarak** (C# için) veya **içeri aktarmalar** (Visual Basic için) kod dosyasının en üstüne deyimi.  
  
     [!code-csharp[Trin_CachedDataWalkthroughs#1](../vsto/codesnippet/CSharp/AdventureWorksDataSet/DataWriter/Program.cs#1)]
     [!code-vb[Trin_CachedDataWalkthroughs#1](../vsto/codesnippet/VisualBasic/AdventureWorksDataSet/DataWriter/Module1.vb#1)]  
  
8.  Aşağıdaki kodu ekleyin `Main` yöntemi. Bu kod, aşağıdaki nesneleri bildirir:  
  
    -   Örneği `AdventureWorksLTDataSet` tanımlanan türü **AdventureWorksDataSet** projesi.  
  
    -   Yapı klasöründeki AdventureWorksReport çalışma kitabı yolu **AdventureWorksReport** projesi.  
  
    -   A <xref:Microsoft.VisualStudio.Tools.Applications.ServerDocument> çalışma kitabındaki veri önbelleği erişmek için kullanılacak nesne.  
  
        > [!NOTE]  
        >  Aşağıdaki kodu kullanarak çalışma kitabı kaydedildiği varsayar *.xlsx* uzantısı. Projenizdeki çalışma kitabının farklı bir uzantı varsa yolu gereken şekilde değiştirin.  
  
     [!code-csharp[Trin_CachedDataWalkthroughs#10](../vsto/codesnippet/CSharp/AdventureWorksDataSet/DataWriter/Program.cs#10)]
     [!code-vb[Trin_CachedDataWalkthroughs#10](../vsto/codesnippet/VisualBasic/AdventureWorksDataSet/DataWriter/Module1.vb#10)]  
  
9. Aşağıdaki kodu ekleyin `Main` yöntemi, önceki adımda eklediğiniz koddan sonra. Bu kod aşağıdaki görevleri gerçekleştirir:  
  
    -   Kullandığı <xref:Microsoft.VisualStudio.Tools.Applications.ServerDocument.CachedData%2A> özelliği <xref:Microsoft.VisualStudio.Tools.Applications.ServerDocument> çalışma kitabında önbelleğe alınmış veri kümesine erişebilmesi için sınıf.  
  
    -   Önbelleğe alınmış veri kümesinden veri yerel veri kümesine okur.  
  
    -   Satır sayısı, veri aldığından emin olmak için yerel veri kümesini görüntüler.  
  
     [!code-csharp[Trin_CachedDataWalkthroughs#11](../vsto/codesnippet/CSharp/AdventureWorksDataSet/DataWriter/Program.cs#11)]
     [!code-vb[Trin_CachedDataWalkthroughs#11](../vsto/codesnippet/VisualBasic/AdventureWorksDataSet/DataWriter/Module1.vb#11)]  
  
10. Üzerinde **yapı** menüsünde tıklatın **Build DataReader**.  
  
## <a name="test-the-project"></a>Projeyi test  
 Konsol uygulamasını çalıştırdığınızda, yerel veri kümesinde satır sayısını görüntüler.  
  
#### <a name="test-the-workbook"></a>Çalışma kitabını test  
  
1.  İçinde **Çözüm Gezgini**, sağ **DataReader** proje, fareyle **hata ayıklama**ve ardından **başlangıç yeni örnek**.  
  
     Uygulamayı yerel veri kümesi 295 satırı bulunduğunu rapor doğrulayın.  
  
2.  Tuşuna **Enter** uygulamayı kapatmak için.  
  
## <a name="next-steps"></a>Sonraki adımlar  
 Bu konularda önbelleğe alınan verilerle çalışma hakkında daha fazla bilgi edinebilirsiniz:  
  
-   Önbelleğe alınan bir veri kümesindeki veriler Excel başlatmadan değiştirme. Daha fazla bilgi için bkz: [izlenecek yol: değişiklik önbelleğe alınmış bir sunucudaki bir çalışma kitabındaki verilere](../vsto/walkthrough-changing-cached-data-in-a-workbook-on-a-server.md).  
  
## <a name="see-also"></a>Ayrıca bkz.  
 [İzlenecek yol: sunucudaki çalışma kitabına veri ekleme](../vsto/walkthrough-inserting-data-into-a-workbook-on-a-server.md)   
 [İzlenecek yol: sunucudaki çalışma kitabında önbelleğe alınmış verileri değiştirme](../vsto/walkthrough-changing-cached-data-in-a-workbook-on-a-server.md)   
  
  