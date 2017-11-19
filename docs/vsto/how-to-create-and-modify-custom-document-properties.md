---
title: "Nasıl yapılır: oluşturma ve özel belge özelliklerini değiştirme | Microsoft Docs"
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
- custom document properties
- documents [Office development in Visual Studio], properties
- document properties [Office development in Visual Studio]
ms.assetid: 99d9dfaf-891f-4f3b-a580-67362afdaf34
caps.latest.revision: "47"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: 78cf27b7d58e85217c770abee1dc6a4151cc1eb1
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2017
---
# <a name="how-to-create-and-modify-custom-document-properties"></a>Nasıl Yapılır: Özel Belge Özelliklerini Oluşturma ve Değiştirme
  Yukarıda listelenen Microsoft Office uygulamaları ile belgeler depolanır yerleşik özellikler sağlar. Ayrıca, oluşturabilir ve belgeyle depolamak istediğiniz ek bilgiler ise özel belge özelliklerini değiştirebilirsiniz.  
  
 [!INCLUDE[appliesto_docprops](../vsto/includes/appliesto-docprops-md.md)]  
  
 Özel özelliklerle çalışmak için bir belgenin CustomDocumentProperties özelliğini kullanın. Örneğin, Microsoft Office Excel için belge düzeyi projede kullanmak <xref:Microsoft.Office.Tools.Excel.Workbook.CustomDocumentProperties%2A> özelliği `ThisWorkbook` sınıfı. Bir VSTO eklenti projesinde Excel için kullanmak <xref:Microsoft.Office.Interop.Excel._Workbook.CustomDocumentProperties%2A> özelliği bir <xref:Microsoft.Office.Interop.Excel.Workbook> nesnesi. Bu özellikler bir <xref:Microsoft.Office.Core.DocumentProperties> bir nesne, <xref:Microsoft.Office.Core.DocumentProperty> nesneleri. Kullanabileceğiniz `Item` belirli bir özellik adı veya dizin koleksiyonundaki göre almak için koleksiyonun özelliği.  
  
 Aşağıdaki örnek, bir özel özellik Excel için belge düzeyi özelleştirmelerinde ekleyin ve bir değer atamak gösterilmiştir.  
  
 ![video bağlantı](../vsto/media/playvideo.gif "video bağlantı") ilgili video gösterimi için bkz: [I: erişimi nasıl yapın ve Microsoft Word özel belge özelliklerini işlemek?](http://go.microsoft.com/fwlink/?LinkId=136772).  
  
## <a name="example"></a>Örnek  
 [!code-vb[Trin_VstcoreProgramming#6](../vsto/codesnippet/VisualBasic/Trin_VstcoreProgrammingExcelVB/ThisWorkbook.vb#6)]
 [!code-csharp[Trin_VstcoreProgramming#6](../vsto/codesnippet/CSharp/Trin_VstcoreProgrammingExcelCS/ThisWorkbook.cs#6)]  
  
## <a name="robust-programming"></a>Güçlü Programlama  
 Erişmeye `Value` özelliği tanımsız özellikleri için özel bir durum oluşturur.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [VSTO eklentilerini programlama](../vsto/programming-vsto-add-ins.md)   
 [Belge düzeyi özelleştirmelerini programlama](../vsto/programming-document-level-customizations.md)   
 [Nasıl yapılır: Okuma ve belge özellikleri yazma](../vsto/how-to-read-from-and-write-to-document-properties.md)  
  
  