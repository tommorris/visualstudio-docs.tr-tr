---
title: "Nasıl yapılır: içerik denetimlerini kullanarak belge bölümlerini koruma | Microsoft Docs"
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
- restricted permissions [Office development in Visual Studio]
- partial document protection [Office development in Visual Studio]
- content controls [Office development in Visual Studio], protecting documents
- Word [Office development in Visual Studio], partial document protection
- document protection [Office development in Visual Studio]
- Word [Office development in Visual Studio], restricted permissions
- GroupContentControl
author: TerryGLee
ms.author: tglee
manager: ghogen
ms.workload: office
ms.openlocfilehash: 444fd63ecfe1fc74161920b17a3c7caead5a434a
ms.sourcegitcommit: f9fbf1f55f9ac14e4e5c6ae58c30dc1800ca6cda
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/10/2018
---
# <a name="how-to-protect-parts-of-documents-by-using-content-controls"></a>Nasıl Yapılır: İçerik Denetimlerini Kullanarak Belge Bölümlerini Koruma
  Belgenin bir bölümünü koruduğunuzda, değiştirme veya silme belgenin bu bölümü içeriği kullanıcıların engellemiş olursunuz. İçerik denetimlerini kullanarak Microsoft Office Word belgesi kısımlarını korumak için birkaç yol vardır:  
  
-   İçerik denetimi koruyabilirsiniz.  
  
-   Bir içerik denetiminde olmayan belgenin bir bölümünü koruyabilirsiniz.  
  
 [!INCLUDE[appliesto_wdalldocapp](../vsto/includes/appliesto-wdalldocapp-md.md)]  
  
##  <a name="EditDeleteControl"></a>İçerik denetimi koruma  
 Kullanıcıların düzenleme veya içerik denetimi tasarım zamanında veya çalışma zamanında bir belge düzeyi projede denetimin özelliklerini ayarlayarak silme engelleyebilir.  
  
 Bir VSTO eklenti projesi kullanarak belgeye çalışma zamanında ekleme içerik denetimleri de koruyabilirsiniz. Daha fazla bilgi için bkz: [nasıl yapılır: Word belgelerine içerik denetimlerine ekleme](../vsto/how-to-add-content-controls-to-word-documents.md).  
  
#### <a name="to-protect-a-content-control-at-design-time"></a>Tasarım zamanında içerik denetimi korumak için  
  
1.  İçinde barındırılan belgesinde [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)] Tasarımcısı, korumak istediğiniz içerik denetimi seçin.  
  
2.  İçinde **özellikleri** penceresindeki birini veya her ikisini aşağıdaki özellikleri ayarlayın:  
  
    -   Kullanıcıların denetimi düzenlemesini önlemek için ayarlanmış **LockContents** için **doğru**.  
  
    -   Kullanıcıların denetimi silmesini önlemek için ayarlanmış **LockContentControl** için **doğru**.  
  
3.  **Tamam**'ı tıklatın.  
  
#### <a name="to-protect-a-content-control-at-run-time"></a>İçerik denetimi çalışma zamanında korumak için  
  
