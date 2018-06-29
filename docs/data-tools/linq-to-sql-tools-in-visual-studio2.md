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
ms.openlocfilehash: 7c7abaa95c3b7c8f5ab78b4d58f383243b176f7a
ms.sourcegitcommit: e9d1018a01af62c3dc5aeb6b325faba7e20bd496
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/28/2018
ms.locfileid: "37089418"
---
# <a name="linq-to-sql-tools-in-visual-studio"></a>LINQ-SQL Visual Studio Araçları

LINQ-SQL Microsoft tarafından yayınlanan ilk nesne ilişkisel eşleme teknolojisi oluştu. İyi temel senaryolarında çalışır ve Visual Studio'da desteklenmeye devam eder, ancak artık etkin geliştirilme aşamasındadır. LINQ-zaten kullanıyor eski bir uygulamayı korurken SQL ya da SQL Server kullanan ve birden çok tablo eşlemesi gerektirmeyen basit uygulamalarda kullanın. Genel olarak, bir nesne ilişkisel Eşleyici katmanı gerekli olduğunda yeni uygulamalar Entity Framework kullanmalıdır.

Visual Studio'da LINQ kullanarak SQL tablolarını temsil eden SQL sınıflar için oluşturduğunuz **Nesne İlişkisel Tasarımcısı** (**O/R Tasarımcısı**).

**O/R Tasarımcısı** tasarım yüzeyinde iki farklı alanlara sahip: varlıklar bölmesi sol ve sağ taraftaki yöntemleri bölmesi. Varlıklar, varlık sınıfları, ilişkileri ve devralma hiyerarşileri görüntüler ana tasarım yüzeyi bölmesidir. Görüntüler tasarım yüzeyi yöntemleri bölmesidir <xref:System.Data.Linq.DataContext> saklı yordamları ve işlevleri için eşlenen yöntemleri.

**O/R Tasarımcısı** oluşturmak için bir görsel tasarım yüzeyi sağlar [LINQ-SQL](/dotnet/framework/data/adonet/sql/linq/index) sınıflar ve bir veritabanındaki nesnelerde dayalı ilişkilendirmelerini (İlişkiler). Diğer bir deyişle, **O/R Tasarımcısı** veritabanındaki nesnelere eşleyen bir uygulamada bir nesne modeli oluşturur. Kesin türü belirtilmiş bir de oluşturur <xref:System.Data.Linq.DataContext> gönderir ve sınıflar ve veritabanı arasındaki verileri alır. **O/R Tasarımcısı** ayrıca saklı yordamlar eşlemek için işlevsellik sağlar ve verecek işlevler <xref:System.Data.Linq.DataContext> veriyor ve sınıflar doldurmak için kullanılan yöntemler. Son olarak, **O/R Tasarımcısı** sınıflar arasındaki tasarım devralma ilişkileri olanağı sağlar.

## <a name="open-the-or-designer"></a>O/R Tasarımcısı'nı açın

SQL varlık modeli projeniz için bir LINQ eklemek için **proje** > **Yeni Öğe Ekle**ve ardından **LINQ'ten SQL'e sınıflarını** proje öğeleri listesinden:

![LINQ-SQL sınıfları](../data-tools/media/raddata-linq-to-sql-classes.png)

Visual Studio oluşturur bir *.dbml* dosya ve çözümünüze ekler. XML eşleme dosyası ve ilgili kod dosyaları budur.

