---
title: NamedRange denetimi | Microsoft Docs
ms.custom: ''
ms.date: 02/02/2017
ms.technology:
- office-development
ms.topic: conceptual
f1_keywords:
- VST.Toolbox.Range
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- ranges, named
- NamedRange control, events
- NamedRange control, data binding
- NamedRange control
author: TerryGLee
ms.author: tglee
manager: douge
ms.workload:
- office
ms.openlocfilehash: 7ea0b0f59731f711dc32258aea31358626825f5d
ms.sourcegitcommit: 0aafcfa08ef74f162af2e5079be77061d7885cac
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/01/2018
ms.locfileid: "34573095"
---
# <a name="namedrange-control"></a>NamedRange denetimi
  <xref:Microsoft.Office.Tools.Excel.NamedRange> Denetimidir benzersiz bir ada sahip olayları gösterir ve verilere bağlanabilen bir aralık. Daha fazla bilgi için bkz: [Excel nesne modeline genel bakış](../vsto/excel-object-model-overview.md).  
  
 [!INCLUDE[appliesto_xlalldocapp](../vsto/includes/appliesto-xlalldocapp-md.md)]  
  
## <a name="create-the-control"></a>Denetim oluşturma  
 Ekleyebileceğiniz <xref:Microsoft.Office.Tools.Excel.NamedRange> Microsoft Office Excel çalışma zamanında veya belge düzeyi projelerine çalışma zamanında denetimler.  
  
 Ekleyebileceğiniz <xref:Microsoft.Office.Tools.Excel.NamedRange> denetimlerini çalışma zamanında VSTO eklenti. Daha fazla bilgi için bkz: [nasıl yapılır: çalışma sayfalarına ekleme NamedRange denetimleri](../vsto/how-to-add-namedrange-controls-to-worksheets.md).  
  
> [!NOTE]  
>  Varsayılan olarak, dinamik olarak oluşturulmuş adlandırılmış aralıklar çalışma sayfasında sürdürülmeyen çalışma kapatıldığında konak kontrolü olarak. Daha fazla bilgi için bkz: [Office belgelerine çalışma zamanında denetimler ekleme](../vsto/adding-controls-to-office-documents-at-run-time.md).  
  
 <xref:Microsoft.Office.Tools.Excel.NamedRange> denetimleri yalnızca belirli sayfalardaki aralıklardan oluşabilir. <xref:Microsoft.Office.Tools.Excel.NamedRange> denetimleri tüm sayfalara uygulanabilen göreli adlara sahip olamaz ve iki veya daha fazla çalışma kitabında (3-b aralıkları) yayılamaz.  
  
## <a name="bind-data-to-the-control"></a>Denetimlere veri bağlama  
 Adlandırılmış bir aralık fazla hücre içerebileceğinden karmaşık veri bağlama için iyi bir aday olarak görünebilir; Ancak, bir aralık yalnızca belirli bir sütuna bir veri kümesinden kolayca eşlenemez hücreleri koleksiyonudur. Bu nedenle, <xref:Microsoft.Office.Tools.Excel.NamedRange> denetimleri yalnızca basit veri bağlama destekler. <xref:Microsoft.Office.Tools.Excel.ListObject> Denetimi karmaşık veri bağlama için kullanılabilir. Daha fazla bilgi için bkz: [ListObject denetimi](../vsto/listobject-control.md).  
  
 <xref:Microsoft.Office.Tools.Excel.NamedRange> Denetimi kullanarak bir veri kaynağına bağlanabilir <xref:System.Windows.Forms.Control.DataBindings%2A> özellikleri. Varsayılan veri bağlama özelliğini <xref:Microsoft.Office.Tools.Excel.NamedRange> denetimi <xref:Microsoft.Office.Tools.Excel.NamedRange.Value2%2A>.  
  
 Veri bağlama kümesindeki herhangi bir mekanizma aracılığıyla güncelleştirdiyseniz <xref:Microsoft.Office.Tools.Excel.NamedRange> denetimi değişiklikleri yansıtır.  
  
## <a name="formatting"></a>Biçimlendirme  
 Uygulanabilir biçimlendirme bir <xref:Microsoft.Office.Interop.Excel.Range> uygulanabilir bir <xref:Microsoft.Office.Tools.Excel.NamedRange> denetim. Bu kenarlıklar, yazı tipi, numara biçimi ve stilleri içerir.  
  
## <a name="rename-the-control"></a>Denetim yeniden adlandırma  
 Eklediğinizde bir <xref:Microsoft.Office.Tools.Excel.NamedRange> çalışma sayfasından denetimine **araç**, Visual Studio otomatik olarak denetim için bir ad oluşturur. Adını değiştirebilirsiniz **özellikleri** penceresi.  
  
## <a name="events"></a>Olaylar  
 Aşağıdaki olaylar kullanılabilir <xref:Microsoft.Office.Tools.Excel.NamedRange> denetimi:  
  
-   <xref:Microsoft.Office.Tools.Excel.NamedRange.BeforeDoubleClick>  
  
-   <xref:Microsoft.Office.Tools.Excel.NamedRange.BeforeRightClick>  
  
-   <xref:Microsoft.Office.Tools.Excel.NamedRange.BindingContextChanged>  
  
-   <xref:Microsoft.Office.Tools.Excel.NamedRange.Change>  
  
-   <xref:Microsoft.Office.Tools.Excel.NamedRange.Deselected>  
  
-   <xref:System.ComponentModel.Component.Disposed>  
  
-   <xref:Microsoft.Office.Tools.Excel.NamedRange.Selected>  
  
-   <xref:Microsoft.Office.Tools.Excel.NamedRange.SelectionChange>  
  
## <a name="see-also"></a>Ayrıca bkz.  
 [Genişletilmiş nesneleri kullanarak Excel'i otomatikleştirmek](../vsto/automating-excel-by-using-extended-objects.md)   
 [Office geliştirme örnekleri ve izlenecek yollar](../vsto/office-development-samples-and-walkthroughs.md)   
 [Office çözümlerinde denetimlere veri bağlama](../vsto/binding-data-to-controls-in-office-solutions.md)   
 [Word belgelerini ve Excel çalışma kitaplarını VSTO eklentileri çalışma zamanında genişletme](../vsto/extending-word-documents-and-excel-workbooks-in-vsto-add-ins-at-run-time.md)   
 [Office belgelerindeki denetimler](../vsto/controls-on-office-documents.md)   
 [Office belgelerine çalışma zamanında denetimler ekleme](../vsto/adding-controls-to-office-documents-at-run-time.md)   
 [Nasıl yapılır: çalışma sayfalarına NamedRange denetimleri ekleme](../vsto/how-to-add-namedrange-controls-to-worksheets.md)   
 [Nasıl yapılır: NamedRange denetimlerinin boyutunu değiştirme](../vsto/how-to-resize-namedrange-controls.md)   
 [Office çözümlerinde denetimlere veri bağlama](../vsto/binding-data-to-controls-in-office-solutions.md)   
 [İzlenecek yol: Program NamedRange denetimi olaylarına karşı](../vsto/walkthrough-programming-against-events-of-a-namedrange-control.md)   
 [Konak denetimlerinin ve konak öğelerinin programlama sınırlamaları](../vsto/programmatic-limitations-of-host-items-and-host-controls.md)  
  
  