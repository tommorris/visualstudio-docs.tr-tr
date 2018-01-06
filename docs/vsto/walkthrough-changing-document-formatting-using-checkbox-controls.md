---
title: "İzlenecek yol: CheckBox denetimlerini kullanarak belge biçimlendirmesini değiştirme | Microsoft Docs"
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
- Word documents, changing formatting using controls
- documents [Office development in Visual Studio], formatting
- check boxes, Word documents
- documents [Office development in Visual Studio], check box controls
- controls [Office development in Visual Studio], adding to documents
ms.assetid: 3740e41d-a57e-43bb-87e7-6e5481ef290b
caps.latest.revision: "70"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload: office
ms.openlocfilehash: a0c8d44c32c03f98a0d2621eff3899ded101b7d3
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/22/2017
---
# <a name="walkthrough-changing-document-formatting-using-checkbox-controls"></a>İzlenecek Yol: CheckBox Denetimlerini Kullanarak Belge Biçimlendirmesini Değiştirme
  Bu kılavuzda Windows Forms denetimleri Microsoft Office Word için belge düzeyi özelleştirmelerinde metin biçimlendirmesini değiştirmek için nasıl kullanılacağını gösterir.  
  
 [!INCLUDE[appliesto_wdalldoc](../vsto/includes/appliesto-wdalldoc-md.md)]  
  
 Bu izlenecek yol aşağıdaki görevleri gösterir:  
  
-   Belge düzeyi projesindeki belgeye metin ve bir denetim tasarım zamanında ekleniyor.  
  
-   Bir seçenek belirlendiğinde, metin biçimlendirmesini.  
  
 Sonuç tamamlanmış bir örnek görmek için Word denetimleri örneğine bakın [Office geliştirme örnekleri ve izlenecek yollar](../vsto/office-development-samples-and-walkthroughs.md).  
  
 [!INCLUDE[note_settings_general](../sharepoint/includes/note-settings-general-md.md)]  
  
## <a name="prerequisites"></a>Önkoşullar  
 Bu izlenecek yolu tamamlamak için aşağıdaki bileşenlere ihtiyacınız vardır:  
  
-   [!INCLUDE[vsto_vsprereq](../vsto/includes/vsto-vsprereq-md.md)]  
  
-   [!INCLUDE[Word_15_short](../vsto/includes/word-15-short-md.md)]veya [!INCLUDE[Word_14_short](../vsto/includes/word-14-short-md.md)].  
  
## <a name="creating-the-project"></a>Projeyi Oluşturma  
 İlk adım bir Word belgesi proje oluşturmaktır.  
  
#### <a name="to-create-a-new-project"></a>Yeni bir proje oluşturmak için  
  
