---
title: 'İzlenecek yol: önbellekteki veri kümesini kullanarak ana ayrıntı ilişkisi oluşturma'
ms.custom: ''
ms.date: 02/02/2017
ms.technology:
- office-development
ms.topic: conceptual
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- master-detail tables [Office development in Visual Studio], walkthroughs
- data caching [Office development in Visual Studio], Master/Detail Relation
author: TerryGLee
ms.author: tglee
manager: douge
ms.workload:
- office
ms.openlocfilehash: 534398e57c1a8111f2b1f83a61322a581539c962
ms.sourcegitcommit: ce154aee5b403d5c1c41da42302b896ad3cf8d82
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/07/2018
ms.locfileid: "34845460"
---
# <a name="walkthrough-create-a-master-detail-relation-using-a-cached-dataset"></a>İzlenecek yol: önbellekteki veri kümesini kullanarak ana ayrıntı ilişkisi oluşturma
  Bu kılavuz, bir çalışma sayfasında bir ana öğe/ayrıntı ilişkisi oluşturma ve veriyi önbelleğe almayı çözümü çevrimdışı kullanılabilir gösterir.  
  
 [!INCLUDE[appliesto_xlalldoc](../vsto/includes/appliesto-xlalldoc-md.md)]  
  
 Bu gözden geçirme sırasında öğreneceksiniz nasıl yapılır:  
  
-   Bir çalışma sayfasına denetimler ekleme.  
  
-   Bir çalışma sayfasına önbelleğe alınacak bir veri kümesi ayarlayın.  
  
-   Kayıtlarda gezinmeye olanak sağlamak için kodu ekleyin.  
  
-   Projenizi sınayın.  
  
