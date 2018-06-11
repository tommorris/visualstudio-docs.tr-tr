---
title: 'Nasıl yapılır: program aracılığıyla tanımlama ve belgelerde aralıkları seçin'
ms.custom: ''
ms.date: 02/02/2017
ms.technology:
- office-development
ms.topic: conceptual
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- documents [Office development in Visual Studio], selecting sentences
- documents [Office development in Visual Studio], ranges
- sentences, selecting in documents
- ranges, selecting in documents
- ranges, defining in documents
author: TerryGLee
ms.author: tglee
manager: douge
ms.workload:
- office
ms.openlocfilehash: 947232d593543276de281d89e3d05d6648f29ec1
ms.sourcegitcommit: 34f7d23ce3bd140dcae875b602d5719bb4363ed1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/11/2018
ms.locfileid: "35257302"
---
# <a name="how-to-programmatically-define-and-select-ranges-in-documents"></a>Nasıl yapılır: program aracılığıyla tanımlama ve belgelerde aralıkları seçin
  Kullanarak bir Microsoft Office Word belgesinde aralığı tanımlayabilirsiniz bir <xref:Microsoft.Office.Interop.Word.Range> nesnesi. Kullanarak, örneğin, bir çeşitli yollarla, tüm belgedeki seçebilirsiniz <xref:Microsoft.Office.Interop.Word.Range.Select%2A> yöntemi <xref:Microsoft.Office.Interop.Word.Range> içerik özelliğini kullanarak veya nesne <xref:Microsoft.Office.Tools.Word.Document> sınıfı (belge düzeyi özelleştirmelerinde) veya <xref:Microsoft.Office.Interop.Word.Document> sınıfı (içinde bir VSTO eklentisinin).  
  
 [!INCLUDE[appliesto_wdalldocapp](../vsto/includes/appliesto-wdalldocapp-md.md)]  
  
## <a name="define-a-range"></a>Bir aralık tanımlayın  
 Aşağıdaki örnek yeni bir oluşturulacağını gösterir <xref:Microsoft.Office.Interop.Word.Range> karakterleri yazdırılamayan karakterleri dahil olmak üzere etkin belgede ilk yedi içeren nesne. Ardından, metin aralığı içinde seçer.  
  
### <a name="to-define-a-range-in-a-document-level-customization"></a>Belge düzeyi özelleştirmelerinde bir aralık tanımlamak için  
  
