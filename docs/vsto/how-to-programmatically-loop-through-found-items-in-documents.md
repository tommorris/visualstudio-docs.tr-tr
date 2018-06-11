---
title: 'Nasıl yapılır: program aracılığıyla bulunan öğeler arasında döngü'
ms.custom: ''
ms.date: 02/02/2017
ms.technology:
- office-development
ms.topic: conceptual
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- loops, through found items in documents
- documents [Office development in Visual Studio], searching
- text [Office development in Visual Studio], searching in documents
author: TerryGLee
ms.author: tglee
manager: douge
ms.workload:
- office
ms.openlocfilehash: 874c092577796fe02e3045ed649c56a3fc9da355
ms.sourcegitcommit: 34f7d23ce3bd140dcae875b602d5719bb4363ed1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/11/2018
ms.locfileid: "35257832"
---
# <a name="how-to-programmatically-loop-through-found-items-in-documents"></a>Nasıl yapılır: program aracılığıyla bulunan öğeler arasında döngü
  <xref:Microsoft.Office.Interop.Word.Find> Sınıfına sahip bir <xref:Microsoft.Office.Interop.Word.Find.Found%2A> döndürür özelliği **true** her Aranan öğe bulundu. Bulunan tüm örneklerini döngü bir <xref:Microsoft.Office.Interop.Word.Range> kullanarak <xref:Microsoft.Office.Interop.Word.Find.Execute%2A> yöntemi.  
  
 [!INCLUDE[appliesto_wdalldocapp](../vsto/includes/appliesto-wdalldocapp-md.md)]  
  
## <a name="to-loop-through-found-items"></a>Bulunan öğeler arasında döngü için  
  
1.  Bildirme bir <xref:Microsoft.Office.Interop.Word.Range> nesnesi.  
  
     Aşağıdaki kod örneği bir belge düzeyi özelleştirmelerinde kullanılabilir.  
  
     [!code-vb[Trin_VstcoreWordAutomation#79](../vsto/codesnippet/VisualBasic/Trin_VstcoreWordAutomationVB/ThisDocument.vb#79)]
     [!code-csharp[Trin_VstcoreWordAutomation#79](../vsto/codesnippet/CSharp/Trin_VstcoreWordAutomationCS/ThisDocument.cs#79)]  
  
     Aşağıdaki kod örneği, bir VSTO eklenti kullanılabilir. Bu örnek etkin belgeyi kullanır.  
  
     [!code-vb[Trin_VstcoreWordAutomationAddIn#79](../vsto/codesnippet/VisualBasic/Trin_VstcoreWordAutomationAddIn/ThisAddIn.vb#79)]
     [!code-csharp[Trin_VstcoreWordAutomationAddIn#79](../vsto/codesnippet/CSharp/Trin_VstcoreWordAutomationAddIn/ThisAddIn.cs#79)]  
  
2.  Kullanım <xref:Microsoft.Office.Interop.Word.Find.Found%2A> dize belge dizenin tüm oluşumlarını aramak ve her zaman 1 ile bir tamsayı değişken artırmak için bir döngü bir özellik bulundu.  
  
     [!code-vb[Trin_VstcoreWordAutomation#80](../vsto/codesnippet/VisualBasic/Trin_VstcoreWordAutomationVB/ThisDocument.vb#80)]
     [!code-csharp[Trin_VstcoreWordAutomation#80](../vsto/codesnippet/CSharp/Trin_VstcoreWordAutomationCS/ThisDocument.cs#80)]  
  
3.  Dize bir ileti kutusu içinde bulunan sayısını görüntüler.  
  
     [!code-vb[Trin_VstcoreWordAutomation#81](../vsto/codesnippet/VisualBasic/Trin_VstcoreWordAutomationVB/ThisDocument.vb#81)]
     [!code-csharp[Trin_VstcoreWordAutomation#81](../vsto/codesnippet/CSharp/Trin_VstcoreWordAutomationCS/ThisDocument.cs#81)]  
  
 Aşağıdaki örnekler tam yöntemi gösterir.  
  
## <a name="document-level-customization-example"></a>Belge düzeyi özelleştirme örnek  
  
### <a name="to-loop-through-items-in-a-document-level-customization"></a>Belge düzeyi özelleştirmelerinde öğeler arasında döngü için  
  
1.  Aşağıdaki örnek bir belge düzeyi özelleştirme için tam kod gösterir. Bu kodu kullanmak için çalıştırın `ThisDocument` projenizdeki sınıfı.  
  
     [!code-vb[Trin_VstcoreWordAutomation#78](../vsto/codesnippet/VisualBasic/Trin_VstcoreWordAutomationVB/ThisDocument.vb#78)]
     [!code-csharp[Trin_VstcoreWordAutomation#78](../vsto/codesnippet/CSharp/Trin_VstcoreWordAutomationCS/ThisDocument.cs#78)]  
  
## <a name="vsto-add-in-example"></a>VSTO eklenti örneği  
  
### <a name="to-loop-through-items-in-an-vsto-add-in"></a>Bir VSTO eklenti öğeler arasında döngü için  
  
1.  Aşağıdaki örnek, VSTO eklenti için tam kod gösterilir. Bu kodu kullanmak için çalıştırın `ThisAddIn` projenizdeki sınıfı.  
  
     [!code-vb[Trin_VstcoreWordAutomationAddIn#78](../vsto/codesnippet/VisualBasic/Trin_VstcoreWordAutomationAddIn/ThisAddIn.vb#78)]
     [!code-csharp[Trin_VstcoreWordAutomationAddIn#78](../vsto/codesnippet/CSharp/Trin_VstcoreWordAutomationAddIn/ThisAddIn.cs#78)]  
  
## <a name="see-also"></a>Ayrıca bkz.  
 [Nasıl yapılır: program aracılığıyla arama ve belgelerde rext değiştirme](../vsto/how-to-programmatically-search-for-and-replace-text-in-documents.md)   
 [Nasıl yapılır: program aracılığıyla arama seçeneklerini ayarlama Word'de](../vsto/how-to-programmatically-set-search-options-in-word.md)   
 [Nasıl yapılır: program aracılığıyla tanımlama ve belgelerde aralıkları seçin](../vsto/how-to-programmatically-define-and-select-ranges-in-documents.md)   
 [Nasıl yapılır: program aracılığıyla aramalardan sonra seçimleri geri yükleme](../vsto/how-to-programmatically-restore-selections-after-searches.md)   
 [Office çözümlerinde isteğe bağlı parametreler](../vsto/optional-parameters-in-office-solutions.md)  
  
  