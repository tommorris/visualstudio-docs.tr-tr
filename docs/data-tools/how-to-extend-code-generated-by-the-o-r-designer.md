---
title: 'Nasıl yapılır: O-R tasarımcısı tarafından oluşturulan kod genişletme'
ms.date: 11/04/2016
ms.topic: conceptual
ms.assetid: d6d1122e-2f55-4607-8d8b-48c3c22600fb
author: gewarren
ms.author: gewarren
manager: douge
ms.prod: visual-studio-dev15
ms.technology: vs-data-tools
ms.workload:
- data-storage
ms.openlocfilehash: 73431c09a4e9054d30ccaef3dd1d74ac401c17e7
ms.sourcegitcommit: e13e61ddea6032a8282abe16131d9e136a927984
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/26/2018
ms.locfileid: "31921792"
---
# <a name="how-to-extend-code-generated-by-the-or-designer"></a>Nasıl yapılır: O/R tasarımcısı tarafından oluşturulan kod genişletme
Tarafından oluşturulan kodu [!INCLUDE[vs_ordesigner_short](../data-tools/includes/vs_ordesigner_short_md.md)] sınıflar ve diğer nesnelere Tasarımcı yüzey üzerinde değişiklik yapıldığında yeniden oluşturur. Tasarımcı kodu yeniden oluşturur, bu kod yeniden oluşturma işlemi nedeniyle, oluşturulan kod eklediğiniz herhangi bir kod genellikle üzerine yazılır. [!INCLUDE[vs_ordesigner_short](../data-tools/includes/vs_ordesigner_short_md.md)] Yazılmaz kodu parçalı sınıf dosyaları Ekle oluşturma yeteneği sağlar. Bir örneği tarafından oluşturulan kodu kendi kodunuzu ekleme [!INCLUDE[vs_ordesigner_short](../data-tools/includes/vs_ordesigner_short_md.md)] veri doğrulama LINQ-SQL (varlık) sınıfları için ekleme. Bilgi için bkz: [nasıl yapılır: sınıflar için doğrulama ekleme](../data-tools/how-to-add-validation-to-entity-classes.md).

[!INCLUDE[note_settings_general](../data-tools/includes/note_settings_general_md.md)]

## <a name="adding-code-to-an-entity-class"></a>Bir varlık sınıfı için kod ekleme

#### <a name="to-create-a-partial-class-and-add-code-to-an-entity-class"></a>Bir parçalı sınıf oluşturun ve kod bir varlık sınıfı eklemek için

1.  Açın veya yeni bir LINQ to SQL sınıfları dosyası oluşturun (**.dbml** dosyası) içinde [!INCLUDE[vs_ordesigner_short](../data-tools/includes/vs_ordesigner_short_md.md)]. (Çift **.dbml** dosyasını **Çözüm Gezgini**/**Database Explorer**.)

2.  İçinde [!INCLUDE[vs_ordesigner_short](../data-tools/includes/vs_ordesigner_short_md.md)], doğrulama ekleyin ve ardından istediğiniz sınıfı sağ **görünümü kodu**.

     Seçilen varlık sınıfı için bir parçalı sınıf ile Kod Düzenleyicisi açılır.

3.  Varlık sınıfı için kısmi sınıf bildirimindeki kodunuzu ekleyin.

## <a name="adding-code-to-a-datacontext"></a>DataContext için kod ekleme

#### <a name="to-create-a-partial-class-and-add-code-to-a-datacontext"></a>Bir parçalı sınıf oluşturun ve bir DataContext kodu eklemek için

1.  Açın veya yeni bir LINQ to SQL sınıfları dosyası oluşturun (**.dbml** dosyası) içinde [!INCLUDE[vs_ordesigner_short](../data-tools/includes/vs_ordesigner_short_md.md)]. (Çift **.dbml** dosyasını **Çözüm Gezgini**/**Database Explorer**.)

2.  İçinde [!INCLUDE[vs_ordesigner_short](../data-tools/includes/vs_ordesigner_short_md.md)], Tasarımcı üzerinde boş bir alana sağ tıklayın ve ardından **görünümü kodu**.

     Kod Düzenleyicisi DataContext için bir parçalı sınıf ile açılır.

3.  Kodunuzu DataContext parçalı sınıf bildirimi ekleyin.

## <a name="see-also"></a>Ayrıca bkz.

- [LINQ-SQL Visual Studio Araçları](../data-tools/linq-to-sql-tools-in-visual-studio2.md)
- [İzlenecek yol: LINQ-SQL sınıfları (O R Tasarımcısı) oluşturma](how-to-create-linq-to-sql-classes-mapped-to-tables-and-views-o-r-designer.md)
- [LINQ to SQL](/dotnet/framework/data/adonet/sql/linq/index)