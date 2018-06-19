---
title: 'Nasıl yapılır: çoğullaştırma üzerinde ve devre dışı bırak (O R Tasarımcısı)'
ms.date: 11/04/2016
ms.topic: conceptual
ms.assetid: 9b693bc3-303a-40a9-97ee-9cef5ca3ae81
author: gewarren
ms.author: gewarren
manager: douge
ms.prod: visual-studio-dev15
ms.technology: vs-data-tools
ms.workload:
- data-storage
ms.openlocfilehash: a8c477ac276ce0ff9c292dc42ba2f5f7d1e53dd9
ms.sourcegitcommit: e13e61ddea6032a8282abe16131d9e136a927984
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/26/2018
ms.locfileid: "31921689"
---
# <a name="how-to-turn-pluralization-on-and-off-or-designer"></a>Nasıl yapılır: çoğullaştırma üzerinde ve devre dışı bırak (O/R Tasarımcısı)
S veya gelen zellikleri bitiş adlara sahip veritabanı nesnelerini sürüklediğinizde, varsayılan olarak, **Sunucu Gezgini**/**Database Explorer** üzerine [LINQ-SQL Visual Studioaraçları](../data-tools/linq-to-sql-tools-in-visual-studio2.md), tekil için oluşturulan varlık sınıflarının adlarını çoğul olarak değiştirilir. Bu, tek bir veri kaydı için oluşturulmuş varlık sınıfı eşlemeleri olgu daha doğru bir şekilde temsil etmek için gerçekleştirilir. Örneğin, müşteriler tabloya ekleme [!INCLUDE[vs_ordesigner_short](../data-tools/includes/vs_ordesigner_short_md.md)] bir varlık sınıfı sonuçlarında sınıfı için yalnızca tek bir müşteri verilerini tutacak çünkü müşteri adlı.

> [!NOTE]
>  Çoğullaştırma yalnızca Visual Studio'nun İngilizce sürümünde varsayılan olarak açıktır.

[!INCLUDE[note_settings_general](../data-tools/includes/note_settings_general_md.md)]

### <a name="to-turn-pluralization-on-and-off"></a>Çoğullaştırma üzerinde ve devre dışı bırakma

1.  Üzerinde **Araçları** menüsünde tıklatın **seçenekleri**.

2.  İçinde **seçenekleri** iletişim kutusunda, genişletin **veritabanı araçları**.

    > [!NOTE]
    >  Seçin **tüm ayarları göster** varsa **veritabanı araçları** düğümü görünür değil.

3.  Tıklatın **O/R Tasarımcısı**.

4.  Ayarlama **adlarının Çoğullaştırma** için **etkin** = **False** ayarlamak için [!INCLUDE[vs_ordesigner_short](../data-tools/includes/vs_ordesigner_short_md.md)] böylece sınıf adları değiştirmez.

5.  Ayarlama **adlarının Çoğullaştırma** için **etkin** = **True** eklenen nesneleri sınıf adlarını çoğullaştırma kuralları uygulamak için [!INCLUDE[vs_ordesigner_short](../data-tools/includes/vs_ordesigner_short_md.md)].

## <a name="see-also"></a>Ayrıca bkz.

- [LINQ-SQL Visual Studio Araçları](../data-tools/linq-to-sql-tools-in-visual-studio2.md)
- [LINQ to SQL](/dotnet/framework/data/adonet/sql/linq/index)
- [Visual Studio'da verilere erişime](../data-tools/accessing-data-in-visual-studio.md)