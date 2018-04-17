---
title: 'Nasıl yapılır: belirli klasör içinde program aracılığıyla arama | Microsoft Docs'
ms.custom: ''
ms.date: 02/02/2017
ms.technology:
- office-development
ms.topic: conceptual
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- Outlook folders [Office development in Visual Studio], searching
author: TerryGLee
ms.author: tglee
manager: douge
ms.workload:
- office
ms.openlocfilehash: aedddb0eab79e66d9d5a41d70a4907a2f22951ab
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/16/2018
---
# <a name="how-to-programmatically-search-within-a-specific-folder"></a>Nasıl yapılır: Belirli Klasör İçinde Program Aracılığıyla Arama Yapma
  Bu kod örneği kullanır `Find` ve `FindNext` e-posta iletilerinin bulunan konu alanında metin aramak için yöntemleri **gelen**. Bu yöntem başlangıç harfi T harfiyle denetlemek için bir dize filtre kullanır, `Subject` metin.  
  
 [!INCLUDE[appliesto_olkallapp](../vsto/includes/appliesto-olkallapp-md.md)]  
  
## <a name="example"></a>Örnek  
 [!code-csharp[Trin_OL_SearchFolder#1](../vsto/codesnippet/CSharp/Trin_OL_SearchFolder/thisaddin.cs#1)]  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Klasörlerle çalışma](../vsto/working-with-folders.md)   
 [Outlook nesne modeline genel bakış](../vsto/outlook-object-model-overview.md)   
 [Nasıl yapılır: Program Aracılığıyla Klasörü Ada Göre Alma](../vsto/how-to-programmatically-retrieve-a-folder-by-name.md)  
  
  