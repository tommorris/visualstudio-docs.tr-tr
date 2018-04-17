---
title: 'İzlenecek yol: Denetimlerini çalışma zamanında VSTO eklenti belgeye ekleme | Microsoft Docs'
ms.custom: ''
ms.date: 02/02/2017
ms.technology:
- office-development
ms.topic: conceptual
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- add-ins [Office development in Visual Studio], adding controls
- application-level add-ins [Office development in Visual Studio], adding controls
- controls [Office development in Visual Studio], adding to documents at run time
- documents [Office development in Visual Studio], adding controls at run time
author: TerryGLee
ms.author: tglee
manager: douge
ms.workload:
- office
ms.openlocfilehash: 1f26a60bdbd0db2464a8ac479b7534fb63f18cea
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/16/2018
---
# <a name="walkthrough-adding-controls-to-a-document-at-run-time-in-a-vsto-add-in"></a>İzlenecek yol: Denetimlerini çalışma zamanında VSTO eklenti belgeye ekleme
  Bir VSTO eklenti kullanarak tüm açık Microsoft Office Word belgesine denetimleri ekleyebilirsiniz. Bu anlatımda Şerit eklemek kullanıcıların sağlamak için nasıl kullanılacağı gösterilir bir <xref:Microsoft.Office.Tools.Word.Controls.Button> veya <xref:Microsoft.Office.Tools.Word.RichTextContentControl> belgeye.  
  
 **Uygulandığı öğe:** Bu konu başlığı altındaki bilgiler Word 2010 VSTO eklentisi projelerine yöneliktir. Daha fazla bilgi için bkz: [Office uygulaması ve proje türüne göre kullanılabilen özellikler](../vsto/features-available-by-office-application-and-project-type.md).  
  
 Bu izlenecek yol aşağıdaki görevleri gösterir:  
  
-   Yeni bir Word VSTO eklenti projesi oluşturma.  
  
-   Bir kullanıcı arabirimi (UI) denetim eklemek için belgeye sağlama.  
  
-   Denetimleri belgeye çalışma zamanında ekleme.  
  
-   Denetimleri belgeden kaldırma.  
  
 [!INCLUDE[note_settings_general](../sharepoint/includes/note-settings-general-md.md)]  
  
## <a name="prerequisites"></a>Önkoşullar  
 Bu izlenecek yolu tamamlamak için aşağıdaki bileşenlere ihtiyacınız vardır:  
  
-   [!INCLUDE[vsto_vsprereq](../vsto/includes/vsto-vsprereq-md.md)]  
  
-   [!INCLUDE[Word_15_short](../vsto/includes/word-15-short-md.md)] veya [!INCLUDE[Word_14_short](../vsto/includes/word-14-short-md.md)].  
  
## <a name="creating-a-new-word-add-in-project"></a>Yeni Word eklenti projesi oluşturma  
 Word VSTO eklenti projesi oluşturarak başlayın.  
  
#### <a name="to-create-a-new-word-vsto-add-in-project"></a>Yeni bir Word VSTO eklenti projesi oluşturmak için  
  
