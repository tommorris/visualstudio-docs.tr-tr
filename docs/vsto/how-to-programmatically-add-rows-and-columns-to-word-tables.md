---
title: 'Nasıl yapılır: program aracılığıyla Word tablolarına satır ve sütun ekleme | Microsoft Docs'
ms.custom: ''
ms.date: 02/02/2017
ms.technology:
- office-development
ms.topic: conceptual
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- rows [Office development in Visual Studio], adding to Word tables
- tables [Office development in Visual Studio], adding rows and columns
- columns [Office development in Visual Studio], adding to Word tables
author: TerryGLee
ms.author: tglee
manager: douge
ms.workload:
- office
ms.openlocfilehash: 5058665c0c6d882e41d534d51a398ae90e0e03e6
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/16/2018
---
# <a name="how-to-programmatically-add-rows-and-columns-to-word-tables"></a>Nasıl yapılır: Word Tablolarına Program Aracılığıyla Satır ve Sütun Ekleme
  Bir Microsoft Office Word tablo hücreleri satırlar ve sütunlar halinde düzenlenir. Kullanabileceğiniz <xref:Microsoft.Office.Interop.Word.Rows.Add%2A> yöntemi <xref:Microsoft.Office.Interop.Word.Rows> tabloya satır eklemek için nesne ve <xref:Microsoft.Office.Interop.Word.Columns.Add%2A> yöntemi <xref:Microsoft.Office.Interop.Word.Columns> sütunlar eklenecek nesne.  
  
 [!INCLUDE[appliesto_wdalldocapp](../vsto/includes/appliesto-wdalldocapp-md.md)]  
  
## <a name="document-level-customization-examples"></a>Belge düzeyi özelleştirme örnekleri  
 Aşağıdaki kod örnekleri, bir belge düzeyi özelleştirmelerinde kullanılabilir. Bu örnekleri kullanmak için bunları çalıştırmak `ThisDocument` projenizdeki sınıfı. Bu örnekler özelleştirme ile zaten ilişkili belgenin en az bir tablo içerdiğini varsayar.  
  
