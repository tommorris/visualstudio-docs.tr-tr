---
title: "Nasıl yapılır: program aracılığıyla bir Web sayfasını Outlook klasörüyle ilişkilendirme | Microsoft Docs"
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
helpviewer_keywords:
- folders [Office development in Visual Studio], Web pages and
- Outlook [Office development in Visual Studio], Web pages attached to folders
- Web pages [Office development in Visual Studio], Outlook folders
ms.assetid: b211b1b2-11e4-4316-87b7-98a3d10f95d1
caps.latest.revision: "16"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: 63f62f339bba33cb638ec4b9d3067e7a546d1015
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2017
---
# <a name="how-to-programmatically-associate-a-web-page-with-an-outlook-folder"></a>Nasıl yapılır: Program Aracılığıyla Web Sayfasını Outlook Klasörüyle İlişkilendirme
  Bu örnek için adlı bir klasör denetler `HtmlView` Microsoft Office Outlook'ta. Klasör yoksa kod klasörü oluşturur ve bir Web sayfası atar. Klasörü zaten varsa, kodu klasör içeriğini görüntüler.  
  
 [!INCLUDE[appliesto_olkallapp](../vsto/includes/appliesto-olkallapp-md.md)]  
  
## <a name="example"></a>Örnek  
 [!code-csharp[Trin_OL_HTMLFolder#1](../vsto/codesnippet/CSharp/Trin_OL_HTMLFolder/thisaddin.cs#1)]  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Klasörlerle çalışma](../vsto/working-with-folders.md)   
 [Nasıl yapılır: program aracılığıyla klasörü ada göre alma](../vsto/how-to-programmatically-retrieve-a-folder-by-name.md)   
 [Nasıl yapılır: program aracılığıyla özel klasör öğeleri oluşturma](../vsto/how-to-programmatically-create-custom-folder-items.md)  
  
  