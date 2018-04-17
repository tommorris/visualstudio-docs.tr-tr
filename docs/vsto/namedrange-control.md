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
ms.openlocfilehash: 5273baec024da8eb339e8f3d12541fc6e98e97c0
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/16/2018
---
# <a name="namedrange-control"></a>NamedRange Denetimi
  <xref:Microsoft.Office.Tools.Excel.NamedRange> Denetimidir benzersiz bir ada sahip olayları gösterir ve verilere bağlanabilen bir aralık. Daha fazla bilgi için bkz: [Excel nesne modeline genel bakış](../vsto/excel-object-model-overview.md).  
  
 [!INCLUDE[appliesto_xlalldocapp](../vsto/includes/appliesto-xlalldocapp-md.md)]  
  
## <a name="creating-the-control"></a>Denetimi oluşturma  
 Ekleyebileceğiniz <xref:Microsoft.Office.Tools.Excel.NamedRange> Microsoft Office Excel çalışma zamanında veya belge düzeyi projelerine çalışma zamanında denetimler.  
  
 Ekleyebileceğiniz <xref:Microsoft.Office.Tools.Excel.NamedRange> denetimlerini çalışma zamanında VSTO eklenti. Daha fazla bilgi için bkz: [nasıl yapılır: çalışma sayfalarına NamedRange denetimleri ekleme](../vsto/how-to-add-namedrange-controls-to-worksheets.md).  
  
> [!NOTE]  
>  Varsayılan olarak, dinamik olarak oluşturulmuş adlandırılmış aralıklar çalışma sayfasında sürdürülmeyen çalışma kapatıldığında konak kontrolü olarak. Daha fazla bilgi için bkz: [Office belgelerine çalışma zamanında denetimler ekleme](../vsto/adding-controls-to-office-documents-at-run-time.md).  
  
 <xref:Microsoft.Office.Tools.Excel.NamedRange> denetimleri yalnızca belirli sayfalardaki aralıklardan oluşabilir. <xref:Microsoft.Office.Tools.Excel.NamedRange> denetimleri tüm sayfalara uygulanabilen göreli adlara sahip olamaz ve iki veya daha fazla çalışma kitabında (3-b aralıkları) yayılamaz.  
  
## <a name="binding-data-to-the-control"></a>Denetimine veri bağlama  
 Adlandırılmış bir aralık fazla hücre içerebileceğinden karmaşık veri bağlama için iyi bir aday olarak görünebilir; Ancak, bir aralık yalnızca belirli bir sütuna bir veri kümesinden kolayca eşlenemez hücreleri koleksiyonudur. Bu nedenle, <xref:Microsoft.Office.Tools.Excel.NamedRange> denetimleri yalnızca basit veri bağlama destekler. <xref:Microsoft.Office.Tools.Excel.ListObject> Denetimi karmaşık veri bağlama için kullanılabilir. Daha fazla bilgi için bkz: [ListObject denetimi](../vsto/listobject-control.md).  
  
 <xref:Microsoft.Office.Tools.Excel.NamedRange> Denetimi kullanarak bir veri kaynağına bağlanabilir <xref:System.Windows.Forms.Control.DataBindings%2A> özellikleri. Varsayılan veri bağlama özelliğini <xref:Microsoft.Office.Tools.Excel.NamedRange> denetimi <xref:Microsoft.Office.Tools.Excel.NamedRange.Value2%2A>.  
  
 Veri bağlama kümesindeki herhangi bir mekanizma aracılığıyla güncelleştirdiyseniz <xref:Microsoft.Office.Tools.Excel.NamedRange> denetimi değişiklikleri yansıtır.  
  
## <a name="formatting"></a>Biçimlendirme  
 Uygulanabilir biçimlendirme bir <xref:Microsoft.Office.Interop.Excel.Range> uygulanabilir bir <xref:Microsoft.Office.Tools.Excel.NamedRange> denetim. Bu kenarlıklar, yazı tipi, numara biçimi ve stilleri içerir.  
  
## <a name="renaming-the-control"></a>Denetimi yeniden adlandırma  
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
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Genişletilmiş nesneleri kullanarak Excel'i otomatikleştirme](../vsto/automating-excel-by-using-extended-objects.md)   
 [Office geliştirme örnekleri ve izlenecek yollar](../vsto/office-development-samples-and-walkthroughs.md)   
 [Office çözümlerinde denetimlere veri bağlama](../vsto/binding-data-to-controls-in-office-solutions.md)   
 [Genişletme Word belgelerini ve Excel çalışma kitaplarını çalışma zamanında VSTO eklentileri](../vsto/extending-word-documents-and-excel-workbooks-in-vsto-add-ins-at-run-time.md)   
 [Office belgelerindeki denetimler](../vsto/controls-on-office-documents.md)   
 [Office belgelerine çalışma zamanında denetimler ekleme](../vsto/adding-controls-to-office-documents-at-run-time.md)   
 [Nasıl yapılır: çalışma sayfalarına NamedRange denetimleri ekleme](../vsto/how-to-add-namedrange-controls-to-worksheets.md)   
 [Nasıl yapılır: NamedRange denetimlerinin boyutunu değiştirme](../vsto/how-to-resize-namedrange-controls.md)   
 [Office çözümlerinde denetimlere veri bağlama](../vsto/binding-data-to-controls-in-office-solutions.md)   
 [İzlenecek yol: NamedRange denetimi olaylarına karşı programlama](../vsto/walkthrough-programming-against-events-of-a-namedrange-control.md)   
 [Konak Denetimlerinin ve Konak Öğelerinin Programlama Sınırlamaları](../vsto/programmatic-limitations-of-host-items-and-host-controls.md)  
  
  