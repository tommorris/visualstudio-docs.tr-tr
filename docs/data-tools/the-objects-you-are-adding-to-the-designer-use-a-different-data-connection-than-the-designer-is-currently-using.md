---
title: "Tasarımcı şu anda kullandığı daha Designer'a eklemekte olduğunuz nesneleri farklı veri bağlantısı kullanın. | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 332ed2f3-3377-4d51-8e3b-fdb98231978e
caps.latest.revision: "3"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.technology: vs-data-tools
ms.openlocfilehash: cb6b3e747db497b80893f271c97bb0f6d8c86894
ms.sourcegitcommit: ee42a8771f0248db93fd2e017a22e2506e0f9404
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/09/2017
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
 