---
title: 'Nasıl yapılır: LINQ tabloları ve görünümleri (O R Tasarımcısı) eşlenen SQL sınıfları için oluşturma'
ms.date: 11/04/2016
ms.topic: conceptual
ms.assetid: 0fb78bbc-7a78-4ab4-b32f-85ece912e660
author: gewarren
ms.author: gewarren
manager: douge
ms.prod: visual-studio-dev15
ms.technology: vs-data-tools
ms.workload:
- data-storage
ms.openlocfilehash: 11fb4265047387e30327bbbe17c9babf1f23ec61
ms.sourcegitcommit: e9d1018a01af62c3dc5aeb6b325faba7e20bd496
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/28/2018
ms.locfileid: "37089331"
---
# <a name="how-to-create-linq-to-sql-classes-mapped-to-tables-and-views-or-designer"></a>Nasıl yapılır: LINQ tabloları ve görünümleri (O/R Tasarımcısı) eşlenen SQL sınıfları için oluşturma
[!INCLUDE[vbtecdlinq](../data-tools/includes/vbtecdlinq_md.md)] Veritabanı tabloları ve görünümleri eşlenen sınıfları çağrılır *sınıflar*. Bir kaydı oluşturan sütunları tek tek tek tek bir varlık sınıfı özelliklerini Eşle ancak varlık sınıfı bir kayda eşler. Tabloları veya görünümleri sürükleyerek veritabanı tabloları veya görünümleri göre varlık sınıfları oluşturmak **Sunucu Gezgini** veya **Database Explorer** üzerine [LINQ-SQL Visual Studioaraçları](../data-tools/linq-to-sql-tools-in-visual-studio2.md). **O/R Tasarımcısı** sınıfları oluşturur ve belirli geçerlidir [!INCLUDE[vbtecdlinq](../data-tools/includes/vbtecdlinq_md.md)] etkinleştirmek için öznitelikler [!INCLUDE[vbtecdlinq](../data-tools/includes/vbtecdlinq_md.md)] işlevi (veri iletişimi ve özelliklerini düzenleme <xref:System.Data.Linq.DataContext>). Hakkında ayrıntılı bilgi için [!INCLUDE[vbtecdlinq](../data-tools/includes/vbtecdlinq_md.md)] sınıfları için bkz [LINQ to SQL nesne modeli](/dotnet/framework/data/adonet/sql/linq/the-linq-to-sql-object-model).

> [!NOTE]
>  **O/R Tasarımcısı** Basit Nesne İlişkisel Eşleyici olduğundan yalnızca 1:1 eşleme ilişkileri destekler. Diğer bir deyişle, bir varlık sınıfı bir veritabanı tablosu veya görünümü ile yalnızca bir 1:1 eşleme ilişkisi olabilir. Birden çok tablo için bir varlık sınıfı eşleme gibi karmaşık eşleme desteklenmiyor. Ancak, birden fazla ilgili tablo katıldığı bir görünüm için bir varlık sınıfı eşleyebilirsiniz.

## <a name="create-linq-to-sql-classes-that-are-mapped-to-database-tables-or-views"></a>LINQ veritabanı tabloları veya görünümleri eşlenmiş SQL sınıfları için oluşturma
 Sürükleyerek tablolar ya da gelen görünümleri **Sunucu Gezgini** veya **Database Explorer** üzerine **O/R Tasarımcısı** ek olarak sınıflar oluşturur <xref:System.Data.Linq.DataContext> yöntemleri, güncelleştirmeleri gerçekleştirmek için kullanılır.

 Varsayılan olarak, [!INCLUDE[vbtecdlinq](../data-tools/includes/vbtecdlinq_md.md)] çalışma zamanı değişiklikleri güncelleştirilebilir varlık sınıfından veritabanına kaydetmek için mantığı oluşturur. Bu mantık (sütun tanımları ve birincil anahtar bilgilerini) tablo şemasını temel alan. Bu davranış istemiyorsanız, saklı yordamlar ekler, güncelleştirmeleri ve varsayılan kullanmak yerine silme gerçekleştirmek için kullanılacak bir varlık sınıfı yapılandırabilirsiniz [!INCLUDE[vbtecdlinq](../data-tools/includes/vbtecdlinq_md.md)] çalışma zamanı davranışı. Daha fazla bilgi için bkz: [nasıl yapılır: güncelleştirme, ekleme ve silme (O/R Tasarımcısı) gerçekleştirmek için saklı yordamlar atamak](../data-tools/how-to-assign-stored-procedures-to-perform-updates-inserts-and-deletes-o-r-designer.md).

