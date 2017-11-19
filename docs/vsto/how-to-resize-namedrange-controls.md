---
title: "Nasıl yapılır: NamedRange denetimlerinin boyutunu değiştirme | Microsoft Docs"
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
- controls [Office development in Visual Studio], resizing
- NamedRange control, resizing
- ranges, resizing in Excel
ms.assetid: 7d6f0b2f-be46-49b7-9f38-b4c8849683f7
caps.latest.revision: "48"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: 344abe2cd271504f476b0464bb8d7b3065716b1d
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2017
---
# <a name="how-to-resize-namedrange-controls"></a>Nasıl yapılır: NamedRange Denetimlerinin Boyutunu Değiştirme
  Boyutunu ayarlayabileceğiniz bir <xref:Microsoft.Office.Tools.Excel.NamedRange> denetlemek için Microsoft Office Excel belgesi eklediğinizde; ancak, daha sonraki bir zamanda yeniden boyutlandırmak isteyebilirsiniz.  
  
 [!INCLUDE[appliesto_xlalldocapp](../vsto/includes/appliesto-xlalldocapp-md.md)]  
  
 Adlandırılmış bir aralık tasarım zamanında veya belge düzeyi projelerine çalışma zamanında yeniden boyutlandırabilirsiniz. Adlandırılmış aralıkları çalışma zamanında uygulama düzeyi VSTO eklentileri yeniden boyutlandırabilirsiniz.  
  
 Bu konuda aşağıdaki görevler açıklanmaktadır:  
  
