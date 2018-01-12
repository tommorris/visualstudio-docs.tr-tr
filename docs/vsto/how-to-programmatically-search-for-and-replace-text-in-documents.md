---
title: "Nasıl yapılır: program aracılığıyla arama ve belgelerdeki metni değiştirme | Microsoft Docs"
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
- documents [Office development in Visual Studio], searching
- text searches, replacing text
- text searches, documents
- text [Office development in Visual Studio], searching in documents
- text [Office development in Visual Studio], text searches
author: TerryGLee
ms.author: tglee
manager: ghogen
ms.workload: office
ms.openlocfilehash: 658da08ee7d61651b02d7d42158637dad7ab16c4
ms.sourcegitcommit: f9fbf1f55f9ac14e4e5c6ae58c30dc1800ca6cda
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/10/2018
---
# <a name="how-to-programmatically-search-for-and-replace-text--in-documents"></a>Nasıl yapılır: Belgelerde Program Aracılığıyla Metin Arama ve Değiştirme
  <xref:Microsoft.Office.Interop.Word.Find> Nesne her ikisi de üyesi olduğu <xref:Microsoft.Office.Interop.Word.Selection> ve <xref:Microsoft.Office.Interop.Word.Range> nesneleri ve bunlardan birini Microsoft Office Word belgelerinde metin aramak için kullanabilirsiniz. Değiştir komutu, Bul komutu uzantısıdır.  
  
 Kullanan bir <xref:Microsoft.Office.Interop.Word.Find> Microsoft Office Word belgesine ve belirli bir metin, biçimlendirme ve stil Ara döngü nesnesine ve kullanmak <xref:Microsoft.Office.Interop.Word.Find.Replacement%2A> bulunan öğelerden herhangi birini değiştirmek için özellik.  
  
 [!INCLUDE[appliesto_wdalldocapp](../vsto/includes/appliesto-wdalldocapp-md.md)]  
  
## <a name="using-a-selection-object"></a>Seçim nesnesi kullanma  
 Kullandığınızda, bir <xref:Microsoft.Office.Interop.Word.Selection> metin seçili metin, belirttiğiniz ölçütlere yalnızca karşı uygulanır arama şu anda bulunacak nesne. Varsa <xref:Microsoft.Office.Interop.Word.Selection> belge aranır bir ekleme noktası olduğundan. Arama ölçütleriyle eşleşen öğe bulundu, otomatik olarak seçilir.  
  
 Bu dikkate almak önemlidir <xref:Microsoft.Office.Interop.Word.Find> ölçütlerdir toplu, yani kriterler önceki arama ölçütlerini eklenir. Önceki aramalardan kullanarak biçimlendirmeyi Temizle <xref:Microsoft.Office.Interop.Word.Find.ClearFormatting%2A> arama önce yöntemi.  
  
#### <a name="to-find-text-using-a-selection-object"></a>Seçim nesnesi kullanarak metin bulmak için  
  
