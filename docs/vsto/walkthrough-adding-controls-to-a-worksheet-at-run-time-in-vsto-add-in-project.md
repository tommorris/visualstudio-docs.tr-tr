---
title: "İzlenecek yol: Ekleme denetimlerini çalışma zamanında VSTO proje eklenti | Microsoft Docs"
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
- add-ins [Office development in Visual Studio], adding controls
- controls [Office development in Visual Studio], adding to worksheets at run time
- application-level add-ins [Office development in Visual Studio], adding controls
- worksheets, adding controls at run time
ms.assetid: 4f68677a-4789-4564-b229-02e2d4031a5f
caps.latest.revision: "38"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload: office
ms.openlocfilehash: 37da15cce48bd16e022db42fa8a08a2b9633b5fc
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/22/2017
---
# <a name="walkthrough-adding-controls-to-a-worksheet-at-run-time-in-vsto-add-in-project"></a>İzlenecek Yol: Çalışma Zamanında VSTO Eklenti Projesindeki Çalışma Sayfasına Denetimler Ekleme
  Bir Excel VSTO eklenti kullanarak herhangi bir açık çalışma sayfasına denetimler ekleyebilirsiniz. Bu anlatımda Şerit eklemek kullanıcıların sağlamak için nasıl kullanılacağı gösterilir bir <xref:Microsoft.Office.Tools.Excel.Controls.Button>, <xref:Microsoft.Office.Tools.Excel.NamedRange>ve <xref:Microsoft.Office.Tools.Excel.ListObject> çalışma. Bilgi için bkz: [Office belgelerine çalışma zamanında denetimler ekleme](../vsto/adding-controls-to-office-documents-at-run-time.md).  
  
 **Uygulandığı öğe:** Bu konu başlığı altındaki bilgiler Excel için VSTO eklentisi projelerine yöneliktir. Daha fazla bilgi için bkz: [Office uygulaması ve proje türüne göre kullanılabilen özellikler](../vsto/features-available-by-office-application-and-project-type.md).  
  
 Bu izlenecek yol aşağıdaki görevleri gösterir:  
  
-   Bir kullanıcı arabirimi (UI) denetim eklemek için çalışma sayfasına sağlama.  
  
-   Çalışma sayfasına denetimler ekleme.  
  
-   Denetimleri çalışma sayfasından kaldırma.  
  
 [!INCLUDE[note_settings_general](../sharepoint/includes/note-settings-general-md.md)]  
  
## <a name="prerequisites"></a>Önkoşullar  
 Bu izlenecek yolu tamamlamak için aşağıdaki bileşenlere ihtiyacınız vardır:  
  
-   [!INCLUDE[vsto_vsprereq](../vsto/includes/vsto-vsprereq-md.md)]  
  
-   Excel  
  
## <a name="creating-a-new-excel-vsto-add-in-project"></a>Eklenti yeni bir Excel VSTO projesi oluşturma  
 Excel VSTO eklenti projesindeki oluşturarak başlayın.  
  
#### <a name="to-create-a-new-excel-vsto-add-in-project"></a>Yeni bir Excel VSTO eklenti projesi oluşturmak için  
  
