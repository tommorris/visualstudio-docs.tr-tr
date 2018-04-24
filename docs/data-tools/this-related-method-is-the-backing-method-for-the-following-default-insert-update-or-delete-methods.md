---
title: İlgili bu yöntem aşağıdaki varsayılan INSERT, update veya delete yöntemleri için yedekleme yöntemidir
ms.date: 11/04/2016
ms.topic: reference
ms.assetid: 62afa6da-97cf-48b9-8de3-33e4d72a0377
author: gewarren
ms.author: gewarren
manager: douge
ms.technology: vs-data-tools
ms.workload:
- data-storage
ms.openlocfilehash: 232f8622592a6abd17df4dfefddf6cf26c0c7511
ms.sourcegitcommit: 42ea834b446ac65c679fa1043f853bea5f1c9c95
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/19/2018
---
# <a name="this-related-method-is-the-backing-method-for-the-following-default-insert-update-or-delete-methods"></a>İlgili bu yöntem aşağıdaki varsayılan INSERT, update veya delete yöntemleri için yedekleme yöntemidir

İlgili bu yöntem aşağıdaki varsayılan INSERT, update veya delete yöntemleri için yedekleme yöntemidir. Silinirse, bu yöntemleri de silinir. Devam etmek istiyor musunuz?

Seçili `DataContext` yöntemi şu anda kullanılan INSERT, Update veya Delete yöntemlerden biri olarak O/R Tasarımcısı varlık sınıflarında biri için. Seçilen yöntemi silme INSERT, Update gerçekleştirmek için varsayılan çalışma zamanı davranışını geri dönmek için bu yöntem tarafından kullanılan varlık sınıfı neden veya güncelleştirme sırasında silin.

## <a name="to-delete-the-selected-method-causing-the-entity-class-to-use-runtime-updates"></a>Çalışma zamanı güncelleştirmeleri kullanacak şekilde varlık sınıfı neden seçilen yöntemi silmek için

- **Evet**'i tıklayın.

    Seçilen yöntemi silinir ve bu yöntem, güncelleştirme davranışını geçersiz kılmak için kullanılan sınıfları SQL çalışma zamanı davranışı varsayılan LINQ kullanarak geri alınır.

## <a name="to-close-the-message-box-leaving-the-selected-method-unchanged"></a>İleti kutusunu kapatmak için seçilen yöntemi değişmeden

- **Hayır**'a tıklayın.

    İleti kutusu kapanır ve değişiklik yapılmaz.

## <a name="see-also"></a>Ayrıca bkz.

- [O/R Tasarımcısı iletileri](../data-tools/o-r-designer-messages.md)
- [LINQ-SQL Visual Studio Araçları](../data-tools/linq-to-sql-tools-in-visual-studio2.md)