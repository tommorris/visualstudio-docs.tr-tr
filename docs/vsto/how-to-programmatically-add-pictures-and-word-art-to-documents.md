---
title: "Nasıl yapılır: program aracılığıyla resim ekleyin ve Word Art belgeleri | Microsoft Docs"
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
- documents [Office development in Visual Studio], adding pictures
- Word documents, adding pictures
- Word documents, adding Word Art
- graphics, adding to Word documents
- WordArt, adding to documents
ms.assetid: 944e1858-bc7c-471f-b5e7-adf3b0fa574d
caps.latest.revision: "24"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: a30c865a1bee9f3e8a75d5362688f1a83baba02a
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2017
---
# <a name="how-to-programmatically-add-pictures-and-word-art-to-documents"></a>Nasıl yapılır: Belgelere Program Aracılığıyla Resim ve Word Art Ekleme
  Tasarım zamanında veya çalışma zamanında belgelere resimler ve çizim nesneleri ekleyebilirsiniz. WordArt, Microsoft Office Word belgelerine dekoratif metin eklemenize olanak tanır. Bu özel metin efektleri çizim özelleştirebilir ve belgenize eklemek nesneleridir.  
  
 [!INCLUDE[appliesto_wdalldocapp](../vsto/includes/appliesto-wdalldocapp-md.md)]  
  
## <a name="adding-a-picture-at-design-time"></a>Tasarım zamanında bir resim ekleme  
 Belge düzeyi özelleştirme geliştiriyorsanız, tasarım zamanında belgeye resim ekleyebilirsiniz.  
  
#### <a name="to-add-a-picture-to-a-word-document-at-design-time"></a>Tasarım zamanında bir Word belgesi için bir resim eklemek için  
  
1.  İmlecinizi resmi belgede eklemek istediğiniz yere yerleştirin.  
  
2.  Tıklatın **Ekle** Şerit sekmesi.  
  
3.  İçinde **çizimler** grubunda **resim**.  
  
4.  İçinde **resim** iletişim kutusunda, eklemek istediğiniz resme gidin ve tıklayın **Ekle**.  
  
     Resim belgenizi geçerli imleç konumu eklenir.  
  
## <a name="adding-a-picture-at-run-time"></a>Çalışma zamanında bir resim ekleme  
 Geçerli imleç konumundaki belgeye resim ekleyebilirsiniz.  
  
#### <a name="to-add-a-picture-at-the-cursor-location"></a>İmleç konumuna resim eklemek için  
  
