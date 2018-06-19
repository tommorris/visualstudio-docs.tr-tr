---
title: 'Nasıl yapılır: Office belgelerine Windows forms denetimleri ekleme'
ms.custom: ''
ms.date: 02/02/2017
ms.technology:
- office-development
ms.topic: conceptual
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- Office documents [Office development in Visual Studio, Windows Forms controls
- Windows Forms controls [Office development in Visual Studio], adding
- controls [Office development in Visual Studio], Windows Forms controls
- documents [Office development in Visual Studio], Windows Forms controls
author: TerryGLee
ms.author: tglee
manager: douge
ms.workload:
- office
ms.openlocfilehash: 6fcff642f75da15f649cc7e3ab525b4db0ac1c83
ms.sourcegitcommit: 209c2c068ff0975994ed892b62aa9b834a7f6077
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/17/2018
ms.locfileid: "34264553"
---
# <a name="how-to-add-windows-forms-controls-to-office-documents"></a>Nasıl yapılır: Office belgelerine Windows Forms denetimleri ekleme
  Belge düzeyi projelerine tasarım zamanında Microsoft Office Excel ve Microsoft Office Word belgelerine Windows Forms denetimleri ekleyebilirsiniz. Çalışma zamanında denetimler belge düzeyi özelleştirmeleri ve VSTO eklentileri ekleyebilirsiniz. Örneğin, ekleyebileceğiniz bir <xref:Microsoft.Office.Tools.Excel.Controls.ComboBox> kullanıcılar Seçenekleri listesinden seçebilmeniz için çalışma sayfasına denetim.  
  
 [!INCLUDE[appliesto_controls](../vsto/includes/appliesto-controls-md.md)]  
  
 Bu konuda aşağıdaki görevler açıklanmaktadır:  
  
-   [Tasarım zamanında denetimler ekleme](#designtime)  
  
-   [Belge düzeyi projelerine çalışma zamanında denetimler ekleme](#runtimedoclevel)  
  
-   [VSTO eklentileri çalışma zamanında denetimler ekleme](#runtimeaddin)  
  
 ![video bağlantı](../vsto/media/playvideo.gif "video bağlantı") ilgili video gösterimi için bkz: [nasıl I: ekleme denetimlerini belgeye yüzey çalışma zamanında?](http://go.microsoft.com/fwlink/?LinkId=132782).  
  
##  <a name="designtime"></a> Tasarım zamanında denetimler ekleme  
 Belge düzeyi projede tasarım zamanında Windows Forms denetimleri eklemenin birkaç yolu vardır.  
  
 [!INCLUDE[note_settings_general](../sharepoint/includes/note-settings-general-md.md)]  
  
### <a name="to-drag-a-windows-forms-control-to-the-document"></a>Bir Windows Forms denetimi belgeye sürükleyin  
  
1.  Oluşturun veya belge Tasarımcısı'nda görünür olmasını sağlamak, bir Excel çalışma kitabı proje veya Word belgesi proje Visual Studio'da açın. Proje oluşturma hakkında daha fazla bilgi için bkz: [nasıl yapılır: Visual Studio oluşturma Office projelerinde](../vsto/how-to-create-office-projects-in-visual-studio.md).  
  
2.  İçinde **ortak denetimler** sekmesinde **araç**, eklemek istediğiniz denetimi tıklayın ve belgeye sürükleyin.  
  
    > [!NOTE]  
    >  Excel'de denetim seçtiğinizde göreceğiniz **=EMBED("WinForms.Control.Host","")** içinde **formül çubuğu**. Bu metin gereklidir ve silinmemelidir.  
  
### <a name="to-draw-a-windows-forms-control-on-the-document"></a>Belge üzerinde bir Windows Forms denetimi çizmek için  
  
1.  Oluşturun veya belge Tasarımcısı'nda görünür olmasını sağlamak, bir Excel çalışma kitabı proje veya Word belgesi proje Visual Studio'da açın. Proje oluşturma hakkında daha fazla bilgi için bkz: [nasıl yapılır: Visual Studio oluşturma Office projelerinde](../vsto/how-to-create-office-projects-in-visual-studio.md).  
  
2.  İçinde **ortak denetimler** sekmesinde **araç**, eklemek istediğiniz denetimi tıklatın.  
  
3.  Belge yerleştirilecek denetimin sol üst köşesinde istediğiniz yeri tıklatın ve bulunması için denetimin sağ alt köşedeki istediğiniz yere sürükleyin.  
  
     Denetim belirtilen konum ve boyutlarının belgeyle eklenir.  
  
    > [!NOTE]  
    >  Excel'de denetim seçtiğinizde göreceğiniz **=EMBED("WinForms.Control.Host","")** içinde **formül çubuğu**. Bu metin gereklidir ve silinmemelidir.  
  
### <a name="to-add-a-windows-forms-control-to-the-document-by-single-clicking-the-control"></a>Bir Windows Forms denetimi belgeye tek-denetimi tıklatarak eklemek için  
  
1.  Oluşturun veya belge Tasarımcısı'nda görünür olmasını sağlamak, bir Excel çalışma kitabı proje veya Word belgesi proje Visual Studio'da açın. Proje oluşturma hakkında daha fazla bilgi için bkz: [nasıl yapılır: Visual Studio oluşturma Office projelerinde](../vsto/how-to-create-office-projects-in-visual-studio.md).  
  
2.  İçinde **ortak denetimler** sekmesinde **araç**, eklemek istediğiniz denetimi tıklatın  
  
3.  Bir belge eklenecek denetimi istediğiniz yeri tıklatın.  
  
     Denetim varsayılan boyut belgeye eklenir.  
  
    > [!NOTE]  
    >  Excel'de denetim seçtiğinizde göreceğiniz **=EMBED("WinForms.Control.Host","")** içinde **formül çubuğu**. Bu metin gereklidir ve silinmemelidir.  
  
### <a name="to-add-a-windows-forms-control-to-the-document-by-double-clicking-the-control"></a>Denetim çift tıklayarak bir Windows Forms denetimi belgeye eklemek için  
  
1.  Oluşturun veya belge Tasarımcısı'nda görünür olmasını sağlamak, bir Excel çalışma kitabı proje veya Word belgesi proje Visual Studio'da açın. Proje oluşturma hakkında daha fazla bilgi için bkz: [nasıl yapılır: Visual Studio oluşturma Office projelerinde](../vsto/how-to-create-office-projects-in-visual-studio.md).  
  
2.  İçinde **ortak denetimler** sekmesinde **araç**, eklemek istediğiniz denetimi çift tıklatın.  
  
     Denetim, belgenin veya etkin bölmeyi merkezindeki belgeye eklenir.  
  
    > [!NOTE]  
    >  Excel'de denetim seçtiğinizde göreceğiniz **=EMBED("WinForms.Control.Host","")** içinde **formül çubuğu**. Bu metin gereklidir ve silinmemelidir.  
  
### <a name="to-add-a-windows-forms-control-to-the-document-by-pressing-the-enter-key"></a>Enter tuşuna basarak bir Windows Forms denetimi belgeye eklemek için  
  
1.  Oluşturun veya belge Tasarımcısı'nda görünür olmasını sağlamak, bir Excel çalışma kitabı proje veya Word belgesi proje Visual Studio'da açın. Proje oluşturma hakkında daha fazla bilgi için bkz: [nasıl yapılır: Visual Studio'da Office projeleri oluşturma](../vsto/how-to-create-office-projects-in-visual-studio.md).  
  
2.  İçinde **ortak denetimler** sekmesinde **araç**, ekleme ve basın istediğiniz denetimi tıklatın **Enter** anahtarı.  
  
     Denetim, belgenin veya etkin bölmeyi merkezindeki belgeye eklenir.  
  
    > [!NOTE]  
    >  Excel'de denetim seçtiğinizde göreceğiniz **=EMBED("WinForms.Control.Host","")** içinde **formül çubuğu**. Bu metin gereklidir ve silinmemelidir.  
  
##  <a name="runtimedoclevel"></a> Belge düzeyi projelerine çalışma zamanında denetimler ekleme  
 Bir belgeye çalışma zamanında Windows Forms denetimlerini programlı olarak ekleyebilirsiniz. Word'de yöntemlerini kullanın <xref:Microsoft.Office.Tools.Word.DocumentBase.Controls%2A> özelliği `ThisDocument` sınıfı. Excel'de yöntemlerini kullanın <xref:Microsoft.Office.Tools.Excel.WorksheetBase.Controls%2A> özelliği bir `Sheet` *n* sınıfı. Her yöntem farklı şekilde denetimin konumunu belirtmenizi sağlayan birçok aşırı yüklemeye sahip.  
  
 Belgeye çalışma zamanında bir Windows Forms denetimi eklediğinizde denetim belge kapatıldığında belgede kalıcı yapılmaz. Belge bir sonraki açılışında denetimi yeniden oluşturabilirsiniz. Daha fazla bilgi için bkz: [Office belgelerine çalışma zamanında denetimler ekleme](../vsto/adding-controls-to-office-documents-at-run-time.md).  
  
### <a name="to-add-a-windows-forms-control-at-runtime"></a>Çalışma zamanında bir Windows Forms Denetim eklemek için  
  
1.  Ekle adına sahip bir yöntem kullanın\<*kontrol sınıfı*> (burada *kontrol sınıfı* gibi eklemek istediğiniz Windows Forms denetimi sınıf adı <xref:Microsoft.Office.Tools.Word.ControlExtensions.AddButton%2A>).  
  
     Aşağıdaki kod örneğinde nasıl ekleneceğini gösterir bir <xref:Microsoft.Office.Tools.Excel.Controls.Button> hücre **C5** , `Sheet1` Excel için belge düzeyi projede.  
  
     [!code-vb[Trin_VstcoreProgrammingControlsExcel#4](../vsto/codesnippet/VisualBasic/my excel chart/Sheet1.vb#4)]
     [!code-csharp[Trin_VstcoreProgrammingControlsExcel#4](../vsto/codesnippet/CSharp/Trin_VstcoreProgrammingControlsExcelCS/Sheet1.cs#4)]  
  
##  <a name="runtimeaddin"></a> VSTO eklentileri çalışma zamanında denetimler ekleme  
 Herhangi bir açık belgeye çalışma zamanında Windows Forms denetimlerini programlı olarak ekleyebilirsiniz. İlk olarak, açık bir belge veya çalışma sayfası üzerinde temel bir ana bilgisayar öğesi oluşturun. Word'de yöntemlerini kullanın <xref:Microsoft.Office.Tools.Word.Document.Controls%2A> yeni konak öğesi özelliği. Excel'de yöntemlerini kullanın <xref:Microsoft.Office.Tools.Excel.Worksheet.Controls%2A> yeni konak öğesi özelliği. Her yöntem farklı şekilde denetimin konumunu belirtmenizi sağlayan birçok aşırı yüklemeye sahip.  
  
 Belgeye çalışma zamanında bir Windows Forms denetimi eklediğinizde denetim belge kapatıldığında belgede kalıcı yapılmaz. Belge bir sonraki açılışında denetimi yeniden oluşturabilirsiniz. Daha fazla bilgi için bkz: [Office belgelerine çalışma zamanında denetimler ekleme](../vsto/adding-controls-to-office-documents-at-run-time.md).  
  
 VSTO eklentisi projelerine konak öğeleri oluşturma hakkında daha fazla bilgi için bkz: [genişletmek Word belgelerini ve Excel çalışma kitaplarını VSTO eklentileri çalışma zamanında](../vsto/extending-word-documents-and-excel-workbooks-in-vsto-add-ins-at-run-time.md).  
  
### <a name="to-add-a-windows-forms-control-at-runtime"></a>Çalışma zamanında bir Windows Forms Denetim eklemek için  
  
1.  Ekle adına sahip bir yöntem kullanın\<*kontrol sınıfı*> (burada *kontrol sınıfı* gibi eklemek istediğiniz Windows Forms denetimi sınıf adı <xref:Microsoft.Office.Tools.Word.ControlExtensions.AddButton%2A>).  
  
    > [!NOTE]  
    >  VSTO eklenti hedefleyen projelerde bu [!INCLUDE[net_v40_short](../sharepoint/includes/net-v40-short-md.md)] veya daha sonra bir başvuru eklemeniz gerekir *Microsoft.Office.Tools.Excel.v4.0.Utilities.dll* veya *Microsoft.Office.Tools.Word.v4.0.Utilities.dll* Ekle erişmeden önce derleme\<*kontrol sınıfı*> yöntemleri.  
  
     Aşağıdaki kod örneğinde nasıl ekleneceğini gösterir bir <xref:Microsoft.Office.Tools.Word.Controls.Button> bir Word VSTO eklentisini kullanarak etkin belgenin ilk paragrafa.  
  
     [!code-vb[Trin_WordAddInDynamicControls#7](../vsto/codesnippet/VisualBasic/trin_wordaddindynamiccontrols/ThisAddIn.vb#7)]
     [!code-csharp[Trin_WordAddInDynamicControls#7](../vsto/codesnippet/CSharp/Trin_WordAddInDynamicControls/ThisAddIn.cs#7)]  
  
## <a name="see-also"></a>Ayrıca bkz.  
 [Windows Forms denetimlerindeki Office belgeleri genel bakış](../vsto/windows-forms-controls-on-office-documents-overview.md)   
 [Office belgelerine çalışma zamanında denetimler ekleme](../vsto/adding-controls-to-office-documents-at-run-time.md)   
 [Nasıl yapılır: çalışma sayfası hücreleri içinde denetimleri yeniden boyutlandırma](../vsto/how-to-resize-controls-within-worksheet-cells.md)   
 [Konak öğelerine ve denetimlerine genel bakış](../vsto/host-items-and-host-controls-overview.md)   
 [Office çözümlerinde isteğe bağlı parametreler](../vsto/optional-parameters-in-office-solutions.md)  
  