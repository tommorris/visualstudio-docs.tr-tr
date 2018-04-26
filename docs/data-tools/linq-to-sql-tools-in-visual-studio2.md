---
title: Visual Studio O/R Tasarımcısı genel bakış
ms.date: 11/04/2016
ms.topic: conceptual
ms.assetid: 45e477c0-5c6b-41f9-b2d0-2808fb4f6537
author: gewarren
ms.author: gewarren
manager: douge
ms.prod: visual-studio-dev15
ms.technology: vs-data-tools
ms.workload:
- data-storage
ms.openlocfilehash: acb279780db1291d62cde8202268e0990a56ea64
ms.sourcegitcommit: e13e61ddea6032a8282abe16131d9e136a927984
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/26/2018
---
# <a name="linq-to-sql-tools-in-visual-studio"></a>LINQ-SQL Visual Studio Araçları

LINQ-SQL Microsoft tarafından yayınlanan ilk nesne ilişkisel eşleme teknolojisi oluştu. İyi temel senaryolarında çalışır ve Visual Studio'da desteklenmeye devam eder, ancak artık etkin geliştirilme aşamasındadır. LINQ-zaten kullanıyor eski bir uygulamayı korurken SQL ya da SQL Server kullanan ve birden çok tablo eşlemesi gerektirmeyen basit uygulamalarda kullanın. Genel olarak, bir nesne ilişkisel Eşleyici katmanı gerekli olduğunda yeni uygulamalar Entity Framework kullanmalıdır.

Visual Studio'da Nesne İlişkisel Tasarımcısı (O/R Tasarımcısı) kullanarak SQL tablolarını temsil eden SQL sınıflar için LINQ oluşturun.

O/R Tasarımcısı tasarım yüzeyinde iki farklı alanlara sahip: varlıklar bölmesi sol ve sağ taraftaki yöntemleri bölmesi. Varlıklar, varlık sınıfları, ilişkileri ve devralma hiyerarşileri görüntüler ana tasarım yüzeyi bölmesidir. Görüntüler tasarım yüzeyi yöntemleri bölmesidir <xref:System.Data.Linq.DataContext> saklı yordamları ve işlevleri için eşlenen yöntemleri.

O/R Tasarımcısı oluşturmak için bir görsel tasarım yüzeyi sağlar [LINQ-SQL](/dotnet/framework/data/adonet/sql/linq/index) sınıflar ve bir veritabanındaki nesnelerde dayalı ilişkilendirmelerini (İlişkiler). Diğer bir deyişle, O/R Tasarımcısı nesne modeli bir veritabanındaki nesneler için eşleşen bir uygulama oluşturmak için kullanılır. Kesin türü belirtilmiş bir de oluşturur <xref:System.Data.Linq.DataContext> sınıflar ve veritabanı arasında veri göndermek ve almak için kullanılır. O/R Tasarımcısı ayrıca saklı yordamlar eşlemek için işlevsellik sağlar ve verecek işlevler <xref:System.Data.Linq.DataContext> veriyor ve sınıflar doldurmak için kullanılan yöntemler. Son olarak, O/R Tasarımcısı sınıflar arasındaki tasarım devralma ilişkileri olanağı sağlar.

## <a name="open-the-or-designer"></a>O/R Tasarımcısı'nı açın

SQL varlık modeli projeniz için bir LINQ eklemek için **proje** > **Yeni Öğe Ekle**ve ardından **LINQ'ten SQL'e sınıflarını** proje öğeleri listesinden:

![LINQ-SQL sınıfları](../data-tools/media/raddata-linq-to-sql-classes.png)

Visual Studio .dbml dosyası oluşturur ve çözümünüze ekler. XML eşleme dosyası ve ilgili kod dosyaları budur.

