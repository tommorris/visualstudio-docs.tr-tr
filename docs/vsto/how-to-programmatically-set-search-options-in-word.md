---
title: "Nasıl yapılır: program aracılığıyla arama seçeneklerini ayarlama Word'de | Microsoft Docs"
ms.custom: ''
ms.date: 02/02/2017
ms.technology:
- office-development
ms.topic: conceptual
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- settings, Word search options
- documents [Office development in Visual Studio], search options
- Word, searching options
- searching, Word options
author: TerryGLee
ms.author: tglee
manager: douge
ms.workload:
- office
ms.openlocfilehash: 3be8d12f18e4ea0b6d05cbad92c08c7b5427315c
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/16/2018
---
# <a name="how-to-programmatically-set-search-options-in-word"></a>Nasıl yapılır: Word'de Program Aracılığıyla Arama Seçeneklerini Ayarlama
  Microsoft Office Word belgelerinde seçimleri için arama seçeneklerini ayarlamak için iki yolu vardır:  
  
-   Özelliklerini ayarlamak bir <xref:Microsoft.Office.Interop.Word.Find> nesnesi.  
  
-   Bağımsız değişkenlerini kullanmak <xref:Microsoft.Office.Interop.Word.Find.Execute%2A> yöntemi bir <xref:Microsoft.Office.Interop.Word.Find> nesnesi.  
  
 [!INCLUDE[appliesto_wdalldocapp](../vsto/includes/appliesto-wdalldocapp-md.md)]  
  
## <a name="using-properties-of-a-find-object"></a>Bul nesnesinin özelliklerini kullanarak  
 Aşağıdaki kod özelliklerini ayarlar bir <xref:Microsoft.Office.Interop.Word.Find> Geçerli seçimdeki metni aramak için nesne. İleriye doğru sarmalama ve metin aramak için arama gibi arama ölçütlerini özelliklerini olduğunu fark <xref:Microsoft.Office.Interop.Word.Find> nesnesi.  
  
 Her özelliklerinin <xref:Microsoft.Office.Interop.Word.Find> nesnesi değil yararlı parametre olarak aynı özelliklerini belirtmeniz gerekir çünkü C# kodu yazarken <xref:Microsoft.Office.Interop.Word.Find.Execute%2A> yöntemi. Bu nedenle bu örnek yalnızca Visual Basic kodu içerir.  
  
#### <a name="to-set-search-options-using-a-find-object"></a>Bir bulma nesnesi ile arama seçeneklerini ayarlama  
  
1.  Özelliklerini ayarla bir <xref:Microsoft.Office.Interop.Word.Find> metni için bir seçim ileriye doğru arama nesnesine **find me**.  
  
     [!code-vb[Trin_VstcoreWordAutomation#76](../vsto/codesnippet/VisualBasic/Trin_VstcoreWordAutomationVB/ThisDocument.vb#76)]  
  
## <a name="using-execute-method-arguments"></a>Yürütme yöntem bağımsız değişkenleri kullanma  
 Aşağıdaki kod <xref:Microsoft.Office.Interop.Word.Find.Execute%2A> yöntemi bir <xref:Microsoft.Office.Interop.Word.Find> Geçerli seçimdeki metni aramak için nesne. İleriye doğru sarmalama ve metin aramak için arama gibi arama ölçütlerini parametre olarak geçirilen bildirimi <xref:Microsoft.Office.Interop.Word.Find.Execute%2A> yöntemi.  
  
#### <a name="to-set-search-options-using-execute-method-arguments"></a>Execute yöntemi bağımsız değişkenleri ile arama seçeneklerini ayarlama  
  
1.  Arama ölçütlerini parametre olarak geçirmek <xref:Microsoft.Office.Interop.Word.Find.Execute%2A> metni için bir seçim ileriye doğru arama yapmak yöntemi **find me**.  
  
     [!code-vb[Trin_VstcoreWordAutomation#77](../vsto/codesnippet/VisualBasic/Trin_VstcoreWordAutomationVB/ThisDocument.vb#77)]
     [!code-csharp[Trin_VstcoreWordAutomation#77](../vsto/codesnippet/CSharp/Trin_VstcoreWordAutomationCS/ThisDocument.cs#77)]  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Nasıl yapılır: program aracılığıyla arama ve belgelerdeki metni değiştirme](../vsto/how-to-programmatically-search-for-and-replace-text-in-documents.md)   
 [Nasıl yapılır: program aracılığıyla bulunan öğeler arasında döngü](../vsto/how-to-programmatically-loop-through-found-items-in-documents.md)   
 [Nasıl yapılır: Aramalardan Sonra Seçimleri Program Aracılığıyla Geri Yükleme](../vsto/how-to-programmatically-restore-selections-after-searches.md)  
  
  