1.  İçinde [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)], Excel VSTO eklenti projesindeki adlı oluşturun **ExcelDynamicControls**. Daha fazla bilgi için bkz: [nasıl yapılır: Visual Studio'da Office projeleri oluşturma](../vsto/how-to-create-office-projects-in-visual-studio.md).  
  
2.  Bir başvuru ekleyin **Microsoft.Office.Tools.Excel.v4.0.Utilities.dll** derleme. Bu başvuru, bu kılavuzda daha sonra bir çalışma sayfasına program aracılığıyla bir Windows Forms denetimi eklemek için gereklidir.  
  
## <a name="providing-a-ui-to-add-controls-to-a-worksheet"></a>Bir çalışma sayfasına denetimler eklemek için bir UI sağlama  
 Özel sekme Şerite ekleyin. Kullanıcılar, bir çalışma sayfasına denetimler eklemek için sekmedeki onay kutularını seçebilirsiniz.  
  
#### <a name="to-provide-a-ui-to-add-controls-to-a-worksheet"></a>Bir çalışma sayfasına denetimler eklemek için bir UI sağlamak için  
  
1.  Üzerinde **proje** menüsünde tıklatın **Yeni Öğe Ekle**.  
  
2.  İçinde **Yeni Öğe Ekle** iletişim kutusunda **Şerit (Görsel Tasarımcı)**ve ardından **Ekle**.  
  
     Adlı bir dosya **Ribbon1.cs** veya **Ribbon1.vb** Şerit Tasarımcısı'nda açılır ve varsayılan bir sekme ve grup görüntüler.  
  
3.  Gelen **Office Şerit denetimleri** sekmesinde **araç**, bir onay kutusu denetimi sürükleyin **group1**.  
  
4.  Tıklatın **CheckBox1** seçin.  
  
5.  İçinde **özellikleri** penceresinde, aşağıdaki özellikleri değiştirin.  
  
    |Özellik|Değer|  
    |--------------|-----------|  
    |**Ad**|**Düğme**|  
    |**Etiket**|**Düğme**|  
  
6.  İkinci bir onay kutusu eklemek **group1**ve ardından aşağıdaki özellikleri değiştirin.  
  
    |Özellik|Değer|  
    |--------------|-----------|  
    |**Ad**|**NamedRange**|  
    |**Etiket**|**NamedRange**|  
  
7.  Üçüncü bir onay kutusu eklemek **group1**ve ardından aşağıdaki özellikleri değiştirin.  
  
    |Özellik|Değer|  
    |--------------|-----------|  
    |**Ad**|**ListObject**|  
    |**Etiket**|**ListObject**|  
  
## <a name="adding-controls-to-the-worksheet"></a>Çalışma sayfasına denetimler ekleme  
 Yönetilen denetimleri yalnızca kapsayıcı hareket ana bilgisayar öğeleri eklenebilir. VSTO eklentisi projelerine herhangi bir açık çalışma kitabı ile çalışmak için VSTO eklentisi çalışma sayfası konak öğesine dönüştürür veya denetimi eklemeden önce var olan bir konak öğesi alır. Kodu oluşturmak için her denetim click olay işleyicilerine ekleyin bir <xref:Microsoft.Office.Tools.Excel.Worksheet> açık çalışma sayfasına göre konak öğesi. Ardından, ekleyin bir <xref:Microsoft.Office.Tools.Excel.Controls.Button>, <xref:Microsoft.Office.Tools.Excel.NamedRange>ve bir <xref:Microsoft.Office.Tools.Excel.ListObject> geçerli seçime adresindeki.  
  
#### <a name="to-add-controls-to-a-worksheet"></a>Bir çalışma sayfasına denetimler ekleme  
  
1.  Şerit Tasarımcısı'nda çift **düğmesini**.  
  
     <xref:Microsoft.Office.Tools.Ribbon.RibbonCheckBox.Click> Olay işleyicisi **düğmesini** onay kutusu Kod Düzenleyicisi'nde açılır.  
  
2.  Değiştir `Button_Click` aşağıdaki kod ile olay işleyicisi.  
  
     Bu kodu kullanır `GetVstoObject` ilk çalışma kitabındaki temsil eder ve ardından ekleyen bir konak öğesini almak için yöntemi bir <xref:Microsoft.Office.Tools.Excel.Controls.Button> şu anda seçili hücre denetim.  
  
     [!code-csharp[Trin_Excel_Dynamic_Controls#2](../vsto/codesnippet/CSharp/Trin_Excel_Dynamic_Controls/Ribbon1.cs#2)]
     [!code-vb[Trin_Excel_Dynamic_Controls#2](../vsto/codesnippet/VisualBasic/Trin_Excel_Dynamic_Controls/Ribbon1.vb#2)]  
  
3.  İçinde **Çözüm Gezgini**, Ribbon1.cs veya Ribbon1.cs dosyasını seçin.  
  
4.  Üzerinde **Görünüm** menüsünde tıklatın **Tasarımcısı**.  
  
5.  Şerit Tasarımcısı'nda çift **NamedRange**.  
  
6.  Değiştir `NamedRange_Click` aşağıdaki kod ile olay işleyicisi.  
  
     Bu kodu kullanır `GetVstoObject` ilk çalışma kitabındaki temsil eder ve ardından tanımlayan bir konak öğesini almak için yöntemi bir <xref:Microsoft.Office.Tools.Excel.NamedRange> denetimi şu anda seçili hücrenin veya hücre için.  
  
     [!code-csharp[Trin_Excel_Dynamic_Controls#3](../vsto/codesnippet/CSharp/Trin_Excel_Dynamic_Controls/Ribbon1.cs#3)]
     [!code-vb[Trin_Excel_Dynamic_Controls#3](../vsto/codesnippet/VisualBasic/Trin_Excel_Dynamic_Controls/Ribbon1.vb#3)]  
  
7.  Şerit Tasarımcısı'nda çift **ListObject**.  
  
8.  Değiştir `ListObject_Click` aşağıdaki kod ile olay işleyicisi.  
  
     Bu kodu kullanır `GetVstoObject` ilk çalışma kitabındaki temsil eder ve ardından tanımlayan bir konak öğesini almak için yöntemi bir <xref:Microsoft.Office.Tools.Excel.ListObject> şu anda seçili hücrenin veya hücre için.  
  
     [!code-csharp[Trin_Excel_Dynamic_Controls#4](../vsto/codesnippet/CSharp/Trin_Excel_Dynamic_Controls/Ribbon1.cs#4)]
     [!code-vb[Trin_Excel_Dynamic_Controls#4](../vsto/codesnippet/VisualBasic/Trin_Excel_Dynamic_Controls/Ribbon1.vb#4)]  
  
9. Aşağıdaki deyimleri Şerit kod dosyasının üstüne ekleyin.  
  
     [!code-csharp[Trin_Excel_Dynamic_Controls#1](../vsto/codesnippet/CSharp/Trin_Excel_Dynamic_Controls/Ribbon1.cs#1)]
     [!code-vb[Trin_Excel_Dynamic_Controls#1](../vsto/codesnippet/VisualBasic/Trin_Excel_Dynamic_Controls/Ribbon1.vb#1)]  
  
## <a name="removing-controls-from-the-worksheet"></a>Çalışma sayfasından denetimleri kaldırma  
 Çalışma sayfası kaydedilir ve denetimleri kalıcı değildir. Program aracılığıyla oluşturulan tüm Windows Forms denetimlerini çalışma kaydedilir ya da çalışma kitabını yeniden açıldığında anahattı denetiminin görünür önce kaldırmanız gerekir. Kodu ekleyin <xref:Microsoft.Office.Interop.Excel.AppEvents_Event.WorkbookBeforeSave> olay Windows Forms denetimleri oluşturulan konak öğesi denetimleri koleksiyondan kaldırır. Daha fazla bilgi için bkz: [Office belgelerinde Dinamik denetimleri kalıcı kılma](../vsto/persisting-dynamic-controls-in-office-documents.md).  
  
#### <a name="to-remove-controls-from-the-worksheet"></a>Çalışma sayfasından denetimleri kaldırmak için  
  
1.  İçinde **Çözüm Gezgini**, ThisAddIn.cs veya ThisAddIn.vb seçin.  
  
2.  Üzerinde **Görünüm** menüsünde tıklatın **kod**.  
  
3.  ThisAddIn sınıfına aşağıdaki yöntemi ekleyin. Bu kod ilk çalışma kitabında alır ve ardından `HasVstoObject` yöntemi çalışma oluşturulan çalışma sayfası nesnesi olup olmadığını denetleyin. Oluşturulan çalışma sayfası nesnesi denetimleri varsa kod o çalışma sayfası nesnesi alır ve denetimleri kaldırma denetimi toplulukta tekrarlanan.  
  
     [!code-csharp[Trin_Excel_Dynamic_Controls#6](../vsto/codesnippet/CSharp/Trin_Excel_Dynamic_Controls/ThisAddIn.cs#6)]
     [!code-vb[Trin_Excel_Dynamic_Controls#6](../vsto/codesnippet/VisualBasic/Trin_Excel_Dynamic_Controls/ThisAddIn.vb#6)]  
  
4.  C# ' ta için bir olay işleyicisi oluşturmalısınız <xref:Microsoft.Office.Interop.Excel.AppEvents_Event.WorkbookBeforeSave> olay. Bu kodu koyabilirsiniz `ThisAddIn_Startup` yöntemi. Olay işleyicileri oluşturma hakkında daha fazla bilgi için bkz: [nasıl yapılır: Office projelerinde olay işleyicileri oluşturma](../vsto/how-to-create-event-handlers-in-office-projects.md). Değiştir `ThisAddIn_Startup` aşağıdaki kod ile yöntemi.  
  
     [!code-csharp[Trin_Excel_Dynamic_Controls#5](../vsto/codesnippet/CSharp/Trin_Excel_Dynamic_Controls/ThisAddIn.cs#5)]  
  
## <a name="testing-the-solution"></a>Çözüm test ediliyor  
 Denetimleri Şerit üzerindeki özel bir sekme seçerek bir çalışma sayfasına ekleyin. Çalışma sayfası kaydettiğinizde, bu denetimlerin kaldırılır.  
  
#### <a name="to-test-the-solution"></a>Çözüm test etmek için.  
  
1.  Projenizi çalıştırmak için F5 tuşuna basın.  
  
2.  Sheet1 içinde herhangi bir hücreyi seçin.  
  
3.  Tıklatın **eklentileri** sekmesi.  
  
4.  İçinde **group1** grubunda **düğmesini**.  
  
     Seçili hücrede bir düğme görüntülenir.  
  
5.  Sheet1'deki farklı bir hücre seçin.  
  
6.  İçinde **group1** grubunda **NamedRange**.  
  
     Adlandırılmış bir aralık seçili hücre için tanımlanır.  
  
7.  Hücre serisi Sheet1'de seçin.  
  
8.  İçinde **group1** grubunda **ListObject**.  
  
     Bir liste nesnesi için seçili hücreleri eklenir.  
  
9. Çalışma sayfası kaydedin.  
  
     Sheet1 artık eklenen denetimler görüntülenir.  
  
## <a name="next-steps"></a>Sonraki Adımlar  
 Bu konudaki Excel VSTO eklentisi projelerine denetimleri hakkında daha fazla bilgi edinebilirsiniz:  
  
-   Bir çalışma sayfasına denetimler kaydetme hakkında bilgi edinmek için Excel VSTO eklenti dinamik bkz [Office geliştirme örnekleri ve izlenecek yollar](../vsto/office-development-samples-and-walkthroughs.md).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Excel çözümleri](../vsto/excel-solutions.md)   
 [Windows Forms denetimleri Office belgeleri genel bakış](../vsto/windows-forms-controls-on-office-documents-overview.md)   
 [Office belgelerindeki denetimler](../vsto/controls-on-office-documents.md)   
 [NamedRange denetimi](../vsto/namedrange-control.md)   
 [ListObject Denetimi](../vsto/listobject-control.md)  
  
  