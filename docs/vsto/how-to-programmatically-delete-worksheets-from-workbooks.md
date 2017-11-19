---
title: "Nasıl yapılır: program aracılığıyla çalışma kitaplarından çalışma sayfaları silme | Microsoft Docs"
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
- workbooks, deleting worksheets
- worksheets, deleting
ms.assetid: c5ae99f0-806d-4320-a29c-75ad444fb996
caps.latest.revision: "48"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: efa5c68555fbd9e309335d8c985c4f14f1b07b18
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2017
---
# <a name="how-to-programmatically-delete-worksheets-from-workbooks"></a>Nasıl yapılır: Program Aracılığıyla Çalışma Kitaplarından Çalışma Sayfaları Silme
  Çalışma kitabındaki tüm çalışma silebilirsiniz. Çalışma sayfası silmek için çalışma sayfası konak öğesi kullanın veya çalışma kitabının sayfaları koleksiyonunu kullanarak çalışma sayfasına erişin.  
  
 [!INCLUDE[appliesto_xlalldocapp](../vsto/includes/appliesto-xlalldocapp-md.md)]  
  
## <a name="using-the-worksheet-host-item"></a>Çalışma sayfası konak öğesi kullanma  
 Belge düzeyi özelleştirmelerinde tasarım zamanında çalışma eklendiyse kullanın <xref:Microsoft.Office.Tools.Excel.Worksheet.Delete%2A> belirtilen çalışma sayfası silmek için yöntem. Aşağıdaki kod çalışma sayfası konak öğesi doğrudan başvurarak çalışma kitabından siler.  
  
> [!IMPORTANT]  
>  Bu kod, aşağıdaki proje şablonlarını kullanarak oluşturduğunuz projelerine çalıştırır:  
>   
>  -   Excel 2013 çalışma kitabı  
> -   Excel 2013 şablonu  
> -   Excel 2010 Çalışma Kitabı  
> -   Excel 2010 Şablonu  
>   
>  Diğer bir proje türünde bu görevi gerçekleştirmek istiyorsanız, bir başvuru eklemeniz gerekir **Microsoft.Office.Interop.Excel** derleme ve ardından bu derleme sınıflardan bir çalışma kitabını açıp çalışma sayfası silmek için kullanmalısınız. Daha fazla bilgi için bkz: [nasıl yapılır: hedef Office uygulamaları aracılığıyla birincil birlikte çalışma derlemeleri](../vsto/how-to-target-office-applications-through-primary-interop-assemblies.md) ve [Excel 2010 birincil birlikte çalışma derleme başvurusu](http://go.microsoft.com/fwlink/?LinkId=189585).  
  
#### <a name="to-delete-a-worksheet-by-using-a-worksheet-host-item"></a>Bir çalışma sayfası bir çalışma sayfası konak öğesi kullanarak silme  
  
1.  Çağrı <xref:Microsoft.Office.Tools.Excel.Worksheet.Delete%2A> yöntemi `Sheet1`.  
  
     [!code-csharp[Trin_VstcoreExcelAutomation#17](../vsto/codesnippet/CSharp/Trin_VstcoreExcelAutomationCS/Sheet1.cs#17)]
     [!code-vb[Trin_VstcoreExcelAutomation#17](../vsto/codesnippet/VisualBasic/Trin_VstcoreExcelAutomation/Sheet1.vb#17)]  
  
## <a name="using-the-sheets-collection-of-the-excel-workbook"></a>Excel çalışma kitabı sayfaları koleksiyonunu kullanarak  
 Microsoft Office Excel çalışma sayfalarına erişin <xref:Microsoft.Office.Interop.Excel.Sheets> aşağıdaki durumlarda koleksiyonu:  
  
-   Bir çalışma sayfasına bir VSTO eklentisini silmek istiyor.  
  
-   Belge düzeyi özelleştirmelerinde çalışma zamanında silmek istediğiniz çalışma sayfası oluşturuldu.  
  
 Aşağıdaki kod çalışma kitabından dizin numarasını üzerinden sayfasını başvurarak siler **sayfaları** koleksiyonu. Bu kod, yeni bir çalışma sayfasına programlı olarak oluşturulduğunu varsayar.  
  
> [!IMPORTANT]  
>  Diğer bir proje türünde bu görevi gerçekleştirmek istiyorsanız, bir başvuru eklemeniz gerekir **Microsoft.Office.Interop.Excel** derleme ve ardından bu derleme sınıflardan bir çalışma kitabını açıp çalışma sayfası silmek için kullanmalısınız. Daha fazla bilgi için bkz: [nasıl yapılır: hedef Office uygulamaları aracılığıyla birincil birlikte çalışma derlemeleri](../vsto/how-to-target-office-applications-through-primary-interop-assemblies.md) ve [Excel 2010 birincil birlikte çalışma derleme başvurusu](http://go.microsoft.com/fwlink/?LinkId=189585).  
  
#### <a name="to-delete-a-worksheet-by-using-the-sheets-collection-of-the-excel-workbook"></a>Excel çalışma kitabı sayfaları koleksiyonunu kullanarak çalışma silmek için  
  
1.  Çağrı <xref:Microsoft.Office.Interop.Excel._Worksheet.Delete%2A> yöntemi <xref:Microsoft.Office.Interop.Excel.Sheets> koleksiyonu.  
  
     [!code-csharp[Trin_VstcoreExcelAutomation#18](../vsto/codesnippet/CSharp/Trin_VstcoreExcelAutomationCS/Sheet1.cs#18)]
     [!code-vb[Trin_VstcoreExcelAutomation#18](../vsto/codesnippet/VisualBasic/Trin_VstcoreExcelAutomation/Sheet1.vb#18)]  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Çalışma sayfaları ile çalışma](../vsto/working-with-worksheets.md)   
 [Nasıl yapılır: çalışma sayfalarını program aracılığıyla gizleme](../vsto/how-to-programmatically-hide-worksheets.md)   
 [Nasıl yapılır: program aracılığıyla çalışma kitaplarındaki çalışma sayfalarını taşıma](../vsto/how-to-programmatically-move-worksheets-within-workbooks.md)   
 [Nasıl yapılır: program aracılığıyla çalışma sayfalarını seçin](../vsto/how-to-programmatically-select-worksheets.md)   
 [Nasıl yapılır: program aracılığıyla yeni çalışma sayfaları çalışma kitaplarına ekleme](../vsto/how-to-programmatically-add-new-worksheets-to-workbooks.md)   
 [Çalışma sayfası konak öğesi](../vsto/worksheet-host-item.md)   
 [Office projelerindeki nesnelere genel erişim](../vsto/global-access-to-objects-in-office-projects.md)   
 [Konak denetimlerinin ve konak öğelerinin programlama sınırlamaları](../vsto/programmatic-limitations-of-host-items-and-host-controls.md)  
  
  