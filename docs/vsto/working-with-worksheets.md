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
ms.workload: office
ms.openlocfilehash: 979f3aa0d138d1e66248ffc51b4f4cc72d62adf4
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/22/2017
---
# <a name="working-with-worksheets"></a>Çalışma Sayfaları ile Çalışma
  <xref:Microsoft.Office.Tools.Excel.Worksheet> Ve <xref:Microsoft.Office.Interop.Excel.Worksheet> sınıfları, yöntemleri ve sayfalarıyla ilgili görevleri gerçekleştirmek için kullandığınız özellikler içerir.  
  
|Görev|Yordam|  
|----------|---------------|  
|Yeni bir çalışma kitabına ekleyin.|[Nasıl yapılır: Çalışma Kitaplarına Program Aracılığıyla Yeni Çalışma Sayfaları Ekleme](../vsto/how-to-programmatically-add-new-worksheets-to-workbooks.md)|  
|Çalışma kitabındaki belirtilen bir konumda kopyası.|[Nasıl yapılır: Çalışma Sayfalarını Program Aracılığıyla Kopyalama](../vsto/how-to-programmatically-copy-worksheets.md)|  
|Belirtilen çalışma silin.|[Nasıl yapılır: Program Aracılığıyla Çalışma Kitaplarından Çalışma Sayfaları Silme](../vsto/how-to-programmatically-delete-worksheets-from-workbooks.md)|  
|Kullanıcının seçimini belirtilen çalışma sayfasına taşıyın.|[Nasıl yapılır: Program Aracılığıyla Çalışma Sayfaları Seçme](../vsto/how-to-programmatically-select-worksheets.md)|  
|Tüm çalışma sayfalarını toplulukta tekrarlama.|[Nasıl yapılır: Çalışma Kitabındaki Tüm Çalışma Sayfalarını Program Aracılığıyla Listeleme](../vsto/how-to-programmatically-list-all-worksheets-in-a-workbook.md)|  
|Önizleme ve bir çalışma sayfası yazdırın.|[Nasıl yapılır: Çalışma Sayfalarını Program Aracılığıyla Yazdırma](../vsto/how-to-programmatically-print-worksheets.md)|  
|Çalışma kitabında yeni bir konuma taşıyın.|[Nasıl yapılır: Çalışma Kitaplarındaki Çalışma Sayfalarını Program Aracılığıyla Taşıma](../vsto/how-to-programmatically-move-worksheets-within-workbooks.md)|  
|Bir veya daha fazla çalışma sayfası görünürlüğünü değiştirin.|[Nasıl yapılır: Çalışma Sayfalarını Program Aracılığıyla Gizleme](../vsto/how-to-programmatically-hide-worksheets.md)|  
|Bir çalışma sayfasına bir bölümünü veya tümünü düzenlenemez şekilde kilitleyin.|[Nasıl yapılır: Çalışma Sayfalarını Program Aracılığıyla Koruma](../vsto/how-to-programmatically-protect-worksheets.md)|  
|Kilit düzenlenebilir bir çalışma sayfasından kaldırın.|[Nasıl yapılır: Çalışma Sayfalarından Program Aracılığıyla Korumayı Kaldırma](../vsto/how-to-programmatically-remove-protection-from-worksheets.md)|  
|Ekleme ve açıklamaları silin.|[Nasıl yapılır: Program Aracılığıyla Çalışma Sayfası Açıklamaları Ekleme ve Silme](../vsto/how-to-programmatically-add-and-delete-worksheet-comments.md)|  
|Göster veya gizle tüm açıklamaları.|[Nasıl yapılır: Program Aracılığıyla Çalışma Sayfası Açıklamalarını Görüntüleme](../vsto/how-to-programmatically-display-worksheet-comments.md)|  
|Çalışma sayfalarında grupları oluşturun.|[Nasıl yapılır: Çalışma Sayfasında Satırları Program Aracılığıyla Gruplama](../vsto/how-to-programmatically-group-rows-in-a-worksheet.md)|  
|Bir satır yalnızca, seçilen hücre içerdiğinde kalın yapın.|[Nasıl yapılır: Program Aracılığıyla Seçili Hücreler İçeren Çalışma Sayfalarındaki Satırlarda Biçimlendirmeyi Değiştirme](../vsto/how-to-programmatically-change-formatting-in-worksheet-rows-containing-selected-cells.md)|  
|Veri ve çalışma sayfaları arasında biçimlendirme kopyalayın.|[Nasıl yapılır: Çalışma Sayfaları Arasında Program Aracılığıyla Veri ve Biçimlendirme Kopyalama](../vsto/how-to-programmatically-copy-data-and-formatting-across-worksheets.md)|  
|Çalışma sayfalarında yazım denetimi yapın.|[Nasıl yapılır: Çalışma Sayfalarında Program Aracılığıyla Yazımı Denetleme](../vsto/how-to-programmatically-check-spelling-in-worksheets.md)|  
|Adlandırılmış aralıkları ve nesneleri listeleme verileri sıralar.|[Nasıl Yapılır: Çalışma Sayfalarında Verileri Programlamayla Sıralama](../vsto/how-to-programmatically-sort-data-in-worksheets.md)|  
  
 Excel görevleri ve Excel nesne modeli hakkında daha fazla bilgi için bkz: [Excel nesne modeline genel bakış](../vsto/excel-object-model-overview.md).  
  
 Bazı durumlarda, VSTO eklentileri bu görevleri gerçekleştirmek yolları belge düzeyi özelleştirmelerindeki bunları gerçekleştirmek yolları farklıdır.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Genişletilmiş nesneleri kullanarak Excel'i otomatikleştirme](../vsto/automating-excel-by-using-extended-objects.md)   
 [Çalışma kitaplarıyla çalışma](../vsto/working-with-workbooks.md)   
 [Aralıklarla çalışma](../vsto/working-with-ranges.md)   
 [Excel Çalışma Sayfalarında Windows Forms Denetimlerini Kullanma](../vsto/using-windows-forms-controls-on-excel-worksheets.md)  
  
  