> [!NOTE]  
>  Bilgisayarınız, aşağıdaki yönergelerde yer alan Visual Studio kullanıcı arabirimi öğelerinden bazıları için farklı adlar veya konumlar gösterebilir. Sahip olduğunuz Visual Studio sürümü ve kullandığınız ayarlar bu öğeleri belirler. Daha fazla bilgi için bkz: [Visual Studio IDE'yi kişiselleştirme](../ide/personalizing-the-visual-studio-ide.md).  
  
## <a name="prerequisites"></a>Önkoşullar  
 Bu izlenecek yolu tamamlamak için aşağıdaki bileşenlere ihtiyacınız vardır:  
  
-   [!INCLUDE[vsto_vsprereq](../vsto/includes/vsto-vsprereq-md.md)]  
  
-   [!INCLUDE[Excel_15_short](../vsto/includes/excel-15-short-md.md)] veya [!INCLUDE[Excel_14_short](../vsto/includes/excel-14-short-md.md)].  
  
-   Northwind SQL Server örnek veritabanına erişim. Veritabanı geliştirme bilgisayarınızda veya bir sunucuda olabilir.  
  
-   SQL Server veritabanına yazma ve okuma izni.  
  
## <a name="create-a-new-project"></a>Yeni bir proje oluşturma  
 Bu adımda, bir Excel çalışma kitabı projesi oluşturur.  
  
### <a name="to-create-a-new-project"></a>Yeni bir proje oluşturmak için  
  
1.  Adında bir Excel çalışma kitabı projesi oluşturun **My ana-ayrıntı**, Visual Basic veya C# kullanarak. Olduğundan emin olun **bir yeni belge oluşturun** seçilir. Daha fazla bilgi için bkz: [nasıl yapılır: Visual Studio'da Office projeleri oluşturma](../vsto/how-to-create-office-projects-in-visual-studio.md).  
  
 Visual Studio Tasarımcısı'nda yeni Excel çalışma kitabı açılır ve ekler **My ana-ayrıntı** için proje **Çözüm Gezgini**.  
  
## <a name="create-the-data-source"></a>Veri kaynağı oluşturun  
 Kullanım **veri kaynakları** penceresi türü belirtilmiş veri kümesi projenize ekleyin.  
  
### <a name="to-create-the-data-source"></a>Veri kaynağı oluşturmak için  
  
1.  Varsa **veri kaynakları** pencere görünür değil, bunu, menü çubuğu seçme görüntülemek **Görünüm** > **diğer pencereler**  >   **Veri kaynakları**.  
  
2.  Seçin **yeni veri kaynağı Ekle** başlatmak için **veri kaynağı Yapılandırma Sihirbazı**.  
  
3.  Seçin **veritabanı** ve ardından **sonraki**.  
  
4.  Northwind örnek SQL Server veritabanı için bir veri bağlantısı seçin veya yeni bir bağlantı kullanarak eklemek **yeni bağlantı** düğmesi.  
  
5.  Seçtikten veya bağlantı oluşturduktan sonra tıklatın **sonraki**.  
  
6.  Bağlantı seçiliyse kaydetme seçeneğini ve ardından temizlemek **sonraki**.  
  
7.  Genişletme **tabloları** düğümünde **veritabanı nesnelerinin** penceresi.  
  
8.  Seçin **siparişleri** tablo ve **sipariş ayrıntılarını** tablo.  
  
9. **Son**'a tıklayın.  
  
 Sihirbaz iki tablolara ekler **veri kaynakları** penceresi. Projenize görünür türü belirtilmiş veri kümesi de ekler **Çözüm Gezgini**.  
  
## <a name="add-controls-to-the-worksheet"></a>Çalışma sayfasına denetimler ekleme  
 Bu adımda, adlandırılmış bir aralık, bir liste nesnesi ve iki düğme birinci çalışma sayfasına ekler. İlk olarak, adlandırılmış aralığın liste nesnesinden ekleyip **veri kaynakları** penceresi otomatik olarak bir veri kaynağına bağlı böylece. Ardından, düğmelerden eklemek **araç**.  
  
### <a name="to-add-a-named-range-and-a-list-object"></a>Adlandırılmış bir aralık ve bir liste nesnesi eklemek için  
  
1.  Doğrulayın **My ana Detail.xlsx** çalışma kitabı, Visual Studio Tasarımcısı'nda açık ile **Sheet1** görüntülenir.  
  
2.  Açık **veri kaynakları** penceresi ve genişletin **siparişleri** düğümü.  
  
3.  Seçin **OrderID** sütun ve görüntülenen açılan oku tıklatın.  
  
4.  Tıklatın **NamedRange** aşağı açılan listeyi ve ardından sürükleyin **OrderID** hücre sütun **A2**.  
  
     A <xref:Microsoft.Office.Tools.Excel.NamedRange> adlı Denetim `OrderIDNamedRange` hücresinde oluşturulur **A2**. Aynı zamanda bir <xref:System.Windows.Forms.BindingSource> adlı `OrdersBindingSource`, bir tablo bağdaştırıcısı ve bir <xref:System.Data.DataSet> örneği projeye eklenir. Denetimin bağlı olduğu <xref:System.Windows.Forms.BindingSource>, sırayla bağlı <xref:System.Data.DataSet> örneği.  
  
5.  Aşağı kaydırın altında olan sütunlar geçmiş **siparişleri** tablo. Listenin en altta **sipariş ayrıntılarını** tablo; bir alt öğesi değil çünkü **siparişleri** tablo. Bunu seçin **sipariş ayrıntılarını** tablosu, aynı düzeyde olanı değil **siparişleri** tablo ve görüntülenen açılan oku tıklatın.  
  
6.  Tıklatın **ListObject** aşağı açılan listeyi ve ardından sürükleyin **sipariş ayrıntıları** hücre tabloya **A6**.  
  
7.  A <xref:Microsoft.Office.Tools.Excel.ListObject> adlı Denetim **Order DetailsListObject** hücresinde oluşturulur **A6**ve bağlı <xref:System.Windows.Forms.BindingSource>.  
  
### <a name="to-add-two-buttons"></a>İki düğmeleri eklemek için  
  
1.  Gelen **ortak denetimler** sekmesinde **araç**, ekleme bir <xref:System.Windows.Forms.Button> hücre denetimine **A3** çalışma sayfasının.  
  
     Bu düğme adlı `Button1`.  
  
2.  Başka bir tane eklemek <xref:System.Windows.Forms.Button> hücre denetimine **B3** çalışma sayfasının.  
  
     Bu düğme adlı `Button2`.  
  
 Ardından, belgede önbelleğe alınacak veri kümesi işaretleyin.  
  
## <a name="cache-the-dataset"></a>Veri kümesi önbelleğe alma  
 Belgede veri kümesini ortak ve ayar yaparak önbelleğe alınacak veri kümesi işaretlemek **CacheInDocument** özelliği.  
  
### <a name="to-cache-the-dataset"></a>Veri kümesi önbelleğe almak için  
  
1.  Seçin **NorthwindDataSet** bileşen alanındaki.  
  
2.  İçinde **özellikleri** penceresinde, değişiklik **değiştiricileri** özelliğine **ortak**.  
  
     Önbelleğe alma etkinleştirmeden önce veri kümeleri ortak olması gerekir.  
  
3.  Değişiklik **CacheInDocument** özelliğine **doğru**.  
  
 Düğmelere metin eklemek ve C# kod olay işleyicilerini kanca eklemek için sonraki adımdır bakın.  
  
## <a name="initialize-the-controls"></a>Denetimleri başlatmak  
 Düğme metni ayarlayın ve sırasında olay işleyicileri ekleyin <xref:Microsoft.Office.Tools.Excel.Workbook.Startup> olay.  
  
### <a name="to-initialize-the-data-and-the-controls"></a>Verileri ve denetimleri başlatmak için  
  
1.  İçinde **Çözüm Gezgini**, sağ **Sheet1.vb** veya **Sheet1.cs**ve ardından **görünümü kodu** kısayol menüsünde.  
  
2.  Aşağıdaki kodu ekleyin `Sheet1_Startup` düğmeleri metnini ayarlamak için yöntem.  
  
     [!code-vb[Trin_VstcoreDataExcel#15](../vsto/codesnippet/VisualBasic/Trin_VstcoreDataExcelVB/Sheet2.vb#15)]
     [!code-csharp[Trin_VstcoreDataExcel#15](../vsto/codesnippet/CSharp/Trin_VstcoreDataExcelCS/Sheet2.cs#15)]  
  
3.  Yalnızca C# ' ta düğme için olay işleyicileri olayları eklemek `Sheet1_Startup` yöntemi.  
  
     [!code-csharp[Trin_VstcoreDataExcel#16](../vsto/codesnippet/CSharp/Trin_VstcoreDataExcelCS/Sheet2.cs#16)]  
  
## <a name="add-code-to-enable-scrolling-through-the-records"></a>Kayıtlarda gezinmeye olanak sağlamak için kod ekleme  
 Kodu ekleyin <xref:System.Windows.Forms.Control.Click> kayıtlar arasında gezinmek için her düğmenin olay işleyicisi.  
  
### <a name="to-scroll-through-the-records"></a>Kayıtlar arasında gezinmek için  
  
1.  Bir olay işleyicisi ekleme <xref:System.Windows.Forms.Control.Click> olayı `Button1`ve geriye doğru kayıtlarda taşımak için aşağıdaki kodu ekleyin:  
  
     [!code-vb[Trin_VstcoreDataExcel#17](../vsto/codesnippet/VisualBasic/Trin_VstcoreDataExcelVB/Sheet2.vb#17)]
     [!code-csharp[Trin_VstcoreDataExcel#17](../vsto/codesnippet/CSharp/Trin_VstcoreDataExcelCS/Sheet2.cs#17)]  
  
2.  Bir olay işleyicisi ekleme <xref:System.Windows.Forms.Control.Click> olayı `Button2`ve kayıtlar arasında ilerlemek için aşağıdaki kodu ekleyin:  
  
     [!code-vb[Trin_VstcoreDataExcel#18](../vsto/codesnippet/VisualBasic/Trin_VstcoreDataExcelVB/Sheet2.vb#18)]
     [!code-csharp[Trin_VstcoreDataExcel#18](../vsto/codesnippet/CSharp/Trin_VstcoreDataExcelCS/Sheet2.cs#18)]  
  
## <a name="test-the-application"></a>Uygulamayı test etme  
 Artık veriler beklendiği gibi görünür ve çözüm çevrimdışı kullanabilir emin olmak için çalışma kitabınızı test edebilirsiniz.  
  
### <a name="to-test-the-data-caching"></a>Veri önbelleğe alma işlemini sınamak için  
  
1.  Tuşuna **F5**.  
  
2.  Adlandırılmış aralığın ve list nesnesinin veri kaynağı ile doldurulduğunu doğrulayın.  
  
3.  Bazı kayıtları düğmeleri tıklatarak kaydırın.  
  
4.  Çalışma kitabını kaydedin ve ardından çalışma kitabını ve Visual Studio'yu kapatın.  
  
5.  Veritabanı bağlantısı devre dışı bırakın. Veritabanı bir sunucuda bulunuyorsa, bilgisayarınızdan ağ kablosunu çıkarın veya veritabanı geliştirme bilgisayarınızda yüklü ise SQL Server hizmetini durdurun.  
  
6.  Excel'i açın ve ardından açın **My ana Detail.xlsx** gelen *\bin* dizini (*\My Master-Detail\bin* Visual Basic'te veya *\My Master-Detail\bin\ hata ayıklama* C#).  
  
7.  Bazı çalışma normalde kesildiğinde çalıştığını görmek için kayıtlar kaydırın.  
  
8.  Veritabanına bağlanın. Veritabanı bir sunucuda bulunuyorsa, bilgisayar ağa yeniden bağlanmak veya veritabanı geliştirme bilgisayarınızda yüklü ise SQL Server hizmetini başlatın.  
  
## <a name="next-steps"></a>Sonraki adımlar  
 Bu kılavuz bir çalışma sayfasında bir ana öğe/ayrıntı ilişkisi oluşturma ve bir veri kümesi önbelleğe alma temellerini gösterir. Sonradan gelebilecek bazı görevler şunlardır:  
  
-   Çözümü dağıtın. Daha fazla bilgi için bkz: [Office çözümü dağıtma](../vsto/deploying-an-office-solution.md)  
  
## <a name="see-also"></a>Ayrıca bkz.  
 [Office çözümlerinde denetimlere veri bağlama](../vsto/binding-data-to-controls-in-office-solutions.md)   
 [Office çözümlerindeki veriler](../vsto/data-in-office-solutions.md)   
 [Verileri önbelleğe](../vsto/caching-data.md)   
 [Konak öğelerine ve denetimlerine genel bakış](../vsto/host-items-and-host-controls-overview.md)  
  
  