1.  Çağrı <xref:Microsoft.Office.Interop.Word.InlineShapes.AddPicture%2A> yöntemi <xref:Microsoft.Office.Interop.Word.InlineShapes> koleksiyonu ve dosya adına geçirin.  
  
     [!code-vb[Trin_VstcoreWordAutomation#108](../vsto/codesnippet/VisualBasic/Trin_VstcoreWordAutomationVB/ThisDocument.vb#108)]
     [!code-csharp[Trin_VstcoreWordAutomation#108](../vsto/codesnippet/CSharp/Trin_VstcoreWordAutomationCS/ThisDocument.cs#108)]  
  
## <a name="adding-wordart-at-design-time"></a>Tasarım zamanında WordArt ekleme  
 Belge düzeyi özelleştirme geliştiriyorsanız, tasarım zamanında belgeye WordArt ekleyebilirsiniz.  
  
#### <a name="to-add-wordart-to-a-word-document-at-design-time"></a>Tasarım zamanında bir Word belgesi WordArt eklemek için  
  
1.  İmlecinizi WordArt belgede eklemek istediğiniz yere yerleştirin.  
  
2.  Tıklatın **Ekle** Şerit sekmesi.  
  
3.  İçinde **metin** grubunda **WordArt**ve ardından bir WordArt stili seçin.  
  
4.  Belgede görünmesini istediğiniz metni ekleyin **WordArt Metnini Düzenle** iletişim kutusu ve tıklatın **Tamam**.  
  
     Metin belgenize Seçili WordArt stili ile eklenir.  
  
## <a name="adding-wordart-at-run-time"></a>Çalışma zamanında WordArt ekleme  
 Geçerli imleç konumundaki belgeye WordArt ekleyebilirsiniz. Belge düzeyi özelleştirmeleri ve VSTO eklentileri için farklı bir yordamdır.  
  
#### <a name="to-add-wordart-at-the-cursor-location-in-a-document-level-customization"></a>Belge düzeyi özelleştirmelerinde İmleç konumuna WordArt eklemek için  
  
1.  Geçerli imleç konumu sol ve üst konumunu alın.  
  
     [!code-vb[Trin_VstcoreWordAutomation#109](../vsto/codesnippet/VisualBasic/Trin_VstcoreWordAutomationVB/ThisDocument.vb#109)]
     [!code-csharp[Trin_VstcoreWordAutomation#109](../vsto/codesnippet/CSharp/Trin_VstcoreWordAutomationCS/ThisDocument.cs#109)]  
  
2.  Çağrı <xref:Microsoft.Office.Interop.Word.Shapes.AddTextEffect%2A> yöntemi <xref:Microsoft.Office.Interop.Word.Shapes> belgedeki nesne.  
  
     [!code-vb[Trin_VstcoreWordAutomation#110](../vsto/codesnippet/VisualBasic/Trin_VstcoreWordAutomationVB/ThisDocument.vb#110)]
     [!code-csharp[Trin_VstcoreWordAutomation#110](../vsto/codesnippet/CSharp/Trin_VstcoreWordAutomationCS/ThisDocument.cs#110)]  
  
#### <a name="to-add-wordart-at-the-cursor-location-in-a-vsto-add-in"></a>Bir VSTO eklentisi imleç konumu WordArt eklemek için  
  
1.  Geçerli imleç konumu sol ve üst konumunu alın.  
  
     [!code-vb[Trin_VstcoreWordAutomationAddIn#109](../vsto/codesnippet/VisualBasic/Trin_VstcoreWordAutomationAddIn/ThisAddIn.vb#109)]
     [!code-csharp[Trin_VstcoreWordAutomationAddIn#109](../vsto/codesnippet/CSharp/Trin_VstcoreWordAutomationAddIn/ThisAddIn.cs#109)]  
  
2.  Çağrı <xref:Microsoft.Office.Interop.Word.Shapes.AddTextEffect%2A> yöntemi <xref:Microsoft.Office.Interop.Word.Shapes> nesne etkin belge (veya belirttiğiniz farklı bir belge).  
  
     [!code-vb[Trin_VstcoreWordAutomationAddIn#110](../vsto/codesnippet/VisualBasic/Trin_VstcoreWordAutomationAddIn/ThisAddIn.vb#110)]
     [!code-csharp[Trin_VstcoreWordAutomationAddIn#110](../vsto/codesnippet/CSharp/Trin_VstcoreWordAutomationAddIn/ThisAddIn.cs#110)]  
  
## <a name="compiling-the-code"></a>Kod Derleniyor  
  
-   Adlı bir resim **SamplePicture.jpg** c sürücüsünde bulunan mevcut olması gerekir  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Nasıl yapılır: varolan belgeleri program aracılığıyla açma](../vsto/how-to-programmatically-open-existing-documents.md)   
 [Nasıl yapılır: Word belgelerine program aracılığıyla metin ekleme](../vsto/how-to-programmatically-insert-text-into-word-documents.md)   
 [Nasıl yapılır: program aracılığıyla aramalardan sonra seçimleri geri yükleme](../vsto/how-to-programmatically-restore-selections-after-searches.md)   
 [Nasıl yapılır: program aracılığıyla belgeleri kaydetme](../vsto/how-to-programmatically-save-documents.md)   
 [Office çözümlerinde isteğe bağlı parametreler](../vsto/optional-parameters-in-office-solutions.md)  
  
  