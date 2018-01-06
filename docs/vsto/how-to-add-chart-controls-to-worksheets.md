---
title: "Nasıl yapılır: çalışma sayfalarına Grafik denetimleri ekleme | Microsoft Docs"
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
- Chart control [Office development in Visual Studio], adding to worksheets
- controls [Office development in Visual Studio], adding to worksheets
ms.assetid: f02568e7-5caa-45b4-aa2a-4f73b0565d4e
caps.latest.revision: "44"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload: office
ms.openlocfilehash: 53b30bb62e4c4f4146b1c43b6fe08f9683ba4867
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-add-chart-controls-to-worksheets"></a>Nasıl Yapılır: Çalışma Sayfalarına Grafik Denetimleri Ekleme
  Ekleyebileceğiniz <xref:Microsoft.Office.Tools.Excel.Chart> Microsoft Office Excel çalışma zamanında ve belge düzeyi özelleştirmelerinde çalışma zamanında denetimler. Ayrıca ekleyebileceğiniz <xref:Microsoft.Office.Tools.Excel.Chart> VSTO eklentileri çalışma zamanında denetimler.  
  
 [!INCLUDE[appliesto_xlalldocapp](../vsto/includes/appliesto-xlalldocapp-md.md)]  
  
 Bu konuda aşağıdaki görevler açıklanmaktadır:  
  
