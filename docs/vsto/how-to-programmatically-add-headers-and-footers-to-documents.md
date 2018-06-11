---
title: 'Nasıl yapılır: program aracılığıyla belgelere üstbilgiler ve altbilgiler ekleme'
ms.custom: ''
ms.date: 02/02/2017
ms.technology:
- office-development
ms.topic: conceptual
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- headers, adding to Office documents
- documents [Office development in Visual Studio], adding headers
- documents [Office development in Visual Studio], adding footers
- footers, adding to documents
author: TerryGLee
ms.author: tglee
manager: douge
ms.workload:
- office
ms.openlocfilehash: 98f9ed1025c264b4fa7432e2ce397e988e6795f4
ms.sourcegitcommit: 34f7d23ce3bd140dcae875b602d5719bb4363ed1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/11/2018
ms.locfileid: "35256038"
---
# <a name="how-to-programmatically-add-headers-and-footers-to-documents"></a>Nasıl yapılır: program aracılığıyla belgelere üstbilgiler ve altbilgiler ekleme
  Metin üstbilgiler ve altbilgiler belgenizi kullanarak ekleyebilirsiniz <xref:Microsoft.Office.Interop.Word.Section.Headers%2A> özelliği ve <xref:Microsoft.Office.Interop.Word.Section.Footers%2A> özelliği <xref:Microsoft.Office.Interop.Word.Section>. Her bir belge bölümü üç üstbilgiler ve altbilgiler içerir:  
  
-   <xref:Microsoft.Office.Interop.Word.WdHeaderFooterIndex.wdHeaderFooterPrimary>  
  
-   <xref:Microsoft.Office.Interop.Word.WdHeaderFooterIndex.wdHeaderFooterEvenPages>  
  
-   <xref:Microsoft.Office.Interop.Word.WdHeaderFooterIndex.wdHeaderFooterFirstPage>  
  
 Belge düzeyi özelleştirmeleri ve VSTO eklentileri için yordamlar farklıdır.  
  
 [!INCLUDE[appliesto_wdalldocapp](../vsto/includes/appliesto-wdalldocapp-md.md)]  
  
## <a name="document-level-customizations"></a>Belge düzeyinde özelleştirmeler  
 Aşağıdaki kod örnekleri kullanmak için bunları çalıştırmak `ThisDocument` projenizdeki sınıfı.  
  
### <a name="to-add-text-to-footers-in-the-document"></a>Altbilgi belgedeki metin ekleme  
  
1.  Aşağıdaki kod örneğinde belgenin her bölüm birincil altbilgi eklenecek metnin yazı tipini ayarlar ve ardından metin altbilgi ekler.  
  
     [!code-vb[Trin_VstcoreWordAutomation#114](../vsto/codesnippet/VisualBasic/Trin_VstcoreWordAutomationVB/ThisDocument.vb#114)]
     [!code-csharp[Trin_VstcoreWordAutomation#114](../vsto/codesnippet/CSharp/Trin_VstcoreWordAutomationCS/ThisDocument.cs#114)]  
  
### <a name="to-add-text-to-headers-in-the-document"></a>Belgedeki üstbilgilere metin ekleme  
  
1.  Aşağıdaki kod örneğinde belgedeki her üstbilgiye sayfa numarasını göstermek için bir alan ekler ve böylece sağa üstbilgi metni hizalar Paragraf hizalamasını ayarlar.  
  
     [!code-vb[Trin_VstcoreWordAutomation#116](../vsto/codesnippet/VisualBasic/Trin_VstcoreWordAutomationVB/ThisDocument.vb#116)]
     [!code-csharp[Trin_VstcoreWordAutomation#116](../vsto/codesnippet/CSharp/Trin_VstcoreWordAutomationCS/ThisDocument.cs#116)]  
  
## <a name="vsto-add-ins"></a>VSTO eklentileri  
 Aşağıdaki kod örnekleri kullanmak için bunları çalıştırmak `ThisAddIn` projenizdeki sınıfı.  
  
### <a name="to-add-text-to-footers-in-a-document"></a>Altbilgi belgedeki metin ekleme  
  
1.  Aşağıdaki kod örneğinde belgenin her bölüm birincil altbilgi eklenecek metnin yazı tipini ayarlar ve ardından metin altbilgi ekler. Bu kod örneği, etkin belgeyi kullanır.  
  
     [!code-vb[Trin_VstcoreWordAutomationAddIn#114](../vsto/codesnippet/VisualBasic/Trin_VstcoreWordAutomationAddIn/ThisAddIn.vb#114)]
     [!code-csharp[Trin_VstcoreWordAutomationAddIn#114](../vsto/codesnippet/CSharp/Trin_VstcoreWordAutomationAddIn/ThisAddIn.cs#114)]  
  
### <a name="to-add-text-to-headers-in-the-document"></a>Belgedeki üstbilgilere metin ekleme  
  
1.  Aşağıdaki kod örneğinde belgedeki her üstbilgiye sayfa numarasını göstermek için bir alan ekler ve böylece sağa üstbilgi metni hizalar Paragraf hizalamasını ayarlar. Bu kod örneği, etkin belgeyi kullanır.  
  
     [!code-vb[Trin_VstcoreWordAutomationAddIn#116](../vsto/codesnippet/VisualBasic/Trin_VstcoreWordAutomationAddIn/ThisAddIn.vb#116)]
     [!code-csharp[Trin_VstcoreWordAutomationAddIn#116](../vsto/codesnippet/CSharp/Trin_VstcoreWordAutomationAddIn/ThisAddIn.cs#116)]  
  
## <a name="see-also"></a>Ayrıca bkz.  
 [Nasıl yapılır: program aracılığıyla yeni belgeler oluşturma](../vsto/how-to-programmatically-create-new-documents.md)   
 [Nasıl yapılır: belgelerde aralıkları program aracılığıyla genişletme](../vsto/how-to-programmatically-extend-ranges-in-documents.md)   
 [Nasıl yapılır: program aracılığıyla bulunan öğeler arasında döngü](../vsto/how-to-programmatically-loop-through-found-items-in-documents.md)  
   