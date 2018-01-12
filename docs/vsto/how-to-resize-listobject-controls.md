---
title: "Nasıl yapılır: ListObject denetimlerinin boyutunu değiştirme | Microsoft Docs"
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
- ListObject control, resizing
author: TerryGLee
ms.author: tglee
manager: ghogen
ms.workload: office
ms.openlocfilehash: e018ed60e60c63dd47b5d56b599ea0f0499f561c
ms.sourcegitcommit: f9fbf1f55f9ac14e4e5c6ae58c30dc1800ca6cda
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/10/2018
---
# <a name="how-to-resize-listobject-controls"></a>Nasıl yapılır: ListObject Denetimlerinin Boyutunu Değiştirme
  Boyutu ayarlama bir <xref:Microsoft.Office.Tools.Excel.ListObject> Microsoft Office Excel çalışma kitabına eklediğinizde denetim; ancak, daha sonraki bir zamanda yeniden boyutlandırmak isteyebilirsiniz. Örneğin, iki sütun listesi için üç sütunları değiştirmek isteyebilirsiniz.  
  
 [!INCLUDE[appliesto_xlalldocapp](../vsto/includes/appliesto-xlalldocapp-md.md)]  
  
 Boyutlandırabilirsiniz <xref:Microsoft.Office.Tools.Excel.ListObject> tasarım zamanında veya belge düzeyi projelerine çalışma zamanında denetimler. Boyutlandırabilirsiniz <xref:Microsoft.Office.Tools.Excel.ListObject> VSTO eklenti projesindeki çalışma zamanında denetimler.  
  
 Bu konuda aşağıdaki görevler açıklanmaktadır:  
  
