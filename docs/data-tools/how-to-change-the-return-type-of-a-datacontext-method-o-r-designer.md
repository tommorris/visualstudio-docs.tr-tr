---
title: "Nasıl yapılır: bir DataContext yöntemi (O R Tasarımcısı) dönüş türünü değiştirme | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: c5b66bff-6dbb-43c0-bffa-317133ca5b9e
caps.latest.revision: "2"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.technology: vs-data-tools
ms.openlocfilehash: 869460f4ac40aece5421611cd83aad6a7f11ef57
ms.sourcegitcommit: ee42a8771f0248db93fd2e017a22e2506e0f9404
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/09/2017
---
# <a name="how-to-change-the-return-type-of-a-datacontext-method-or-designer"></a>Nasıl yapılır: bir DataContext yöntemi (O/R Tasarımcısı) dönüş türünü değiştirme
Dönüş türü bir <xref:System.Data.Linq.DataContext> yöntemi (bir saklı yordam veya işlevi temel alınarak oluşturulan) farklı olduğu saklı yordamı veya işlevi bağlı olarak [!INCLUDE[vs_ordesigner_short](../data-tools/includes/vs_ordesigner_short_md.md)]. Bir öğenin varolan bir varlık sınıfı doğrudan üzerine bırakın, bir <xref:System.Data.Linq.DataContext> varlık sınıfı dönüş türüne sahip yöntemi (saklı yordam veya işlev tarafından döndürülen veri şeması ve varlık sınıfı şeklini eşleşirse) oluşturulur. Boş bir alanı bir öğe bırakma durumunda [!INCLUDE[vs_ordesigner_short](../data-tools/includes/vs_ordesigner_short_md.md)], <xref:System.Data.Linq.DataContext> otomatik olarak oluşturulan bir tür döndüren yöntem oluşturulur. Dönüş türünü değiştirebilirsiniz bir <xref:System.Data.Linq.DataContext> yöntemleri bölmesine ekledikten sonra yöntemi. İnceleme veya dönüş türünü değiştirmek için bir <xref:System.Data.Linq.DataContext> yöntemi seçin ve **dönüş türü** özelliğinde **özellikleri** penceresi.  
  
> [!NOTE]
>  Geri alınamaz <xref:System.Data.Linq.DataContext> kullanarak otomatik olarak oluşturulan türünü döndürmek için bir varlık sınıfı olarak ayarlanan bir dönüş türüne sahip yöntemleri **özellikleri** penceresi. Geri dönmek için bir <xref:System.Data.Linq.DataContext> yöntemi bir otomatik olarak oluşturulan türünü döndürmek için özgün veritabanı nesnesi O/R Tasarımcısı yeniden sürükleyin gerekir.  
  
[!INCLUDE[note_settings_general](../data-tools/includes/note_settings_general_md.md)]  
  
## <a name="to-change-the-return-type-of-a-datacontext-method-from-the-auto-generated-type-to-an-entity-class"></a>Bir varlık sınıfı için otomatik olarak oluşturulan türünden DataContext yöntemin dönüş türünü değiştirmek için  
  
1.  Seçin <xref:System.Data.Linq.DataContext> yöntemleri bölmesinde yöntemi.  
  
2.  Seçin **dönüş türü** içinde **özellikleri** penceresini açın ve ardından kullanılabilir varlık sınıfı içinde **dönüş türü** listesi. İstenen varlık sınıfı listede değilse, ekleyin veya içinde oluşturulduğu [!INCLUDE[vs_ordesigner_short](../data-tools/includes/vs_ordesigner_short_md.md)] listesine eklemek için.  
  
3.  .Dbml dosyasını kaydedin.  
  
## <a name="to-change-the-return-type-of-a-datacontext-method-from-an-entity-class-back-to-the-auto-generated-type"></a>Otomatik olarak oluşturulan türü geri varlık sınıfından DataContext yöntemin dönüş türünü değiştirmek için  
  
1.  Seçin <xref:System.Data.Linq.DataContext> yöntemleri bölmesinde yöntemi ve silin.  
  
2.  Veritabanı nesnesinden sürükleyin **Sunucu Gezgini**/**Database Explorer** boş bir alana O/R Tasarımcısı'nın üzerine.  
  
3.  .Dbml dosyasını kaydedin.  
  
## <a name="see-also"></a>Ayrıca bkz.
[LINQ-SQL Visual Studio Araçları](../data-tools/linq-to-sql-tools-in-visual-studio2.md)   
[LINQ-SQL](/dotnet/framework/data/adonet/sql/linq/index)   
[DataContext yöntemleri (O/R Tasarımcısı)](../data-tools/datacontext-methods-o-r-designer.md)   
[Nasıl yapılır: saklı yordamları ve işlevleri (O/R Tasarımcısı) eşlenen DataContext yöntemleri oluşturma](../data-tools/how-to-create-datacontext-methods-mapped-to-stored-procedures-and-functions-o-r-designer.md)