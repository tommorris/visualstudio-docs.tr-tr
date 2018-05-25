---
title: 'Nasıl yapılır: içerik ekleme denetimlerine Word belgeleri'
ms.custom: ''
ms.date: 02/02/2017
ms.technology:
- office-development
ms.topic: conceptual
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- restricted permissions [Office development in Visual Studio]
- DropDownListContentControl, adding to documents
- BuildingBlockGalleryContentControl, adding to documents
- partial document protection [Office development in Visual Studio]
- RichTextContentControl, adding to documents
- Word [Office development in Visual Studio], partial document protection
- content controls [Office development in Visual Studio], protecting
- PictureContentControl, adding to documents
- GroupContentControl, adding to documents
- document protection [Office development in Visual Studio]
- PlainTextContentControl, adding to documents
- content controls [Office development in Visual Studio], adding
- ComboBoxContentControl, adding to documents
- DatePickerContentControl, adding to documents
- Word [Office development in Visual Studio], restricted permissions
author: TerryGLee
ms.author: tglee
manager: douge
ms.workload:
- office
ms.openlocfilehash: 9ac9fbb7528559189dc74d1bf5c1d9645e47f261
ms.sourcegitcommit: 697162f54d3c4e30df702fd0289e447e211e3a85
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/25/2018
---
# <a name="how-to-add-content-controls-to-word-documents"></a>Nasıl yapılır: içerik ekleme denetimlerine Word belgeleri
  Belge düzeyi Word projelerinde, içerik denetimleri belgeye projenizde tasarım zamanında veya çalışma zamanında ekleyebilirsiniz. Word VSTO eklenti projelerinde herhangi bir açık belgeye çalışma zamanında içerik denetimleri ekleyebilirsiniz.  
  
 [!INCLUDE[appliesto_wdalldocapp](../vsto/includes/appliesto-wdalldocapp-md.md)]  
  
 Bu konuda aşağıdaki görevler açıklanmaktadır:  
  
