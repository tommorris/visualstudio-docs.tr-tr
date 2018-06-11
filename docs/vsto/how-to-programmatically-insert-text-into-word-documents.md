---
title: 'Nasıl yapılır: Word belgelerine program aracılığıyla metin ekleme'
ms.custom: ''
ms.date: 02/02/2017
ms.technology:
- office-development
ms.topic: conceptual
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- ranges, inserting text in documents
- text [Office development in Visual Studio], inserting in documents
- ranges, replacing text in documents
- documents [Office development in Visual Studio], inserting text
- text [Office development in Visual Studio], replacing
author: TerryGLee
ms.author: tglee
manager: douge
ms.workload:
- office
ms.openlocfilehash: 331fa8a91bb4fff51cb59b7a9f3cce23a38b3d2e
ms.sourcegitcommit: 34f7d23ce3bd140dcae875b602d5719bb4363ed1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/11/2018
ms.locfileid: "35257218"
---
# <a name="how-to-programmatically-insert-text-into-word-documents"></a>Nasıl yapılır: Word belgelerine program aracılığıyla metin ekleme
  Microsoft Office Word belgelerine metin eklemek için başlıca üç yolu vardır:  
  
-   Metin bir aralıkta ekleyin.  
  
-   Metin aralığı içinde yeni metinle değiştirir.  
  
-   Kullanım <xref:Microsoft.Office.Interop.Word.Selection.TypeText%2A> yöntemi bir <xref:Microsoft.Office.Interop.Word.Selection> imlecin veya seçimin metin eklenecek nesne.  
  
> [!NOTE]  
>  İçerik denetimleri ve yer işaretleri de metin ekleyebilirsiniz. Daha fazla bilgi için bkz: [içerik denetimleri](../vsto/content-controls.md) ve [yer işareti denetimi](../vsto/bookmark-control.md).  
  
 [!INCLUDE[appliesto_wdalldocapp](../vsto/includes/appliesto-wdalldocapp-md.md)]  
  
## <a name="insert-text-in-a-range"></a>Bir aralık içinde metin ekleme  
 Kullanım <xref:Microsoft.Office.Interop.Word.Range.Text%2A> özelliği bir <xref:Microsoft.Office.Interop.Word.Range> bir belgeye metin eklemek için nesne.  
  
### <a name="to-insert-text-in-a-range"></a>Bir aralık içinde metin eklemek için  
  
