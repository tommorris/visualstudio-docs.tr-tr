---
title: "Bu yöntemi aşağıdaki varsayılan INSERT, update veya delete yöntemleri için yedekleme yöntemi ile ilgili | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 62afa6da-97cf-48b9-8de3-33e4d72a0377
caps.latest.revision: "3"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.technology: vs-data-tools
ms.openlocfilehash: 3f8a31f886548d03f7acac58d392713ced297b42
ms.sourcegitcommit: ee42a8771f0248db93fd2e017a22e2506e0f9404
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/09/2017
---
# <a name="this-related-method-is-the-backing-method-for-the-following-default-insert-update-or-delete-methods"></a>İlgili bu yöntem aşağıdaki varsayılan INSERT, update veya delete yöntemleri için yedekleme yöntemidir
İlgili bu yöntem aşağıdaki varsayılan INSERT, update veya delete yöntemleri için yedekleme yöntemidir. Silinirse, bu yöntemleri de silinir. Devam etmek istiyor musunuz?  
  
 Seçili `DataContext` yöntemi şu anda kullanılan INSERT, Update veya Delete yöntemlerden biri olarak O/R Tasarımcısı varlık sınıflarında biri için. Seçilen yöntemi silme INSERT, Update gerçekleştirmek için varsayılan çalışma zamanı davranışını geri dönmek için bu yöntem tarafından kullanılan varlık sınıfı neden veya güncelleştirme sırasında silin.  
  
### <a name="to-delete-the-selected-method-causing-the-entity-class-to-use-runtime-updates"></a>Çalışma zamanı güncelleştirmeleri kullanacak şekilde varlık sınıfı neden seçilen yöntemi silmek için  
  
-   **Evet**'i tıklayın.  
  
     Seçilen yöntemi silinir ve bu yöntem, güncelleştirme davranışını geçersiz kılmak için kullanılan sınıfları SQL çalışma zamanı davranışı varsayılan LINQ kullanarak geri alınır.  
  
### <a name="to-close-the-message-box-leaving-the-selected-method-unchanged"></a>İleti kutusunu kapatmak için seçilen yöntemi değişmeden  
  
-   **Hayır**'a tıklayın.  
  
     İleti kutusu kapanır ve değişiklik yapılmaz.  
  
## <a name="see-also"></a>Ayrıca bkz.
[O/R Tasarımcısı iletileri](../data-tools/o-r-designer-messages.md)  
[LINQ-SQL Visual Studio Araçları](../data-tools/linq-to-sql-tools-in-visual-studio2.md)