---
title: "Nasıl yapılır: program aracılığıyla geçerli Outlook öğesini belirleme | Microsoft Docs"
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
- mail items [Office development in Visual Studio], current
- e-mail [Office development in Visual Studio], current item
- SelectionChange event
- Outlook [Office development in Visual Studio], current item
ms.assetid: b4fb5ccd-b297-463e-9208-1fec42482531
caps.latest.revision: "28"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: d1f577f77179ed0fcfdb3b9dc94575509ee701b6
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2017
---
# <a name="how-to-programmatically-determine-the-current-outlook-item"></a>Nasıl yapılır: Program Aracılığıyla Geçerli Outlook Öğesini Belirleme
  Bu örnek Explorer.SelectionChange olay adı geçerli klasörde ve seçili öğe hakkında bazı bilgileri görüntülemek için kullanır. Kod, daha sonra seçilen öğeyi görüntüler.  
  
 [!INCLUDE[appliesto_olkallapp](../vsto/includes/appliesto-olkallapp-md.md)]  
  
## <a name="example"></a>Örnek  
 [!code-vb[Trin_OL_CurrentItem#1](../vsto/codesnippet/VisualBasic/Trin_OL_CurrentItem/thisaddin.vb#1)]
 [!code-csharp[Trin_OL_CurrentItem#1](../vsto/codesnippet/CSharp/Trin_OL_CurrentItem/thisaddin.cs#1)]  
  
## <a name="compiling-the-code"></a>Kod Derleniyor  
 Bu örnek gerektirir:  
  
-   Randevu, kişi ve Microsoft Office Outlook e-posta öğeleri.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Outlook nesne modeline genel bakış](../vsto/outlook-object-model-overview.md)   
 [Nasıl yapılır: program aracılığıyla klasörü ada göre alma](../vsto/how-to-programmatically-retrieve-a-folder-by-name.md)   
 [Nasıl yapılır: program aracılığıyla belirli bir kişi arama](../vsto/how-to-programmatically-search-for-a-specific-contact.md)  
  
  