1.  Bir başlangıç ve bitiş karakteri geçirerek aralığı belgeye eklemek <xref:Microsoft.Office.Tools.Word.Document.Range%2A> yöntemi <xref:Microsoft.Office.Tools.Word.Document> sınıfı. Bu kod örneği kullanmak için çalıştırın `ThisDocument` projenizdeki sınıfı.  
  
     [!code-vb[Trin_VstcoreWordAutomation#18](../vsto/codesnippet/VisualBasic/Trin_VstcoreWordAutomationVB/ThisDocument.vb#18)]
     [!code-csharp[Trin_VstcoreWordAutomation#18](../vsto/codesnippet/CSharp/Trin_VstcoreWordAutomationCS/ThisDocument.cs#18)]  
  
### <a name="to-define-a-range-by-using-a-vsto-add-in"></a>Bir VSTO eklentisini kullanarak bir aralık tanımlamak için  
  
1.  Bir başlangıç ve bitiş karakteri geçirerek aralığı belgeye eklemek <xref:Microsoft.Office.Interop.Word._Document.Range%2A> yöntemi <xref:Microsoft.Office.Interop.Word.Document> sınıfı. Aşağıdaki kod örneğinde etkin belge için bir aralığı ekler. Bu kod örneği kullanmak için çalıştırın `ThisAddIn` projenizdeki sınıfı.  
  
     [!code-vb[Trin_VstcoreWordAutomationAddIn#18](../vsto/codesnippet/VisualBasic/Trin_VstcoreWordAutomationAddIn/ThisAddIn.vb#18)]
     [!code-csharp[Trin_VstcoreWordAutomationAddIn#18](../vsto/codesnippet/CSharp/Trin_VstcoreWordAutomationAddIn/ThisAddIn.cs#18)]  
  
## <a name="select-a-range-in-a-document-level-customization"></a>Belge düzeyi özelleştirmelerinde bir aralık seçin  
 Aşağıdaki örnekler kullanarak tüm belgeyi Seç nasıl <xref:Microsoft.Office.Interop.Word.Range.Select%2A> yöntemi bir <xref:Microsoft.Office.Interop.Word.Range> kullanarak veya nesne <xref:Microsoft.Office.Tools.Word.Document.Content%2A> özelliği <xref:Microsoft.Office.Tools.Word.Document> sınıfı.  
  
### <a name="to-select-the-entire-document-as-a-range-by-using-the-select-method"></a>Tüm belgeyi Seç yöntemini kullanarak bir aralık olarak seçmek için  
  
1.  Kullanım <xref:Microsoft.Office.Interop.Word.Range.Select%2A> yöntemi bir <xref:Microsoft.Office.Interop.Word.Range> tüm belgeyi içerir. Aşağıdaki kod örneğini kullanmak için çalıştırın `ThisDocument` projenizdeki sınıfı.  
  
     [!code-vb[Trin_VstcoreWordAutomation#19](../vsto/codesnippet/VisualBasic/Trin_VstcoreWordAutomationVB/ThisDocument.vb#19)]
     [!code-csharp[Trin_VstcoreWordAutomation#19](../vsto/codesnippet/CSharp/Trin_VstcoreWordAutomationCS/ThisDocument.cs#19)]  
  
### <a name="to-select-the-entire-document-as-a-range-by-using-the-content-property"></a>İçerik özelliği kullanarak tüm belgeyi bir aralık olarak seçmek için  
  
1.  Kullanım <xref:Microsoft.Office.Tools.Word.Document.Content%2A> tüm belgeyi kapsayan bir aralık tanımlamak için özellik.  
  
     [!code-vb[Trin_VstcoreWordAutomation#20](../vsto/codesnippet/VisualBasic/Trin_VstcoreWordAutomationVB/ThisDocument.vb#20)]
     [!code-csharp[Trin_VstcoreWordAutomation#20](../vsto/codesnippet/CSharp/Trin_VstcoreWordAutomationCS/ThisDocument.cs#20)]  
  
 Bir aralık tanımlamak için diğer nesnelerin özelliklerini ve yöntemlerini kullanabilirsiniz.  
  
### <a name="to-select-a-sentence-in-the-active-document"></a>Etkin belgede bir cümle seçmek için  
  
1.  Kullanarak aralığı ayarlayın <xref:Microsoft.Office.Interop.Word.Sentences> koleksiyonu. Seçmek istediğiniz cümlenin dizinini kullanın.  
  
     [!code-vb[Trin_VstcoreWordAutomation#21](../vsto/codesnippet/VisualBasic/Trin_VstcoreWordAutomationVB/ThisDocument.vb#21)]
     [!code-csharp[Trin_VstcoreWordAutomation#21](../vsto/codesnippet/CSharp/Trin_VstcoreWordAutomationCS/ThisDocument.cs#21)]  
  
 Bir cümle seçmek için başka bir aralık için başlangıç ve bitiş değerlerini el ile ayarlamak için yoludur.  
  
### <a name="to-select-a-sentence-by-manually-setting-the-start-and-end-values"></a>Başlangıç ve bitiş değerlerini el ile ayarlayarak bir cümle seçmek için  
  
1.  Aralık değişkeni oluşturun.  
  
     [!code-vb[Trin_VstcoreWordAutomation#23](../vsto/codesnippet/VisualBasic/Trin_VstcoreWordAutomationVB/ThisDocument.vb#23)]
     [!code-csharp[Trin_VstcoreWordAutomation#23](../vsto/codesnippet/CSharp/Trin_VstcoreWordAutomationCS/ThisDocument.cs#23)]  
  
2.  Belgede, en az iki cümle olup olmadığını denetleyin ayarlayın *Başlat* ve *son* bağımsız değişkenleri aralık ve aralık seçin.  
  
     [!code-vb[Trin_VstcoreWordAutomation#24](../vsto/codesnippet/VisualBasic/Trin_VstcoreWordAutomationVB/ThisDocument.vb#24)]
     [!code-csharp[Trin_VstcoreWordAutomation#24](../vsto/codesnippet/CSharp/Trin_VstcoreWordAutomationCS/ThisDocument.cs#24)]  
  
## <a name="select-a-range-by-using-a-vsto-add-in"></a>Bir VSTO eklentisini kullanarak bir aralık seçin  
 Aşağıdaki örnekler kullanarak tüm belgeyi Seç nasıl <xref:Microsoft.Office.Interop.Word.Range.Select%2A> yöntemi bir <xref:Microsoft.Office.Interop.Word.Range> kullanarak veya nesne <xref:Microsoft.Office.Interop.Word._Document.Content%2A> özelliği <xref:Microsoft.Office.Interop.Word.Document> sınıfı.  
  
### <a name="to-select-the-entire-document-as-a-range-by-using-the-select-method"></a>Tüm belgeyi Seç yöntemini kullanarak bir aralık olarak seçmek için  
  
1.  Kullanım <xref:Microsoft.Office.Interop.Word.Range.Select%2A> yöntemi bir <xref:Microsoft.Office.Interop.Word.Range> tüm belgeyi içerir. Aşağıdaki kod örneğinde etkin belgesinin içeriğini seçer. Bu kod örneği kullanmak için çalıştırın `ThisAddIn` projenizdeki sınıfı.  
  
     [!code-vb[Trin_VstcoreWordAutomationAddIn#19](../vsto/codesnippet/VisualBasic/Trin_VstcoreWordAutomationAddIn/ThisAddIn.vb#19)]
     [!code-csharp[Trin_VstcoreWordAutomationAddIn#19](../vsto/codesnippet/CSharp/Trin_VstcoreWordAutomationAddIn/ThisAddIn.cs#19)]  
  
### <a name="to-select-the-entire-document-as-a-range-by-using-the-content-property"></a>İçerik özelliği kullanarak tüm belgeyi bir aralık olarak seçmek için  
  
1.  Kullanım <xref:Microsoft.Office.Interop.Word._Document.Content%2A> tüm belgeyi kapsayan bir aralık tanımlamak için özellik.  
  
     [!code-vb[Trin_VstcoreWordAutomationAddIn#20](../vsto/codesnippet/VisualBasic/Trin_VstcoreWordAutomationAddIn/ThisAddIn.vb#20)]
     [!code-csharp[Trin_VstcoreWordAutomationAddIn#20](../vsto/codesnippet/CSharp/Trin_VstcoreWordAutomationAddIn/ThisAddIn.cs#20)]  
  
 Bir aralık tanımlamak için diğer nesnelerin özelliklerini ve yöntemlerini kullanabilirsiniz.  
  
### <a name="to-select-a-sentence-in-the-active-document"></a>Etkin belgede bir cümle seçmek için  
  
1.  Kullanarak aralığı ayarlayın <xref:Microsoft.Office.Interop.Word.Sentences> koleksiyonu. Seçmek istediğiniz cümlenin dizinini kullanın.  
  
     [!code-vb[Trin_VstcoreWordAutomationAddIn#21](../vsto/codesnippet/VisualBasic/Trin_VstcoreWordAutomationAddIn/ThisAddIn.vb#21)]
     [!code-csharp[Trin_VstcoreWordAutomationAddIn#21](../vsto/codesnippet/CSharp/Trin_VstcoreWordAutomationAddIn/ThisAddIn.cs#21)]  
  
 Bir cümle seçmek için başka bir aralık için başlangıç ve bitiş değerlerini el ile ayarlamak için yoludur.  
  
### <a name="to-select-a-sentence-by-manually-setting-the-start-and-end-values"></a>Başlangıç ve bitiş değerlerini el ile ayarlayarak bir cümle seçmek için  
  
1.  Aralık değişkeni oluşturun.  
  
     [!code-vb[Trin_VstcoreWordAutomationAddIn#23](../vsto/codesnippet/VisualBasic/Trin_VstcoreWordAutomationAddIn/ThisAddIn.vb#23)]
     [!code-csharp[Trin_VstcoreWordAutomationAddIn#23](../vsto/codesnippet/CSharp/Trin_VstcoreWordAutomationAddIn/ThisAddIn.cs#23)]  
  
2.  Belgede, en az iki cümle olup olmadığını denetleyin ayarlayın *Başlat* ve *son* bağımsız değişkenleri aralık ve aralık seçin.  
  
     [!code-vb[Trin_VstcoreWordAutomationAddIn#24](../vsto/codesnippet/VisualBasic/Trin_VstcoreWordAutomationAddIn/ThisAddIn.vb#24)]
     [!code-csharp[Trin_VstcoreWordAutomationAddIn#24](../vsto/codesnippet/CSharp/Trin_VstcoreWordAutomationAddIn/ThisAddIn.cs#24)]  
  
## <a name="see-also"></a>Ayrıca bkz.  
 [Word nesne modeline genel bakış](../vsto/word-object-model-overview.md)   
 [Nasıl yapılır: belgelerde aralıkları program aracılığıyla genişletme](../vsto/how-to-programmatically-extend-ranges-in-documents.md)   
 [Nasıl yapılır: program aracılığıyla aralıklardaki başlangıç ve bitiş karakterlerini alma](../vsto/how-to-programmatically-retrieve-start-and-end-characters-in-ranges.md)   
 [Nasıl yapılır: belgelerde aralıkları program aracılığıyla genişletme](../vsto/how-to-programmatically-extend-ranges-in-documents.md)   
 [Nasıl yapılır: Word belgelerinde aralıkları'program aracılığıyla sıfırlama](../vsto/how-to-programmatically-reset-ranges-in-word-documents.md)   
 [Nasıl yapılır: aralıkları veya seçimleri program aracılığıyla daraltma](../vsto/how-to-programmatically-collapse-ranges-or-selections-in-documents.md)   
 [Nasıl yapılır: aralık oluştururken program aracılığıyla paragraf işaretlerini dışlama](../vsto/how-to-programmatically-exclude-paragraph-marks-when-creating-ranges.md)  
  
  