[!INCLUDE[note_settings_general](../data-tools/includes/note_settings_general_md.md)]

### <a name="to-create-linq-to-sql-classes-that-are-mapped-to-database-tables-or-views"></a>LINQ veritabanı tabloları veya görünümleri eşlenmiş SQL sınıfları oluşturmak için

1.  İçinde **Server** veya **Database Explorer**, genişletin **tabloları** veya **görünümleri** ve veritabanı tablosunun bulun veya kullanmak istediğiniz görüntüleyin, uygulama.

2.  Tabloyu sürükleyin veya üzerine görüntüleyin **O/R Tasarımcısı**.

     Bir varlık sınıfı oluşturulur ve tasarım yüzeyine görünür. Varlık sınıfı Seçili tabloyu veya görünümü'ndeki sütunlarda eşleme özellikleri vardır.

## <a name="create-an-object-data-source-and-display-the-data-on-a-form"></a>Nesne veri kaynağına oluşturun ve veriler bir form üzerinde görüntüleyin.
 Varlık sınıflarını kullanarak oluşturduktan sonra **O/R Tasarımcısı**, nesne veri kaynağına oluşturmak ve doldurmak [veri kaynakları penceresi](add-new-data-sources.md) varlık sınıflarla.

### <a name="to-create-an-object-data-source-based-on-linq-to-sql-entity-classes"></a>LINQ üzerinde SQL sınıflar için temel bir nesne veri kaynağı oluşturmak için

1.  Üzerinde **yapı** menüsünde tıklatın **yapı çözümü** projenizi yapılandırmak için.

2.  Üzerinde **veri** menüsünde tıklatın **veri kaynaklarını Göster**.

3.  İçinde **veri kaynakları** penceresinde tıklatın **yeni veri kaynağı Ekle**.

4.  Tıklatın **nesne** üzerinde **bir veri kaynağı türü seç** sayfasında ve ardından **sonraki**.

5.  Düğümleri genişletin ve bulun ve sınıfınızı seçin.

    > [!NOTE]
    >  Varsa **müşteri** sınıfı kullanılabilir değil, Sihirbazı iptal, projeyi oluşturun ve sihirbazı yeniden çalıştırın.

6.  Tıklatın **son** veri kaynağı oluşturun ve eklemek için **müşteri** varlık sınıfı için **veri kaynakları** penceresi.

7.  Sürükleme öğelerinden **veri kaynakları** forma penceresi.

## <a name="see-also"></a>Ayrıca bkz.

- [LINQ-SQL Visual Studio Araçları](../data-tools/linq-to-sql-tools-in-visual-studio2.md)
- [İzlenecek yol: LINQ (O R Tasarımcısı) SQL sınıfları için oluşturma](how-to-create-linq-to-sql-classes-mapped-to-tables-and-views-o-r-designer.md)
- [DataContext yöntemleri (O/R Tasarımcısı)](../data-tools/datacontext-methods-o-r-designer.md)
- [Nasıl yapılır: saklı yordamları ve işlevleri (O/R Tasarımcısı) eşlenen DataContext yöntemleri oluşturma](../data-tools/how-to-create-datacontext-methods-mapped-to-stored-procedures-and-functions-o-r-designer.md)
- [LINQ to SQL nesne modeli](/dotnet/framework/data/adonet/sql/linq/the-linq-to-sql-object-model)
- [İzlenecek yol: Ekle özelleştirme, güncelleştirme ve Varlık davranışını silme](../data-tools/walkthrough-customizing-the-insert-update-and-delete-behavior-of-entity-classes.md)
- [Nasıl yapılır: LINQ-SQL sınıfları (O/R Tasarımcısı) arasında bir ilişki (ilişki) oluşturun](../data-tools/how-to-create-an-association-relationship-between-linq-to-sql-classes-o-r-designer.md)