> [!IMPORTANT]  
>  Bu kod, aşağıdaki proje şablonlarını kullanarak oluşturduğunuz projelerine çalıştırır:  
>   
>  -   Word 2013 belge  
> -   Word 2013 şablonu  
> -   Word 2010 Belgesi  
> -   Word 2010 Şablonu  
>   
>  Diğer bir proje türünde bu görevi gerçekleştirmek istiyorsanız, bir başvuru eklemeniz gerekir **Microsoft.Office.Interop.Word** derleme ve ardından gerekir bu derleme sınıflardan satırları ve sütunları tablolara eklemek için kullanın. Daha fazla bilgi için bkz: [nasıl yapılır: hedef Office uygulamaları aracılığıyla birincil birlikte çalışma derlemeleri](../vsto/how-to-target-office-applications-through-primary-interop-assemblies.md) ve [Word 2010 birincil birlikte çalışma derleme başvurusu](http://go.microsoft.com/fwlink/?LinkId=189588).  
  
#### <a name="to-add-a-row-to-a-table"></a>Tabloya satır eklemek için  
  
1.  Kullanım <xref:Microsoft.Office.Interop.Word.Rows.Add%2A> tabloya satır eklemek için yöntem.  
  
     [!code-vb[Trin_VstcoreWordAutomation#95](../vsto/codesnippet/VisualBasic/Trin_VstcoreWordAutomationVB/ThisDocument.vb#95)]
     [!code-csharp[Trin_VstcoreWordAutomation#95](../vsto/codesnippet/CSharp/Trin_VstcoreWordAutomationCS/ThisDocument.cs#95)]  
  
#### <a name="to-add-a-column-to-a-table"></a>Bir tabloya bir sütun eklemek için  
  
1.  Kullanmak <xref:Microsoft.Office.Interop.Word.Columns.Add%2A> yöntemi ve ardından <xref:Microsoft.Office.Interop.Word.Columns.DistributeWidth%2A> tüm sütunları aynı genişlikte yapmak için yöntem.  
  
     [!code-vb[Trin_VstcoreWordAutomation#96](../vsto/codesnippet/VisualBasic/Trin_VstcoreWordAutomationVB/ThisDocument.vb#96)]
     [!code-csharp[Trin_VstcoreWordAutomation#96](../vsto/codesnippet/CSharp/Trin_VstcoreWordAutomationCS/ThisDocument.cs#96)]  
  
## <a name="vsto-add-in-examples"></a>VSTO eklentileri örnekleri  
 Aşağıdaki kod örnekleri, VSTO eklenti içinde kullanılabilir. Örnekleri kullanmak için bunları çalıştırmak `ThisAddIn` projenizdeki sınıfı. Bu örnekler etkin belgeyi en az bir tablo zaten sahip olduğunu varsayın.  
  
> [!IMPORTANT]  
>  Word VSTO eklentisi şablonları kullanarak oluşturduğunuz projelerde bu kodu çalıştırır.  
>   
>  Diğer bir proje türünde bu görevi gerçekleştirmek istiyorsanız, bir başvuru eklemeniz gerekir **Microsoft.Office.Interop.Word** derleme ve ardından gerekir bu derleme sınıflardan satırları ve sütunları tablolara eklemek için kullanın. Daha fazla bilgi için bkz: [nasıl yapılır: hedef Office uygulamaları aracılığıyla birincil birlikte çalışma derlemeleri](../vsto/how-to-target-office-applications-through-primary-interop-assemblies.md) ve [Word 2010 birincil birlikte çalışma derleme başvurusu](http://go.microsoft.com/fwlink/?LinkId=189588).  
  
#### <a name="to-add-a-row-to-a-table"></a>Tabloya satır eklemek için  
  
1.  Kullanım <xref:Microsoft.Office.Interop.Word.Rows.Add%2A> tabloya satır eklemek için yöntem.  
  
     [!code-vb[Trin_VstcoreWordAutomationAddIn#95](../vsto/codesnippet/VisualBasic/Trin_VstcoreWordAutomationAddIn/ThisAddIn.vb#95)]
     [!code-csharp[Trin_VstcoreWordAutomationAddIn#95](../vsto/codesnippet/CSharp/Trin_VstcoreWordAutomationAddIn/ThisAddIn.cs#95)]  
  
#### <a name="to-add-a-column-to-a-table"></a>Bir tabloya bir sütun eklemek için  
  
1.  Kullanmak <xref:Microsoft.Office.Interop.Word.Columns.Add%2A> yöntemi ve ardından <xref:Microsoft.Office.Interop.Word.Columns.DistributeWidth%2A> tüm sütunları aynı genişlikte yapmak için yöntem.  
  
     [!code-vb[Trin_VstcoreWordAutomationAddIn#96](../vsto/codesnippet/VisualBasic/Trin_VstcoreWordAutomationAddIn/ThisAddIn.vb#96)]
     [!code-csharp[Trin_VstcoreWordAutomationAddIn#96](../vsto/codesnippet/CSharp/Trin_VstcoreWordAutomationAddIn/ThisAddIn.cs#96)]  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Nasıl yapılır: program aracılığıyla Word tabloları oluşturma](../vsto/how-to-programmatically-create-word-tables.md)   
 [Nasıl yapılır: program aracılığıyla metin ve Word tablolarında hücrelere biçimlendirme ekleme](../vsto/how-to-programmatically-add-text-and-formatting-to-cells-in-word-tables.md)   
 [Nasıl yapılır: Belge Özellikleriyle Word Tablolarını Program Aracılığıyla Doldurma](../vsto/how-to-programmatically-populate-word-tables-with-document-properties.md)  
  
  