---
title: "Nasıl yapılır: program aracılığıyla belgeleri kaydetme | Microsoft Docs"
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
- documents [Office development in Visual Studio], saving
- Word [Office development in Visual Studio], saving documents
ms.assetid: a6225ae9-94f5-421a-9860-5299002d543d
caps.latest.revision: "44"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload: office
ms.openlocfilehash: 251522a745ee7b8dc9894a403f09d1a6d3f32793
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-programmatically-save-documents"></a>Nasıl yapılır: Program Aracılığıyla Belgeleri Kaydetme
  Microsoft Office Word belgeleri kaydetmek için birkaç yolu vardır. Belgenin adını değiştirmeden bir belgeyi kaydedebilir veya yeni bir adla bir belge kaydedebilirsiniz.  
  
 [!INCLUDE[appliesto_wdalldocapp](../vsto/includes/appliesto-wdalldocapp-md.md)]  
  
## <a name="saving-a-document-without-changing-the-name"></a>Bir belge adı değiştirmeden kaydetme  
  
#### <a name="to-save-the-document-associated-with-a-document-level-customization"></a>Belge düzeyi özelleştirme ile ilişkilendirilmiş belgeyi kaydetmek için  
  
1.  Çağrı <xref:Microsoft.Office.Tools.Word.Document.Save%2A> yöntemi <xref:Microsoft.Office.Tools.Word.Document> sınıfı. Bu kod örneği kullanmak için çalıştırın `ThisDocument` projenizdeki sınıfı.  
  
     [!code-vb[Trin_VstcoreWordAutomation#7](../vsto/codesnippet/VisualBasic/Trin_VstcoreWordAutomationVB/ThisDocument.vb#7)]
     [!code-csharp[Trin_VstcoreWordAutomation#7](../vsto/codesnippet/CSharp/Trin_VstcoreWordAutomationCS/ThisDocument.cs#7)]  
  
#### <a name="to-save-the-active-document"></a>Etkin belgeyi kaydetmek için  
  
1.  Çağrı <xref:Microsoft.Office.Interop.Word._Document.Save%2A> etkin belge için yöntem. Bu kod örneği kullanmak için çalıştırın `ThisDocument` veya `ThisAddIn` projenizdeki sınıfı.  
  
     [!code-vb[Trin_VstcoreWordAutomation#8](../vsto/codesnippet/VisualBasic/Trin_VstcoreWordAutomationVB/ThisDocument.vb#8)]
     [!code-csharp[Trin_VstcoreWordAutomation#8](../vsto/codesnippet/CSharp/Trin_VstcoreWordAutomationCS/ThisDocument.cs#8)]  
  
 Kaydetmek istediğiniz belge etkin belgeyi olup emin değilseniz, sunucu adına göre başvurabilir.  
  
#### <a name="to-save-a-document-specified-by-name"></a>Adıyla belirtilen belgeyi kaydetmek için  
  
1.  Bağımsız değişken olarak belge adı kullanmak <xref:Microsoft.Office.Interop.Word.Documents> koleksiyonu. Bu kod örneği kullanmak için çalıştırın `ThisDocument` veya `ThisAddIn` projenizdeki sınıfı.  
  
     [!code-vb[Trin_VstcoreWordAutomation#9](../vsto/codesnippet/VisualBasic/Trin_VstcoreWordAutomationVB/ThisDocument.vb#9)]
     [!code-csharp[Trin_VstcoreWordAutomation#9](../vsto/codesnippet/CSharp/Trin_VstcoreWordAutomationCS/ThisDocument.cs#9)]  
  
## <a name="saving-a-document-with-a-new-name"></a>Belgeye yeni bir adla kaydetme  
 Belgeye yeni bir adla kaydetmek için Farklı Kaydet yöntemini kullanın. Bu yöntemi kullanabilirsiniz <xref:Microsoft.Office.Tools.Word.Document> konak öğesi belge düzeyi Word projesindeki ya da yerel <xref:Microsoft.Office.Interop.Word.Document> herhangi bir Word projesinin nesne. Bu yöntem, yeni dosya adı belirtin, ancak başka bir bağımsız değişken isteğe bağlı gerektirir.  
  
> [!NOTE]  
>  Gösteriyorsa, **Farklı Kaydet** iletişim kutusu içinde <xref:Microsoft.Office.Interop.Word.ApplicationEvents4_Event.DocumentBeforeSave> olay işleyicisi `ThisDocument` ve *iptal* parametresi **yanlış**, uygulama olabilir beklenmedik bir şekilde çıkın. Ayarlarsanız *iptal* parametresi **doğru**, otomatik kaydetme devre dışı olduğunu belirten bir hata iletisi görünür.  
  
#### <a name="to-save-the-document-associated-with-a-document-level-customization-with-a-new-name"></a>Belge düzeyi özelleştirme yeni bir adla ilişkili belgeyi kaydetmek için  
  
1.  Çağrı <xref:Microsoft.Office.Tools.Word.Document.SaveAs%2A> yöntemi `ThisDocument` bir tam yol ve dosya adını kullanarak projenizdeki sınıfı. Bu klasörde aynı adı taşıyan bir dosya zaten varsa, sessiz bir şekilde üzerine yazılır. Bu kod örneği kullanmak için çalıştırın `ThisDocument` sınıfı.  
  
    > [!NOTE]  
    >  <xref:Microsoft.Office.Tools.Word.Document.SaveAs%2A> Yöntemi, bir hedef dizin yok veya dosya kaydetme diğer sorunlar varsa bir özel durum oluşturur. Kullanmak için iyi bir uygulamadır bir **try... catch** geçici engelleme <xref:Microsoft.Office.Tools.Word.Document.SaveAs%2A> yöntemi veya çağrılan yöntemin içinde.  
  
     [!code-vb[Trin_VstcoreWordAutomation#10](../vsto/codesnippet/VisualBasic/Trin_VstcoreWordAutomationVB/ThisDocument.vb#10)]
     [!code-csharp[Trin_VstcoreWordAutomation#10](../vsto/codesnippet/CSharp/Trin_VstcoreWordAutomationCS/ThisDocument.cs#10)]  
  
#### <a name="to-save-a-native-document-with-a-new-name"></a>Yerel belgeyi yeni adla kaydetmek için  
  
1.  Çağrı <xref:Microsoft.Office.Interop.Word._Document.SaveAs%2A> yöntemi <xref:Microsoft.Office.Interop.Word.Document> kaydetmek bir tam yol ve dosya adını kullanarak istediğiniz. Bu klasörde aynı adı taşıyan bir dosya zaten varsa, sessiz bir şekilde üzerine yazılır.  
  
     Aşağıdaki kod örneğinde etkin belgeyi yeni adla kaydeder. Bu kod örneği kullanmak için çalıştırın `ThisDocument` veya `ThisAddIn` projenizdeki sınıfı.  
  
    > [!NOTE]  
    >  <xref:Microsoft.Office.Interop.Word._Document.SaveAs%2A> Yöntemi, bir hedef dizin yok veya dosya kaydetme diğer sorunlar varsa bir özel durum oluşturur. Kullanmak için iyi bir uygulamadır bir **try... catch** geçici engelleme <xref:Microsoft.Office.Interop.Word._Document.SaveAs%2A> yöntemi veya çağrılan yöntemin içinde.  
  
     [!code-vb[Trin_VstcoreWordAutomationAddIn#10](../vsto/codesnippet/VisualBasic/Trin_VstcoreWordAutomationAddIn/ThisAddIn.vb#10)]
     [!code-csharp[Trin_VstcoreWordAutomationAddIn#10](../vsto/codesnippet/CSharp/Trin_VstcoreWordAutomationAddIn/ThisAddIn.cs#10)]  
  
## <a name="compiling-the-code"></a>Kod Derleniyor  
 Bu kod örneği için şunlar gerekir:  
  
-   Ada göre bir belgeyi kaydetmek için NewDocument.doc isimli bir belge c sürücüsünde Test adlı bir dizinde olması gerekir  
  
-   Belgeye yeni bir adla kaydetmek için Test adlı bir dizin c sürücüsünde gerekir  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Nasıl yapılır: program aracılığıyla belgeleri kapatma](../vsto/how-to-programmatically-close-documents.md)   
 [Nasıl yapılır: varolan belgeleri program aracılığıyla açma](../vsto/how-to-programmatically-open-existing-documents.md)   
 [Belge konak öğesi](../vsto/document-host-item.md)   
 [Office Çözümlerinde İsteğe Bağlı Parametreler](../vsto/optional-parameters-in-office-solutions.md)  
  
  