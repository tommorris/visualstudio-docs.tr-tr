---
title: "Nasıl yapılır: Word belgelerine yer işareti denetimi ekleme | Microsoft Docs"
ms.custom: 
ms.date: 02/02/2017
ms.reviewer: 
ms.suite: 
ms.technology:
- office-development
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- VST.Bookmark.Dialog
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- Bookmark control, adding to documents
- Create Bookmark Control dialog box
- controls [Office development in Visual Studio], adding to documents
author: TerryGLee
ms.author: tglee
manager: ghogen
ms.workload:
- office
ms.openlocfilehash: 2ebe8536887f2f60876b64407ffb96cdaf4618c9
ms.sourcegitcommit: f9fbf1f55f9ac14e4e5c6ae58c30dc1800ca6cda
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/10/2018
---
# <a name="how-to-add-bookmark-controls-to-word-documents"></a>Nasıl Yapılır: Word Belgelerine Yer İşareti Denetimi Ekleme
  Belge düzeyi projelerine eklediğiniz <xref:Microsoft.Office.Tools.Word.Bookmark> belgenin projenizdeki tasarım zamanında veya çalışma zamanında denetimler. VSTO eklenti projelerinde eklediğiniz <xref:Microsoft.Office.Tools.Word.Bookmark> herhangi bir açık belgeye çalışma zamanında denetimler.  
  
 [!INCLUDE[appliesto_wdalldocapp](../vsto/includes/appliesto-wdalldocapp-md.md)]  
  
 Bu konuda aşağıdaki görevler açıklanmaktadır:  
  
