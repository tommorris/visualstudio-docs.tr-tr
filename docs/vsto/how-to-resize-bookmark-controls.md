---
title: "Nasıl yapılır: yer işareti denetimlerini yeniden boyutlandırma | Microsoft Docs"
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
- controls [Office development in Visual Studio], resizing
- Bookmark control, resizing
ms.assetid: 3de1c774-921a-4113-a54a-e3b8d4a65d53
caps.latest.revision: "45"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload: office
ms.openlocfilehash: 4129e7405422f5b9490965e658caebce216db1e2
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-resize-bookmark-controls"></a>Nasıl Yapılır: Yer İşareti Denetimlerini Yeniden Boyutlandırma
  Boyutu ayarlama bir <xref:Microsoft.Office.Tools.Word.Bookmark> Microsoft Office Word belgesine eklediğinizde denetim. Bunu daha sonra yeniden boyutlandırabilirsiniz.  
  
 [!INCLUDE[appliesto_wdalldocapp](../vsto/includes/appliesto-wdalldocapp-md.md)]  
  
 Yer işareti yeniden boyutlandırmak için üç yolu vardır:  
  
-   Metin ekleyip <xref:Microsoft.Office.Tools.Word.Bookmark> denetim.  
  
     Bir yer işaretine metin eklediğinizde yer işaretinin boyutu otomatik olarak yeni metin içeren artırır. Metin sildiğinizde, yer işaretinin boyutu otomatik olarak azaltır.  
  
-   Değişiklik <xref:Microsoft.Office.Tools.Word.Bookmark.Start%2A> ve <xref:Microsoft.Office.Tools.Word.Bookmark.End%2A> özelliklerini <xref:Microsoft.Office.Tools.Word.Bookmark> denetim.  
  
     Bu seçenek, yalnızca birkaç karakterleriyle boyutunu değiştiriyorsanız yararlıdır.  
  
-   Yeniden <xref:Microsoft.Office.Tools.Word.Bookmark> denetim.  
  
     Bu boyut veya yer işareti konumunu önemli bir değişiklik olduğunda yararlıdır.  
  
 Belge düzeyi projelerine eklediğiniz <xref:Microsoft.Office.Tools.Word.Bookmark> belgenin projenizdeki tasarım zamanında veya çalışma zamanında denetimler. VSTO eklenti projelerinde eklediğiniz <xref:Microsoft.Office.Tools.Word.Bookmark> herhangi bir açık belgeye çalışma zamanında denetimler. Daha fazla bilgi için bkz: [nasıl yapılır: Word belgelerine yer işareti Denetimler Ekle](../vsto/how-to-add-bookmark-controls-to-word-documents.md).  
  
 [!INCLUDE[note_settings_general](../sharepoint/includes/note-settings-general-md.md)]  
  
## <a name="changing-the-start-and-end-properties"></a>Başlangıç ve bitiş özelliklerini değiştirme  
  
#### <a name="to-resize-a-bookmark-in-a-document-level-project-at-design-time"></a>Belge düzeyi projede yer işareti tasarım zamanında yeniden boyutlandırmak için  
  
1.  İşaretinde seçin **özellikleri** penceresi.  
  
2.  Artırma veya azaltma değerini <xref:Microsoft.Office.Tools.Word.Bookmark.Start%2A> özelliği.  
  
3.  Artırma veya azaltma değerini <xref:Microsoft.Office.Tools.Word.Bookmark.End%2A> özelliği.  
  
#### <a name="to-resize-a-bookmark-in-a-document-level-project-at-run-time"></a>Belge düzeyi projede yer işareti çalışma zamanında yeniden boyutlandırmak için  
  