-   [Tasarım zamanında ListObject denetimleri yeniden boyutlandırma](#designtime)  
  
-   [Belge düzeyi projesindeki çalışma zamanında ListObject denetimleri yeniden boyutlandırma](#runtimedoclevel)  
  
-   [VSTO eklenti projesindeki çalışma zamanında ListObject denetimleri yeniden boyutlandırma](#runtimeaddin)  
  
 Hakkında daha fazla bilgi için <xref:Microsoft.Office.Tools.Excel.ListObject> denetimleri bkz [ListObject denetimi](../vsto/listobject-control.md).  
  
 ![video bağlantı](../vsto/media/playvideo.gif "video bağlantı") ilgili video gösterimi için bkz: [nasıl yapmak I: Sütun Ekle çalışma zamanında veri bağlama listesi nesnesine?](http://go.microsoft.com/fwlink/?LinkID=130318).  
  
##  <a name="designtime"></a>ListObject denetimi tasarım zamanında yeniden boyutlandırma  
 Listeyi yeniden boyutlandırmak için tıklayın ve boyutlandırma birini sürükleyin veya boyutunda tanımlayabilirsiniz **listeyi yeniden boyutlandır** iletişim kutusu.  
  
#### <a name="to-resize-a-list-by-using-the-resize-list-dialog-box"></a>Bir listeyi listeyi yeniden boyutlandır iletişim kutusunu kullanarak yeniden boyutlandırmak için  
  
  
1.  Herhangi bir yeri tıklatın <xref:Microsoft.Office.Tools.Excel.ListObject> tablo. **Tablo araçları, tasarım** Şerit sekmesinde görünür.  
  
2.  Özellikleri bölümünde tıklayın **yeniden boyutlandırma tablo**.  

    ![VSTO_ResizeTable](../vsto/media/vsto-resizetable.png)
  
3.  Yeni veri aralığını tablonuzun seçin.  
  
4.  **Tamam**'ı tıklatın.  
  
##  <a name="runtimedoclevel"></a>Belge düzeyi projesindeki çalışma zamanında ListObject denetimi yeniden boyutlandırma  
 Boyutlandırabilirsiniz bir <xref:Microsoft.Office.Tools.Excel.ListObject> kullanarak çalışma zamanında denetim <xref:Microsoft.Office.Tools.Excel.ListObject.Resize%2A> yöntemi. Taşımak için bu yöntemi kullanarak <xref:Microsoft.Office.Tools.Excel.ListObject> çalışma sayfası üzerinde yeni bir konuma denetim. Üstbilgiler aynı satır ve yeniden boyutlandırılmış kalmalı <xref:Microsoft.Office.Tools.Excel.ListObject> denetimi özgün liste nesnesiyle çakışmaması gerekir. Yeniden boyutlandırılan <xref:Microsoft.Office.Tools.Excel.ListObject> denetim üstbilgisi satır ve verilerin en az bir satır içermelidir.  
  
#### <a name="to-resize-a-list-object-programmatically"></a>Bir liste nesnesi programlı olarak yeniden boyutlandırmak için  
  
1.  Oluşturma bir <xref:Microsoft.Office.Tools.Excel.ListObject> hücre yayılan denetim **A1** aracılığıyla **B3** üzerinde `Sheet1`.  
  
     [!code-csharp[Trin_VstcoreHostControlsExcel#6](../vsto/codesnippet/CSharp/Trin_VstcoreHostControlsExcelCS/Sheet1.cs#6)]
     [!code-vb[Trin_VstcoreHostControlsExcel#6](../vsto/codesnippet/VisualBasic/Trin_VstcoreHostControlsExcelVB/Sheet1.vb#6)]  
  
2.  Listeyi hücreleri içerecek şekilde yeniden boyutlandırın **A1** aracılığıyla **C5**.  
  
     [!code-csharp[Trin_VstcoreHostControlsExcel#7](../vsto/codesnippet/CSharp/Trin_VstcoreHostControlsExcelCS/Sheet1.cs#7)]
     [!code-vb[Trin_VstcoreHostControlsExcel#7](../vsto/codesnippet/VisualBasic/Trin_VstcoreHostControlsExcelVB/Sheet1.vb#7)]  
  
##  <a name="runtimeaddin"></a>Bir VSTO eklenti projesindeki çalışma zamanında ListObject yeniden boyutlandırma  
 Boyutlandırabilirsiniz bir <xref:Microsoft.Office.Tools.Excel.ListObject> herhangi bir açık çalışma zamanında denetim. Ekleme hakkında daha fazla bilgi için bir <xref:Microsoft.Office.Tools.Excel.ListObject> denetiminin çalışma sayfasına bir VSTO eklenti kullanarak, bkz: [nasıl yapılır: çalışma sayfalarına ListObject denetimleri ekleme](../vsto/how-to-add-listobject-controls-to-worksheets.md).  
  
#### <a name="to-resize-a-list-object-programmatically"></a>Bir liste nesnesi programlı olarak yeniden boyutlandırmak için  
  
1.  Oluşturma bir <xref:Microsoft.Office.Tools.Excel.ListObject> hücre yayılan denetim **A1** aracılığıyla **B3** üzerinde `Sheet1`.  
  
     [!code-csharp[Trin_Excel_Dynamic_Controls#12](../vsto/codesnippet/CSharp/Trin_Excel_Dynamic_Controls/ThisAddIn.cs#12)]
     [!code-vb[Trin_Excel_Dynamic_Controls#12](../vsto/codesnippet/VisualBasic/Trin_Excel_Dynamic_Controls/ThisAddIn.vb#12)]  
  
2.  Listeyi hücreleri içerecek şekilde yeniden boyutlandırın **A1** aracılığıyla **C5**.  
  
     [!code-csharp[Trin_Excel_Dynamic_Controls#13](../vsto/codesnippet/CSharp/Trin_Excel_Dynamic_Controls/ThisAddIn.cs#13)]
     [!code-vb[Trin_Excel_Dynamic_Controls#13](../vsto/codesnippet/VisualBasic/Trin_Excel_Dynamic_Controls/ThisAddIn.vb#13)]  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Genişletme Word belgelerini ve Excel çalışma kitaplarını çalışma zamanında VSTO eklentileri](../vsto/extending-word-documents-and-excel-workbooks-in-vsto-add-ins-at-run-time.md)   
 [Office belgelerindeki denetimler](../vsto/controls-on-office-documents.md)   
 [Office belgelerine çalışma zamanında denetimler ekleme](../vsto/adding-controls-to-office-documents-at-run-time.md)   
 [Konak öğelerine ve denetimlerine genel bakış](../vsto/host-items-and-host-controls-overview.md)   
 [Genişletilmiş nesneleri kullanarak Excel'i otomatikleştirme](../vsto/automating-excel-by-using-extended-objects.md)   
 [ListObject denetimi](../vsto/listobject-control.md)   
 [Nasıl yapılır: çalışma sayfalarına ListObject denetimleri ekleme](../vsto/how-to-add-listobject-controls-to-worksheets.md)   
 [Nasıl yapılır: yer işareti denetimlerini yeniden boyutlandırma](../vsto/how-to-resize-bookmark-controls.md)   
 [Nasıl yapılır: NamedRange Denetimlerinin Boyutunu Değiştirme](../vsto/how-to-resize-namedrange-controls.md)  
  
  