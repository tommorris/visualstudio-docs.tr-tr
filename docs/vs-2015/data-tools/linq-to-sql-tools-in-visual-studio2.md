---
title: LINQ to SQL Araçları'nda Visual Studio2 | Microsoft Docs
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 45e477c0-5c6b-41f9-b2d0-2808fb4f6537
caps.latest.revision: 15
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: 19d9bccad36a186c93aeb8aef8e93b63320a00d2
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/22/2018
ms.locfileid: "42631988"
---
# <a name="linq-to-sql-tools-in-visual-studio"></a>LINQ to SQL araçlarını Visual Studio'da
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Bu konuda en son sürümünü şu yolda bulunabilir: [LINQ to SQL Araçları'nda Visual Studio2](https://docs.microsoft.com/visualstudio/data-tools/linq-to-sql-tools-in-visual-studio2).  
  
  
LINQ to SQL Microsoft tarafından yayınlanan ilk nesne ilişkisel eşleme teknoloji oluştu. Temel senaryolarında iyi çalışır ve Visual Studio'da desteklenmeye devam eder, ancak artık etkin geliştirilme aşamasındadır. LINQ zaten kullandığı eski bir uygulama korurken SQL veya SQL Server'ı kullanın ve birden çok tablo eşleme gerektirmeyen basit uygulamalar kullanın. Genel olarak, bir nesne ilişkisel eşleyicidir katmanı gerekli olduğunda yeni uygulamalar Entity Framework kullanmanız gerekir.  
  
 Visual Studio kullanarak SQL tablolarını temsil eden SQL sınıflarına LINQ oluşturma [!INCLUDE[vs_ordesigner_short](../includes/vs-ordesigner-short-md.md)].  
  
 [!INCLUDE[vs_ordesigner_short](../includes/vs-ordesigner-short-md.md)] Tasarım yüzeyinde iki farklı alanlara sahiptir: varlıklar bölmesinde solda ve sağdaki yöntemler bölmesi. Varlıklar, varlık sınıfları, ilişkilerini ve devralma hiyerarşilerini görüntüler ana tasarım yüzeyi bölmesidir. Yöntemler bölmesini görüntüler tasarım yüzeyine olduğu <xref:System.Data.Linq.DataContext> saklı yordamları ve işlevleri için eşlenmiş yöntemleri.  
  
 [!INCLUDE[vs_ordesigner_long](../includes/vs-ordesigner-long-md.md)] ([!INCLUDE[vs_ordesigner_short](../includes/vs-ordesigner-short-md.md)]) Oluşturmak için bir görsel tasarım yüzeyi sağlar [LINQ to SQL](http://msdn.microsoft.com/library/73d13345-eece-471a-af40-4cc7a2f11655) varlık sınıfları ve ilişkileri (ilişki) bir veritabanındaki nesneleri temel alan. Diğer bir deyişle, [!INCLUDE[vs_ordesigner_short](../includes/vs-ordesigner-short-md.md)] uygulamada veritabanındaki nesnelerle eşleşen bir nesne modeli oluşturmak için kullanılır. Türü kesin belirlenmiş bir ayrıca oluşturur <xref:System.Data.Linq.DataContext> varlık sınıfları ve veritabanı arasında veri göndermek ve almak için kullanılır. [!INCLUDE[vs_ordesigner_short](../includes/vs-ordesigner-short-md.md)] Ayrıca saklı yordamlar eşlemek üzere işlevsellik sağlar ve yaramaz <xref:System.Data.Linq.DataContext> veriyor ve varlık sınıfları doldurma için kullanılan yöntemler. Son olarak, [!INCLUDE[vs_ordesigner_short](../includes/vs-ordesigner-short-md.md)] tasarım varlık sınıfları arasındaki devralma ilişkileri olanağı sağlar.  
  
## <a name="opening-the-or-designer"></a>O/R Tasarımcısı açma  
 LINQ to SQL varlık modeli projenize eklemek için seçin **proje &#124; Yeni Öğe Ekle** seçip **LINQ to SQL sınıfları** proje öğeleri listesinden:  
  
 ![LINQ to SQL sınıfları](../data-tools/media/raddata-linq-to-sql-classes.png "raddata LINQ to SQL sınıfları")  
  
 Visual Studio bir .dbml dosyası oluşturur ve çözümünüze ekler. XML eşleme dosyası ve ilgili kod dosyaları budur.  
  
 ![LINQ to SQL sınıfları Çözüm Gezgini'nde](../data-tools/media/raddata-linq-to-sql-classes-in-solution-explorer.png "Çözüm Gezgini'nde raddata LINQ to SQL sınıfları")  
  
 Bir .dbml dosyası seçtiğinizde, Visual Studio model görsel olarak oluşturmanıza olanak sağlayan O/R Tasarımcı yüzeyine gösterir. Sunucu Gezgini'nden Northwind Customers ve Orders tablolarını sürüklenen sonra Tasarımcı aşağıda gösterilmiştir. Tablolar arasında ilişki unutmayın.  
  
 ![LINQ to SQL Tasarımcı](../data-tools/media/raddata-linq-to-sql-designer.png "raddata LINQ to SQL Tasarımcı")  
  
> [!IMPORTANT]
>  [!INCLUDE[vs_ordesigner_short](../includes/vs-ordesigner-short-md.md)] Yalnızca 1:1 eşleme ilişkileri desteklediğinden, bir Basit Nesne İlişkisel eşleyicisidir. Diğer bir deyişle, bir varlık sınıfı yalnızca 1:1 eşleme ilişkisi olan bir veritabanı tablosu veya görünümü olabilir. Birleştirilmiş bir tabloya bir varlık sınıfı eşleme gibi karmaşık eşleme desteklenmiyor; Entity Framework için karmaşık eşleme kullanın. Ayrıca, bir tek yönlü bir kod oluşturucuyu Tasarımcısı olur. Başka bir deyişle, Tasarımcı yüzeyine yaptığınız değişiklikleri kod dosyasında yansıtılır. El ile yapılan kod dosyası değil yansıtılır [!INCLUDE[vs_ordesigner_short](../includes/vs-ordesigner-short-md.md)]. Kod dosyasında el ile yaptığınız tüm değişiklikler Tasarımcı kaydedilir ve kod yeniden oluşturulursa üzerine yazılır. Kullanıcı kodu ekleyin ve tarafından oluşturulan sınıflar genişletme hakkında daha fazla bilgi için [!INCLUDE[vs_ordesigner_short](../includes/vs-ordesigner-short-md.md)], bkz: [nasıl yapılır: genişletme O/R Tasarımcısı oluşturulan kod](../data-tools/how-to-extend-code-generated-by-the-o-r-designer.md).  
  
## <a name="creating-and-configuring-the-datacontext"></a>DataContext yapılandırma ve oluşturma  
 Siz ekledikten sonra bir **LINQ to SQL sınıfları** öğesi projeye ve açık [!INCLUDE[vs_ordesigner_short](../includes/vs-ordesigner-short-md.md)], boş bir tasarım yüzeyinde boş bir temsil eden <xref:System.Data.Linq.DataContext> yapılandırılması hazır. <xref:System.Data.Linq.DataContext> tasarım yüzeyine sürüklediğiniz ilk öğesi tarafından sağlanan bağlantı bilgileriyle yapılandırıldı... Bu nedenle, <xref:System.Data.Linq.DataContext> ilk öğesinden tasarım yüzeyine bırakılan bağlantı bilgilerini kullanarak yapılandırılır. Hakkında daha fazla bilgi için <xref:System.Data.Linq.DataContext> sınıfı bakın [DataContext yöntemi (O/R Tasarımcısı)](../data-tools/datacontext-methods-o-r-designer.md).  
  
## <a name="creating-entity-classes-that-map-to-database-tables-and-views"></a>Veritabanı tabloları ve görünümleri eşleştiren varlık sınıfları oluşturma  
 Veritabanı tabloları ve görünümleri sürükleyerek, tablolar ve görünümler ile eşlenen varlık sınıfları oluşturabilirsiniz **Sunucu Gezgini**/**veritabanı Gezgini** üzerine [!INCLUDE[vs_ordesigner_short](../includes/vs-ordesigner-short-md.md)]. Önceki bölümde belirtildiği gibi <xref:System.Data.Linq.DataContext> tasarım yüzeyine sürüklediğiniz ilk öğesi tarafından sağlanan bağlantı bilgileriyle yapılandırılır. Farklı bir bağlantı kullanan bir sonraki öğe için eklenip eklenmediğini [!INCLUDE[vs_ordesigner_short](../includes/vs-ordesigner-short-md.md)], bağlantı için değiştirebileceğiniz <xref:System.Data.Linq.DataContext>. Daha fazla bilgi için [nasıl yapılır: tablolar ve görünümler (O/R Tasarımcısı) ile eşlenen SQL sınıflarına LINQ oluşturma](../data-tools/how-to-create-linq-to-sql-classes-mapped-to-tables-and-views-o-r-designer.md).  
  
## <a name="creating-datacontext-methods-that-call-stored-procedures-and-functions"></a>Saklı yordamları ve işlevleri çağırma DataContext yöntemi oluşturma  
 Oluşturabileceğiniz <xref:System.Data.Linq.DataContext> çağıran yöntemleri (eşleştirilmiş) saklı yordamları ve işlevleri sürükleyerek **Sunucu Gezgini**/**veritabanı Gezgini** üzerine[!INCLUDE[vs_ordesigner_short](../includes/vs-ordesigner-short-md.md)]. Saklı yordamları ve işlevleri eklenir [!INCLUDE[vs_ordesigner_short](../includes/vs-ordesigner-short-md.md)] yöntemleri olarak <xref:System.Data.Linq.DataContext>.  
  
> [!NOTE]
>  Saklı yordamları ve işlevleri sürüklediğinizde **Sunucu Gezgini**/**veritabanı Gezgini** üzerine [!INCLUDE[vs_ordesigner_short](../includes/vs-ordesigner-short-md.md)], dönüş türü oluşturulan <xref:System.Data.Linq.DataContext> yöntemi farklıdır Öğeyi Bırak yere bağlı olarak. Daha fazla bilgi için [DataContext yöntemi (O/R Tasarımcısı)](../data-tools/datacontext-methods-o-r-designer.md).  
  
## <a name="configuring-a-datacontext-to-use-stored-procedures-to-save-data-between-entity-classes-and-a-database"></a>Bir DataContext varlık sınıfları ve veritabanı arasında veri kaydetmek için saklı yordamları kullanmak için yapılandırma  
 Daha önce belirtildiği gibi oluşturabileceğiniz <xref:System.Data.Linq.DataContext> saklı yordamları ve işlevleri çağıran yöntemleri. Ayrıca, aynı zamanda için varsayılan kullanılabilir saklı yordamlar atayabilirsiniz [!INCLUDE[vbtecdlinq](../includes/vbtecdlinq-md.md)] ekleme, güncelleştirme gerçekleştiren ve siler çalışma zamanı davranışı. Daha fazla bilgi için [nasıl yapılır: güncelleştirme, ekleme ve silme (O/R Tasarımcısı) gerçekleştirmek için saklı yordamlar atama](../data-tools/how-to-assign-stored-procedures-to-perform-updates-inserts-and-deletes-o-r-designer.md).  
  
## <a name="inheritance-and-the-or-designer"></a>Devralma ve O/R Tasarımcısı  
 Gibi diğer nesneler [!INCLUDE[vbtecdlinq](../includes/vbtecdlinq-md.md)] sınıflar, devralma kullanabilirsiniz ve diğer sınıflarından türetilmiş. Bir veritabanında kalıtım ilişkileri çeşitli yollarla oluşturulur. [!INCLUDE[vs_ordesigner_short](../includes/vs-ordesigner-short-md.md)] İlişkisel sistemlerde sık uygulandığı şekilde tek tablolu devralma kavramını destekler. Daha fazla bilgi için [nasıl yapılır: O/R Tasarımcısı kullanarak devralmayı yapılandırma](../data-tools/how-to-configure-inheritance-by-using-the-o-r-designer.md).  
  
## <a name="linq-to-sql-queries"></a>LINQ to SQL sorguları  
 Tarafından oluşturulan varlık sınıfları [!INCLUDE[vs_ordesigner_short](../includes/vs-ordesigner-short-md.md)] ile kullanılmak üzere tasarlanmış [LINQ (dil ile tümleşik sorgu)](http://msdn.microsoft.com/library/a73c4aec-5d15-4e98-b962-1274021ea93d). Daha fazla bilgi için [nasıl yapılır: bilgi sorgulama](http://msdn.microsoft.com/library/e538d288-2070-40ca-9da6-4fbc68cd6ad0).  
  
## <a name="separating-the-generated-datacontext-and-entity-class-code-into-different-namespaces"></a>Üretilen DataContext ve varlık sınıfı kodu farklı ad alanında ayırma  
 [!INCLUDE[vs_ordesigner_short](../includes/vs-ordesigner-short-md.md)] Sağlar **bağlam Namespace** ve **varlık Namespace** özellikleri <xref:System.Data.Linq.DataContext>. Bu özellikler ne ad alanı belirlemek <xref:System.Data.Linq.DataContext> ve varlık sınıfı kod içinde oluşturulur. Bu özellikler varsayılan olarak, boş olur ve <xref:System.Data.Linq.DataContext> ve varlık sınıfları, uygulamanın ad alanına oluşturulur. Uygulamanın ad alanı başka bir ad alanı içinde kod üretmek için bir değer olarak girin. **bağlam Namespace** ve/veya **varlık Namespace** özellikleri.  
  
## <a name="in-this-section"></a>Bu bölümde  
 [DataContext yöntemi (O/R Tasarımcısı)](../data-tools/datacontext-methods-o-r-designer.md)  
 Ne <xref:System.Data.Linq.DataContext> yöntemleri olan ve bunların nasıl oluşturulacağı.  
  
 [Veri sınıfı devralma (O/R Tasarımcısı)](../data-tools/data-class-inheritance-o-r-designer.md)  
 Tek tablo devralma ve nasıl öğesinde uygulanır kavramını açıklar [!INCLUDE[vs_ordesigner_short](../includes/vs-ordesigner-short-md.md)].  
  
 [Nasıl yapılır: LINQ to SQL sınıfları tablolar ve görünümler (O/R Tasarımcısı) ile eşlenmiş oluşturma](../data-tools/how-to-create-linq-to-sql-classes-mapped-to-tables-and-views-o-r-designer.md)  
 Tabloları ve görünümleri veritabanındaki eşlendiğine varlık sınıfları oluşturma işlemini açıklar.  
  
 [Nasıl yapılır: LINQ to SQL sınıfları (O/R Tasarımcısı) arasında bir ilişki (ilişki) oluşturun](../data-tools/how-to-create-an-association-relationship-between-linq-to-sql-classes-o-r-designer.md)  
 Arasında bir ilişki oluşturma işlemini açıklamaktadır [!INCLUDE[vbtecdlinq](../includes/vbtecdlinq-md.md)] varlık sınıfları.  
  
 [Nasıl yapılır: saklı yordamları ve işlevleri (O/R Tasarımcısı) için eşlenen DataContext-metotları oluşturma](../data-tools/how-to-create-datacontext-methods-mapped-to-stored-procedures-and-functions-o-r-designer.md)  
 Nasıl oluşturulacağını açıklar <xref:System.Data.Linq.DataContext> bunlar çağrıldığında, saklı yordamları ve işlevleri çalıştırmak yöntemleri.  
  
 [Nasıl yapılır: güncelleştirme, ekleme ve silme (O/R Tasarımcısı) gerçekleştirmek için saklı yordamlar atama](../data-tools/how-to-assign-stored-procedures-to-perform-updates-inserts-and-deletes-o-r-designer.md)  
 Nasıl yapılandırılacağını açıklar bir <xref:System.Data.Linq.DataContext> sınıfları bir veritabanına geri varlıktan verileri kaydedilirken saklı yordamları kullanın.  
  
 [Nasıl yapılır: bir DataContext yöntemi (O/R Tasarımcısı) dönüş türünü değiştirme](../data-tools/how-to-change-the-return-type-of-a-datacontext-method-o-r-designer.md)  
 Dönüş türünü ayarlama işlemi açıklanmaktadır bir <xref:System.Data.Linq.DataContext> varlık sınıfı türü veya O/R tasarımcısı tarafından oluşturulan bir otomatik olarak üretilen tür yöntemi.  
  
 [Nasıl yapılır: Varlık sınıflarına doğrulama ekleme](../data-tools/how-to-add-validation-to-entity-classes.md)  
 Etkinleştirme kodu eklenmesi özelliği değiştiğinde ve varlık sınıfı güncelleştirmeler sırasında kısmi yöntemler oluşturmayı açıklar.  
  
 [Nasıl yapılır: Aç çoğullaştırmayı açıp kapamasına (O/R Tasarımcısı)](../data-tools/how-to-turn-pluralization-on-and-off-o-r-designer.md)  
 Açma ve kapatma otomatik olarak eklenen sınıfları yeniden adlandırılmasını açıklar [!INCLUDE[vs_ordesigner_short](../includes/vs-ordesigner-short-md.md)].  
  
 [Nasıl yapılır: O/R Tasarımcısı kullanarak devralmayı yapılandırma](../data-tools/how-to-configure-inheritance-by-using-the-o-r-designer.md)  
 Tek tablo kalıtım kullanarak varlık sınıflarını yapılandırmayı açıklar [!INCLUDE[vs_ordesigner_short](../includes/vs-ordesigner-short-md.md)].  
  
 [Nasıl yapılır: bir O/R tasarımcısı tarafından oluşturulan kodu genişletme](../data-tools/how-to-extend-code-generated-by-the-o-r-designer.md)  
 Nasıl ve nerede açıklar O/R Tasarımcısı nesnelerde yapılan kod yenilediğinizde üzerine yazılmaz kod eklemek için.  
  
 [İzlenecek yol: Tek tablolu devralma (O/R Tasarımcısı) kullanarak LINQ to SQL sınıfları oluşturma](../data-tools/walkthrough-creating-linq-to-sql-classes-by-using-single-table-inheritance-o-r-designer.md)  
 Tek tablo kalıtım kullanarak varlık sınıflarını yapılandırma için adım adım yönergeler sağlar [!INCLUDE[vs_ordesigner_short](../includes/vs-ordesigner-short-md.md)].  
  
 [İzlenecek yol: INSERT özelleştirme, güncelleştirme ve silme davranışı varlık sınıflarının](../data-tools/walkthrough-customizing-the-insert-update-and-delete-behavior-of-entity-classes.md)  
 Yapılandırma için adım adım yönergeler sağlar bir <xref:System.Data.Linq.DataContext> sınıfları bir veritabanına geri varlıktan verileri kaydedilirken saklı yordamları kullanın.  
  
## <a name="reference-content"></a>Başvuru içeriği  
 <xref:System.Linq>  
  
 <xref:System.Data.Linq>  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [.NET için Visual Studio veri araçları](../data-tools/visual-studio-data-tools-for-dotnet.md)   
 [Sık sorulan sorular](http://msdn.microsoft.com/library/252ed666-0679-4eea-b71b-2f14117ef443)   
 [LINQ to SQL](http://msdn.microsoft.com/library/73d13345-eece-471a-af40-4cc7a2f11655)   
 [Visual Studio'da verilere erişime](../data-tools/accessing-data-in-visual-studio.md)