1.  Belgenin başlangıcına aralıkta belirtin ve metin eklemek **yeni metin**.  
  
     Aşağıdaki kod örneği bir belge düzeyi özelleştirmelerinde kullanılabilir.  
  
     [!code-vb[Trin_VstcoreWordAutomation#51](../vsto/codesnippet/VisualBasic/Trin_VstcoreWordAutomationVB/ThisDocument.vb#51)]
     [!code-csharp[Trin_VstcoreWordAutomation#51](../vsto/codesnippet/CSharp/Trin_VstcoreWordAutomationCS/ThisDocument.cs#51)]  
  
     Aşağıdaki kod örneğinde, VSTO eklenti içinde kullanılabilir. Bu kod, etkin belgeyi kullanır.  
  
     [!code-vb[Trin_VstcoreWordAutomationAddIn#51](../vsto/codesnippet/VisualBasic/Trin_VstcoreWordAutomationAddIn/ThisAddIn.vb#51)]
     [!code-csharp[Trin_VstcoreWordAutomationAddIn#51](../vsto/codesnippet/CSharp/Trin_VstcoreWordAutomationAddIn/ThisAddIn.cs#51)]  
  
2.  Seçin <xref:Microsoft.Office.Interop.Word.Range> bir karakter eklenen metnin uzunluğu genişletilmiştir nesnesi.  
  
     [!code-vb[Trin_VstcoreWordAutomation#52](../vsto/codesnippet/VisualBasic/Trin_VstcoreWordAutomationVB/ThisDocument.vb#52)]
     [!code-csharp[Trin_VstcoreWordAutomation#52](../vsto/codesnippet/CSharp/Trin_VstcoreWordAutomationCS/ThisDocument.cs#52)]  
  
## <a name="replace-text-in-a-range"></a>Bir aralıktaki metni Değiştir  
 Belirtilen aralığı metin içeriyorsa, aralıktaki tüm metni eklenen metinle değiştirilir.  
  
### <a name="to-replace-text-in-a-range"></a>Bir aralıktaki metni değiştirmek için  
  
1.  Oluşturma bir <xref:Microsoft.Office.Interop.Word.Range> belgedeki ilk 12 karakter içeren nesne.  
  
     Aşağıdaki kod örneği bir belge düzeyi özelleştirmelerinde kullanılabilir.  
  
     [!code-vb[Trin_VstcoreWordAutomation#53](../vsto/codesnippet/VisualBasic/Trin_VstcoreWordAutomationVB/ThisDocument.vb#53)]
     [!code-csharp[Trin_VstcoreWordAutomation#53](../vsto/codesnippet/CSharp/Trin_VstcoreWordAutomationCS/ThisDocument.cs#53)]  
  
     Aşağıdaki kod örneğinde, VSTO eklenti içinde kullanılabilir. Bu kod, etkin belgeyi kullanır.  
  
     [!code-vb[Trin_VstcoreWordAutomationAddIn#53](../vsto/codesnippet/VisualBasic/Trin_VstcoreWordAutomationAddIn/ThisAddIn.vb#53)]
     [!code-csharp[Trin_VstcoreWordAutomationAddIn#53](../vsto/codesnippet/CSharp/Trin_VstcoreWordAutomationAddIn/ThisAddIn.cs#53)]  
  
2.  Bu karakter dizesi ile değiştirin **yeni metin**.  
  
     [!code-vb[Trin_VstcoreWordAutomation#54](../vsto/codesnippet/VisualBasic/Trin_VstcoreWordAutomationVB/ThisDocument.vb#54)]
     [!code-csharp[Trin_VstcoreWordAutomation#54](../vsto/codesnippet/CSharp/Trin_VstcoreWordAutomationCS/ThisDocument.cs#54)]  
  
3.  Aralık seçin.  
  
     [!code-vb[Trin_VstcoreWordAutomation#55](../vsto/codesnippet/VisualBasic/Trin_VstcoreWordAutomationVB/ThisDocument.vb#55)]
     [!code-csharp[Trin_VstcoreWordAutomation#55](../vsto/codesnippet/CSharp/Trin_VstcoreWordAutomationCS/ThisDocument.cs#55)]  
  
## <a name="insert-text-using-typetext"></a>TypeText kullanarak metin ekleme  
 <xref:Microsoft.Office.Interop.Word.Selection.TypeText%2A> Yöntemi seçimi metin ekler. <xref:Microsoft.Office.Interop.Word.Selection.TypeText%2A> kullanıcının bilgisayarda ayarlama seçeneklere bağlı olarak farklı şekilde davranır. Aşağıdaki yordamdaki kod bildiren bir <xref:Microsoft.Office.Interop.Word.Selection> nesne değişkeni ve devre dışı bırakır **üzerine yazma** açık değilse seçeneği. Varsa **üzerine yazma** seçeneği etkinleştirilirse, ardından imleci yanındaki herhangi bir metin üzerine yazılır.  
  
### <a name="to-insert-text-using-the-typetext-method"></a>TypeText yöntemini kullanarak metin eklemek için  
  
1.  Bildirme bir <xref:Microsoft.Office.Interop.Word.Selection> nesne değişkeni.  
  
     [!code-vb[Trin_VstcoreWordAutomation#57](../vsto/codesnippet/VisualBasic/Trin_VstcoreWordAutomationVB/ThisDocument.vb#57)]
     [!code-csharp[Trin_VstcoreWordAutomation#57](../vsto/codesnippet/CSharp/Trin_VstcoreWordAutomationCS/ThisDocument.cs#57)]  
  
2.  Kapatma **üzerine yazma** açık değilse seçeneği.  
  
     [!code-vb[Trin_VstcoreWordAutomation#58](../vsto/codesnippet/VisualBasic/Trin_VstcoreWordAutomationVB/ThisDocument.vb#58)]
     [!code-csharp[Trin_VstcoreWordAutomation#58](../vsto/codesnippet/CSharp/Trin_VstcoreWordAutomationCS/ThisDocument.cs#58)]  
  
3.  Geçerli seçim bir ekleme noktası olup olmadığını görmek için test edin.  
  
     Varsa, kodu kullanarak bir cümle ekler <xref:Microsoft.Office.Interop.Word.Selection.TypeText%2A>ve ardından kullanarak bir paragraf işareti <xref:Microsoft.Office.Interop.Word.Selection.TypeParagraph%2A> yöntemi.  
  
     [!code-vb[Trin_VstcoreWordAutomation#59](../vsto/codesnippet/VisualBasic/Trin_VstcoreWordAutomationVB/ThisDocument.vb#59)]
     [!code-csharp[Trin_VstcoreWordAutomation#59](../vsto/codesnippet/CSharp/Trin_VstcoreWordAutomationCS/ThisDocument.cs#59)]  
  
4.  Kodda **ElseIf** engelleme seçimi normal bir seçim olup olmadığını görmek için sınar. İse, başka bir **varsa** engelleme görmek için sınar olup olmadığını **ReplaceSelection** seçeneği açıktır. Varsa, kodu kullanan <xref:Microsoft.Office.Interop.Word.Selection.Collapse%2A> seçimi metnin seçili bloğunun başlangıcında bir ekleme noktası daraltmak için seçimin yöntemi. Metin ve bir paragraf işareti ekleyin.  
  
     [!code-vb[Trin_VstcoreWordAutomation#60](../vsto/codesnippet/VisualBasic/Trin_VstcoreWordAutomationVB/ThisDocument.vb#60)]
     [!code-csharp[Trin_VstcoreWordAutomation#60](../vsto/codesnippet/CSharp/Trin_VstcoreWordAutomationCS/ThisDocument.cs#60)]  
  
5.  Seçimi bir ekleme noktası veya seçili metni sonra kod bloğunu değilse **Else** blok hiçbir şey yapmaz.  
  
     [!code-vb[Trin_VstcoreWordAutomation#61](../vsto/codesnippet/VisualBasic/Trin_VstcoreWordAutomationVB/ThisDocument.vb#61)]
     [!code-csharp[Trin_VstcoreWordAutomation#61](../vsto/codesnippet/CSharp/Trin_VstcoreWordAutomationCS/ThisDocument.cs#61)]  
  
 Aynı zamanda <xref:Microsoft.Office.Interop.Word.Selection.TypeBackspace%2A> yöntemi <xref:Microsoft.Office.Interop.Word.Selection> işlevselliğini taklit eder nesne **geri** klavyenizde anahtar. Ancak, geldiğinde ekleme ve bir metin değiştirmeye <xref:Microsoft.Office.Interop.Word.Range> nesnesi daha fazla denetim sunar.  
  
 Aşağıdaki örnek eksiksiz kodu gösterir. Bu örneği kullanmak için kodu çalıştırın `ThisDocument` veya `ThisAddIn` projenizdeki sınıfı.  
  
 [!code-vb[Trin_VstcoreWordAutomation#56](../vsto/codesnippet/VisualBasic/Trin_VstcoreWordAutomationVB/ThisDocument.vb#56)]
 [!code-csharp[Trin_VstcoreWordAutomation#56](../vsto/codesnippet/CSharp/Trin_VstcoreWordAutomationCS/ThisDocument.cs#56)]  
  
## <a name="see-also"></a>Ayrıca bkz.  
 [Nasıl yapılır: program aracılığıyla, belgelerdeki metni biçimlendirme](../vsto/how-to-programmatically-format-text-in-documents.md)   
 [Nasıl yapılır: program aracılığıyla tanımlama ve belgelerde aralıkları seçin](../vsto/how-to-programmatically-define-and-select-ranges-in-documents.md)   
 [Nasıl yapılır: belgelerde aralıkları program aracılığıyla genişletme](../vsto/how-to-programmatically-extend-ranges-in-documents.md)  
  
  