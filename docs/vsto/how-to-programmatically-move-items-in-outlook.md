---
title: "Nasıl yapılır: Outlook'ta program aracılığıyla öğeleri taşıma | Microsoft Docs"
ms.custom: 
ms.date: 02/02/2017
ms.reviewer: 
ms.suite: 
ms.technology: office-development
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- VB
- CSharp
helpviewer_keywords: Outlook folders [Office development in Visual Studio], moving items
ms.assetid: ac524f2e-a3e8-496d-bd5a-714799be44ab
caps.latest.revision: "18"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: fc7afe28e435e0dcdd58c7403f6282ebf3609a23
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2017
---
# <a name="how-to-programmatically-move-items-in-outlook"></a>Nasıl yapılır: Outlook'ta Program Aracılığıyla Öğeleri Taşıma
  Bu örnek, okunmamış e-posta iletileri taşır **gelen** adlı bir klasöre **Test**. Bu örnek yalnızca Word'ün iletileri taşır **Test** içinde `Subject` alan.  
  
 [!INCLUDE[appliesto_olkallapp](../vsto/includes/appliesto-olkallapp-md.md)]  
  
## <a name="example"></a>Örnek  
 [!code-csharp[Trin_OL_MoveItems#1](../vsto/codesnippet/CSharp/Trin_OL_MoveItems/thisaddin.cs#1)]  
  
## <a name="compiling-the-code"></a>Kod Derleniyor  
 Bu örnek gerektirir:  
  
-   Adlı bir Outlook posta klasörü **Test**.  
  
-   Word ile ulaşan e-posta iletisine **Test** içinde `Subject` alan.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Klasörlerle çalışma](../vsto/working-with-folders.md)   
 [Nasıl yapılır: program aracılığıyla klasörü ada göre alma](../vsto/how-to-programmatically-retrieve-a-folder-by-name.md)   
 [Nasıl yapılır: belirli klasör içinde program aracılığıyla arama](../vsto/how-to-programmatically-search-within-a-specific-folder.md)   
 [Nasıl yapılır: bir e-posta iletisi alındığında program aracılığıyla işlem gerçekleştirme](../vsto/how-to-programmatically-perform-actions-when-an-e-mail-message-is-received.md)  
  
  