1.  Ayarlama `LockContents` içerik denetimi özelliği **true** kullanıcıların denetimi düzenlemesini önlemek ve ayarlamak için `LockContentControl` özelliğine **true** kullanıcıların denetimi silmesini önlemek için.  
  
     Aşağıdaki kod örneğinde kullanımı gösterilir <xref:Microsoft.Office.Tools.Word.RichTextContentControl.LockContents%2A> ve <xref:Microsoft.Office.Tools.Word.RichTextContentControl.LockContentControl%2A> iki farklı özelliklerini <xref:Microsoft.Office.Tools.Word.RichTextContentControl> belge düzeyi projesindeki nesneleri. Bu kodu çalıştırmak için kodu ekleyin `ThisDocument` projenizi ve çağrı sınıfında `AddProtectedContentControls` yönteminden `ThisDocument_Startup` olay işleyicisi.  
  
     [!code-csharp[Trin_ContentControlHowToProtect#2](../vsto/codesnippet/CSharp/Trin_ContentControlHowToProtect/ThisDocument.cs#2)]
     [!code-vb[Trin_ContentControlHowToProtect#2](../vsto/codesnippet/VisualBasic/Trin_ContentControlHowToProtect/ThisDocument.vb#2)]  
  
     Aşağıdaki kod örneğinde kullanımı gösterilir <xref:Microsoft.Office.Tools.Word.RichTextContentControl.LockContents%2A> ve <xref:Microsoft.Office.Tools.Word.RichTextContentControl.LockContentControl%2A> iki farklı özelliklerini <xref:Microsoft.Office.Tools.Word.RichTextContentControl> VSTO eklenti projesindeki nesneleri. Bu kodu çalıştırmak için kodu ekleyin `ThisAddIn` projenizi ve çağrı sınıfında `AddProtectedContentControls` yönteminden `ThisAddIn_Startup` olay işleyicisi.  
  
     [!code-vb[Trin_WordAddInDynamicControls#14](../vsto/codesnippet/VisualBasic/trin_wordaddindynamiccontrols/ThisAddIn.vb#14)]
     [!code-csharp[Trin_WordAddInDynamicControls#14](../vsto/codesnippet/CSharp/Trin_WordAddInDynamicControls/ThisAddIn.cs#14)]  
  
## <a name="protecting-a-part-of-a-document-that-is-not-in-a-content-control"></a>Bir belgenin bir içerik denetiminde olmayan bir bölümü koruma  
 Bir alanı bir belgenin değiştirme alanı koyarak kullanıcıların engelleyebilir bir <xref:Microsoft.Office.Tools.Word.GroupContentControl>. Aşağıdaki senaryolarda kullanışlıdır:  
  
-   İçerik denetimleri içermeyen bir alanı korumak istiyorsunuz.  
  
-   İçerik denetimleri içeren bir alanı korumak istediğiniz, ancak metin veya korumak istediğiniz diğer öğeleri içerik denetimlerinde değildir.  
  
> [!NOTE]  
>  Oluşturursanız, bir <xref:Microsoft.Office.Tools.Word.GroupContentControl> katıştırılmış içerik denetimleri içeren, katıştırılmış içerik denetimleri otomatik olarak korunmaz. Kullanıcıların bir katıştırılmış içerik denetimi düzenlemesini önlemek için kullanın **LockContents** denetiminin özelliği.  
  
#### <a name="to-protect-an-area-of-a-document-at-design-time"></a>Tasarım zamanında bir alanı bir belgenin korumak için  
  
1.  İçinde barındırılan belgesinde [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)] Tasarımcısı, korumak istediğiniz bölgeyi seçin.  
  
2.  Şerit'te tıklatın **Geliştirici** sekmesi.  
  
    > [!NOTE]  
    >  Varsa **Geliştirici** sekmesi görünür değilse, ilk Göster gerekir. Daha fazla bilgi için bkz: [nasıl yapılır: Şeritte Geliştirici sekmesini gösterme](../vsto/how-to-show-the-developer-tab-on-the-ribbon.md).  
  
3.  İçinde **denetimleri** grubunda **grup** açılan düğmesine ve ardından **grup**.  
  
     A <xref:Microsoft.Office.Tools.Word.GroupContentControl> korumalı içeren bölge oluşturulan otomatik olarak `ThisDocument` projenizdeki sınıfı. Tasarım zamanında grup denetimini temsil eden kenarlık görünür, ancak çalışma zamanında görünür bir kenarlık yoktur.  
  
#### <a name="to-protect-an-area-of-a-document-at-run-time"></a>Çalışma zamanında bir alanı bir belgenin korumak için  
  
1.  Program aracılığıyla korumak ve ardından çağırmak için istediğiniz bölgeyi seçin <xref:Microsoft.Office.Tools.Word.ControlCollection.AddGroupContentControl%2A> yöntemi oluşturmak için bir <xref:Microsoft.Office.Tools.Word.GroupContentControl>.  
  
     Belge düzeyi projesi için aşağıdaki kod örneğinde belgede ilk paragrafa metin ilk paragrafa seçer ve ardından başlatır ekler bir <xref:Microsoft.Office.Tools.Word.GroupContentControl>. Bu kodu çalıştırmak için kodu ekleyin `ThisDocument` projenizi ve çağrı sınıfında `ProtectFirstParagraph` yönteminden `ThisDocument_Startup` olay işleyicisi.  
  
     [!code-csharp[Trin_ContentControlHowToProtect#1](../vsto/codesnippet/CSharp/Trin_ContentControlHowToProtect/ThisDocument.cs#1)]
     [!code-vb[Trin_ContentControlHowToProtect#1](../vsto/codesnippet/VisualBasic/Trin_ContentControlHowToProtect/ThisDocument.vb#1)]  
  
     Etkin belgedeki ilk paragrafa metin ilk paragrafa seçer ve ardından başlatır VSTO eklenti projesi için aşağıdaki kod örneğinde ekler bir <xref:Microsoft.Office.Tools.Word.GroupContentControl>. Bu kodu çalıştırmak için kodu ekleyin `ThisAddIn` projenizi ve çağrı sınıfında `ProtectFirstParagraph` yönteminden `ThisAddIn_Startup` olay işleyicisi.  
  
     [!code-vb[Trin_WordAddInDynamicControls#15](../vsto/codesnippet/VisualBasic/trin_wordaddindynamiccontrols/ThisAddIn.vb#15)]
     [!code-csharp[Trin_WordAddInDynamicControls#15](../vsto/codesnippet/CSharp/Trin_WordAddInDynamicControls/ThisAddIn.cs#15)]  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Genişletilmiş nesneleri kullanarak Word'ü Otomatikleştirme](../vsto/automating-word-by-using-extended-objects.md)   
 [İçerik denetimleri](../vsto/content-controls.md)   
 [Nasıl yapılır: Word belgelerine içerik denetimleri ekleme](../vsto/how-to-add-content-controls-to-word-documents.md)   
 [Konak öğelerine ve denetimlerine genel bakış](../vsto/host-items-and-host-controls-overview.md)   
 [Konak denetimlerinin ve konak öğelerinin programlama sınırlamaları](../vsto/programmatic-limitations-of-host-items-and-host-controls.md)   
 [Office Belgelerine Çalışma Zamanında Denetim Ekleme](../vsto/adding-controls-to-office-documents-at-run-time.md)  
   