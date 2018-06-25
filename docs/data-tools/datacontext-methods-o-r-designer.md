---
title: DataContext yöntemleri (O R Tasarımcısı)
ms.date: 11/04/2016
ms.topic: conceptual
ms.assetid: c149f4e5-3b61-4c33-892e-3e26d47f3eeb
author: gewarren
ms.author: gewarren
manager: douge
ms.prod: visual-studio-dev15
ms.technology: vs-data-tools
ms.workload:
- data-storage
ms.openlocfilehash: 3d8e3a39c79b5dee339c8835c78143277f3015f6
ms.sourcegitcommit: 30f653d9625ba763f6b58f02fb74a24204d064ea
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/25/2018
ms.locfileid: "36756135"
---
# <a name="datacontext-methods-or-designer"></a>DataContext yöntemleri (O/R Tasarımcısı)

<xref:System.Data.Linq.DataContext> yöntemler (bağlamında [LINQ-SQL Visual Studio Araçları](../data-tools/linq-to-sql-tools-in-visual-studio2.md)), yöntemler <xref:System.Data.Linq.DataContext> saklı yordamları ve işlevleri bir veritabanında çalıştırın sınıfı.

<xref:System.Data.Linq.DataContext> Sınıfı bir [!INCLUDE[vbtecdlinq](../data-tools/includes/vbtecdlinq_md.md)] conduit arasında bir SQL Server veritabanı olarak davranan sınıfı ve [!INCLUDE[vbtecdlinq](../data-tools/includes/vbtecdlinq_md.md)] o veritabanına eşlenen sınıflar. <xref:System.Data.Linq.DataContext> Sınıfı bağlantı dizesi bilgilerini ve bir veritabanına bağlanma ve veritabanındaki verileri işlemek için yöntemler içerir. Varsayılan olarak, <xref:System.Data.Linq.DataContext> sınıfı, gibi çağırabilirsiniz birkaç yöntem içerir <xref:System.Data.Linq.DataContext.SubmitChanges%2A> gönderir yöntemi güncelleştirilmiş verileri [!INCLUDE[vbtecdlinq](../data-tools/includes/vbtecdlinq_md.md)] veritabanı sınıfları. Ayrıca, ek oluşturabilirsiniz <xref:System.Data.Linq.DataContext> saklı yordamları ve işlevleri için eşleme yöntemleri. Diğer bir deyişle, bu özel yöntemleri çağırma saklı yordam veya işlev veritabanında için çalıştığı <xref:System.Data.Linq.DataContext> yöntemi eşlenmedi. İçin yeni yöntemler ekleyebilirsiniz <xref:System.Data.Linq.DataContext> herhangi bir sınıf genişletmek için yöntemleri eklemek gibi sınıfı. Ancak, hakkındaki tartışmalara içinde <xref:System.Data.Linq.DataContext> bağlamında yöntemleri **O/R Tasarımcısı**, bu <xref:System.Data.Linq.DataContext> saklı yordamları ve ele alınan işlevleri için eşleme yöntemleri.

## <a name="methods-pane"></a>Yöntemleri bölmesi

<xref:System.Data.Linq.DataContext> saklı yordamları ve işlevleri için eşleme yöntemlerini görüntülenir **yöntemleri** bölmesinde **O/R Tasarımcısı**. **Yöntemleri** bölmesidir tarafında bölmesinde **varlıklar** bölmesinde (ana tasarım yüzeyi). **Yöntemleri** bölmesi listeler tüm <xref:System.Data.Linq.DataContext> kullanılarak oluşturulan yöntemleri **O/R Tasarımcısı**. Varsayılan olarak, **yöntemleri** bölmesinde boş; Sürükle saklı yordamları veya işlevlerden **Sunucu Gezgini** veya **Database Explorer** üzerine **O/R Tasarımcısı**  oluşturmak için <xref:System.Data.Linq.DataContext> yöntemleri ve doldurmak **yöntemleri** bölmesi. Daha fazla bilgi için bkz: [nasıl yapılır: saklı yordamları ve işlevleri (O/R Tasarımcısı) eşlenen DataContext oluşturma yöntemleri](../data-tools/how-to-create-datacontext-methods-mapped-to-stored-procedures-and-functions-o-r-designer.md).

> [!NOTE]
> Açın ve sağ tıklayarak yöntemleri bölmesini kapatmak **O/R Tasarımcısı** ve ardından **yöntemler Bölmesini Gizle** veya **yöntemleri bölmesini göster**, veya klavyekısayolunukullanın **CTRL**+**1**.

## <a name="two-types-of-datacontext-methods"></a>İki tür DataContext yöntemi

DataContext, saklı yordamları ve işlevleri veritabanındaki Eşle bu yöntemleri yöntemleridir. Oluşturma ve DataContext yöntemleri eklemek **yöntemleri** bölmesinde **O/R Tasarımcısı**. İki farklı vardır <xref:System.Data.Linq.DataContext> yöntemleri; bir veya daha fazla sonuç kümesi döndüren olanlar ve değişmeyen:

-   <xref:System.Data.Linq.DataContext> bir veya daha fazla sonuç kümesi döndüren yöntemleri:

     Bu tür oluşturma <xref:System.Data.Linq.DataContext> saklı yordamları ve işlevleri veritabanında çalıştırmak ve sonuçları döndürmek, uygulamanızın yalnızca gerektiğinde yöntemi. Daha fazla bilgi için bkz: [nasıl yapılır: saklı yordamları ve işlevleri (O/R Tasarımcısı) eşlenen DataContext oluşturma yöntemleri](../data-tools/how-to-create-datacontext-methods-mapped-to-stored-procedures-and-functions-o-r-designer.md), System.Data.Linq.ISingleResult\<T >, ve <xref:System.Data.Linq.IMultipleResults>.

-   <xref:System.Data.Linq.DataContext> Sonuç kümesi döndüren değil yöntemleri: gibi ekler, güncelleştirmeleri ve belirli bir varlık sınıfı için siler.

     Bu tür oluşturma <xref:System.Data.Linq.DataContext> varsayılan kullanmak yerine saklı yordamları çalıştırmak, uygulamanızın sahip olduğunda yöntemi [!INCLUDE[vbtecdlinq](../data-tools/includes/vbtecdlinq_md.md)] kaydetme davranışını değiştiren bir varlık sınıfı ve veritabanı arasında veri. Daha fazla bilgi için bkz: [nasıl yapılır: güncelleştirme, ekleme ve silme (O/R Tasarımcısı) gerçekleştirmek için saklı yordamlar atamak](../data-tools/how-to-assign-stored-procedures-to-perform-updates-inserts-and-deletes-o-r-designer.md).

## <a name="return-types-of-datacontext-methods"></a>Dönüş türleri DataContext yöntemi

Saklı yordamları ve işlevleri sürüklediğinizde **Sunucu Gezgini** veya **Database Explorer** üzerine **O/R Tasarımcısı**, dönüş türü oluşturulan <xref:System.Data.Linq.DataContext> yöntemi, öğenin bırakın yere bağlı olarak farklılık gösterir. Öğeleri doğrudan varolan bir varlık sınıfı bırakarak oluşturur bir <xref:System.Data.Linq.DataContext> varlık sınıfı dönüş türü yöntemiyle; boş bir alanı üzerine öğeleri bırakma **O/R Tasarımcısı** oluşturur (ya da bölmesinde) bir <xref:System.Data.Linq.DataContext> yöntemi otomatik olarak oluşturulan bir türü döndürür. Otomatik olarak oluşturulan saklı yordam veya işlev adı ve saklı yordam veya işlev tarafından döndürülen alanlara eşleme özelliklerini eşleşen ada sahiptir.

> [!NOTE]
> Dönüş türünü değiştirebilirsiniz bir <xref:System.Data.Linq.DataContext> yöntemleri bölmesine ekledikten sonra yöntemi. İnceleme veya dönüş türünü değiştirmek için bir <xref:System.Data.Linq.DataContext> yöntemi seçin ve incelemek **dönüş türü** özelliğinde **özellikleri** penceresi. Daha fazla bilgi için bkz: [nasıl yapılır: bir DataContext yöntemi (O/R Tasarımcısı) dönüş türünü değiştirme](../data-tools/how-to-change-the-return-type-of-a-datacontext-method-o-r-designer.md).

O/R Tasarımcısı yüzeyine veritabanından sürüklediğiniz nesneleri veritabanında nesne adına göre otomatik olarak adlandırılır. Aynı nesne birden çok kez sürüklediğinizde, bir sayı adlarını ayıran yeni adının sonuna eklenir. Veritabanı nesne adları, boşluk veya Visual Basic veya C# içinde değil desteklenen karakter içerdiğinde, boşluk veya geçersiz bir karakter alt çizgi ile değiştirilir.

## <a name="see-also"></a>Ayrıca bkz.

- [LINQ-SQL Visual Studio Araçları](../data-tools/linq-to-sql-tools-in-visual-studio2.md)
- [LINQ to SQL](/dotnet/framework/data/adonet/sql/linq/index)
- [Saklı yordamlar](/dotnet/framework/data/adonet/sql/linq/stored-procedures)
- [Nasıl yapılır: saklı yordamları ve işlevleri (O/R Tasarımcısı) eşlenen DataContext yöntemleri oluşturma](../data-tools/how-to-create-datacontext-methods-mapped-to-stored-procedures-and-functions-o-r-designer.md)
- [Nasıl yapılır: güncelleştirme, ekleme ve silme (O/R Tasarımcısı) gerçekleştirmek için saklı yordamlar atayın](../data-tools/how-to-assign-stored-procedures-to-perform-updates-inserts-and-deletes-o-r-designer.md)
- [İzlenecek yol: Ekle özelleştirme, güncelleştirme ve Varlık davranışını silme](../data-tools/walkthrough-customizing-the-insert-update-and-delete-behavior-of-entity-classes.md)
- [İzlenecek yol: LINQ (O R Tasarımcısı) SQL sınıfları için oluşturma](how-to-create-linq-to-sql-classes-mapped-to-tables-and-views-o-r-designer.md)