![Çözüm Gezgini'nde SQL sınıflarına LINQ](../data-tools/media/raddata-linq-to-sql-classes-in-solution-explorer.png)

.Dbml dosya seçtiğinizde, Visual Studio model görsel olarak oluşturmanızı sağlayan O/R Tasarımcısı yüzeyini gösterir. Sunucu Gezgini'nde Northwind müşterileri ve Siparişler tablolarını sürüklenen sonra Tasarımcı aşağıda gösterilmektedir. Tablolar arasında ilişki unutmayın.

![LINQ-SQL Tasarımcısı](../data-tools/media/raddata-linq-to-sql-designer.png)

> [!IMPORTANT]
> O/R Tasarımcısı Basit Nesne İlişkisel Eşleyici çünkü yalnızca 1:1 eşleme ilişkileri destekler. Diğer bir deyişle, bir varlık sınıfı bir veritabanı tablosu veya görünümü ile yalnızca bir 1:1 eşleme ilişkisi olabilir. Birleştirilmiş bir tabloya bir varlık sınıfı eşleme gibi karmaşık eşleme desteklenmiyor; Entity Framework karmaşık eşleme için kullanın. Ayrıca, bir tek yönlü kod oluşturucuyu Tasarımcısı olur. Bu, yalnızca Tasarımcı yüzeyine yaptığınız değişiklikler kod dosyasında yansıtılır anlamına gelir. Kod dosyasını el ile yapılan değişiklikler, O/R Tasarımcısı'nda yansıtılmaz. Kod dosyasını el ile yaptığınız tüm değişiklikler Tasarımcı kaydedilir ve kod yeniden üzerine yazılır. Kullanıcı kodu ekleyin ve O/R tasarımcısı tarafından oluşturulan sınıflar genişletme hakkında daha fazla bilgi için bkz: [nasıl yapılır: genişletmek O/R Tasarımcısı oluşturulan kodda](../data-tools/how-to-extend-code-generated-by-the-o-r-designer.md).

## <a name="create-and-configure-the-datacontext"></a>Oluşturma ve DataContext yapılandırma

Eklediğiniz sonra bir **LINQ'ten SQL'e sınıflarını** öğe projeye ve O/R Tasarımcısı'nı açın, boş bir boş tasarım yüzeyini temsil eden <xref:System.Data.Linq.DataContext> yapılandırılması için hazır. <xref:System.Data.Linq.DataContext> tasarım yüzeyine sürüklenen ilk öğe tarafından sağlanan bağlantı bilgileriyle yapılandırılmış... Bu nedenle, <xref:System.Data.Linq.DataContext> bağlantı bilgilerini tasarım yüzeyine bırakılan ilk öğesi kullanılarak yapılandırılır. Hakkında daha fazla bilgi için <xref:System.Data.Linq.DataContext> sınıfı bakın, [DataContext yöntemleri (O/R Tasarımcısı)](../data-tools/datacontext-methods-o-r-designer.md).

## <a name="create-entity-classes-that-map-to-database-tables-and-views"></a>Veritabanı tabloları ve görünümleri eşlenen sınıflar oluşturma

Tabloları ve görünümleri için veritabanı tabloları ve görünümleri sürükleyerek eşlenen varlık sınıfları oluşturabilirsiniz **Sunucu Gezgini**/**Database Explorer** O/R Tasarımcısı üzerine. Önceki bölümde belirtildiği gibi <xref:System.Data.Linq.DataContext> tasarım yüzeyine sürüklenen ilk öğe tarafından sağlanan bağlantı bilgileriyle yapılandırılır. Farklı bir bağlantı kullanan bir sonraki öğe O/R Tasarımcısı eklediyseniz, bağlantı için değiştirebileceğiniz <xref:System.Data.Linq.DataContext>. Daha fazla bilgi için bkz: [nasıl yapılır: tabloları ve görünümleri (O/R Tasarımcısı) eşlenen SQL sınıfları için oluşturma LINQ](../data-tools/how-to-create-linq-to-sql-classes-mapped-to-tables-and-views-o-r-designer.md).

## <a name="create-datacontext-methods-that-call-stored-procedures-and-functions"></a>Saklı yordamları ve işlevleri çağırma DataContext yöntemleri oluşturma

Oluşturabileceğiniz <xref:System.Data.Linq.DataContext> çağıran yöntemlerini (eşlendiği) saklı yordamları ve işlevleri sürükleyerek **Sunucu Gezgini**/**Database Explorer** O/R Tasarımcısı üzerine. Saklı yordamları ve işlevleri eklendiğinde O/R Tasarımcısı yöntemleri <xref:System.Data.Linq.DataContext>.

> [!NOTE]
> Saklı yordamları ve işlevleri sürüklediğinizde **Sunucu Gezgini**/**Database Explorer** O/R Tasarımcısı, dönüş türü oluşturulan üzerine <xref:System.Data.Linq.DataContext> yöntemi farklıdır öğenin bırakın yere bağlı olarak. Daha fazla bilgi için bkz: [DataContext yöntemleri (O/R Tasarımcısı)](../data-tools/datacontext-methods-o-r-designer.md).

## <a name="configure-a-datacontext-to-use-stored-procedures-to-save-data-between-entity-classes-and-a-database"></a>Saklı yordamları varlık sınıfları ve bir veritabanı arasında veri kaydetmek için kullanılacak bir DataContext yapılandırın

Daha önce belirtildiği gibi oluşturabileceğiniz <xref:System.Data.Linq.DataContext> saklı yordamları ve işlevleri çağırma yöntemleri. Ayrıca, varsayılan LINQ ekler, güncelleştirmeleri gerçekleştiren ve siler SQL çalışma zamanı davranışı için kullanılan saklı yordamlar atayabilirsiniz. Daha fazla bilgi için bkz: [nasıl yapılır: güncelleştirme, ekleme ve silme (O/R Tasarımcısı) gerçekleştirmek için saklı yordamlar atamak](../data-tools/how-to-assign-stored-procedures-to-perform-updates-inserts-and-deletes-o-r-designer.md).

## <a name="inheritance-and-the-or-designer"></a>Devralma ve O/R Tasarımcısı

Diğer nesneleri gibi LINQ'ten SQL'e sınıflarını devralma kullanabilirsiniz ve diğer sınıflardan türetilmiş olmalıdır. Bir veritabanında, çeşitli yollarla devralma ilişkisi oluşturulur. İlişkisel sistemlerinde genellikle gerçekleştirilir gibi O/R Tasarımcısı tek Tablo Devralma kavramını destekler. Daha fazla bilgi için bkz: [nasıl yapılır: devralma O/R Tasarımcısı kullanarak yapılandırma](../data-tools/how-to-configure-inheritance-by-using-the-o-r-designer.md).

## <a name="linq-to-sql-queries"></a>LINQ to SQL sorguları

O/R tasarımcısı tarafından oluşturulan sınıflar ile kullanılmak üzere tasarlanmış [dil ile tümleşik sorgu (LINQ)](/dotnet/csharp/linq/). Daha fazla bilgi için bkz: [nasıl yapılır: Sorgu bilgi](/dotnet/framework/data/adonet/sql/linq/how-to-query-for-information).

## <a name="separate-the-generated-datacontext-and-entity-class-code-into-different-namespaces"></a>Farklı ad alanında oluşturulan DataContext ve varlık sınıfı kod ayırın

O/R Tasarımcısı sağlar **bağlamı Namespace** ve **varlık Namespace** özellikleri <xref:System.Data.Linq.DataContext>. Hangi ad alanı bu özellikleri belirlemek <xref:System.Data.Linq.DataContext> ve varlık sınıfı kodu içine oluşturulur. Bu özellikler varsayılan olarak, boş ve <xref:System.Data.Linq.DataContext> ve varlık sınıflar, uygulamanın ad alanına oluşturulur. Uygulamanın ad alanı dışında bir ad alanı içine kodunu oluşturmak için bir değer olarak girin **bağlamı Namespace** ve/veya **varlık Namespace** özellikleri.

## <a name="reference-content"></a>Başvuru içeriği

- <xref:System.Linq>
- <xref:System.Data.Linq>

## <a name="see-also"></a>Ayrıca bkz.

- [LINQ-SQL (.NET Framework)](/dotnet/framework/data/adonet/sql/linq/index)
- [Sık sorulan sorular (.NET Framework)](/dotnet/framework/data/adonet/sql/linq/frequently-asked-questions)