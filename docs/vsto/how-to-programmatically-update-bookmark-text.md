---
title: "Nasıl yapılır: program aracılığıyla, yer işareti metnini güncelleştirme | Microsoft Docs"
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
- bookmarks, updating text
- text [Office development in Visual Studio], updating in bookmarks
- Bookmark control, updating contents
ms.assetid: 2324164d-2538-4695-9aaf-7285ce403be3
caps.latest.revision: "46"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: ee78ad2aac4ff9cefcb3291d3b1b2010d8a1c26c
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2017
---
# <a name="how-to-programmatically-update-bookmark-text"></a>Nasıl yapılır: Yer İşareti Metnini Program Aracılığıyla Güncelleştirme
  Sonraki bir zamanda veya bir yer işareti metinde değiştirmek için metin alabilmeleri Microsoft Office Word belgesinde yer tutucu yer işareti içine metin ekleyebilirsiniz. Belge düzeyi özelleştirme geliştiriyorsanız metinde da güncelleştirebilirsiniz bir <xref:Microsoft.Office.Tools.Word.Bookmark> veriye bağlı denetim. Daha fazla bilgi için bkz: [Office çözümlerinde denetimlere veri bağlama](../vsto/binding-data-to-controls-in-office-solutions.md).  
  
 [!INCLUDE[appliesto_wdalldocapp](../vsto/includes/appliesto-wdalldocapp-md.md)]  
  
 Yer işareti nesnesi iki türden biri olabilir:  
  
-   A <xref:Microsoft.Office.Tools.Word.Bookmark> konak kontrolü.  
  
     <xref:Microsoft.Office.Tools.Word.Bookmark>denetimleri uzatma yerel <xref:Microsoft.Office.Interop.Word.Bookmark> verileri bağlama ve olayları açığa etkinleştirerek nesneleri. Konak denetimleri hakkında daha fazla bilgi için bkz: [konak öğelerine ve denetimlerine genel bakış](../vsto/host-items-and-host-controls-overview.md).  
  
-   Yerel bir <xref:Microsoft.Office.Interop.Word.Bookmark> nesnesi.  
  
     <xref:Microsoft.Office.Interop.Word.Bookmark>nesneleri olayları ya da veri bağlama özellikleri yok.  
  
 Bir yer işaretine metin atadığınızda, davranışı arasında farklı bir <xref:Microsoft.Office.Interop.Word.Bookmark> ve <xref:Microsoft.Office.Tools.Word.Bookmark>. Daha fazla bilgi için bkz: [yer işareti denetimi](../vsto/bookmark-control.md).  
  
## <a name="using-host-controls"></a>Konak denetimleri kullanma  
  
#### <a name="to-update-bookmark-contents-using-a-bookmark-control"></a>Bir yer işareti denetimi kullanma yer işareti içeriği güncelleştirmek için  
  
1.  İsteyen bir yordamı oluşturmak bir `bookmark` işaretinin adı bağımsız değişkeni ve `newText` atamak dize bağımsız değişkeni <xref:Microsoft.Office.Tools.Word.Bookmark.Text%2A> özelliği.  
  
    > [!NOTE]  
    >  Metne atama <xref:Microsoft.Office.Tools.Word.Bookmark.Text%2A> veya <xref:Microsoft.Office.Tools.Word.Bookmark.FormattedText%2A> özelliği bir <xref:Microsoft.Office.Tools.Word.Bookmark> denetim silinecek yer işareti neden olmaz.  
  
     [!code-vb[Trin_VstcoreWordAutomation#63](../vsto/codesnippet/VisualBasic/Trin_VstcoreWordAutomationVB/ThisDocument.vb#63)]
     [!code-csharp[Trin_VstcoreWordAutomation#63](../vsto/codesnippet/CSharp/Trin_VstcoreWordAutomationCS/ThisDocument.cs#63)]  
  
2.  Ata *newText* dizesinden <xref:Microsoft.Office.Tools.Word.Bookmark.Text%2A> özelliği <xref:Microsoft.Office.Tools.Word.Bookmark>.  
  
     [!code-vb[Trin_VstcoreWordAutomation#64](../vsto/codesnippet/VisualBasic/Trin_VstcoreWordAutomationVB/ThisDocument.vb#64)]
     [!code-csharp[Trin_VstcoreWordAutomation#64](../vsto/codesnippet/CSharp/Trin_VstcoreWordAutomationCS/ThisDocument.cs#64)]  
  
## <a name="using-word-objects"></a>Word nesnelerini kullanma  
  
#### <a name="to-update-bookmark-contents-using-a-word-bookmark-object"></a>Yer işareti içeriğini bir Word Bookmark nesnesi kullanarak güncelleştirmek için  
  
1.  Sahip bir yordam oluşturma bir `bookmark` adı bağımsız değişkeni <xref:Microsoft.Office.Interop.Word.Bookmark>ve bir `newText` atamak dize bağımsız değişkeni <xref:Microsoft.Office.Interop.Word.Range.Text%2A> yer işaretinin özelliği.  
  
    > [!NOTE]  
    >  Yerel bir Word metin atama <xref:Microsoft.Office.Interop.Word.Bookmark> nesne silinecek yer işareti neden olur.  
  
     [!code-vb[Trin_VstcoreWordAutomation#65](../vsto/codesnippet/VisualBasic/Trin_VstcoreWordAutomationVB/ThisDocument.vb#65)]
     [!code-csharp[Trin_VstcoreWordAutomation#65](../vsto/codesnippet/CSharp/Trin_VstcoreWordAutomationCS/ThisDocument.cs#65)]  
  
2.  Ata *newText* dizesinden <xref:Microsoft.Office.Interop.Word.Range.Text%2A> yer işaretinin otomatik olarak siler işaretinin özelliği. Yer işaretine yeniden ekleyin <xref:Microsoft.Office.Interop.Word.Bookmarks> koleksiyonu.  
  
     Aşağıdaki kod örneği bir belge düzeyi özelleştirmelerinde kullanılabilir.  
  
     [!code-vb[Trin_VstcoreWordAutomation#66](../vsto/codesnippet/VisualBasic/Trin_VstcoreWordAutomationVB/ThisDocument.vb#66)]
     [!code-csharp[Trin_VstcoreWordAutomation#66](../vsto/codesnippet/CSharp/Trin_VstcoreWordAutomationCS/ThisDocument.cs#66)]  
  
     Aşağıdaki kod örneğinde, VSTO eklenti içinde kullanılabilir. Bu örnek etkin belgeyi kullanır.  
  
     [!code-vb[Trin_VstcoreWordAutomationAddIn#66](../vsto/codesnippet/VisualBasic/Trin_VstcoreWordAutomationAddIn/ThisAddIn.vb#66)]
     [!code-csharp[Trin_VstcoreWordAutomationAddIn#66](../vsto/codesnippet/CSharp/Trin_VstcoreWordAutomationAddIn/ThisAddIn.cs#66)]  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Nasıl yapılır: Word belgelerine program aracılığıyla metin ekleme](../vsto/how-to-programmatically-insert-text-into-word-documents.md)   
 [Word nesne modeline genel bakış](../vsto/word-object-model-overview.md)   
 [Yer işareti denetimi](../vsto/bookmark-control.md)  
  
  