![Çözüm Gezgini'nde SQL sınıflarına LINQ](../data-tools/media/raddata-linq-to-sql-classes-in-solution-explorer.png)

Seçtiğinizde, *.dbml* dosya, Visual Studio gösterir **O/R Tasarımcısı** yüzeyini görsel olarak model oluşturmanızı sağlar. Northwind sonra Tasarımcı aşağıda gösterilmiştir `Customers` ve `Orders` tabloları sürüklenen gelen **Sunucu Gezgini**. Tablolar arasında ilişki unutmayın.

![LINQ-SQL Tasarımcısı](../data-tools/media/raddata-linq-to-sql-designer.png)

> [!IMPORTANT]
> **O/R Tasarımcısı** Basit Nesne İlişkisel Eşleyici olduğundan yalnızca 1:1 eşleme ilişkileri destekler. Diğer bir deyişle, bir varlık sınıfı bir veritabanı tablosu veya görünümü ile yalnızca bir 1:1 eşleme ilişkisi olabilir. Birleştirilmiş bir tabloya bir varlık sınıfı eşleme gibi karmaşık eşleme desteklenmiyor; Entity Framework karmaşık eşleme için kullanın. Ayrıca, bir tek yönlü kod oluşturucuyu Tasarımcısı olur. Bu, yalnızca Tasarımcı yüzeyine yaptığınız değişiklikler kod dosyasında yansıtılır anlamına gelir. Kod dosyasına el ile yapılan bir değişiklik değil yansıtılır **O/R Tasarımcısı**. Kod dosyasını el ile yaptığınız tüm değişiklikler Tasarımcı kaydedilir ve kod yeniden üzerine yazılır. Kullanıcı kodu ekleyin ve tarafından oluşturulan sınıflar genişletme hakkında bilgi için **O/R Tasarımcısı**, bkz: [nasıl yapılır: O/R tasarımcısı tarafından oluşturulan kod genişletmek](../data-tools/how-to-extend-code-generated-by-the-o-r-designer.md).

## <a name="create-and-configure-the-datacontext"></a>Oluşturma ve DataContext yapılandırma

Eklediğiniz sonra bir **LINQ'ten SQL'e sınıflarını** öğe projeye ve açık **O/R Tasarımcısı**, boş bir boş tasarım yüzeyini temsil eden <xref:System.Data.Linq.DataContext> yapılandırılması için hazır. <xref:System.Data.Linq.DataContext> tasarım yüzeyine sürüklenen ilk öğe tarafından sağlanan bağlantı bilgileriyle yapılandırılır. Bu nedenle, <xref:System.Data.Linq.DataContext> bağlantı bilgilerini tasarım yüzeyine bırakılan ilk öğesi kullanılarak yapılandırılır. Hakkında daha fazla bilgi için <xref:System.Data.Linq.DataContext> sınıfı bakın, [DataContext yöntemleri (O/R Tasarımcısı)](../data-tools/datacontext-methods-o-r-designer.md).

## <a name="create-entity-classes-that-map-to-database-tables-and-views"></a>Veritabanı tabloları ve görünümleri eşlenen sınıflar oluşturma

Tabloları ve görünümleri için veritabanı tabloları ve görünümleri sürükleyerek eşlenen varlık sınıfları oluşturabilirsiniz **Sunucu Gezgini** veya **Database Explorer** üzerine **O/R Tasarımcısı**. Önceki bölümde belirtildiği gibi <xref:System.Data.Linq.DataContext> tasarım yüzeyine sürüklenen ilk öğe tarafından sağlanan bağlantı bilgileriyle yapılandırılır. Farklı bir bağlantı kullanan bir sonraki öğe için eklediyseniz **O/R Tasarımcısı**, bağlantı için değiştirebileceğiniz <xref:System.Data.Linq.DataContext>. Daha fazla bilgi için bkz: [nasıl yapılır: tabloları ve görünümleri (O/R Tasarımcısı) eşlenen SQL sınıfları için oluşturma LINQ](../data-tools/how-to-create-linq-to-sql-classes-mapped-to-tables-and-views-o-r-designer.md).

## <a name="create-datacontext-methods-that-call-stored-procedures-and-functions"></a>Saklı yordamları ve işlevleri çağırma DataContext yöntemleri oluşturma

Oluşturabileceğiniz <xref:System.Data.Linq.DataContext> çağıran yöntemlerini (eşlendiği) saklı yordamları ve işlevleri sürükleyerek **Sunucu Gezgini** veya **Database Explorer** üzerine **O/R Tasarımcısı** . Saklı yordamları ve işlevleri eklenir **O/R Tasarımcısı** yöntemleri olarak <xref:System.Data.Linq.DataContext>.

> [!NOTE]
> Saklı yordamları ve işlevleri sürüklediğinizde **Sunucu Gezgini** veya **Database Explorer** üzerine **O/R Tasarımcısı**, dönüş türü oluşturulan <xref:System.Data.Linq.DataContext> yöntemi, öğenin bırakın yere bağlı olarak farklılık gösterir. Daha fazla bilgi için bkz: [DataContext yöntemleri (O/R Tasarımcısı)](../data-tools/datacontext-methods-o-r-designer.md).

## <a name="configure-a-datacontext-to-use-stored-procedures-to-save-data-between-entity-classes-and-a-database"></a>Saklı yordamları varlık sınıfları ve bir veritabanı arasında veri kaydetmek için kullanılacak bir DataContext yapılandırın

Daha önce belirtildiği gibi oluşturabileceğiniz <xref:System.Data.Linq.DataContext> saklı yordamları ve işlevleri çağırma yöntemleri. Ayrıca, LINQ to gerçekleştirir SQL çalışma zamanı davranışı, güncelleştirmeler, ekler ve siler varsayılan için kullanılan saklı yordamlar atayabilirsiniz. Daha fazla bilgi için bkz: [nasıl yapılır: güncelleştirme, ekleme ve silme (O/R Tasarımcısı) gerçekleştirmek için saklı yordamlar atamak](../data-tools/how-to-assign-stored-procedures-to-perform-updates-inserts-and-deletes-o-r-designer.md).

## <a name="inheritance-and-the-or-designer"></a>Devralma ve O/R Tasarımcısı

Diğer nesneleri gibi LINQ'ten SQL'e sınıflarını devralma kullanabilirsiniz ve diğer sınıflardan türetilmiş olmalıdır. Bir veritabanında, çeşitli yollarla devralma ilişkisi oluşturulur. **O/R Tasarımcısı** ilişkisel sistemlerinde genellikle gerçekleştirilir gibi tek Tablo Devralma kavramını destekler. Daha fazla bilgi için bkz: [nasıl yapılır: devralma O/R Tasarımcısı kullanarak yapılandırma](../data-tools/how-to-configure-inheritance-by-using-the-o-r-designer.md).

## <a name="linq-to-sql-queries"></a>LINQ to SQL sorguları

Tarafından oluşturulan sınıflar **O/R Tasarımcısı** ile kullanılmak üzere tasarlanmış [dil ile tümleşik sorgu (LINQ)](/dotnet/csharp/linq/). Daha fazla bilgi için bkz: [nasıl yapılır: Sorgu bilgi](/dotnet/framework/data/adonet/sql/linq/how-to-query-for-information).

## <a name="separate-the-generated-datacontext-and-entity-class-code-into-different-namespaces"></a>Farklı ad alanında oluşturulan DataContext ve varlık sınıfı kod ayırın

**O/R Tasarımcısı** sağlar **bağlamı Namespace** ve **varlık Namespace** özellikleri <xref:System.Data.Linq.DataContext>. Hangi ad alanı bu özellikleri belirlemek <xref:System.Data.Linq.DataContext> ve varlık sınıfı kodu içine oluşturulur. Bu özellikler varsayılan olarak, boş ve <xref:System.Data.Linq.DataContext> ve varlık sınıflar, uygulamanın ad alanına oluşturulur. Uygulamanın ad alanı dışında bir ad alanı içine kodunu oluşturmak için bir değer olarak girin **bağlamı Namespace** ve/veya **varlık Namespace** özellikleri.

## <a name="reference-content"></a>Başvuru içeriği

- <xref:System.Linq>
- <xref:System.Data.Linq>

## <a name="see-also"></a>Ayrıca bkz.

- [LINQ-SQL (.NET Framework)](/dotnet/framework/data/adonet/sql/linq/index)
- [Sık sorulan sorular (.NET Framework)](/dotnet/framework/data/adonet/sql/linq/frequently-asked-questions)