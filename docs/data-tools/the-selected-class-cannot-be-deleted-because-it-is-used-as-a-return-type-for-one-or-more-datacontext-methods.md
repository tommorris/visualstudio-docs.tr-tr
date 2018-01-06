---
title: "Seçilen sınıf için bir veya daha fazla DataContext yöntemleri bir dönüş türü olarak kullanıldığından silinemiyor | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: d68254a0-f3a1-47e2-aed3-a83471e1d711
caps.latest.revision: "3"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.technology: vs-data-tools
ms.workload: data-storage
ms.openlocfilehash: 78107218af8c4b32e1cace3137fa15fe31fcbc52
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/22/2017
---
# <a name="the-selected-class-cannot-be-deleted-because-it-is-used-as-a-return-type-for-one-or-more-datacontext-methods"></a>Seçilen sınıf için bir veya daha fazla DataContext yöntemleri bir dönüş türü olarak kullanıldığından silinemiyor
Bir veya daha fazla dönüş türü <xref:System.Data.Linq.DataContext> yöntemleri olan seçili varlık sınıfı. Silme için dönüş türü olarak kullanılan bir varlık sınıfı bir <xref:System.Data.Linq.DataContext> yöntemi başarısız projeyi derleme neden olur. Seçilen varlık sınıfını silmek için tanımlamak <xref:System.Data.Linq.DataContext> farklı varlık sınıfı için kendi dönüş türleri ayarlamak ve bunu kullanan yöntemleri.  
  
 Dönüş türleri dönmek için <xref:System.Data.Linq.DataContext> özgün otomatik olarak oluşturulan türleriyle, yöntemleri silmeniz <xref:System.Data.Linq.DataContext> yöntemi yöntemleri bölmesinden nesneden sürükleyin **Sunucu Gezgini** / **Database Explorer** O/R Tasarımcısı yeniden üzerine.  
  
### <a name="to-correct-this-error"></a>Bu hatayı düzeltmek için  
  
1.  Tanımlamak <xref:System.Data.Linq.DataContext> seçerek varlık sınıfı bir dönüş türü olarak kullanan yöntemleri bir <xref:System.Data.Linq.DataContext> yöntemi yöntemler bölmesinde ve İnceleme **dönüş türü** özelliğinde **özellikleri** penceresi .  
  
2.  Ayarlama **dönüş türü** farklı varlık sınıfı ya da delete <xref:System.Data.Linq.DataContext> yöntemleri bölmesinden yöntemi.  
  
## <a name="see-also"></a>Ayrıca bkz.
[O/R Tasarımcısı iletileri](../data-tools/o-r-designer-messages.md)  
[LINQ-SQL Visual Studio Araçları](../data-tools/linq-to-sql-tools-in-visual-studio2.md)