1.  Bir arama dizesi bir değişkene atayın.  
  
     [!code-vb[Trin_VstcoreWordAutomation#68](../vsto/codesnippet/VisualBasic/Trin_VstcoreWordAutomationVB/ThisDocument.vb#68)]
     [!code-csharp[Trin_VstcoreWordAutomation#68](../vsto/codesnippet/CSharp/Trin_VstcoreWordAutomationCS/ThisDocument.cs#68)]  
  
2.  Önceki aramalardan Biçimlendirmeyi Temizle.  
  
     [!code-vb[Trin_VstcoreWordAutomation#69](../vsto/codesnippet/VisualBasic/Trin_VstcoreWordAutomationVB/ThisDocument.vb#69)]
     [!code-csharp[Trin_VstcoreWordAutomation#69](../vsto/codesnippet/CSharp/Trin_VstcoreWordAutomationCS/ThisDocument.cs#69)]  
  
3.  Aramayı yürütün ve sonuçlarını içeren bir ileti kutusu görüntüler.  
  
     [!code-vb[Trin_VstcoreWordAutomation#70](../vsto/codesnippet/VisualBasic/Trin_VstcoreWordAutomationVB/ThisDocument.vb#70)]
     [!code-csharp[Trin_VstcoreWordAutomation#70](../vsto/codesnippet/CSharp/Trin_VstcoreWordAutomationCS/ThisDocument.cs#70)]  
  
 Aşağıdaki örnek tam yöntemini gösterir.  
  
 [!code-vb[Trin_VstcoreWordAutomation#67](../vsto/codesnippet/VisualBasic/Trin_VstcoreWordAutomationVB/ThisDocument.vb#67)]
 [!code-csharp[Trin_VstcoreWordAutomation#67](../vsto/codesnippet/CSharp/Trin_VstcoreWordAutomationCS/ThisDocument.cs#67)]  
  
## <a name="using-a-range-object"></a>Range nesnesi kullanma  
 Kullanarak bir <xref:Microsoft.Office.Interop.Word.Range> nesne hiçbir şey kullanıcı arabirimini görüntülemeden metin aramanıza olanak sağlar. <xref:Microsoft.Office.Interop.Word.Find> Nesnesi döndürür **True** arama ölçütleriyle eşleşen metin bulunursa ve **False** mevcut değilse. Aynı zamanda yeniden tanımlamaktadır <xref:Microsoft.Office.Interop.Word.Range> metin bulunursa arama ölçütleriyle eşleşen nesne.  
  
#### <a name="to-find-text-using-a-range-object"></a>Aralık nesnesi kullanarak metin bulmak için  
  
1.  Tanımlayan bir <xref:Microsoft.Office.Interop.Word.Range> belgedeki ikinci paragrafı içeren nesne.  
  
     Aşağıdaki kod örneği bir belge düzeyi özelleştirmelerinde kullanılabilir.  
  
     [!code-vb[Trin_VstcoreWordAutomation#72](../vsto/codesnippet/VisualBasic/Trin_VstcoreWordAutomationVB/ThisDocument.vb#72)]
     [!code-csharp[Trin_VstcoreWordAutomation#72](../vsto/codesnippet/CSharp/Trin_VstcoreWordAutomationCS/ThisDocument.cs#72)]  
  
     Aşağıdaki kod örneğinde, VSTO eklenti içinde kullanılabilir. Bu örnek etkin belgeyi kullanır.  
  
     [!code-vb[Trin_VstcoreWordAutomationAddIn#72](../vsto/codesnippet/VisualBasic/Trin_VstcoreWordAutomationAddIn/ThisAddIn.vb#72)]
     [!code-csharp[Trin_VstcoreWordAutomationAddIn#72](../vsto/codesnippet/CSharp/Trin_VstcoreWordAutomationAddIn/ThisAddIn.cs#72)]  
  
2.  Kullanarak <xref:Microsoft.Office.Interop.Word.Range.Find%2A> özelliği <xref:Microsoft.Office.Interop.Word.Range> nesnesi, önce varolan herhangi biçimlendirme seçeneklerini temizleyin ve ardından üstteki arama **find me**.  
  
     [!code-vb[Trin_VstcoreWordAutomation#73](../vsto/codesnippet/VisualBasic/Trin_VstcoreWordAutomationVB/ThisDocument.vb#73)]
     [!code-csharp[Trin_VstcoreWordAutomation#73](../vsto/codesnippet/CSharp/Trin_VstcoreWordAutomationCS/ThisDocument.cs#73)]  
  
3.  İleti kutusu içinde arama sonuçlarını görüntülemek ve seçmek <xref:Microsoft.Office.Interop.Word.Range> görünür hale getirmek için.  
  
     [!code-vb[Trin_VstcoreWordAutomation#74](../vsto/codesnippet/VisualBasic/Trin_VstcoreWordAutomationVB/ThisDocument.vb#74)]
     [!code-csharp[Trin_VstcoreWordAutomation#74](../vsto/codesnippet/CSharp/Trin_VstcoreWordAutomationCS/ThisDocument.cs#74)]  
  
     Arama başarısız olursa, ikinci paragraf seçilir; başarılı olursa, arama ölçütlerini görüntülenir.  
  
 Aşağıdaki örnek bir belge düzeyi özelleştirme için tam kod gösterir. Bu örneği kullanmak için kodu çalıştırın `ThisDocument` projenizdeki sınıfı.  
  
 [!code-vb[Trin_VstcoreWordAutomation#71](../vsto/codesnippet/VisualBasic/Trin_VstcoreWordAutomationVB/ThisDocument.vb#71)]
 [!code-csharp[Trin_VstcoreWordAutomation#71](../vsto/codesnippet/CSharp/Trin_VstcoreWordAutomationCS/ThisDocument.cs#71)]  
  
 Aşağıdaki örnek, VSTO eklenti için tam kod gösterilir. Bu örneği kullanmak için kodu çalıştırın `ThisAddIn` projenizdeki sınıfı.  
  
 [!code-vb[Trin_VstcoreWordAutomationAddIn#71](../vsto/codesnippet/VisualBasic/Trin_VstcoreWordAutomationAddIn/ThisAddIn.vb#71)]
 [!code-csharp[Trin_VstcoreWordAutomationAddIn#71](../vsto/codesnippet/CSharp/Trin_VstcoreWordAutomationAddIn/ThisAddIn.cs#71)]  
  
## <a name="searching-for-and-replacing-text-in-documents"></a>Arama ve belgelerdeki metni değiştirme  
 Aşağıdaki kod geçerli seçim arar ve tüm dize oluşumlarını değiştirir **find me** dizesi ile **bulunan**.  
  
#### <a name="to-search-for-and-replace-text-in-documents"></a>Belgelerde metin için arama ve değiştirme için  
  
1.  Aşağıdaki örnek kod ekleme `ThisDocument` veya `ThisAddIn` projenizdeki sınıfı.  
  
     [!code-vb[Trin_VstcoreWordAutomation#75](../vsto/codesnippet/VisualBasic/Trin_VstcoreWordAutomationVB/ThisDocument.vb#75)]
     [!code-csharp[Trin_VstcoreWordAutomation#75](../vsto/codesnippet/CSharp/Trin_VstcoreWordAutomationCS/ThisDocument.cs#75)]  
  
     <xref:Microsoft.Office.Interop.Word.Find> Sınıfına sahip bir <xref:Microsoft.Office.Interop.Word.Find.ClearFormatting%2A> yöntemi ve <xref:Microsoft.Office.Interop.Word.Replacement> sınıfı ayrıca sahip kendi <xref:Microsoft.Office.Interop.Word.Replacement.ClearFormatting%2A> yöntemi. Bulma ve değiştirme işlemlerini gerçekleştirirken her iki nesnenin ClearFormatting yöntemini kullanmanız gerekir. Yalnızca kullanırsanız <xref:Microsoft.Office.Interop.Word.Find> nesne değiştirme metninde beklenmedik sonuçlar alabilirsiniz.  
  
2.  Kullanım <xref:Microsoft.Office.Interop.Word.Find.Execute%2A> yöntemi <xref:Microsoft.Office.Interop.Word.Find> bulunan her öğenin değiştirmek için nesne. Hangi öğelerin değişeceğini belirtmek için kullanın *Değiştir* parametresi. Bu parametre şunlardan biri olabilir <xref:Microsoft.Office.Interop.Word.WdReplace> değerler:  
  
    -   <xref:Microsoft.Office.Interop.Word.WdReplace.wdReplaceAll>tüm öğeleri değiştirir.  
  
    -   <xref:Microsoft.Office.Interop.Word.WdReplace.wdReplaceNone>bulunan öğelerin hiçbiri yerini alır.  
  
    -   <xref:Microsoft.Office.Interop.Word.WdReplace.wdReplaceOne>bulunan ilk öğeyi değiştirir.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Nasıl yapılır: program aracılığıyla arama seçeneklerini ayarlama Word'de](../vsto/how-to-programmatically-set-search-options-in-word.md)   
 [Nasıl yapılır: program aracılığıyla bulunan öğeler arasında döngü](../vsto/how-to-programmatically-loop-through-found-items-in-documents.md)   
 [Nasıl yapılır: program aracılığıyla tanımlama ve belgelerde aralıkları seçin](../vsto/how-to-programmatically-define-and-select-ranges-in-documents.md)   
 [Nasıl yapılır: program aracılığıyla aramalardan sonra seçimleri geri yükleme](../vsto/how-to-programmatically-restore-selections-after-searches.md)   
 [Office Çözümlerinde İsteğe Bağlı Parametreler](../vsto/optional-parameters-in-office-solutions.md)  
  