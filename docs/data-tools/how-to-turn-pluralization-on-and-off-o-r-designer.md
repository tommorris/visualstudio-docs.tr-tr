---
title: "Nasıl yapılır: çoğullaştırma üzerinde ve devre dışı bırak (O R Tasarımcısı) | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 9b693bc3-303a-40a9-97ee-9cef5ca3ae81
caps.latest.revision: "2"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.technology: vs-data-tools
ms.workload: data-storage
ms.openlocfilehash: a78f38d4b02311a164e0858744b70fbc5fb0ddaa
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/22/2017
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
  
## <a name="see-also"></a>Ayrıca Bkz.  
[LINQ-SQL Visual Studio Araçları](../data-tools/linq-to-sql-tools-in-visual-studio2.md)   
[LINQ-SQL](/dotnet/framework/data/adonet/sql/linq/index)   
[Visual Studio'da verilere erişime](../data-tools/accessing-data-in-visual-studio.md)