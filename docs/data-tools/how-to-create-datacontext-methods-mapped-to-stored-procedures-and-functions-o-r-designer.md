---
title: 'Nasıl yapılır: saklı yordamları ve işlevleri (O R Tasarımcısı) eşlenen DataContext yöntemleri oluşturma'
ms.date: 11/04/2016
ms.topic: conceptual
ms.assetid: e7ca32f1-50b3-48af-ad92-ceafd749296a
author: gewarren
ms.author: gewarren
manager: douge
ms.prod: visual-studio-dev15
ms.technology: vs-data-tools
ms.workload:
- data-storage
ms.openlocfilehash: ffec139089f77a1d5c3ffd855e16f12b31e35c17
ms.sourcegitcommit: e13e61ddea6032a8282abe16131d9e136a927984
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/26/2018
---
# <a name="how-to-create-datacontext-methods-mapped-to-stored-procedures-and-functions-or-designer"></a>Nasıl yapılır: saklı yordamları ve işlevleri (O/R Tasarımcısı) eşlenen DataContext yöntemleri oluşturma
Saklı yordamları ve işlevleri eklenebilir [!INCLUDE[vs_ordesigner_short](../data-tools/includes/vs_ordesigner_short_md.md)] olarak <xref:System.Data.Linq.DataContext> yöntemleri. Yöntemini çağırarak ve gerekli parametre geçirme saklı yordam veya işlev veritabanı üzerinde çalışır ve dönüş türünde veri döndürür <xref:System.Data.Linq.DataContext> yöntemi. Hakkında ayrıntılı bilgi için <xref:System.Data.Linq.DataContext> yöntemleri bkz [DataContext yöntemleri (O/R Tasarımcısı)](../data-tools/datacontext-methods-o-r-designer.md).

> [!NOTE]
>  Saklı yordamlar Ayrıca varsayılan geçersiz kılmak için kullanılabilir [!INCLUDE[vbtecdlinq](../data-tools/includes/vbtecdlinq_md.md)] ekler, güncelleştirmeleri gerçekleştiren ve değişiklikleri veritabanına varlık sınıflardan kaydedildiğinde siler çalışma zamanı davranışı. Daha fazla bilgi için bkz: [nasıl yapılır: güncelleştirme, ekleme ve silme (O/R Tasarımcısı) gerçekleştirmek için saklı yordamlar atamak](../data-tools/how-to-assign-stored-procedures-to-perform-updates-inserts-and-deletes-o-r-designer.md).

## <a name="creating-datacontext-methods"></a>DataContext yöntemi oluşturma
 Oluşturabileceğiniz <xref:System.Data.Linq.DataContext> sürükleyerek yöntemleri saklı yordamları veya işlevlerden **Sunucu Gezgini/veritabanı Gezgini** üzerine [!INCLUDE[vs_ordesigner_short](../data-tools/includes/vs_ordesigner_short_md.md)].

> [!NOTE]
>  Dönüş türü oluşturulan <xref:System.Data.Linq.DataContext> yöntemi farklı nerede saklı yordamı veya üzerinde çalışması bağlı olarak [!INCLUDE[vs_ordesigner_short](../data-tools/includes/vs_ordesigner_short_md.md)]. Öğeleri varolan bir varlık sınıfı doğrudan üzerine bırakarak oluşturur bir <xref:System.Data.Linq.DataContext> yöntemi varlık sınıfı dönüş türüne sahip. Öğe boş bir alanı bırakarak [!INCLUDE[vs_ordesigner_short](../data-tools/includes/vs_ordesigner_short_md.md)] oluşturur bir <xref:System.Data.Linq.DataContext> otomatik olarak oluşturulan bir tür döndüren yöntemi. Dönüş türünü değiştirebilirsiniz bir <xref:System.Data.Linq.DataContext> yöntemleri bölmesine ekledikten sonra yöntemi. İnceleme veya dönüş türünü değiştirmek için bir <xref:System.Data.Linq.DataContext> yöntemi seçin ve incelemek **dönüş türü** özelliğinde **özellikleri** penceresi. Daha fazla bilgi için bkz: [nasıl yapılır: bir DataContext yöntemi (O/R Tasarımcısı) dönüş türünü değiştirme](../data-tools/how-to-change-the-return-type-of-a-datacontext-method-o-r-designer.md).

[!INCLUDE[note_settings_general](../data-tools/includes/note_settings_general_md.md)]

#### <a name="to-create-datacontext-methods-that-return-automatically-generated-types"></a>Otomatik olarak döndüren yöntemler türleri oluşturulan DataContext oluşturmak için

1.  İçinde **Sunucu Gezgini**/**Database Explorer**, genişletin **saklı yordamlar** çalıştığınız veritabanı düğümü.

2.  İstenen saklı yordam bulun ve boş bir alanı sürükleyin [!INCLUDE[vs_ordesigner_short](../data-tools/includes/vs_ordesigner_short_md.md)].

     <xref:System.Data.Linq.DataContext> Yöntemi ile otomatik olarak oluşturulan bir dönüş türü oluşturulur ve görüntülenir **yöntemleri** bölmesi.

#### <a name="to-create-datacontext-methods-that-have-the-return-type-of-an-entity-class"></a>Bir varlık sınıfı dönüş türüne sahip DataContext yöntemleri oluşturmak için

1.  İçinde **Sunucu Gezgini**/**Database Explorer**, genişletin **saklı yordamlar** çalıştığınız veritabanı düğümü.

2.  İstenen saklı yordam bulun ve varolan bir varlık sınıfı sürükleyin [!INCLUDE[vs_ordesigner_short](../data-tools/includes/vs_ordesigner_short_md.md)].

     <xref:System.Data.Linq.DataContext> Yöntemi seçili varlık sınıfı, dönüş türü ile oluşturulur ve görüntülenir **yöntemleri** bölmesi.

> [!NOTE]
>  Varolan dönüş türünü değiştirme hakkında bilgi için <xref:System.Data.Linq.DataContext> yöntemleri bkz [nasıl yapılır: bir DataContext yöntemi (O/R Tasarımcısı) dönüş türünü değiştirme](../data-tools/how-to-change-the-return-type-of-a-datacontext-method-o-r-designer.md).

## <a name="see-also"></a>Ayrıca bkz.

- [LINQ-SQL Visual Studio Araçları](../data-tools/linq-to-sql-tools-in-visual-studio2.md)
- [DataContext yöntemleri (O/R Tasarımcısı)](../data-tools/datacontext-methods-o-r-designer.md)
- [İzlenecek yol: LINQ-SQL sınıfları oluşturma](how-to-create-linq-to-sql-classes-mapped-to-tables-and-views-o-r-designer.md)
- [LINQ to SQL](/dotnet/framework/data/adonet/sql/linq/index)
- [Visual Basic'de LINQ'e giriş](/dotnet/visual-basic/programming-guide/language-features/linq/introduction-to-linq)
- [C# üzerinde LINQ](/dotnet/csharp/linq/linq-in-csharp)