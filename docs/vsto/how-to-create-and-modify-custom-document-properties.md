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
author: TerryGLee
ms.author: tglee
manager: ghogen
ms.workload: office
ms.openlocfilehash: 5d081beb3422126f6ccf7484cb08e7fa43da8874
ms.sourcegitcommit: f9fbf1f55f9ac14e4e5c6ae58c30dc1800ca6cda
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/10/2018
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
 [Nasıl Yapılır: Belge Özelliklerinden Okuma ve Yazma](../vsto/how-to-read-from-and-write-to-document-properties.md)  
  
  