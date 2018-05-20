---
title: Genişletilmiş nesneleri kullanarak Word otomatikleştirme
ms.custom: ''
ms.date: 02/02/2017
ms.technology: office-development
ms.prod: visual-studio-dev15
ms.topic: conceptual
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- Word [Office development in Visual Studio], automating
- extended objects [Office development in Visual Studio], Word
- automation [Office development in Visual Studio], Word
- host items [Office development in Visual Studio], Word
- automating Word
- controls [Office development in Visual Studio], Word host controls
- host controls, Word
- host controls [Office development in Visual Studio], Word
- Word [Office development in Visual Studio], host controls
author: TerryGLee
ms.author: tglee
manager: douge
ms.workload:
- office
ms.openlocfilehash: 8ac9c610cdc7111eaeb5204e1b9d4fe6cde27a9c
ms.sourcegitcommit: 209c2c068ff0975994ed892b62aa9b834a7f6077
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/17/2018
---
# <a name="automate-word-by-using-extended-objects"></a>Genişletilmiş nesneleri kullanarak Word otomatikleştirme
  Visual Studio'da Word çözümleri geliştirdiğinizde, kullanabileceğiniz *konak öğelerini* ve *konak kontrolü*Çözümlerinizdeki s. Bunlar gibi bazı yaygın olarak kullanılan nesneler Word nesne modeli (Word için birincil birlikte çalışma derlemesi tarafından sunulan başka bir deyişle, nesne modeli) genişleten nesnelerdir <xref:Microsoft.Office.Interop.Word.Document> ve <xref:Microsoft.Office.Interop.Word.ContentControl> nesneleri. Genişletilmiş nesneler esas alan Word nesneleri gibi davranır, ancak nesnelere ek olaylar ve veri bağlama özellikleri ekleyin.  
  
 [!INCLUDE[appliesto_wdalldocapp](../vsto/includes/appliesto-wdalldocapp-md.md)]  
  
 Bunlar kullanılabileceği bağlamı çözüm her tür için farklı olmasına rağmen konak denetimlerinin ve konak öğelerinin VSTO eklentileri ve belge düzeyi özelleştirmeleri kullanılabilir. Daha fazla bilgi için bkz: [konak öğelerini ve konak denetimlerine genel bakış](../vsto/host-items-and-host-controls-overview.md).  
  
## <a name="document-host-item"></a>Belge konak öğesi  
 Word projeleri verin erişmenizi <xref:Microsoft.Office.Tools.Word.Document> konak öğesi. <xref:Microsoft.Office.Tools.Word.Document> Konak öğesi ana bilgisayar denetimleri ve Windows Forms denetimleri de dahil olmak üzere, diğer denetimler için kapsayıcı olarak davranır ve yüzeyinde denetimler hakkında bilgi tutar. <xref:Microsoft.Office.Tools.Word.Document> Konak öğesi de aynı üyeleri çoğunu sağlar <xref:Microsoft.Office.Interop.Word.Document> Word nesne modelindeki karşılık gelen sınıf olan sınıf.  
  
 Daha fazla bilgi için bkz: [belge konak öğesi](../vsto/document-host-item.md).  
  
## <a name="word-host-controls"></a>Word konak denetimleri  
 Word için yardımcı denetimleri oluşturmak, düzenlemek ve belgeleri otomatikleştirmek birkaç konak vardır. Çoğu işlevleri, alma, sunma ve verileri koruma içerir. Bu ana bilgisayar denetimleri, olaylar ve dekiler yerel Word nesne modelinde bulunmayan veri bağlama özellikleri sağlar.  
  
 Belge düzeyi projelerine tasarım zamanında belgenize herhangi bir konak kontrolü ekleyebilir veya çalışma zamanında içerik ve yer işareti denetimleri ekleyebilirsiniz. VSTO eklenti projelerinde herhangi bir açık belgeye çalışma zamanında içerik ve yer işareti denetimleri ekleyebilirsiniz.  
  
 Word projelerinde kullanabileceğiniz ana bilgisayar denetimleri hakkında daha fazla bilgi için aşağıdaki konulara bakın:  
  
-   [İçerik denetimleri](../vsto/content-controls.md)  
  
-   [Yer işareti denetimi](../vsto/bookmark-control.md)  
  
-   [XMLNode denetimi](../vsto/xmlnode-control.md)  
  
-   [XMLNodes denetimi](../vsto/xmlnodes-control.md)  
  
## <a name="see-also"></a>Ayrıca bkz.  
 [Nasıl yapılır: Word belgelerine içerik denetimleri ekleme](../vsto/how-to-add-content-controls-to-word-documents.md)   
 [Nasıl yapılır: Word belgelerine yer işareti denetimi ekleme](../vsto/how-to-add-bookmark-controls-to-word-documents.md)   
 [Nasıl yapılır: Word belgelerine XMLNode denetimleri ekleme](../vsto/how-to-add-xmlnode-controls-to-word-documents.md)   
 [Nasıl yapılır: Word belgelerine XMLNodes denetimleri ekleme](../vsto/how-to-add-xmlnodes-controls-to-word-documents.md)   
 [Nasıl yapılır: yer işareti denetimlerini yeniden boyutlandırma](../vsto/how-to-resize-bookmark-controls.md)   
 [İzlenecek yol: içerik denetimlerini kullanarak şablon oluşturma](../vsto/walkthrough-creating-a-template-by-using-content-controls.md)   
 [İzlenecek yol: içerik denetimlerini özel XML bölümlerine bağlama](../vsto/walkthrough-binding-content-controls-to-custom-xml-parts.md)   
 [İzlenecek yol: yer işaretleri için kısayol menüleri oluşturma](../vsto/walkthrough-creating-shortcut-menus-for-bookmarks.md)   
 [Word çözümleri](../vsto/word-solutions.md)   
 [Konak öğelerine ve denetimlerine genel bakış](../vsto/host-items-and-host-controls-overview.md)   
 [Konak denetimlerinin ve konak öğelerinin programlama sınırlamaları](../vsto/programmatic-limitations-of-host-items-and-host-controls.md)   
 [Word belgelerini ve Excel çalışma kitaplarını VSTO eklentileri çalışma zamanında genişletme](../vsto/extending-word-documents-and-excel-workbooks-in-vsto-add-ins-at-run-time.md)  
  
  