-   [Tasarım zamanında NamedRange denetimleri yeniden boyutlandırma](#designtime)  
  
-   [Belge düzeyi projesindeki çalışma zamanında NamedRange denetimleri yeniden boyutlandırma](#runtimedoclevel)  
  
-   [VSTO eklenti projesindeki çalışma zamanında NamedRange denetimleri yeniden boyutlandırma](#runtimeaddin)  
  
##  <a name="designtime"></a>Tasarım zamanında NamedRange denetimleri yeniden boyutlandırma  
 Adlandırılmış bir aralık boyutunda tanımlayarak boyutlandırabilirsiniz **ad tanımla** iletişim kutusu.  
  
#### <a name="to-resize-a-named-range-by-using-the-define-name-dialog-box"></a>Adlandırılmış bir aralık ad Tanımla iletişim kutusunu kullanarak yeniden boyutlandırmak için  
  
1.  Sağ bir <xref:Microsoft.Office.Tools.Excel.NamedRange> denetim.  
  
2.  Tıklatın **adlandırılmış aralıkları Yönet** kısayol menüsünde.  
  
     **Ad tanımla** iletişim kutusu görüntülenir.  
  
3.  Yeniden boyutlandırma adlandırılmış aralığı seçin.  
  
4.  Clear **başvurduğu** kutusu.  
  
5.  Adlandırılmış aralığın boyutunu tanımlamak için kullanmak istediğiniz hücreleri seçin.  
  
6.  **Tamam**'ı tıklatın.  
  
##  <a name="runtimedoclevel"></a>Belge düzeyi projesindeki çalışma zamanında NamedRange denetimleri yeniden boyutlandırma  
 Kullanarak, program aracılığıyla bir adlandırılmış bir aralık boyutlandırabilirsiniz <xref:Microsoft.Office.Tools.Excel.NamedRange.RefersTo%2A> özelliği.  
  
> [!NOTE]  
>  İçinde **özellikleri** penceresinde <xref:Microsoft.Office.Tools.Excel.NamedRange.RefersTo%2A> özelliği salt okunur olarak işaretlenmiş.  
  
#### <a name="to-resize-a-named-range-programmatically"></a>Adlandırılmış bir aralık programlı olarak yeniden boyutlandırmak için  
  
1.  Oluşturma bir <xref:Microsoft.Office.Tools.Excel.NamedRange> hücre denetiminde **A1** , `Sheet1`.  
  
     [!code-csharp[Trin_VstcoreHostControlsExcel#4](../vsto/codesnippet/CSharp/Trin_VstcoreHostControlsExcelCS/Sheet1.cs#4)]
     [!code-vb[Trin_VstcoreHostControlsExcel#4](../vsto/codesnippet/VisualBasic/Trin_VstcoreHostControlsExcelVB/Sheet1.vb#4)]  
  
2.  Adlandırılmış aralığın hücresini dahil etmek için yeniden boyutlandır **B1**.  
  
     [!code-csharp[Trin_VstcoreHostControlsExcel#5](../vsto/codesnippet/CSharp/Trin_VstcoreHostControlsExcelCS/Sheet1.cs#5)]
     [!code-vb[Trin_VstcoreHostControlsExcel#5](../vsto/codesnippet/VisualBasic/Trin_VstcoreHostControlsExcelVB/Sheet1.vb#5)]  
  
##  <a name="runtimeaddin"></a>Bir VSTO eklenti projesindeki çalışma zamanında NamedRange denetimleri yeniden boyutlandırma  
 Boyutlandırabilirsiniz bir <xref:Microsoft.Office.Tools.Excel.NamedRange> herhangi bir açık çalışma zamanında denetim. Ekleme hakkında daha fazla bilgi için bir <xref:Microsoft.Office.Tools.Excel.NamedRange> denetiminin çalışma sayfasına bir VSTO eklenti kullanarak, bkz: [nasıl yapılır: çalışma sayfalarına NamedRange denetimleri ekleme](../vsto/how-to-add-namedrange-controls-to-worksheets.md).  
  
#### <a name="to-resize-a-named-range-programmatically"></a>Adlandırılmış bir aralık programlı olarak yeniden boyutlandırmak için  
  
1.  Oluşturma bir <xref:Microsoft.Office.Tools.Excel.NamedRange> hücre denetiminde **A1** , `Sheet1`.  
  
     [!code-csharp[Trin_Excel_Dynamic_Controls#10](../vsto/codesnippet/CSharp/Trin_Excel_Dynamic_Controls/ThisAddIn.cs#10)]
     [!code-vb[Trin_Excel_Dynamic_Controls#10](../vsto/codesnippet/VisualBasic/Trin_Excel_Dynamic_Controls/ThisAddIn.vb#10)]  
  
2.  Adlandırılmış aralığın hücresini dahil etmek için yeniden boyutlandır **B1**.  
  
     [!code-csharp[Trin_Excel_Dynamic_Controls#11](../vsto/codesnippet/CSharp/Trin_Excel_Dynamic_Controls/ThisAddIn.cs#11)]
     [!code-vb[Trin_Excel_Dynamic_Controls#11](../vsto/codesnippet/VisualBasic/Trin_Excel_Dynamic_Controls/ThisAddIn.vb#11)]  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Genişletme Word belgelerini ve Excel çalışma kitaplarını çalışma zamanında VSTO eklentileri](../vsto/extending-word-documents-and-excel-workbooks-in-vsto-add-ins-at-run-time.md)   
 [Office belgelerine çalışma zamanında denetimler ekleme](../vsto/adding-controls-to-office-documents-at-run-time.md)   
 [Office belgelerindeki denetimler](../vsto/controls-on-office-documents.md)   
 [Konak öğelerine ve denetimlerine genel bakış](../vsto/host-items-and-host-controls-overview.md)   
 [Genişletilmiş nesneleri kullanarak Excel'i otomatikleştirme](../vsto/automating-excel-by-using-extended-objects.md)   
 [NamedRange denetimi](../vsto/namedrange-control.md)   
 [Nasıl yapılır: çalışma sayfalarına NamedRange denetimleri ekleme](../vsto/how-to-add-namedrange-controls-to-worksheets.md)   
 [Nasıl yapılır: yer işareti denetimlerini yeniden boyutlandırma](../vsto/how-to-resize-bookmark-controls.md)   
 [Nasıl yapılır: ListObject denetimlerinin boyutunu değiştirme](../vsto/how-to-resize-listobject-controls.md)  
  
  