1.  Adlı Word için VSTO eklenti projesindeki oluşturun **WordDynamicControls**. Daha fazla bilgi için bkz: [nasıl yapılır: Visual Studio'da Office projeleri oluşturma](../vsto/how-to-create-office-projects-in-visual-studio.md).  
  
2.  Bir başvuru ekleyin **Microsoft.Office.Tools.Word.v4.0.Utilities.dll** derleme. Bu başvuru, bu kılavuzda daha sonra belgeyi program aracılığıyla bir Windows Forms denetimi eklemek için gereklidir.  
  
## <a name="providing-a-ui-to-add-controls-to-a-document"></a>Belge denetimleri eklemek için bir UI sağlama  
 Özel sekme Word Şeritte ekleyin. Kullanıcılar, bir belgeye denetimleri eklemek için sekmedeki onay kutularını seçebilirsiniz.  
  
#### <a name="to-provide-a-ui-to-add-controls-to-a-document"></a>Belge denetimleri eklemek için bir kullanıcı Arabirimi sağlamak için  
  
1.  Üzerinde **proje** menüsünde tıklatın **Yeni Öğe Ekle**.  
  
2.  İçinde **Yeni Öğe Ekle** iletişim kutusunda **Şerit (Görsel Tasarımcı)**.  
  
3.  Yeni Şerit adını değiştirmek **MyRibbon**, tıklatıp **Ekle**.  
  
     **MyRibbon.cs** veya **MyRibbon.vb** dosyası Şerit Tasarımcısı'nda açılır ve varsayılan bir sekme ve grup görüntüler.  
  
4.  Şerit Tasarımcısı'nda tıklatın **group1** grubu.  
  
5.  İçinde **özellikleri** penceresinde, değişiklik **etiket** özelliği için **group1** için **Denetimler Ekle**.  
  
6.  Gelen **Office Şerit denetimleri** sekmesinde **araç**, sürükleyin bir **onay kutusunu** üzerine kontrol **group1**.  
  
7.  Tıklatın **CheckBox1** seçin.  
  
8.  İçinde **özellikleri** penceresinde, aşağıdaki özellikleri değiştirin.  
  
    |Özellik|Değer|  
    |--------------|-----------|  
    |**Ad**|**addButtonCheckBox**|  
    |**Etiket**|**Ekle düğmesi**|  
  
9. İkinci bir onay kutusu eklemek **group1**ve ardından aşağıdaki özellikleri değiştirin.  
  
    |Özellik|Değer|  
    |--------------|-----------|  
    |**Ad**|**addRichTextCheckBox**|  
    |**Etiket**|**Zengin Metin Denetimi Ekle**|  
  
10. Şerit Tasarımcısı'nda çift **Ekle düğmesi**.  
  
     <xref:Microsoft.Office.Tools.Ribbon.RibbonCheckBox.Click> Olay işleyicisi **Ekle düğmesi** onay kutusu Kod Düzenleyicisi'nde açılır.  
  
11. Çift tıklayın ve döndürmek için Şerit Tasarımcısı **zengin metin denetimi Ekle**.  
  
     <xref:Microsoft.Office.Tools.Ribbon.RibbonCheckBox.Click> Olay işleyicisi **zengin metin denetimi Ekle** onay kutusu Kod Düzenleyicisi'nde açılır.  
  
 Bu kılavuzda daha sonra etkin belgede denetimleri eklemek ve kaldırmak için bu olay işleyicileri için kod ekleyeceksiniz.  
  
## <a name="adding-and-removing-controls-on-the-active-document"></a>Ekleme ve etkin belgede denetimleri kaldırma  
 VSTO eklenti kodu etkin belgeye dönüştürmeniz gerekir bir <xref:Microsoft.Office.Tools.Word.Document> *konak öğesi* bir denetim eklemeden önce. Office çözümlerinde denetimleri için kapsayıcılar olarak davranan konak öğelerine yönetilen denetimler eklenebilir. VSTO eklenti projelerinde konak öğeleri GetVstoObject yöntemi kullanarak çalışma zamanında oluşturulabilir.  
  
 Yöntemlere ekleme `ThisAddIn` eklemek veya kaldırmak için çağrılabilir sınıfı bir <xref:Microsoft.Office.Tools.Word.Controls.Button> veya <xref:Microsoft.Office.Tools.Word.RichTextContentControl> etkin belgede. Bu kılavuzda daha sonra bu yöntemlerden çağıracak <xref:Microsoft.Office.Tools.Ribbon.RibbonCheckBox.Click> olay işleyicileri Şerit üzerindeki onay kutularının.  
  
#### <a name="to-add-and-remove-controls-on-the-active-document"></a>Etkin belgede denetimleri eklemek ve kaldırmak için  
  
1.  İçinde **Çözüm Gezgini**, ThisAddIn.cs veya ThisAddIn.vb kod düzenleyicisinde dosyayı açmak için çift tıklayın.  
  
2.  Aşağıdaki kodu ekleyin `ThisAddIn` sınıfı. Bu kod bildirir <xref:Microsoft.Office.Tools.Word.Controls.Button> ve <xref:Microsoft.Office.Tools.Word.RichTextContentControl> belgeye eklenecek denetimleri temsil eden nesne.  
  
     [!code-vb[Trin_WordAddInDynamicControlsWalkthrough#1](../vsto/codesnippet/VisualBasic/Trin_WordAddInDynamicControlsWalkthrough/ThisAddIn.vb#1)]
     [!code-csharp[Trin_WordAddInDynamicControlsWalkthrough#1](../vsto/codesnippet/CSharp/Trin_WordAddInDynamicControlsWalkthrough/ThisAddIn.cs#1)]  
  
3.  Aşağıdaki yöntemi ekleyin `ThisAddIn` sınıfı. Kullanıcı tıkladığında **Ekle düğmesi** Şerit üzerindeki onay kutusunu, bu yöntem ekler bir <xref:Microsoft.Office.Tools.Word.Controls.Button> onay kutusunun seçili olduğundan geçerli seçime <xref:Microsoft.Office.Tools.Word.Controls.Button> onay kutusu işaretli değilse.  
  
     [!code-vb[Trin_WordAddInDynamicControlsWalkthrough#2](../vsto/codesnippet/VisualBasic/Trin_WordAddInDynamicControlsWalkthrough/ThisAddIn.vb#2)]
     [!code-csharp[Trin_WordAddInDynamicControlsWalkthrough#2](../vsto/codesnippet/CSharp/Trin_WordAddInDynamicControlsWalkthrough/ThisAddIn.cs#2)]  
  
4.  Aşağıdaki yöntemi ekleyin `ThisAddIn` sınıfı. Kullanıcı tıkladığında **zengin metin denetimi Ekle** Şerit üzerindeki onay kutusunu, bu yöntem ekler bir <xref:Microsoft.Office.Tools.Word.RichTextContentControl> onay kutusunun seçili olduğundan geçerli seçime <xref:Microsoft.Office.Tools.Word.RichTextContentControl> onay kutusu işaretli değilse.  
  
     [!code-vb[Trin_WordAddInDynamicControlsWalkthrough#3](../vsto/codesnippet/VisualBasic/Trin_WordAddInDynamicControlsWalkthrough/ThisAddIn.vb#3)]
     [!code-csharp[Trin_WordAddInDynamicControlsWalkthrough#3](../vsto/codesnippet/CSharp/Trin_WordAddInDynamicControlsWalkthrough/ThisAddIn.cs#3)]  
  
## <a name="removing-the-button-control-when-the-document-is-saved"></a>Düğme denetimi belge kaldırma kaydedilir  
 Belge kaydedildiğinde ve sonra kapalı olduğunda Windows Forms denetimleri kalıcı değildir. Ancak, her denetim için ActiveX sarmalayıcısı belgede kalır ve belgeyi yeniden açıldığında, bu sarmalayıcının kenarlığı son kullanıcılar tarafından görülebilir. VSTO eklentileri dinamik olarak oluşturulan Windows Forms denetimlerinde temizlemek için birkaç yolu vardır. Bu kılavuzda, program aracılığıyla kaldırdığınız <xref:Microsoft.Office.Tools.Word.Controls.Button> zaman Belge kaydedildiğinde denetim.  
  
#### <a name="to-remove-the-button-control-when-the-document-is-saved"></a>Belge kaydedildiğinde düğme denetimini kaldırmak için  
  
1.  ThisAddIn.cs veya ThisAddIn.vb kod dosyasında aşağıdaki yöntemi ekleyin `ThisAddIn` sınıfı. Bu yöntem için bir olay işleyicisidir <xref:Microsoft.Office.Interop.Word.ApplicationEvents4_Event.DocumentBeforeSave> olay. Kaydedilen belge varsa bir <xref:Microsoft.Office.Tools.Word.Document> , olay işleyicisi ilişkili konak öğesi konak öğesi alır ve kaldırır <xref:Microsoft.Office.Tools.Word.Controls.Button> denetim varsa.  
  
     [!code-vb[Trin_WordAddInDynamicControlsWalkthrough#4](../vsto/codesnippet/VisualBasic/Trin_WordAddInDynamicControlsWalkthrough/ThisAddIn.vb#4)]
     [!code-csharp[Trin_WordAddInDynamicControlsWalkthrough#4](../vsto/codesnippet/CSharp/Trin_WordAddInDynamicControlsWalkthrough/ThisAddIn.cs#4)]  
  
2.  C# ' ta aşağıdaki kodu ekleyin `ThisAddIn_Startup` olay işleyicisi. Bu kod C# ' ta bağlanmak için gerekli `Application_DocumentBeforeSave` olay işleyicisi ile <xref:Microsoft.Office.Interop.Word.ApplicationEvents4_Event.DocumentBeforeSave> olay.  
  
     [!code-csharp[Trin_WordAddInDynamicControlsWalkthrough#5](../vsto/codesnippet/CSharp/Trin_WordAddInDynamicControlsWalkthrough/ThisAddIn.cs#5)]  
  
## <a name="adding-and-removing-controls-when-the-user-clicks-the-check-boxes-on-the-ribbon"></a>Kullanıcı Şerit üzerindeki onay kutularını tıkladığında ekleme ve kaldırma denetimleri  
 Son olarak, değişiklik <xref:Microsoft.Office.Tools.Ribbon.RibbonCheckBox.Click> olay işleyicileri onay kutularının eklediğiniz Şerit denetimleri belgesinde eklemek veya kaldırmak için.  
  
#### <a name="to-add-or-remove-controls-when-the-user-clicks-the-check-boxes-on-the-ribbon"></a>Kullanıcı Şerit üzerindeki onay kutularını tıkladığında eklemek veya kaldırmak için denetimleri  
  
1.  MyRibbon.cs veya MyRibbon.vb kod dosyasında oluşturulan Değiştir `addButtonCheckBox_Click` ve `addRichTextCheckBox_Click` aşağıdaki kod ile olay işleyicileri. Bu kod çağırmak için bu olay işleyicilerini yeniden tanımlamaktadır `ToggleButtonOnDocument` ve `ToggleRichTextControlOnDocument` eklediğiniz yöntemleri `ThisAddIn` bu kılavuzda daha önce sınıfı.  
  
     [!code-vb[Trin_WordAddInDynamicControlsWalkthrough#6](../vsto/codesnippet/VisualBasic/Trin_WordAddInDynamicControlsWalkthrough/MyRibbon.vb#6)]
     [!code-csharp[Trin_WordAddInDynamicControlsWalkthrough#6](../vsto/codesnippet/CSharp/Trin_WordAddInDynamicControlsWalkthrough/MyRibbon.cs#6)]  
  
## <a name="testing-the-solution"></a>Çözüm test ediliyor  
 Denetimleri Şerit üzerindeki özel sekmesinden seçerek belgeye ekleyin. Belgeyi kaydettiğinizde, <xref:Microsoft.Office.Tools.Word.Controls.Button> denetimi kaldırılır.  
  
#### <a name="to-test-the-solution"></a>Çözüm test etmek için.  
  
1.  Projenizi çalıştırmak için F5 tuşuna basın.  
  
2.  Etkin belgedeki birkaç kez yeni boş paragraflar belgeye eklemek için basın.  
  
3.  İlk paragrafa seçin.  
  
4.  Tıklatın **eklentileri** sekmesi.  
  
5.  İçinde **Denetimler Ekle** grubunda **Ekle düğmesi**.  
  
     İlk paragrafa bir düğme görüntülenir.  
  
6.  Son paragrafı seçin.  
  
7.  İçinde **Denetimler Ekle** grubunda **zengin metin denetimi Ekle**.  
  
     Zengin metin içeriği denetimi son paragraf eklenir.  
  
8.  Belgeyi kaydedin.  
  
     Düğme belgeden kaldırılır.  
  
## <a name="next-steps"></a>Sonraki Adımlar  
 VSTO eklentileri aşağıdaki konulardan denetimleri hakkında daha fazla bilgi edinebilirsiniz:  
  
-   Word Eklentisi Dinamik Denetim Örneği'diğer türlerde denetimleri belgeye çalışma zamanında ekleme ve belgeyi yeniden açıldığında denetimleri yeniden nasıl oluşturulduğunu gösteren bir örnek için bkz: [Office geliştirme örnekleri ve izlenecek yollar](../vsto/office-development-samples-and-walkthroughs.md).  
  
-   Excel için VSTO eklenti kullanarak çalışma sayfasına denetimler ekleme nasıl izlenecek yol için bkz: [izlenecek yol: ekleme denetimlerini çalışma zamanında VSTO eklenti proje](../vsto/walkthrough-adding-controls-to-a-worksheet-at-run-time-in-vsto-add-in-project.md).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Word çözümleri](../vsto/word-solutions.md)   
 [Office belgelerine çalışma zamanında denetimler ekleme](../vsto/adding-controls-to-office-documents-at-run-time.md)   
 [Office belgelerinde Dinamik denetimleri kalıcı kılma](../vsto/persisting-dynamic-controls-in-office-documents.md)   
 [Nasıl yapılır: Windows Forms denetimleri Office belgelerine ekleme](../vsto/how-to-add-windows-forms-controls-to-office-documents.md)   
 [Nasıl yapılır: Word belgelerine içerik denetimleri ekleme](../vsto/how-to-add-content-controls-to-word-documents.md)   
 [VSTO Eklentilerindeki Word Belgelerini ve Excel Çalışma Kitaplarını Çalışma Zamanında Genişletme](../vsto/extending-word-documents-and-excel-workbooks-in-vsto-add-ins-at-run-time.md)  
  
  