-   [Tasarım zamanında yer işareti denetimi ekleme](#designtime)  
  
-   [Belge düzeyi projesindeki çalışma zamanında yer işareti denetimi ekleme](#runtimedoclevel)  
  
-   [Çalışma zamanında VSTO eklenti projesindeki yer işareti denetimi ekleme](#runtimeaddin)  
  
 Hakkında daha fazla bilgi için <xref:Microsoft.Office.Tools.Word.Bookmark> denetimleri bkz [yer işareti denetimi](../vsto/bookmark-control.md).  
  
##  <a name="designtime"></a>Tasarım zamanında yer işareti denetimi ekleme  
 Eklemek için çeşitli yollar vardır <xref:Microsoft.Office.Tools.Word.Bookmark> tasarım zamanında belge düzeyi projesindeki belgeye denetimleri:  
  
-   Visual Studio'dan **araç**.  
  
     Sürükleyebilirsiniz <xref:Microsoft.Office.Tools.Word.Bookmark> gelen denetim **araç** belgenize. Zaten kullanıyorsanız, bu şekilde seçmek isteyebilirsiniz **araç** belgenize Windows Forms denetimleri eklemek için.  
  
-   Word'ün içinden.  
  
     Ekleyebileceğiniz <xref:Microsoft.Office.Tools.Word.Bookmark> denetim yerel yer işareti eklediğiniz belgenizi aynı şekilde. Bu şekilde ekleme avantajı, oluşturduğunuz zamanında denetiminizi adlandırabilirsiniz olmasıdır.  
  
-   Gelen **veri kaynakları** penceresi.  
  
     Sürükleyebilirsiniz <xref:Microsoft.Office.Tools.Word.Bookmark> belgenizden denetimine **veri kaynakları** penceresi. Denetimi aynı anda verilere bağlama istediğinizde kullanışlıdır. Aynı şekilde bir Windows Form denetiminden eklediğiniz konak kontrolü ekleyebilirsiniz **veri kaynakları** penceresi. Daha fazla bilgi için bkz: [verileri bağlama ve Windows Forms](/dotnet/framework/winforms/data-binding-and-windows-forms).  
  
 [!INCLUDE[note_settings_general](../sharepoint/includes/note-settings-general-md.md)]  
  
#### <a name="to-add-a-bookmark-control-to-a-document-from-the-toolbox"></a>Araç Kutusu'ndan bir belge için bir yer işareti denetimi eklemek için  
  
1.  Açık **araç** tıklatıp **Word denetimleri** sekmesi.  
  
2.  Sürükleme bir <xref:Microsoft.Office.Tools.Word.Bookmark> belgeye denetim.  
  
     **Yer işareti Ekle** iletişim kutusu görüntülenir.  
  
3.  Metin veya işaretinde dahil etmek istediğiniz diğer öğeleri seçin.  
  
4.  **Tamam**'ı tıklatın.  
  
     Varsayılan yer işareti adını tutmak istemiyorsanız adını değiştirebilirsiniz **özellikleri** penceresi.  
  
#### <a name="to-add-a-bookmark-control-to-a-document-in-word"></a>Bir Word belgesini bir yer işareti denetimi eklemek için  
  
1.  İçinde barındırılan belgesinde [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)] Tasarımcısı, yer işareti ekleyin veya yer işaretinin içermesini istediğiniz metni seçin istediğiniz imleci yerleştirin.  
  
2.  Üzerinde **Ekle** Şerit sekmesi, **bağlantılar** grubunda **yer işareti** düğmesi.  
  
3.  İçinde **yer işareti** iletişim kutusunda, yeni yer işaretinin adını yazın ve tıklatın **Ekle**.  
  
##  <a name="runtimedoclevel"></a>Belge düzeyi projesindeki çalışma zamanında yer işareti denetimi ekleme  
 Ekleyebileceğiniz <xref:Microsoft.Office.Tools.Word.Bookmark> denetimlerini programlı olarak belgenize çalışma zamanında yöntemlerini kullanarak <xref:Microsoft.Office.Tools.Word.Document.Controls%2A> özelliği `ThisDocument` projenizdeki sınıfı. Eklemek için kullanabileceğiniz iki yöntem aşırı bir <xref:Microsoft.Office.Tools.Word.Bookmark> aşağıdaki yollarla denetimi:  
  
-   Ekleme bir <xref:Microsoft.Office.Tools.Word.Bookmark> belirtilen aralıkta.  
  
-   Ekleme bir <xref:Microsoft.Office.Tools.Word.Bookmark> belgesindeki yerel bir yer işareti dayanır (diğer bir deyişle, bir <xref:Microsoft.Office.Interop.Word.Bookmark>).  
  
 Dinamik olarak oluşturulan <xref:Microsoft.Office.Tools.Word.Bookmark> denetimleri kalıcı değildir belgede belge kapalı olduğunda. Ancak, yerel <xref:Microsoft.Office.Interop.Word.Bookmark> belgede kalır. Yeniden oluşturabilirsiniz bir <xref:Microsoft.Office.Tools.Word.Bookmark> dayanan yerel bir yer işareti belgenin sonraki açılışında. Daha fazla bilgi için bkz: [Office belgelerine çalışma zamanında denetimler ekleme](../vsto/adding-controls-to-office-documents-at-run-time.md).  
  
#### <a name="to-add-a-bookmark-control-to-a-document-programmatically"></a>Bir yer işareti denetimi belgeye programlı olarak eklemek için  
  
1.  İçinde `ThisDocument_Startup` projenizdeki olay işleyicisi ekleme eklemek için aşağıdaki kodu <xref:Microsoft.Office.Tools.Word.Bookmark> belgede ilk paragrafa denetimine.  
  
     [!code-csharp[Trin_VstcoreHostControlsWord#1](../vsto/codesnippet/CSharp/trin_vstcorehostcontrolsword/ThisDocument.cs#1)]
     [!code-vb[Trin_VstcoreHostControlsWord#1](../vsto/codesnippet/VisualBasic/Trin_VstcoreHostControlsWordVB/ThisDocument.vb#1)]  
  
    > [!NOTE]  
    >  Oluşturmak istiyorsanız bir <xref:Microsoft.Office.Tools.Word.Bookmark> varolan bir denetim <xref:Microsoft.Office.Interop.Word.Bookmark>, kullanın <xref:Microsoft.Office.Tools.Word.ControlCollection.AddBookmark%2A> yöntemi ve varolan geçirin <xref:Microsoft.Office.Interop.Word.Bookmark>.  
  
##  <a name="runtimeaddin"></a>VSTO eklenti projesindeki çalışma zamanında ekleme yer işareti denetimi  
 Ekleyebileceğiniz <xref:Microsoft.Office.Tools.Word.Bookmark> denetimlerine programlı olarak herhangi bir açık belgeye çalışma zamanında VSTO eklenti kullanarak. Bunu yapmak için Oluştur bir <xref:Microsoft.Office.Tools.Word.Document> barındırma açık olan bir belgeye bağlı öğesi ve yöntemlerini kullanın <xref:Microsoft.Office.Tools.Word.Document.Controls%2A> bu konak öğesi özelliği. Eklemek için kullanabileceğiniz iki yöntem aşırı bir <xref:Microsoft.Office.Tools.Word.Bookmark> aşağıdaki yollarla denetimi:  
  
-   Ekleme bir <xref:Microsoft.Office.Tools.Word.Bookmark> belirtilen aralıkta.  
  
-   Ekleme bir <xref:Microsoft.Office.Tools.Word.Bookmark> belgesindeki yerel bir yer işareti dayanır (diğer bir deyişle, bir <xref:Microsoft.Office.Interop.Word.Bookmark>).  
  
 Dinamik olarak oluşturulan <xref:Microsoft.Office.Tools.Word.Bookmark> denetimleri kalıcı değildir belgede belge kapalı olduğunda. Ancak, yerel <xref:Microsoft.Office.Interop.Word.Bookmark> belgede kalır. Yeniden oluşturabilirsiniz bir <xref:Microsoft.Office.Tools.Word.Bookmark> dayanan yerel bir yer işareti belgenin sonraki açılışında. Daha fazla bilgi için bkz: [Office belgelerinde Dinamik denetimleri kalıcı kılma](../vsto/persisting-dynamic-controls-in-office-documents.md).  
  
 VSTO eklentisi projelerine konak öğeleri oluşturma hakkında daha fazla bilgi için bkz: [genişletme Word belgelerini ve Excel çalışma kitaplarını VSTO eklentileri çalışma zamanında](../vsto/extending-word-documents-and-excel-workbooks-in-vsto-add-ins-at-run-time.md).  
  
#### <a name="to-add-a-bookmark-control-at-a-specified-range"></a>Belirli bir aralıkta bir yer işareti denetimi eklemek için  
  
1.  Kullanım <xref:Microsoft.Office.Tools.Word.ControlCollection.AddBookmark%2A> yöntemi ve geçişinde <xref:Microsoft.Office.Interop.Word.Range> , eklemek istediğiniz <xref:Microsoft.Office.Tools.Word.Bookmark>.  
  
     Aşağıdaki kod örneğinde yeni ekler <xref:Microsoft.Office.Tools.Word.Bookmark> etkin belgenin başlangıcına. Bu örneği kullanmak için kodu çalıştırın `ThisAddIn_Startup` Word VSTO eklenti projesindeki olay işleyicisi.  
  
     [!code-vb[Trin_WordAddInDynamicControls#4](../vsto/codesnippet/VisualBasic/trin_wordaddindynamiccontrols/ThisAddIn.vb#4)]
     [!code-csharp[Trin_WordAddInDynamicControls#4](../vsto/codesnippet/CSharp/Trin_WordAddInDynamicControls/ThisAddIn.cs#4)]  
  
#### <a name="to-add-a-bookmark-control-that-is-based-on-a-native-bookmark-control"></a>Yerel bir yer işareti denetimine bağlı bir yer işareti denetimi ekleme  
  
1.  Kullanmak <xref:Microsoft.Office.Tools.Word.ControlCollection.AddBookmark%2A> yöntemi ve varolan geçirin <xref:Microsoft.Office.Interop.Word.Bookmark> temel olarak yeni için kullanmak istediğiniz <xref:Microsoft.Office.Tools.Word.Bookmark>.  
  
     Aşağıdaki kod örneğinde yeni bir oluşturur <xref:Microsoft.Office.Tools.Word.Bookmark> yani ilk göre <xref:Microsoft.Office.Interop.Word.Bookmark> etkin belgedeki. Bu örneği kullanmak için kodu çalıştırın `ThisAddIn_Startup` Word VSTO eklenti projesindeki olay işleyicisi.  
  
     [!code-vb[Trin_WordAddInDynamicControls#5](../vsto/codesnippet/VisualBasic/trin_wordaddindynamiccontrols/ThisAddIn.vb#5)]
     [!code-csharp[Trin_WordAddInDynamicControls#5](../vsto/codesnippet/CSharp/Trin_WordAddInDynamicControls/ThisAddIn.cs#5)]  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Genişletilmiş nesneleri kullanarak Word'ü Otomatikleştirme](../vsto/automating-word-by-using-extended-objects.md)   
 [Konak öğelerine ve denetimlerine genel bakış](../vsto/host-items-and-host-controls-overview.md)   
 [Office belgelerine çalışma zamanında denetimler ekleme](../vsto/adding-controls-to-office-documents-at-run-time.md)   
 [Konak denetimlerinin ve konak öğelerinin programlama sınırlamaları](../vsto/programmatic-limitations-of-host-items-and-host-controls.md)   
 [VSTO eklentilerini programlama](../vsto/programming-vsto-add-ins.md)   
 [Belge düzeyi özelleştirmelerini programlama](../vsto/programming-document-level-customizations.md)   
 [Nasıl Yapılır: Yer İşareti Denetimlerini Yeniden Boyutlandırma](../vsto/how-to-resize-bookmark-controls.md)  
  
  