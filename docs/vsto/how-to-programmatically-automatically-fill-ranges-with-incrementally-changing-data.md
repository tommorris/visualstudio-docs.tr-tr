---
title: "Nasıl yapılır: program aracılığıyla otomatik olarak doldurma artımlı şekilde değişen verilerle birlikte aralıkları | Microsoft Docs"
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
- Autofill method [Excel]
- filling ranges automatically
- ranges, automatically filling
- workbooks, filling ranges
author: TerryGLee
ms.author: tglee
manager: ghogen
ms.workload: office
ms.openlocfilehash: d6634fea629358368d3b61c5b505e5eec7ec0186
ms.sourcegitcommit: f9fbf1f55f9ac14e4e5c6ae58c30dc1800ca6cda
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/10/2018
---
# <a name="how-to-programmatically-automatically-fill-ranges-with-incrementally-changing-data"></a>Nasıl yapılır: Aralıkları Artımlı Şekilde Değişen Verilerle Program Aracılığıyla Otomatik Biçimde Doldurma
  <xref:Microsoft.Office.Interop.Excel.Range.AutoFill%2A> Yöntemi <xref:Microsoft.Office.Interop.Excel.Range> nesne çalışma sayfasındaki bir aralığı değerlerle otomatik olarak doldurmanıza olanak sağlar. Çoğu zaman <xref:Microsoft.Office.Interop.Excel.Range.AutoFill%2A> yöntemi rutin olarak artan veya azalan bir aralık değerleri depolamak için kullanılır. Sabit listesinden isteğe bağlı bir sabit sağlayarak için davranış belirtebilirsiniz <xref:Microsoft.Office.Interop.Excel.XlAutoFillType> numaralandırması.  
  
 [!INCLUDE[appliesto_xlalldocapp](../vsto/includes/appliesto-xlalldocapp-md.md)]  
  
 İki aralıkları kullanırken belirtmelisiniz <xref:Microsoft.Office.Interop.Excel.Range.AutoFill%2A>:  
  
-   Çağıran aralık <xref:Microsoft.Office.Interop.Excel.Range.AutoFill%2A> dolgunun başlangıç noktasını belirler ve bir başlangıç değeri içeren yöntemi.  
  
-   Bir parametre olarak geçirilen doldurmak istediğiniz aralık <xref:Microsoft.Office.Interop.Excel.Range.AutoFill%2A> yöntemi. Bu hedef aralığın başlangıç değerini içeren aralığı eklemeniz gerekir.  
  
    > [!NOTE]  
    >  Geçiremezsiniz bir <xref:Microsoft.Office.Tools.Excel.NamedRange> yerine kontrol <xref:Microsoft.Office.Interop.Excel.Range>. Daha fazla bilgi için bkz: [programsal sınırlamalar, ana bilgisayar öğeleri ve ana bilgisayar denetimleri](../vsto/programmatic-limitations-of-host-items-and-host-controls.md).  
  
## <a name="example"></a>Örnek  
 [!code-csharp[Trin_VstcoreExcelAutomation#49](../vsto/codesnippet/CSharp/Trin_VstcoreExcelAutomationCS/Sheet1.cs#49)]
 [!code-vb[Trin_VstcoreExcelAutomation#49](../vsto/codesnippet/VisualBasic/Trin_VstcoreExcelAutomation/Sheet1.vb#49)]  
  
## <a name="compiling-the-code"></a>Kod Derleniyor  
 İlk hücrenin doldurmak istediğiniz aralığın başlangıç değeri içermelidir.  
  
 Örnek, üç bölgeyi doldurmanızı gerektirir:  
  
-   B sütunundaki beş hafta eklemektir. İlk değer için türü **Pazartesi** B1 hücresindeki.  
  
-   Sütun C beş ay eklemektir. İlk değer için türü **Ocak** C1 hücresindeki.  
  
-   Sütun D numaraları, iki her satır için olarak artan bir dizi eklemektir. İlk değerlerini yazın **4** D1 hücresinde ve **6** D2 hücresine.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Aralıklarla çalışma](../vsto/working-with-ranges.md)   
 [Nasıl yapılır: program aracılığıyla çalışma sayfası aralıklarına başvuran](../vsto/how-to-programmatically-refer-to-worksheet-ranges-in-code.md)   
 [Nasıl yapılır: program aracılığıyla çalışma kitaplarındaki aralıklara stilleri uygulayın](../vsto/how-to-programmatically-apply-styles-to-ranges-in-workbooks.md)   
 [Nasıl yapılır: Excel hesaplarını program aracılığıyla çalıştırma](../vsto/how-to-programmatically-run-excel-calculations-programmatically.md)   
 [Konak öğelerine ve denetimlerine genel bakış](../vsto/host-items-and-host-controls-overview.md)   
 [Office Çözümlerinde İsteğe Bağlı Parametreler](../vsto/optional-parameters-in-office-solutions.md)  
  
  