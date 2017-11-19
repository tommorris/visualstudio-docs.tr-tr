---
title: "Nasıl yapılır: Okuma ve yazma belge özelliklerinden | Microsoft Docs"
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
- Word [Office development in Visual Studio], document properties
- documents [Office development in Visual Studio], properties
- document properties [Office development in Visual Studio]
- Excel [Office development in Visual Studio], document properties
ms.assetid: e9ef9fa3-36b9-48fb-8148-f5152463c03c
caps.latest.revision: "54"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: ca687f9482d65621ad848c2ca6459c6fe782f8ba
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2017
---
# <a name="how-to-read-from-and-write-to-document-properties"></a>Nasıl Yapılır: Belge Özelliklerinden Okuma ve Yazma
  Belge özellikleri belge birlikte depolayabilirsiniz. Office uygulamaları bir dizi yazar, başlık ve konu gibi yerleşik özellikleri sağlar. Bu konu, Microsoft Office Excel ve Microsoft Office Word belgesi özelliklerini ayarlamak gösterilmiştir.  
  
 ![video bağlantı](../vsto/media/playvideo.gif "video bağlantı") ilgili video gösterimi için bkz: [I: erişimi nasıl yapın ve Microsoft Word özel belge özelliklerini işlemek?](http://go.microsoft.com/fwlink/?LinkId=136772).  
  
 [!INCLUDE[appliesto_docprops](../vsto/includes/appliesto-docprops-md.md)]  
  
## <a name="setting-document-properties-in-excel"></a>Excel'de belge özelliklerini ayarlama  
 Excel yerleşik özellikleriyle çalışmak için aşağıdaki özellikleri kullanın:  
  
-   Bir belge düzeyi projede kullanma <xref:Microsoft.Office.Tools.Excel.Workbook.BuiltinDocumentProperties%2A> özelliği `ThisWorkbook` sınıfı.  
  
-   Bir VSTO eklenti projesinde kullanmak <xref:Microsoft.Office.Interop.Excel._Workbook.BuiltinDocumentProperties%2A> özelliği bir <xref:Microsoft.Office.Interop.Excel.Workbook> nesnesi.  
  
 Bu özellikler bir <xref:Microsoft.Office.Core.DocumentProperties> bir nesne, <xref:Microsoft.Office.Core.DocumentProperty> nesneleri. Kullanabileceğiniz `Item` belirli bir özellik adı veya dizin koleksiyonundaki göre almak için koleksiyonun özelliği.  
  
 Aşağıdaki kod örneği, yerleşik değiştirileceği gösterilmektedir **numarasıyla** belge düzeyi projede özelliği.  
  
#### <a name="to-change-the-revision-number-property-in-excel"></a>Excel'de düzeltme numarası özelliğini değiştirmek için  
  
1.  Yerleşik belge özelliklerini bir değişkene atayın.  
  
     [!code-vb[Trin_VstcoreProgramming#7](../vsto/codesnippet/VisualBasic/Trin_VstcoreProgrammingExcelVB/ThisWorkbook.vb#7)]
     [!code-csharp[Trin_VstcoreProgramming#7](../vsto/codesnippet/CSharp/Trin_VstcoreProgrammingExcelCS/ThisWorkbook.cs#7)]  
  
2.  Artırma `Revision Number` bir özellik.  
  
     [!code-vb[Trin_VstcoreProgramming#8](../vsto/codesnippet/VisualBasic/Trin_VstcoreProgrammingExcelVB/ThisWorkbook.vb#8)]
     [!code-csharp[Trin_VstcoreProgramming#8](../vsto/codesnippet/CSharp/Trin_VstcoreProgrammingExcelCS/ThisWorkbook.cs#8)]  
  
## <a name="setting-document-properties-in-word"></a>Word'de belge özelliklerini ayarlama  
 Word'de yerleşik özellikleriyle çalışmak için aşağıdaki özellikleri kullanın:  
  
-   Bir belge düzeyi projede kullanma <xref:Microsoft.Office.Tools.Word.Document.BuiltInDocumentProperties%2A> özelliği `ThisDocument` sınıfı.  
  
-   Bir VSTO eklenti projesinde kullanmak <xref:Microsoft.Office.Interop.Word._Document.BuiltInDocumentProperties%2A> özelliği bir <xref:Microsoft.Office.Interop.Word.Document> nesnesi.  
  
 Bu özellikler bir <xref:Microsoft.Office.Core.DocumentProperties> bir nesne, <xref:Microsoft.Office.Core.DocumentProperty> nesneleri. Kullanabileceğiniz `Item` belirli bir özellik adı veya dizin koleksiyonundaki göre almak için koleksiyonun özelliği.  
  
 Aşağıdaki kod örneği, yerleşik değiştirileceği gösterilmektedir **konu** belge düzeyi projede özelliği.  
  
#### <a name="to-change-the-subject-property"></a>Konu özelliğini değiştirmek için  
  
1.  Yerleşik belge özelliklerini bir değişkene atayın.  
  
     [!code-csharp[Trin_VstcoreProgrammingWord#1](../vsto/codesnippet/CSharp/Trin_VstcoreProgrammingWordCS/ThisDocument.cs#1)]
     [!code-vb[Trin_VstcoreProgrammingWord#1](../vsto/codesnippet/VisualBasic/Trin_VstcoreProgrammingWordVB/ThisDocument.vb#1)]  
  
2.  Değişiklik `Subject` özelliğini "Whitepaper".  
  
     [!code-csharp[Trin_VstcoreProgrammingWord#2](../vsto/codesnippet/CSharp/Trin_VstcoreProgrammingWordCS/ThisDocument.cs#2)]
     [!code-vb[Trin_VstcoreProgrammingWord#2](../vsto/codesnippet/VisualBasic/Trin_VstcoreProgrammingWordVB/ThisDocument.vb#2)]  
  
## <a name="robust-programming"></a>Güçlü Programlama  
 Örneklerde, kodu yazmış olduğunuz varsayılmaktadır `ThisWorkbook` Excel için belge düzeyi projede sınıfı ve `ThisDocument` Word için belge düzeyi projede sınıfı.  
  
 Microsoft Office Word ve Excel ve bunların nesnelerle çalışma rağmen kullanılabilir yerleşik belge özelliklerinin listesini sağlar. Tanımlanmamış özellik erişmeye çalışılırken bir özel durum oluşturur.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [VSTO eklentilerini programlama](../vsto/programming-vsto-add-ins.md)   
 [Belge düzeyi özelleştirmelerini programlama](../vsto/programming-document-level-customizations.md)   
 [Nasıl yapılır: oluşturma ve özel belge özelliklerini değiştirme](../vsto/how-to-create-and-modify-custom-document-properties.md)  
  
  