1.  Adlı bir Word belgesi proje oluşturun **My Word biçimlendirme**. Sihirbazı'nda seçin **bir yeni belge oluşturun**.  
  
     Daha fazla bilgi için bkz: [nasıl yapılır: Visual Studio'da Office projeleri oluşturma](../vsto/how-to-create-office-projects-in-visual-studio.md).  
  
     Visual Studio tasarımcıda yeni Word belgesini açar ve ekler **My Word biçimlendirme** için proje **Çözüm Gezgini**.  
  
## <a name="adding-text-and-controls-to-the-word-document"></a>Word belgesine metin ve denetimler ekleme  
 Bu kılavuzda üç onay kutusunu ve bazı metin ekleme bir <xref:Microsoft.Office.Tools.Word.Bookmark> Word belgesine denetim. Onay kutularını seçenekleri, kullanıcıya metni biçimlendirme için sunar.  
  
#### <a name="to-add-three-check-boxes"></a>Üç onay kutusunu eklemek için  
  
1.  Belge Visual Studio Tasarımcısı'nda açık olduğunu doğrulayın.  
  
2.  Gelen **ortak denetimler** sekmesinde **araç**, ilk sürükleyin <xref:Microsoft.Office.Tools.Word.Controls.CheckBox> belgeye denetim.  
  
3.  İçinde **özellikleri** penceresinde, aşağıdaki özellikleri değiştirin.  
  
    |Özellik|Değer|  
    |--------------|-----------|  
    |**Ad**|**applyBoldFont**|  
    |**Metin**|**Kalın**|  
  
4.  Tuşuna **Enter** ekleme noktasını ilk onay kutusunun altına getirin.  
  
5.  İkinci bir onay kutusu belgeye eklemek `ApplyBoldFont` onay kutusunu işaretleyin ve aşağıdaki özellikleri değiştirin.  
  
    |Özellik|Değer|  
    |--------------|-----------|  
    |**Ad**|**ApplyItalicFont**|  
    |**Metin**|**İtalik**|  
  
6.  Tuşuna **Enter** ekleme noktasını ikinci onay kutusunun altına getirin.  
  
7.  Üçüncü bir onay kutusu belgeye eklemek `ApplyItalicFont` onay kutusunu işaretleyin ve aşağıdaki özellikleri değiştirin.  
  
    |Özellik|Değer|  
    |--------------|-----------|  
    |**Ad**|**applyUnderlineFont**|  
    |**Metin**|**Alt çizgi**|  
  
#### <a name="to-add-text-and-a-bookmark-control"></a>Metin ve bir yer işareti denetimi ekleme  
  
1.  Ekleme noktasını onay kutusu denetimleri altına getirin ve aşağıdaki metni yazın:  
  
     **Bu metin biçimlendirmesini değiştirmek için bir onay kutusuna tıklayın.**  
  
2.  Gelen **Word denetimleri** sekmesinde **araç**, sürükleyin bir <xref:Microsoft.Office.Tools.Word.Bookmark> belgeye denetim.  
  
     **Yer işareti Denetimi Ekle** iletişim kutusu görüntülenir.  
  
3.  Belgeye eklediğiniz metni seçip tıklatın **Tamam**.  
  
     A <xref:Microsoft.Office.Tools.Word.Bookmark> adlı Denetim **Bookmark1** belgedeki seçili metne eklenir.  
  
4.  İçinde **özellikleri** penceresinde değerini değiştirme **(ad)** özelliğine **fontText.**  
  
 Ardından, bir onay kutusu işaretli ya da temizlenmiş metni biçimlendirmek için kod yazma.  
  
## <a name="formatting-the-text-when-a-check-box-is-checked-or-cleared"></a>Biçimlendirme metin bir onay kutusu işaretli temizlenmiş mi  
 Kullanıcı bir biçimlendirme seçeneğini seçtiğinde, belgedeki metin biçimi değiştirin.  
  
#### <a name="to-change-formatting-when-a-check-box-is-selected"></a>Bir onay kutusu seçildiğinde biçimlendirmeyi değiştirmek için seçili  
  
1.  Sağ `ThisDocument` içinde **Çözüm Gezgini**ve ardından **görünümü kodu** kısayol menüsünde.  
  
2.  Yalnızca C# ' ta aşağıdaki sabitleri ekleyin **ThisDocument** sınıfı.  
  
     [!code-csharp[Trin_VstcoreProgrammingControlsWord#2](../vsto/codesnippet/CSharp/Trin_VstcoreProgrammingControlsWordCS/ThisDocument.cs#2)]  
  
3.  Aşağıdaki kodu ekleyin <xref:System.Windows.Forms.Control.Click> olay işleyicisi `applyBoldFont` onay kutusu.  
  
     [!code-vb[Trin_VstcoreProgrammingControlsWord#3](../vsto/codesnippet/VisualBasic/my chart options/ThisDocument.vb#3)]
     [!code-csharp[Trin_VstcoreProgrammingControlsWord#3](../vsto/codesnippet/CSharp/Trin_VstcoreProgrammingControlsWordCS/ThisDocument.cs#3)]  
  
4.  Aşağıdaki kodu ekleyin <xref:System.Windows.Forms.Control.Click> olay işleyicisi `applyItalicFont` onay kutusu.  
  
     [!code-vb[Trin_VstcoreProgrammingControlsWord#4](../vsto/codesnippet/VisualBasic/my chart options/ThisDocument.vb#4)]
     [!code-csharp[Trin_VstcoreProgrammingControlsWord#4](../vsto/codesnippet/CSharp/Trin_VstcoreProgrammingControlsWordCS/ThisDocument.cs#4)]  
  
5.  Aşağıdaki kodu ekleyin <xref:System.Windows.Forms.Control.Click> olay işleyicisi `applyUnderlineFont` onay kutusu.  
  
     [!code-vb[Trin_VstcoreProgrammingControlsWord#5](../vsto/codesnippet/VisualBasic/my chart options/ThisDocument.vb#5)]
     [!code-csharp[Trin_VstcoreProgrammingControlsWord#5](../vsto/codesnippet/CSharp/Trin_VstcoreProgrammingControlsWordCS/ThisDocument.cs#5)]  
  
6.  C# ' ta metin kutuları için olay işleyicileri eklemelisiniz <xref:Microsoft.Office.Tools.Word.Document.Startup> olay. Olay işleyicileri oluşturma hakkında daha fazla bilgi için bkz: [nasıl yapılır: Office projelerinde olay işleyicileri oluşturma](../vsto/how-to-create-event-handlers-in-office-projects.md).  
  
     [!code-csharp[Trin_VstcoreProgrammingControlsWord#6](../vsto/codesnippet/CSharp/Trin_VstcoreProgrammingControlsWordCS/ThisDocument.cs#6)]  
  
## <a name="testing-the-application"></a>Uygulamayı Test Etme  
 Artık seçtiğinizde veya onay kutusunu temizleyin, metni doğru biçimlendirildiğinden emin olmak için belgenizi test edebilirsiniz.  
  
#### <a name="to-test-your-document"></a>Belgenizi test etmek için  
  
1.  Projenizi çalıştırmak için F5 tuşuna basın.  
  
2.  Bir onay kutusunun işaretini kaldırın veya seçin.  
  
3.  Metni doğru şekilde biçimlendirildiğini doğrulayın.  
  
## <a name="next-steps"></a>Sonraki Adımlar  
 Bu kılavuzda onay kutularını kullanarak ve program aracılığıyla metin Word belgelerini biçimlendirmesini değiştirme temellerini gösterir. Sonradan gelebilecek bazı görevler şunlardır:  
  
-   Metin kutusunu doldurmak için bir düğmesini kullanın. Daha fazla bilgi için bkz: [izlenecek yol: bir belgeyi bir düğme kullanarak metin kutusunda metin görüntüleme](../vsto/walkthrough-displaying-text-in-a-text-box-in-a-document-using-a-button.md).  
  
-   Grafik türlerini seçmek için radyo düğmelerini kullanarak. Daha fazla bilgi için bkz: [izlenecek yol: belge kullanarak radyo düğmeleri grafik güncelleme](../vsto/walkthrough-updating-a-chart-in-a-document-using-radio-buttons.md).  
  
-  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Word kullanımında izlenecek yollar](../vsto/walkthroughs-using-word.md)   
 [Office geliştirme örnekleri ve izlenecek yollar](../vsto/office-development-samples-and-walkthroughs.md)   
 [NamedRange denetimi](../vsto/namedrange-control.md)   
 [Office Belgelerindeki Windows Forms Denetimleri Sınırlamaları](../vsto/limitations-of-windows-forms-controls-on-office-documents.md)  
  
  