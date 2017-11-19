---
title: "Nasıl yapılır: program aracılığıyla metin dosyaları çalışma kitapları olarak açma | Microsoft Docs"
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
- workbooks, opening text files as
- text [Office development in Visual Studio], text files
- text files, opening as workbooks
ms.assetid: 056ae3d0-7fe7-4c28-a2a5-5a948baee0e6
caps.latest.revision: "47"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: b4148a9a8a8de627ed56f5e1abc6da3469399330
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2017
---
# <a name="how-to-programmatically-open-text-files-as-workbooks"></a>Nasıl yapılır: Metin Dosyalarını Program Aracılığıyla Çalışma Kitapları Biçiminde Açma
  Bir metin dosyası bir çalışma kitabı açabilirsiniz. Açmak istediğiniz metin dosyası adına geçmesi gerekir. Başlangıç Ayrıştırılmaya ve veri dosyasındaki sütun biçiminin satır numarası gibi çeşitli isteğe bağlı parametreleri belirtebilirsiniz.  
  
 [!INCLUDE[appliesto_xlalldocapp](../vsto/includes/appliesto-xlalldocapp-md.md)]  
  
## <a name="example"></a>Örnek  
 [!code-csharp[Trin_VstcoreExcelAutomation#80](../vsto/codesnippet/CSharp/Trin_VstcoreExcelAutomationCS/Sheet1.cs#80)]
 [!code-vb[Trin_VstcoreExcelAutomation#80](../vsto/codesnippet/VisualBasic/Trin_VstcoreExcelAutomation/Sheet1.vb#80)]  
  
## <a name="compiling-the-code"></a>Kod Derleniyor  
 Bu örnekte aşağıdaki bileşenler gereklidir:  
  
-   Adlı bir virgülle ayrılmış metin dosyası `Test.txt` en az üç satırlık metin içerir.  
  
-   Metin dosyasını `Test.txt` c sürücüsünde bulunan depolanması  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Çalışma kitaplarıyla çalışma](../vsto/working-with-workbooks.md)   
 [Nasıl yapılır: program aracılığıyla çalışma kitaplarını açma](../vsto/how-to-programmatically-open-workbooks.md)   
 [Nasıl yapılır: program aracılığıyla yeni çalışma kitapları oluşturma](../vsto/how-to-programmatically-create-new-workbooks.md)   
 [Nasıl yapılır: çalışma kitaplarını program aracılığıyla kaydetme](../vsto/how-to-programmatically-save-workbooks.md)   
 [Nasıl yapılır: program aracılığıyla çalışma kitaplarını kapatma](../vsto/how-to-programmatically-close-workbooks.md)   
 [Office çözümlerinde isteğe bağlı parametreler](../vsto/optional-parameters-in-office-solutions.md)  
  
  