-   [Tasarım zamanında grafik denetimleri ekleme](#designtime)  
  
-   [Belge düzeyi projesindeki çalışma zamanında grafik denetimleri ekleme](#runtimedoclevel)  
  
-   [Çalışma zamanında VSTO eklenti projesindeki grafik denetimleri ekleme](#runtimeaddin)  
  
 Hakkında daha fazla bilgi için <xref:Microsoft.Office.Tools.Excel.Chart> denetimleri bkz [grafik denetiminin](../vsto/chart-control.md).  
  
##  <a name="designtime"></a>Tasarım zamanında grafik denetimleri ekleme  
 Ekleyebileceğiniz <xref:Microsoft.Office.Tools.Excel.Chart> eklemek uygulamadan bir grafik aynı şekilde, bir çalışma sayfasına denetim.  
  
> [!NOTE]  
>  <xref:Microsoft.Office.Tools.Excel.Chart> Denetim kullanılabilir değil **araç** veya **veri kaynakları** penceresi.  
  
#### <a name="to-add-a-chart-host-control-to-a-worksheet-in-excel"></a>Excel çalışma sayfasındaki grafik konak kontrolü eklemek için  
  
1.  Üzerinde **Ekle** sekmesinde **grafikleri** grubunda **sütun**, bir grafik kategorisine tıklayın ve ardından istediğiniz grafik türüne tıklayın.  
  
2.  İçinde **Grafik Ekle** iletişim kutusu, tıklatın **Tamam**.  
  
3.  Üzerinde **tasarım** sekmesinde **veri** grubunda **veri Seç**.  
  
4.  İçinde **veri kaynağı Seç** iletişim kutusu, tıklatın **grafik** **veri aralığı** kutusuna ve herhangi bir varsayılan seçimi temizleyin.  
  
5.  İçinde **grafiği için veri** sayfası, grafik için verileri içeren hücre aralığı seçin (hücreleri **A5** aracılığıyla **D8**).  
  
6.  İçinde **veri kaynağı Seç** iletişim kutusu, tıklatın **Tamam**.  
  
##  <a name="runtimedoclevel"></a>Belge düzeyi projesindeki çalışma zamanında grafik denetimleri ekleme  
 Ekleyebileceğiniz <xref:Microsoft.Office.Tools.Excel.Chart> çalışma zamanında dinamik olarak denetim. Dinamik olarak oluşturulmuş grafikler belgede sürdürülmez belge kapatıldığında konak kontrolü olarak. Daha fazla bilgi için bkz: [Office belgelerine çalışma zamanında denetimler ekleme](../vsto/adding-controls-to-office-documents-at-run-time.md).  
  
#### <a name="to-add-a-chart-control-to-a-worksheet-programmatically"></a>Grafik denetimi bir çalışma sayfasına programlı olarak eklemek için  
  
1.  İçinde <xref:Microsoft.Office.Tools.Excel.Worksheet.Startup> olay işleyicisi `Sheet1`, eklemek için aşağıdaki kodu ekleyin <xref:Microsoft.Office.Tools.Excel.Chart> denetim.  
  
     [!code-csharp[Trin_VstcoreHostControlsExcel#1](../vsto/codesnippet/CSharp/Trin_VstcoreHostControlsExcelCS/Sheet1.cs#1)]
     [!code-vb[Trin_VstcoreHostControlsExcel#1](../vsto/codesnippet/VisualBasic/Trin_VstcoreHostControlsExcelVB/Sheet1.vb#1)]  
  
##  <a name="runtimeaddin"></a>Bir VSTO eklenti projesindeki çalışma zamanında grafik denetimleri ekleme  
 Ekleyebileceğiniz bir <xref:Microsoft.Office.Tools.Excel.Chart> VSTO eklenti projesindeki herhangi bir açık çalışma sayfasına program aracılığıyla denetimine. Daha fazla bilgi için bkz: [genişletme Word belgelerini ve Excel çalışma kitaplarını VSTO eklentileri çalışma zamanında](../vsto/extending-word-documents-and-excel-workbooks-in-vsto-add-ins-at-run-time.md).  
  
 Dinamik olarak oluşturulmuş grafik denetimleri çalışma sayfasında sürdürülmez çalışma kapatıldığında konak kontrolü olarak. Daha fazla bilgi için bkz: [Office belgelerine çalışma zamanında denetimler ekleme](../vsto/adding-controls-to-office-documents-at-run-time.md).  
  
#### <a name="to-add-a-chart-control-to-a-worksheet-programmatically"></a>Grafik denetimi bir çalışma sayfasına programlı olarak eklemek için  
  
1.  Aşağıdaki kod açık çalışma sayfası üzerinde temel alır ve ardından ekleyen bir çalışma sayfası konak öğesi oluşturur bir <xref:Microsoft.Office.Tools.Excel.Chart> denetim.  
  
     [!code-csharp[Trin_Excel_Dynamic_Controls#9](../vsto/codesnippet/CSharp/Trin_Excel_Dynamic_Controls/ThisAddIn.cs#9)]
     [!code-vb[Trin_Excel_Dynamic_Controls#9](../vsto/codesnippet/VisualBasic/Trin_Excel_Dynamic_Controls/ThisAddIn.vb#9)]  
  
## <a name="compiling-the-code"></a>Kod Derleniyor  
 Bu örnekte aşağıdaki gereksinimlere sahiptir:  
  
-   Grafiği, A5-aralığında D8 çalışma sayfasında depolanan veriler.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Genişletme Word belgelerini ve Excel çalışma kitaplarını çalışma zamanında VSTO eklentileri](../vsto/extending-word-documents-and-excel-workbooks-in-vsto-add-ins-at-run-time.md)   
 [Office belgelerindeki denetimler](../vsto/controls-on-office-documents.md)   
 [Grafik denetimi](../vsto/chart-control.md)   
 [Genişletilmiş nesneleri kullanarak Excel'i otomatikleştirme](../vsto/automating-excel-by-using-extended-objects.md)   
 [Konak öğelerine ve denetimlerine genel bakış](../vsto/host-items-and-host-controls-overview.md)   
 [Office çözümlerinde denetimlere veri bağlama](../vsto/binding-data-to-controls-in-office-solutions.md)   
 [Konak Denetimlerinin ve Konak Öğelerinin Programlama Sınırlamaları](../vsto/programmatic-limitations-of-host-items-and-host-controls.md)  
  
  