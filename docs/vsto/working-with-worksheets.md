---
title: "Çalışma sayfaları ile çalışma | Microsoft Docs"
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
- Excel [Office development in Visual Studio], worksheets
- worksheets [Office development in Visual Studio], common tasks
ms.assetid: d9204916-6471-4cf0-89a1-d46dae0e2599
caps.latest.revision: "13"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: bc188299dbc5fe6f8f048b4971fa4973ba2f72f2
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2017
---
# <a name="working-with-worksheets"></a>Çalışma Sayfaları ile Çalışma
  <xref:Microsoft.Office.Tools.Excel.Worksheet> Ve <xref:Microsoft.Office.Interop.Excel.Worksheet> sınıfları, yöntemleri ve sayfalarıyla ilgili görevleri gerçekleştirmek için kullandığınız özellikler içerir.  
  
|Görev|Yordam|  
|----------|---------------|  
|Yeni bir çalışma kitabına ekleyin.|[Nasıl yapılır: program aracılığıyla yeni çalışma sayfaları çalışma kitaplarına ekleme](../vsto/how-to-programmatically-add-new-worksheets-to-workbooks.md)|  
|Çalışma kitabındaki belirtilen bir konumda kopyası.|[Nasıl yapılır: çalışma sayfalarını program aracılığıyla kopyalama](../vsto/how-to-programmatically-copy-worksheets.md)|  
|Belirtilen çalışma silin.|[Nasıl yapılır: program aracılığıyla çalışma kitaplarından çalışma sayfaları silme](../vsto/how-to-programmatically-delete-worksheets-from-workbooks.md)|  
|Kullanıcının seçimini belirtilen çalışma sayfasına taşıyın.|[Nasıl yapılır: program aracılığıyla çalışma sayfalarını seçin](../vsto/how-to-programmatically-select-worksheets.md)|  
|Tüm çalışma sayfalarını toplulukta tekrarlama.|[Nasıl yapılır: program aracılığıyla çalışma kitabındaki tüm çalışma sayfalarını listesi](../vsto/how-to-programmatically-list-all-worksheets-in-a-workbook.md)|  
|Önizleme ve bir çalışma sayfası yazdırın.|[Nasıl yapılır: çalışma sayfalarını program aracılığıyla yazdırma](../vsto/how-to-programmatically-print-worksheets.md)|  
|Çalışma kitabında yeni bir konuma taşıyın.|[Nasıl yapılır: program aracılığıyla çalışma kitaplarındaki çalışma sayfalarını taşıma](../vsto/how-to-programmatically-move-worksheets-within-workbooks.md)|  
|Bir veya daha fazla çalışma sayfası görünürlüğünü değiştirin.|[Nasıl yapılır: çalışma sayfalarını program aracılığıyla gizleme](../vsto/how-to-programmatically-hide-worksheets.md)|  
|Bir çalışma sayfasına bir bölümünü veya tümünü düzenlenemez şekilde kilitleyin.|[Nasıl yapılır: çalışma sayfalarını program aracılığıyla koruma](../vsto/how-to-programmatically-protect-worksheets.md)|  
|Kilit düzenlenebilir bir çalışma sayfasından kaldırın.|[Nasıl yapılır: çalışma sayfalarından program aracılığıyla korumayı kaldırma](../vsto/how-to-programmatically-remove-protection-from-worksheets.md)|  
|Ekleme ve açıklamaları silin.|[Nasıl yapılır: program aracılığıyla ekleme ve silme çalışma sayfası açıklamaları](../vsto/how-to-programmatically-add-and-delete-worksheet-comments.md)|  
|Göster veya gizle tüm açıklamaları.|[Nasıl yapılır: program aracılığıyla çalışma sayfası açıklamalarını görüntüleme](../vsto/how-to-programmatically-display-worksheet-comments.md)|  
|Çalışma sayfalarında grupları oluşturun.|[Nasıl yapılır: çalışma sayfasında satırları program aracılığıyla gruplama](../vsto/how-to-programmatically-group-rows-in-a-worksheet.md)|  
|Bir satır yalnızca, seçilen hücre içerdiğinde kalın yapın.|[Nasıl yapılır: program aracılığıyla seçili hücreler içeren çalışma sayfalarındaki satırlarda biçimlendirmeyi değiştirme](../vsto/how-to-programmatically-change-formatting-in-worksheet-rows-containing-selected-cells.md)|  
|Veri ve çalışma sayfaları arasında biçimlendirme kopyalayın.|[Nasıl yapılır: program aracılığıyla veri ve biçimlendirme çalışma sayfaları arasında kopyalama](../vsto/how-to-programmatically-copy-data-and-formatting-across-worksheets.md)|  
|Çalışma sayfalarında yazım denetimi yapın.|[Nasıl yapılır: program aracılığıyla çalışma sayfalarında yazım denetimi](../vsto/how-to-programmatically-check-spelling-in-worksheets.md)|  
|Adlandırılmış aralıkları ve nesneleri listeleme verileri sıralar.|[Nasıl yapılır: çalışma sayfalarında verileri programlamayla sıralama](../vsto/how-to-programmatically-sort-data-in-worksheets.md)|  
  
 Excel görevleri ve Excel nesne modeli hakkında daha fazla bilgi için bkz: [Excel nesne modeline genel bakış](../vsto/excel-object-model-overview.md).  
  
 Bazı durumlarda, VSTO eklentileri bu görevleri gerçekleştirmek yolları belge düzeyi özelleştirmelerindeki bunları gerçekleştirmek yolları farklıdır.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Genişletilmiş nesneleri kullanarak Excel'i otomatikleştirme](../vsto/automating-excel-by-using-extended-objects.md)   
 [Çalışma kitaplarıyla çalışma](../vsto/working-with-workbooks.md)   
 [Aralıklarla çalışma](../vsto/working-with-ranges.md)   
 [Windows Forms denetimlerini Excel çalışma sayfalarında kullanma](../vsto/using-windows-forms-controls-on-excel-worksheets.md)  
  
  