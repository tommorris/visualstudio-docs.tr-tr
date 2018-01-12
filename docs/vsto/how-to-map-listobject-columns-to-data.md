---
title: "Nasıl yapılır: ListObject sütunlarıyla verileri eşleme | Microsoft Docs"
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
- data [Office development in Visual Studio], mapping to ListObject column
- ListObject control, mapping data
author: TerryGLee
ms.author: tglee
manager: ghogen
ms.workload: office
ms.openlocfilehash: c8def85e851ac6a51eef59e3f0538025f0e7ce6c
ms.sourcegitcommit: f9fbf1f55f9ac14e4e5c6ae58c30dc1800ca6cda
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/10/2018
---
# <a name="how-to-map-listobject-columns-to-data"></a>Nasıl Yapılır: ListObject Sütunlarıyla Verileri Eşleme
  Bağladığınızda bir <xref:Microsoft.Office.Tools.Excel.ListObject> denetimini bir <xref:System.Data.DataTable>bir listedeki tüm sütunları görüntülemek istemeyebilirsiniz veya verilere bağlı olmayan bazı sütunları olabilir. Görünmesini istediğiniz sütunları eşleyebilirsiniz <xref:Microsoft.Office.Tools.Excel.ListObject> çağırdığınızda <xref:Microsoft.Office.Tools.Excel.ListObject.SetDataBinding%2A> yöntemi.  
  
 [!INCLUDE[appliesto_xlalldocapp](../vsto/includes/appliesto-xlalldocapp-md.md)]  
  
 ![video bağlantı](../vsto/media/playvideo.gif "video bağlantı") ilgili video gösterimi için bkz: [nasıl I: oluşturmak listesini bir SharePoint listesine bağlı Excel'de?](http://go.microsoft.com/fwlink/?LinkID=130263).  
  
## <a name="mapping-columns"></a>Sütunları eşleme  
  
#### <a name="to-map-a-data-table-to-columns-in-a-list"></a>Veri tablosu bir listedeki sütunlara eşlemek için  
  
1.  Oluşturma <xref:System.Data.DataTable> sınıf düzeyinde.  
  
     [!code-csharp[Trin_VstcoreHostControlsExcel#16](../vsto/codesnippet/CSharp/Trin_VstcoreHostControlsExcelCS/Sheet3.cs#16)]
     [!code-vb[Trin_VstcoreHostControlsExcel#16](../vsto/codesnippet/VisualBasic/Trin_VstcoreHostControlsExcelVB/Sheet3.vb#16)]  
  
2.  Örnek sütunlar ve verilerde ekleme `Startup` olay işleyicisi `Sheet1` sınıfı (belge düzeyi projede) veya `ThisAddIn` sınıfında (VSTO eklenti projesindeki).  
  
     [!code-csharp[Trin_VstcoreHostControlsExcel#17](../vsto/codesnippet/CSharp/Trin_VstcoreHostControlsExcelCS/Sheet3.cs#17)]
     [!code-vb[Trin_VstcoreHostControlsExcel#17](../vsto/codesnippet/VisualBasic/Trin_VstcoreHostControlsExcelVB/Sheet3.vb#17)]  
  
3.  Çağrı <xref:Microsoft.Office.Tools.Excel.ListObject.SetDataBinding%2A> yöntemi ve sütun adları göründükleri sırada geçirin. Yeni oluşturulan için liste nesnesi bağlanacak <xref:System.Data.DataTable>, ancak liste nesnesindeki sütunların sırası içinde göründükleri sırada farklı <xref:System.Data.DataTable>.  
  
     [!code-csharp[Trin_VstcoreHostControlsExcel#18](../vsto/codesnippet/CSharp/Trin_VstcoreHostControlsExcelCS/Sheet3.cs#18)]
     [!code-vb[Trin_VstcoreHostControlsExcel#18](../vsto/codesnippet/VisualBasic/Trin_VstcoreHostControlsExcelVB/Sheet3.vb#18)]  
  
## <a name="specifying-unmapped-columns"></a>Eşlenmemiş sütunları belirtme  
 Sütunları eşlediğinizde bir <xref:System.Data.DataTable>, bazı sütunlar verileri boş bir dize geçirerek bağlanmalıdır değil olduğunu da belirtebilirsiniz. Verilere bağlı yeni bir sütun daha sonra eklenen <xref:Microsoft.Office.Tools.Excel.ListObject> denetim.  
  
#### <a name="to-specify-an-unmapped-column-when-mapping-listobject-columns"></a>ListObject sütunları eşlerken eşlenmeyecek bir sütunu belirtmek için  
  
1.  Çağrı <xref:Microsoft.Office.Tools.Excel.ListObject.SetDataBinding%2A> yöntemi ve sütun adları göründükleri sırada geçirin. Boş bir dize eşlenmeyecek sütunun nerede eklenir belirtmek için kullanın; Bu durumda, bir başlık sütunu ve soyadı sütununun arasında.  
  
     [!code-csharp[Trin_VstcoreHostControlsExcel#19](../vsto/codesnippet/CSharp/Trin_VstcoreHostControlsExcelCS/Sheet3.cs#19)]
     [!code-vb[Trin_VstcoreHostControlsExcel#19](../vsto/codesnippet/VisualBasic/Trin_VstcoreHostControlsExcelVB/Sheet3.vb#19)]  
  
## <a name="compiling-the-code"></a>Kod Derleniyor  
 Bu kod örneği, var olan varsayar <xref:Microsoft.Office.Tools.Excel.ListObject> adlı `list1` bu kodu göründüğü çalışma sayfası üzerinde.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Genişletme Word belgelerini ve Excel çalışma kitaplarını çalışma zamanında VSTO eklentileri](../vsto/extending-word-documents-and-excel-workbooks-in-vsto-add-ins-at-run-time.md)   
 [Office belgelerindeki denetimler](../vsto/controls-on-office-documents.md)   
 [Office belgelerine çalışma zamanında denetimler ekleme](../vsto/adding-controls-to-office-documents-at-run-time.md)   
 [Nasıl yapılır: ListObject denetimlerini veri ile doldurma](../vsto/how-to-fill-listobject-controls-with-data.md)   
 [Genişletilmiş nesneleri kullanarak Excel'i otomatikleştirme](../vsto/automating-excel-by-using-extended-objects.md)   
 [ListObject Denetimi](../vsto/listobject-control.md)  
  
  