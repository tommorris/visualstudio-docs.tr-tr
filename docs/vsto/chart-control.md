---
title: Grafik denetimi | Microsoft Docs
ms.custom: 
ms.date: 02/02/2017
ms.reviewer: 
ms.suite: 
ms.technology: office-development
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: VST.ProjectItem.ExcelChart
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- Chart control [Office development in Visual Studio], events
- Chart control [Office development in Visual Studio]
- Chart control [Office development in Visual Studio], data binding
ms.assetid: 64f1a7cc-cc66-47da-aaeb-44a62ae53909
caps.latest.revision: "51"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload: office
ms.openlocfilehash: fc5dfd4916383af8b69c14a87805e965ea855d23
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/22/2017
---
# <a name="chart-control"></a>Grafik Denetimi
  <xref:Microsoft.Office.Tools.Excel.Chart> Denetim olayları gösteren bir grafik nesnesi değil. Bir çalışma sayfasına bir grafik eklediğinizde, Visual Studio oluşturur bir <xref:Microsoft.Office.Tools.Excel.Chart> dayalı Microsoft Office Excel nesne modeline çapraz geçiş yapmak zorunda kalmadan doğrudan programlama yapabilirsiniz, nesne.  
  
 [!INCLUDE[appliesto_xlalldocapp](../vsto/includes/appliesto-xlalldocapp-md.md)]  
  
## <a name="creating-the-control"></a>Denetimi oluşturma  
 Ekleyebileceğiniz <xref:Microsoft.Office.Tools.Excel.Chart> Microsoft Office Excel çalışma zamanında veya belge düzeyi projesindeki çalışma zamanında denetimler.  
  
 Ekleyebileceğiniz <xref:Microsoft.Office.Tools.Excel.Chart> denetimlerini çalışma zamanında VSTO eklenti. Daha fazla bilgi için bkz: [nasıl yapılır: çalışma sayfalarına Grafik denetimleri ekleme](../vsto/how-to-add-chart-controls-to-worksheets.md).  
  
> [!NOTE]  
>  Dinamik olarak oluşturulmuş grafik nesneleri çalışma sayfasında sürdürülmez çalışma kapatıldığında konak kontrolü olarak. Daha fazla bilgi için bkz: [Office belgelerine çalışma zamanında denetimler ekleme](../vsto/adding-controls-to-office-documents-at-run-time.md).  
  
## <a name="formatting"></a>Biçimlendirme  
 Tüm biçimlendirme, uygulanabilir bir <xref:Microsoft.Office.Interop.Excel.Chart> de uygulanabilir bir <xref:Microsoft.Office.Tools.Excel.Chart> denetim. Bu, kenarlıklar, yazı tipi, grafik türü, kılavuz çizgilerini, gösterge ve veri etiketlerini içerir.  
  
## <a name="events"></a>Olaylar  
 Aşağıdaki olaylar kullanılabilir <xref:Microsoft.Office.Tools.Excel.Chart> denetimi:  
  
-   <xref:Microsoft.Office.Tools.Excel.Chart.ActivateEvent>  
  
-   <xref:Microsoft.Office.Tools.Excel.Chart.BeforeDoubleClick>  
  
-   <xref:Microsoft.Office.Tools.Excel.Chart.BeforeRightClick>  
  
-   <xref:Microsoft.Office.Tools.Excel.Chart.BindingContextChanged>  
  
-   <xref:Microsoft.Office.Tools.Excel.Chart.Calculate>  
  
-   <xref:Microsoft.Office.Tools.Excel.Chart.Deactivate>  
  
-   <xref:System.ComponentModel.Component.Disposed>  
  
-   <xref:Microsoft.Office.Tools.Excel.Chart.DragOver>  
  
-   <xref:Microsoft.Office.Tools.Excel.Chart.DragPlot>  
  
-   <xref:Microsoft.Office.Tools.Excel.Chart.MouseDown>  
  
-   <xref:Microsoft.Office.Tools.Excel.Chart.MouseMove>  
  
-   <xref:Microsoft.Office.Tools.Excel.Chart.MouseUp>  
  
-   <xref:Microsoft.Office.Tools.Excel.Chart.Resize>  
  
-   <xref:Microsoft.Office.Tools.Excel.Chart.SelectEvent>  
  
-   <xref:Microsoft.Office.Tools.Excel.Chart.SeriesChange>  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Office geliştirme örnekleri ve izlenecek yollar](../vsto/office-development-samples-and-walkthroughs.md)   
 [Genişletme Word belgelerini ve Excel çalışma kitaplarını çalışma zamanında VSTO eklentileri](../vsto/extending-word-documents-and-excel-workbooks-in-vsto-add-ins-at-run-time.md)   
 [Office belgelerindeki denetimler](../vsto/controls-on-office-documents.md)   
 [Office belgelerine çalışma zamanında denetimler ekleme](../vsto/adding-controls-to-office-documents-at-run-time.md)   
 [Genişletilmiş nesneleri kullanarak Excel'i otomatikleştirme](../vsto/automating-excel-by-using-extended-objects.md)   
 [Nasıl yapılır: çalışma sayfalarına Grafik denetimleri ekleme](../vsto/how-to-add-chart-controls-to-worksheets.md)   
 [Office çözümlerinde denetimlere veri bağlama](../vsto/binding-data-to-controls-in-office-solutions.md)   
 [Konak Denetimlerinin ve Konak Öğelerinin Programlama Sınırlamaları](../vsto/programmatic-limitations-of-host-items-and-host-controls.md)  
  
  