---
title: Tasarımcı şu anda kullandığı daha Designer'a eklemekte olduğunuz nesneleri farklı veri bağlantısı kullanın. | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.topic: conceptual
ms.assetid: 332ed2f3-3377-4d51-8e3b-fdb98231978e
author: gewarren
ms.author: gewarren
manager: douge
ms.technology: vs-data-tools
ms.workload:
- data-storage
ms.openlocfilehash: c738a9beb0f2807a186a7c8b8e3f7138c82c9bfa
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/16/2018
---
# <a name="the-objects-you-are-adding-to-the-designer-use-a-different-data-connection-than-the-designer-is-currently-using"></a>Tasarımcı şu anda kullandığı daha Designer'a eklediğiniz nesnelerin farklı veri bağlantısı kullanın.
Tasarımcı şu anda kullandığı daha Designer'a eklediğiniz nesnelerin farklı veri bağlantısı kullanın. Tasarımcı tarafından kullanılan bağlantı değiştirmek istiyor musunuz?  
  
 Öğeleri eklediğinizde [!INCLUDE[vs_ordesigner_long](../data-tools/includes/vs_ordesigner_long_md.md)] ([!INCLUDE[vs_ordesigner_short](../data-tools/includes/vs_ordesigner_short_md.md)]), tüm öğeleri bir paylaşılan veri bağlantısı kullanın. (Tasarım yüzeyini temsil eden <xref:System.Data.Linq.DataContext>, yüzey üzerinde tüm nesneleri için tek bir bağlantı kullanır.) Nesne şu anda tasarımcı tarafından kullanılan veri bağlantısı farklı bir veri bağlantısı kullanır Tasarımcısı eklerseniz, bu ileti görüntülenir. Bu hatayı gidermek için var olan bağlantıyı korumak seçebilirsiniz. Bu seçim yaparsanız, seçili nesnenin eklenmez. Nesne eklemek ve sıfırlamak alternatif olarak, seçebileceğiniz <xref:System.Data.Linq.DataContext> yeni bağlantı için bağlantı.  
  
> [!NOTE]
>  Tıklatırsanız **Evet**, tüm varlık sınıfları [!INCLUDE[vs_ordesigner_short](../data-tools/includes/vs_ordesigner_short_md.md)] yeni bir bağlantı eşlenir.  
  
### <a name="to-replace-the-existing-connection-with-the-connection-used-by-the-selected-object"></a>Seçilen nesne tarafından kullanılan bağlantı ile var olan bağlantıyı değiştirmek için  
  
-   **Evet**'i tıklayın.  
  
     Seçilen nesne eklenir [!INCLUDE[vs_ordesigner_short](../data-tools/includes/vs_ordesigner_short_md.md)], ve DataContext.Connection yeni bir bağlantı ayarlayın.  
  
### <a name="to-continue-to-use-the-existing-connection-and-cancel-adding-the-selected-object"></a>Var olan bağlantıyı kullanın ve seçilen nesne eklemeyi iptal etmek devam etmek için  
  
-   **Hayır**'a tıklayın.  
  
     Eylemi iptal edildi. Mevcut bir bağlantı ayarlamak DataContext.Connection kalır.  
  
## <a name="see-also"></a>Ayrıca bkz.
[O/R Tasarımcısı iletileri](../data-tools/o-r-designer-messages.md)  
[LINQ-SQL Visual Studio Araçları](../data-tools/linq-to-sql-tools-in-visual-studio2.md)
 