-   [Tasarım zamanında içerik denetimleri ekleme](#designtime)  
  
-   [Belge düzeyi projesindeki çalışma zamanında içerik denetimleri ekleme](#runtimedoclevel)  
  
-   [Çalışma zamanında VSTO eklenti projesindeki içerik denetimleri ekleme](#runtimeaddin)  
  
 İçerik denetimleri hakkında daha fazla bilgi için bkz: [içerik denetimleri](../vsto/content-controls.md).  
  
##  <a name="designtime"></a> İçerik ekleme tasarım zamanında denetimleri  
 Belge düzeyi projede tasarım zamanında içerik denetimleri eklemenin birkaç yolu vardır:  
  
-   İçerik denetimden eklemek **Word denetimleri** sekmesinde **araç**.  
  
-   İçerik denetimi eklemek aynı şekilde belgenize yerel içerik denetimi Word'de eklemek.  
  
-   İçerik denetimi belgenizden sürükleyin **veri kaynakları** penceresi. Denetim oluşturulduğunda denetimi veriye bağlamak istediğinizde kullanışlıdır. Daha fazla bilgi için bkz: [nasıl yapılır: belgeleri nesne verileriyle doldurma](../vsto/how-to-populate-documents-with-data-from-objects.md) ve [nasıl yapılır: belgeleri veritabanı verileriyle doldurma](../vsto/how-to-populate-documents-with-data-from-a-database.md).  
  
 [!INCLUDE[note_settings_general](../sharepoint/includes/note-settings-general-md.md)]  
  
### <a name="to-add-a-content-control-to-a-document-by-using-the-toolbox"></a>Araç kutusu kullanarak belgeye içerik denetimi ekleme  
  
1.  İçinde barındırılan belgesinde [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)] Tasarımcısı, içerik denetimi eklemek veya değiştirmek için içerik denetimi istediğiniz metni seçin istediğiniz imleci yerleştirin.  
  
2.  Açık **araç** tıklatıp **Word denetimleri** sekmesi.  
  
3.  Denetim aşağıdaki yollardan biriyle ekleyin:  
  
    -   Bir içerik denetiminde çift **araç**.  
  
         veya  
  
    -   Bir içerik denetimi **araç** ve tuşuna basarak **Enter** anahtarı.  
  
         veya  
  
    -   İçerik denetimden sürükleyin **araç** belge. İçerik denetimi, fare işaretçisini konumu değil, belgedeki geçerli seçime eklenir.  
  
> [!NOTE]  
>  Ekleyemezsiniz bir <xref:Microsoft.Office.Tools.Word.GroupContentControl> kullanarak **araç**. Yalnızca ekleyebilirsiniz bir <xref:Microsoft.Office.Tools.Word.GroupContentControl> Word'de veya çalışma zamanında.  
  
> [!NOTE]  
>  Visual Studio araç onay kutusu içerik denetiminde sağlamaz. Bir onay kutusu içerik denetimi belgeye eklemek için oluşturmalısınız bir <xref:Microsoft.Office.Tools.Word.ContentControl> program aracılığıyla nesne. Daha fazla bilgi için bkz: [içerik denetimleri](../vsto/content-controls.md).  
  
#### <a name="to-add-a-content-control-to-a-document-in-word"></a>Bir Word belgesini içerik denetimi eklemek için  
  
1.  İçinde barındırılan belgesinde [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)] Tasarımcısı, içerik denetimi eklemek veya değiştirmek için içerik denetimi istediğiniz metni seçin istediğiniz imleci yerleştirin.  
  
2.  Şerit'te tıklatın **Geliştirici** sekmesi.  
  
    > [!NOTE]  
    >  Varsa **Geliştirici** sekmesi görünür değilse, ilk Göster gerekir. Daha fazla bilgi için bkz: [nasıl yapılır: Şeritte Geliştirici sekmesini gösterme](../vsto/how-to-show-the-developer-tab-on-the-ribbon.md).  
  
3.  İçinde **denetimleri** grubunda, eklemek istediğiniz içerik denetimi simgesini tıklatın.  
  
##  <a name="runtimedoclevel"></a> Belge düzeyi projesindeki çalışma zamanında içerik denetimleri ekleme  
 İçerik denetimleri program aracılığıyla çalışma zamanında belgenizi yöntemlerini kullanarak ekleyebileceğiniz <xref:Microsoft.Office.Tools.Word.Document.Controls%2A> özelliği `ThisDocument` projenizdeki sınıfı. Her yöntemi aşağıdaki yollarla içerik denetimi eklemek için kullanabileceğiniz üç aşırı yüklemeye sahip:  
  
-   Bir denetimi geçerli seçimi daha ekleyin.  
  
-   Belirli bir aralıkta bir denetim ekleyin.  
  
-   Belgedeki yerel içerik denetimine bağlı bir denetim ekleyin.  
  
 Dinamik olarak belge kapalı olduğunda içerik denetimleri sürdürülmez belgede oluşturuldu. Ancak, yerel bir içerik denetimi belgede kalır. Belge açıldığında bir yerel içerik denetimine bağlı bir içerik denetimi yeniden oluşturabilirsiniz. Daha fazla bilgi için bkz: [Office belgelerine çalışma zamanında denetimler ekleme](../vsto/adding-controls-to-office-documents-at-run-time.md).  
  
> [!NOTE]  
>  Word 2010 projesindeki belgeye bir onay kutusu içerik denetimi eklemek için oluşturmalısınız bir <xref:Microsoft.Office.Tools.Word.ContentControl> nesnesi. Daha fazla bilgi için bkz: [içerik denetimleri](../vsto/content-controls.md).  
  
### <a name="to-add-a-content-control-at-the-current-selection"></a>İçerik denetimi geçerli seçimi daha eklemek için  
  
1.  Kullanım bir <xref:Microsoft.Office.Tools.Word.ControlCollection> adına sahip yöntemi `Add` \< *kontrol sınıfı*> (burada *kontrol sınıfı* , gibieklemekistediğiniziçerikdenetimisınıfadı<xref:Microsoft.Office.Tools.Word.ControlCollection.AddRichTextContentControl%2A>), ve yeni denetim adı için tek bir parametreye sahip.  
  
     Aşağıdaki kod örneğinde <xref:Microsoft.Office.Tools.Word.ControlCollection.AddRichTextContentControl%2A> yeni bir ekleme yöntemi <xref:Microsoft.Office.Tools.Word.RichTextContentControl> belgenin başlangıcına. Bu kodu çalıştırmak için kodu ekleyin `ThisDocument` projenizi ve çağrı sınıfında `AddRichTextControlAtSelection` yönteminden `ThisDocument_Startup` olay işleyicisi.  
  
     [!code-csharp[Trin_ContentControlReference#700](../vsto/codesnippet/CSharp/trin_wordcontentcontrolreference/RichText.cs#700)]
     [!code-vb[Trin_ContentControlReference#700](../vsto/codesnippet/VisualBasic/trin_contentcontrolreference/RichText.vb#700)]  
  
### <a name="to-add-a-content-control-at-a-specified-range"></a>Belirli bir aralıkta içerik denetimi eklemek için  
  
1.  Kullanım bir <xref:Microsoft.Office.Tools.Word.ControlCollection> adına sahip yöntemi `Add` \< *kontrol sınıfı*> (burada *kontrol sınıfı* , gibieklemekistediğiniziçerikdenetimisınıfadı<xref:Microsoft.Office.Tools.Word.ControlCollection.AddRichTextContentControl%2A>), ve sahip bir <xref:Microsoft.Office.Interop.Word.Range> parametresi.  
  
     Aşağıdaki kod örneğinde <xref:Microsoft.Office.Tools.Word.ControlCollection.AddRichTextContentControl%2A> yeni bir ekleme yöntemi <xref:Microsoft.Office.Tools.Word.RichTextContentControl> belgenin başlangıcına. Bu kodu çalıştırmak için kodu ekleyin `ThisDocument` projenizi ve çağrı sınıfında `AddRichTextControlAtRange` yönteminden `ThisDocument_Startup` olay işleyicisi.  
  
     [!code-csharp[Trin_ContentControlReference#701](../vsto/codesnippet/CSharp/trin_wordcontentcontrolreference/RichText.cs#701)]
     [!code-vb[Trin_ContentControlReference#701](../vsto/codesnippet/VisualBasic/trin_contentcontrolreference/RichText.vb#701)]  
  
### <a name="to-add-a-content-control-that-is-based-on-a-native-content-control"></a>Yerel bir içerik denetimine bağlı bir içerik denetimi eklemek için  
  
1.  Kullanım bir <xref:Microsoft.Office.Tools.Word.ControlCollection> adına sahip yöntemi `Add` \< *kontrol sınıfı*> (burada *kontrol sınıfı* , gibieklemekistediğiniziçerikdenetimisınıfadı<xref:Microsoft.Office.Tools.Word.ControlCollection.AddRichTextContentControl%2A>), ve sahip bir `Microsoft.Office.Interop.Word.ContentControl` parametresi.  
  
     Aşağıdaki kod örneğinde <xref:Microsoft.Office.Tools.Word.ControlCollection.AddRichTextContentControl%2A> yeni yöntemi <xref:Microsoft.Office.Tools.Word.RichTextContentControl> belgedeki her yerel zengin metin denetimi için. Bu kodu çalıştırmak için kodu ekleyin `ThisDocument` projenizi ve çağrı sınıfında `CreateRichTextControlsFromNativeControls` yönteminden `ThisDocument_Startup` olay işleyicisi.  
  
     [!code-csharp[Trin_ContentControlReference#702](../vsto/codesnippet/CSharp/trin_wordcontentcontrolreference/RichText.cs#702)]
     [!code-vb[Trin_ContentControlReference#702](../vsto/codesnippet/VisualBasic/trin_contentcontrolreference/RichText.vb#702)]  
  
##  <a name="runtimeaddin"></a> Çalışma zamanında VSTO eklenti projesindeki içerik denetimleri ekleme  
 İçerik denetimlerini programlı olarak herhangi bir açık belgeye çalışma zamanında VSTO eklenti kullanarak ekleyebilirsiniz. Bunu yapmak için Oluştur bir <xref:Microsoft.Office.Tools.Word.Document> barındırma açık olan bir belgeye bağlı öğesi ve yöntemlerini kullanın <xref:Microsoft.Office.Tools.Word.Document.Controls%2A> bu konak öğesi özelliği. Her yöntemi aşağıdaki yollarla içerik denetimi eklemek için kullanabileceğiniz üç aşırı yüklemeye sahip:  
  
-   Bir denetimi geçerli seçimi daha ekleyin.  
  
-   Belirli bir aralıkta bir denetim ekleyin.  
  
-   Belgedeki yerel içerik denetimine bağlı bir denetim ekleyin.  
  
 Dinamik olarak belge kapalı olduğunda içerik denetimleri sürdürülmez belgede oluşturuldu. Ancak, yerel bir içerik denetimi belgede kalır. Belge açıldığında bir yerel içerik denetimine bağlı bir içerik denetimi yeniden oluşturabilirsiniz. Daha fazla bilgi için bkz: [Office belgelerinde Dinamik denetimleri kalıcı](../vsto/persisting-dynamic-controls-in-office-documents.md).  
  
 VSTO eklentisi projelerine konak öğeleri oluşturma hakkında daha fazla bilgi için bkz: [genişletmek Word belgelerini ve Excel çalışma kitaplarını VSTO eklentileri çalışma zamanında](../vsto/extending-word-documents-and-excel-workbooks-in-vsto-add-ins-at-run-time.md).  
  
> [!NOTE]  
>  Belge bir onay kutusu içerik denetimi eklemek için oluşturmalısınız bir <xref:Microsoft.Office.Tools.Word.ContentControl> nesnesi. Daha fazla bilgi için bkz: [içerik denetimleri](../vsto/content-controls.md).  
  
### <a name="to-add-a-content-control-at-the-current-selection"></a>İçerik denetimi geçerli seçimi daha eklemek için  
  
1.  Kullanım bir <xref:Microsoft.Office.Tools.Word.ControlCollection> adına sahip yöntemi `Add` \< *kontrol sınıfı*> (burada *kontrol sınıfı* , gibieklemekistediğiniziçerikdenetimisınıfadı<xref:Microsoft.Office.Tools.Word.ControlCollection.AddRichTextContentControl%2A>), ve yeni denetim adı için tek bir parametreye sahip.  
  
     Aşağıdaki kod örneğinde <xref:Microsoft.Office.Tools.Word.ControlCollection.AddRichTextContentControl%2A> yeni bir ekleme yöntemi <xref:Microsoft.Office.Tools.Word.RichTextContentControl> etkin belgenin başlangıcına. Bu kodu çalıştırmak için kodu ekleyin `ThisAddIn` projenizi ve çağrı sınıfında `AddRichTextControlAtSelection` yönteminden `ThisAddIn_Startup` olay işleyicisi.  
  
     [!code-vb[Trin_WordAddInDynamicControls#1](../vsto/codesnippet/VisualBasic/trin_wordaddindynamiccontrols/ThisAddIn.vb#1)]
     [!code-csharp[Trin_WordAddInDynamicControls#1](../vsto/codesnippet/CSharp/Trin_WordAddInDynamicControls/ThisAddIn.cs#1)]  
  
### <a name="to-add-a-content-control-at-a-specified-range"></a>Belirli bir aralıkta içerik denetimi eklemek için  
  
1.  Kullanım bir <xref:Microsoft.Office.Tools.Word.ControlCollection> adına sahip yöntemi `Add` \< *kontrol sınıfı*> (burada *kontrol sınıfı* , gibieklemekistediğiniziçerikdenetimisınıfadı<xref:Microsoft.Office.Tools.Word.ControlCollection.AddRichTextContentControl%2A>), ve sahip bir <xref:Microsoft.Office.Interop.Word.Range> parametresi.  
  
     Aşağıdaki kod örneğinde <xref:Microsoft.Office.Tools.Word.ControlCollection.AddRichTextContentControl%2A> yeni bir ekleme yöntemi <xref:Microsoft.Office.Tools.Word.RichTextContentControl> etkin belgenin başlangıcına. Bu kodu çalıştırmak için kodu ekleyin `ThisAddIn` projenizi ve çağrı sınıfında `AddRichTextControlAtRange` yönteminden `ThisAddIn_Startup` olay işleyicisi.  
  
     [!code-vb[Trin_WordAddInDynamicControls#2](../vsto/codesnippet/VisualBasic/trin_wordaddindynamiccontrols/ThisAddIn.vb#2)]
     [!code-csharp[Trin_WordAddInDynamicControls#2](../vsto/codesnippet/CSharp/Trin_WordAddInDynamicControls/ThisAddIn.cs#2)]  
  
#### <a name="to-add-a-content-control-that-is-based-on-a-native-content-control"></a>Yerel bir içerik denetimine bağlı bir içerik denetimi eklemek için  
  
1.  Kullanım bir <xref:Microsoft.Office.Tools.Word.ControlCollection> adına sahip yöntemi `Add` \< *kontrol sınıfı*> (burada *kontrol sınıfı* , gibieklemekistediğiniziçerikdenetimisınıfadı<xref:Microsoft.Office.Tools.Word.ControlCollection.AddRichTextContentControl%2A>), ve sahip bir `Microsoft.Office.Interop.Word.ContentControl` parametresi.  
  
     Aşağıdaki kod örneğinde <xref:Microsoft.Office.Tools.Word.ControlCollection.AddRichTextContentControl%2A> yeni yöntemi <xref:Microsoft.Office.Tools.Word.RichTextContentControl> belge açıldıktan sonra bir belgedeki her yerel zengin metin denetimi için. Bu kodu çalıştırmak için kodu ekleyin `ThisAddIn` projenizdeki sınıfı.  
  
     [!code-vb[Trin_WordAddInDynamicControls#3](../vsto/codesnippet/VisualBasic/trin_wordaddindynamiccontrols/ThisAddIn.vb#3)]
     [!code-csharp[Trin_WordAddInDynamicControls#3](../vsto/codesnippet/CSharp/Trin_WordAddInDynamicControls/ThisAddIn.cs#3)]  
  
     C# ' de ekleyebilirsiniz gerekir `Application_DocumentOpen` olay işleyicisine <xref:Microsoft.Office.Interop.Word.ApplicationEvents4_Event.DocumentOpen> olay.  
  
     [!code-csharp[Trin_WordAddInDynamicControls#6](../vsto/codesnippet/CSharp/Trin_WordAddInDynamicControls/ThisAddIn.cs#6)]  
  
## <a name="see-also"></a>Ayrıca bkz.  
 [Genişletilmiş nesneleri kullanarak Word otomatikleştirme](../vsto/automating-word-by-using-extended-objects.md)   
 [Konak öğelerine ve denetimlerine genel bakış](../vsto/host-items-and-host-controls-overview.md)   
 [Office belgelerine çalışma zamanında denetimler ekleme](../vsto/adding-controls-to-office-documents-at-run-time.md)   
 [Konak denetimlerinin ve konak öğelerinin programlama sınırlamaları](../vsto/programmatic-limitations-of-host-items-and-host-controls.md)   
 [VSTO eklentilerini programlama](../vsto/programming-vsto-add-ins.md)   
 [Belge düzeyi özelleştirmelerini programlama](../vsto/programming-document-level-customizations.md)  
  