1.  Değiştirme <xref:Microsoft.Office.Tools.Word.Bookmark.Start%2A> ve <xref:Microsoft.Office.Tools.Word.Bookmark.End%2A> özelliklerini bir <xref:Microsoft.Office.Tools.Word.Bookmark> çalışma zamanında veya tasarım zamanında oluşturulan.  
  
     Aşağıdaki kod örneğinde beş karakter adında bir yer işareti başlangıcına ekler `SampleBookmark`. Bu kod, metin yer işaretinden önce en az beş karakter olduğunu varsayar.  
  
     [!code-csharp[Trin_VstcoreHostControlsWord#2](../vsto/codesnippet/CSharp/trin_vstcorehostcontrolsword/ThisDocument.cs#2)]
     [!code-vb[Trin_VstcoreHostControlsWord#2](../vsto/codesnippet/VisualBasic/Trin_VstcoreHostControlsWordVB/ThisDocument.vb#2)]  
  
     Aşağıdaki kod örneğinde beş karakteri aynı yer işaretinin sonuna ekler. Bu kod yer işaretinden sonra en az beş karakterlik metin olduğunu varsayar.  
  
     [!code-csharp[Trin_VstcoreHostControlsWord#3](../vsto/codesnippet/CSharp/trin_vstcorehostcontrolsword/ThisDocument.cs#3)]
     [!code-vb[Trin_VstcoreHostControlsWord#3](../vsto/codesnippet/VisualBasic/Trin_VstcoreHostControlsWordVB/ThisDocument.vb#3)]  
  
#### <a name="to-resize-a-bookmark-in-an-vsto-add-in-project-at-run-time"></a>Çalışma zamanında VSTO eklenti projesindeki yer işareti yeniden boyutlandırmak için  
  
1.  Değiştirme <xref:Microsoft.Office.Tools.Word.Bookmark.Start%2A> ve <xref:Microsoft.Office.Tools.Word.Bookmark.End%2A> özelliklerini bir <xref:Microsoft.Office.Tools.Word.Bookmark> çalışma zamanında oluşturulan.  
  
     Aşağıdaki kod örneği oluşturur bir <xref:Microsoft.Office.Tools.Word.Bookmark> etkin belgenin ilk paragraf metni içerir ve ardından başlangıcı ve sonu beş karakteri kaldırır <xref:Microsoft.Office.Tools.Word.Bookmark>.  
  
     [!code-vb[Trin_WordAddInDynamicControls#16](../vsto/codesnippet/VisualBasic/trin_wordaddindynamiccontrols/ThisAddIn.vb#16)]
     [!code-csharp[Trin_WordAddInDynamicControls#16](../vsto/codesnippet/CSharp/Trin_WordAddInDynamicControls/ThisAddIn.cs#16)]  
  
## <a name="recreating-the-bookmark"></a>Yer işareti yeniden oluşturma  
 Varolan yer imi aynı ada sahip, ancak farklı bir boyut olan yeni bir yer işareti ekleyerek bir belge düzeyi projede yer işareti yeniden boyutlandırabilirsiniz.  
  
#### <a name="to-recreate-a-bookmark-in-a-document-level-project-at-design-time"></a>Belge düzeyi projede yer işareti tasarım zamanında yeniden oluşturmak için  
  
1.  Yeni eklenmesini istediğiniz metni seçin <xref:Microsoft.Office.Tools.Word.Bookmark> denetim.  
  
2.  Üzerinde **Ekle** menüsünde tıklatın **yer işareti**.  
  
3.  İçinde **yer işareti** iletişim kutusunda, yeniden boyutlandırma ve istediğiniz yer işaretinin adını seçin **Ekle**.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Nasıl yapılır: Word belgelerine yer işareti denetimi ekleme](../vsto/how-to-add-bookmark-controls-to-word-documents.md)   
 [Genişletilmiş nesneleri kullanarak Word'ü Otomatikleştirme](../vsto/automating-word-by-using-extended-objects.md)   
 [Konak öğelerine ve denetimlerine genel bakış](../vsto/host-items-and-host-controls-overview.md)   
 [Nasıl yapılır: NamedRange denetimlerinin boyutunu değiştirme](../vsto/how-to-resize-namedrange-controls.md)   
 [Nasıl yapılır: ListObject denetimlerinin boyutunu değiştirme](../vsto/how-to-resize-listobject-controls.md)   
 [Konak Denetimlerinin ve Konak Öğelerinin Programlama Sınırlamaları](../vsto/programmatic-limitations-of-host-items-and-host-controls.md)  
  
  