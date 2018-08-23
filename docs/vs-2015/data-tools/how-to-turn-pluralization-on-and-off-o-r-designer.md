---
title: 'Nasıl yapılır: açma ve kapatma (O R Designer) çoğullaştırma kapatma | Microsoft Docs'
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 9b693bc3-303a-40a9-97ee-9cef5ca3ae81
caps.latest.revision: 6
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: 02fa8b50b28f967a0835f68e85d146ca1eea514b
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/22/2018
ms.locfileid: "42694679"
---
# <a name="how-to-turn-pluralization-on-and-off-or-designer"></a>Nasıl yapılır: Aç çoğullaştırmayı açıp kapamasına (O/R Tasarımcısı)
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Bu konuda en son sürümünü şu yolda bulunabilir: [nasıl yapılır: açma ve kapatma (O R Designer) çoğullaştırma kapatma](https://docs.microsoft.com/visualstudio/data-tools/how-to-turn-pluralization-on-and-off-o-r-designer).  
  
  
Varsayılan olarak, s ya da gelen zellikleri sonlanan adlara sahip veritabanı nesneleri sürüklediğinizde **Sunucu Gezgini**/**veritabanı Gezgini** üzerine [LINQ to SQL araçlarını Visual Studio'da](../data-tools/linq-to-sql-tools-in-visual-studio2.md), tekil için üretilen varlık sınıflarının ad çoğul olarak değiştirilir. Bu, daha doğru bir şekilde oluşturulan varlık sınıfı verilerin tek bir kaydına eşler olgu temsil etmek için gerçekleştirilir. Örneğin, bir Müşteriler tablosunu ekleme [!INCLUDE[vs_ordesigner_short](../includes/vs-ordesigner-short-md.md)] sınıfın yalnızca tek bir müşterinin verilerini tutacak çünkü bir varlık sınıfı sonuçlarında adlı müşteri.  
  
> [!NOTE]
>  Çoğullaştırma yalnızca İngilizce sürümü Visual Studio'nun içinde varsayılan olarak açıktır.  
  
 [!INCLUDE[note_settings_general](../includes/note-settings-general-md.md)]  
  
### <a name="to-turn-pluralization-on-and-off"></a>Çoğullaştırmayı açıp kapatmak için  
  
1.  Üzerinde **Araçları** menüsünü tıklatın **seçenekleri**.  
  
2.  İçinde **seçenekleri** iletişim kutusunda **veritabanı araçları**.  
  
> [!NOTE]
>  Seçin **tüm ayarları göster** varsa **veritabanı araçları** düğümü görünür değil.  
  
1.  Tıklayın **O/R Tasarımcısı**.  
  
2.  Ayarlama **adların Çoğullaştırılmasını** için **etkin** = **False** ayarlanacak [!INCLUDE[vs_ordesigner_short](../includes/vs-ordesigner-short-md.md)] böylece sınıf adları değiştirmez.  
  
3.  Ayarlama **adların Çoğullaştırılmasını** için **etkin** = **True** eklenen nesneleri sınıf adlarını çoğullaştırma kuralları uygulamak için [!INCLUDE[vs_ordesigner_short](../includes/vs-ordesigner-short-md.md)].  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [LINQ to SQL araçlarını Visual Studio'da](../data-tools/linq-to-sql-tools-in-visual-studio2.md)   
 [LINQ to SQL](http://msdn.microsoft.com/library/73d13345-eece-471a-af40-4cc7a2f11655)   
 [Visual Studio'da verilere erişime](../data-tools/accessing-data-in-visual-studio.md)

