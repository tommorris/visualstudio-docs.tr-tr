---
title: "Office belgelerine kalıcı Dinamik denetimleri | Microsoft Docs"
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
- Office documents [Office development in Visual Studio, Windows Forms controls
- Office documents [Office development in Visual Studio, host controls
- controls [Office development in Visual Studio], persisting in the document
- Windows Forms controls [Office development in Visual Studio], persisting in the document
- documents [Office development in Visual Studio], Windows Forms controls
- documents [Office development in Visual Studio], host controls
- host controls [Office development in Visual Studio], persisting in the document
ms.assetid: 200352d1-66aa-4156-9ecd-6fd8792974cd
caps.latest.revision: "38"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: 1e78fb90532cf75ca2e0f2a9dc6b6aa9759c75e3
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2017
---
# <a name="persisting-dynamic-controls-in-office-documents"></a>Office Belgelerinde Dinamik Denetimleri Kalıcı Kılma
  Belge veya çalışma kitabı kaydedilmiş ve kapandığında çalışma zamanında eklenen denetimleri kalıcı değildir. Tam ana bilgisayar denetimleri ve Windows Forms denetimleri için farklı bir davranıştır. Her iki durumda da, kullanıcının belgeyi açana zaman denetimlerin yeniden oluşturması için çözümünüze kod ekleyebilirsiniz.  
  
 Çalışma zamanında belgelere ekleme denetimlerini çağrılır *Dinamik denetimleri*. Dinamik denetimleri hakkında daha fazla bilgi için bkz: [Office belgelerine çalışma zamanında denetimler ekleme](../vsto/adding-controls-to-office-documents-at-run-time.md).  
  
 [!INCLUDE[appliesto_controls](../vsto/includes/appliesto-controls-md.md)]  
  
## <a name="persisting-host-controls-in-the-document"></a>Belgede kalıcı ana bilgisayar denetimleri  
 Bir Belge kaydedildiğinde ve sonra kapalı olduğunda, tüm dinamik ana bilgisayar denetimleri belgeden kaldırılır. Yalnızca arka plandaki yerel Office nesneleri geriye kalır. Örneğin, bir <xref:Microsoft.Office.Tools.Excel.ListObject> konak kontrolü hale bir <xref:Microsoft.Office.Interop.Excel.ListObject>. Ana bilgisayar denetim olaylarına yerel Office nesneleri bağlı değil ve konak kontrolü veri bağlama işlevselliğini yok.  
  
 Aşağıdaki tabloda her ana denetim türü için bir belgedeki geride yerel Office nesnesi listeler.  
  
|Ana bilgisayar Denetim türü|Yerel Office nesne türü|  
|-----------------------|-------------------------------|  
|<xref:Microsoft.Office.Tools.Excel.Chart>|<xref:Microsoft.Office.Interop.Excel.Chart>|  
|<xref:Microsoft.Office.Tools.Excel.ListObject>|<xref:Microsoft.Office.Interop.Excel.ListObject>|  
|<xref:Microsoft.Office.Tools.Excel.NamedRange>|<xref:Microsoft.Office.Interop.Excel.Range>|  
|<xref:Microsoft.Office.Tools.Word.Bookmark>|<xref:Microsoft.Office.Interop.Word.Bookmark>|  
|<xref:Microsoft.Office.Tools.Word.BuildingBlockGalleryContentControl><br /><br /> <xref:Microsoft.Office.Tools.Word.ComboBoxContentControl><br /><br /> <xref:Microsoft.Office.Tools.Word.ContentControl><br /><br /> <xref:Microsoft.Office.Tools.Word.DatePickerContentControl><br /><br /> <xref:Microsoft.Office.Tools.Word.DropDownListContentControl><br /><br /> <xref:Microsoft.Office.Tools.Word.GroupContentControl><br /><br /> <xref:Microsoft.Office.Tools.Word.PictureContentControl><br /><br /> <xref:Microsoft.Office.Tools.Word.PlainTextContentControl><br /><br /> <xref:Microsoft.Office.Tools.Word.RichTextContentControl>|<xref:Microsoft.Office.Interop.Word.ContentControl>|  
  
### <a name="re-creating-dynamic-host-controls-when-documents-are-opened"></a>Belge açıldığında dinamik ana bilgisayar denetimleri yeniden oluşturma  
 Bir kullanıcı belgeyi açtığında, var olan yerel denetimlere yerine dinamik ana bilgisayar denetimleri yeniden oluşturabilirsiniz. Bir belge açıldığında bu şekilde ana bilgisayar denetimleri oluşturma kullanıcılar bekleyebilirsiniz deneyimi benzetimini yapar.  
  
 Konak kontrolü, Word yeniden oluşturmak için veya bir <xref:Microsoft.Office.Tools.Excel.NamedRange> veya <xref:Microsoft.Office.Tools.Excel.ListObject> konak kontrolü Excel, kullanım için bir `Add` \< *kontrol sınıfı*> yöntemi bir <xref:Microsoft.Office.Tools.Excel.ControlCollection> veya <xref:Microsoft.Office.Tools.Word.ControlCollection> nesnesi. Yerel Office nesnesi için bir parametre içeren bir yöntem kullanın.  
  
 Örneğin oluşturmak istiyorsanız, bir <xref:Microsoft.Office.Tools.Excel.ListObject> konak var olan bir yerel denetiminden <xref:Microsoft.Office.Interop.Excel.ListObject> belge açıldığında kullanın <xref:Microsoft.Office.Tools.Excel.ControlCollection.AddListObject%2A> yöntemi ve varolan geçirin <xref:Microsoft.Office.Interop.Excel.ListObject>. Aşağıdaki kod örneğinde bu Excel için belge düzeyi projede gösterir. Kod bir dinamik yeniden oluşturur <xref:Microsoft.Office.Tools.Excel.ListObject> var olan temel <xref:Microsoft.Office.Interop.Excel.ListObject> adlı `MyListObject` içinde `Sheet1` sınıfı.  
  
 [!code-csharp[Trin_ExcelWorkbookDynamicControls#6](../vsto/codesnippet/CSharp/trin_excelworkbookdynamiccontrols4/Sheet1.cs#6)]
 [!code-vb[Trin_ExcelWorkbookDynamicControls#6](../vsto/codesnippet/VisualBasic/trin_excelworkbookdynamiccontrols4/Sheet1.vb#6)]  
  
### <a name="re-creating-charts"></a>Grafikleri yeniden oluşturma  
 Yeniden oluşturmak için bir <xref:Microsoft.Office.Tools.Excel.Chart> konak kontrolü, yerel silmelisiniz <xref:Microsoft.Office.Interop.Excel.Chart>ve yeniden oluşturmak <xref:Microsoft.Office.Tools.Excel.Chart> kullanarak <xref:Microsoft.Office.Tools.Excel.ControlCollection.AddChart%2A> veya <xref:Microsoft.Office.Tools.Excel.ControlCollection.AddChart%2A> yöntemi. Yoktur hiçbir `Add` \< *kontrol sınıfı*> Yeni bir oluşturmanızı sağlayan yöntemi <xref:Microsoft.Office.Tools.Excel.Chart> var olan temel <xref:Microsoft.Office.Interop.Excel.Chart>.  
  
 Yerel ilk silmezseniz <xref:Microsoft.Office.Interop.Excel.Chart>, yeniden oluşturduğunuzda, ikinci ve yinelenen bir grafik oluşturur sonra <xref:Microsoft.Office.Tools.Excel.Chart>.  
  
## <a name="persisting-windows-forms-controls-in-documents"></a>Belgelerde kalıcı Windows Forms denetimleri  
 Bir Belge kaydedildiğinde ve sonra kapalı olduğunda [!INCLUDE[vsto_runtime](../vsto/includes/vsto-runtime-md.md)] dinamik olarak oluşturulan tüm Windows Forms denetimlerini belgeden otomatik olarak kaldırır. Ancak, davranış belge düzeyi ve VSTO eklentisi projelerine için farklıdır.  
  
 Belge düzeyi özelleştirmelerindeki denetimleri ve (Bu belgenin denetimlere barındırmak için kullanılan), temel alınan ActiveX sarmalayıcıları belgeyi bir sonraki açılışında kaldırılır. Denetimleri şimdiye kadar olan bir göstergesi vardır.  
  
 VSTO eklentileri denetimler kaldırılır, ancak belgede ActiveX sarmalayıcıları kalır. Kullanıcı belge açıldığında ActiveX sarmalayıcıları görülebilir. Belge kaydedildi en son ne zaman göründüğü gibi Excel'de ActiveX sarmalayıcıları denetimleri görüntülerini görüntüler. Word, bunlar üzerinde kullanıcı sürece ActiveX sarmalayıcıları görünmez, bu durumda bunlar denetimleri kenarlık temsil eden bir noktalı çizgi gösterme. ActiveX sarmalayıcıları birkaç yolu vardır. Daha fazla bilgi için bkz: [kaldırma ActiveX sarmalayıcıları eklentide bir](#removingActiveX).  
  
### <a name="re-creating-windows-forms-controls-when-documents-are-opened"></a>Belge açıldığında Windows Forms denetimlerini yeniden oluşturma  
 Kullanıcının belgeyi açana zaman silinmiş Windows Forms denetimleri yeniden oluşturabilirsiniz. Bunu yapmak için çözümünüzün aşağıdaki görevleri gerçekleştirmeniz gerekir:  
  
1.  Belge kaydedildiğinde veya boyutu, konumu ve denetimlerin durumu hakkındaki bilgileri depolar. Belge düzeyi özelleştirmelerinde belgedeki verileri önbelleğe almak için bu verileri kaydedebilirsiniz. Bir VSTO eklenti, bu veriler özel bir XML parçasına belgedeki kaydedebilirsiniz.  
  
2.  Belge açıldığında bir olayda denetimleri yeniden oluşturun. Belge düzeyi projelerine Bunu yapmak için `Sheet`  *n*  `_Startup` veya `ThisDocument_Startup` olay işleyicileri. VSTO eklenti projelerinde bu olay işleyicileri yapabileceğiniz <xref:Microsoft.Office.Interop.Excel.AppEvents_Event.WorkbookOpen> veya <xref:Microsoft.Office.Interop.Word.ApplicationEvents4_Event.DocumentOpen> olaylar.  
  
###  <a name="removingActiveX"></a>Bir ek bileşenindeki ActiveX sarmalayıcıları kaldırma  
 Bir VSTO eklenti kullanarak belgeye dinamik Windows Forms denetimleri eklediğinizde, denetimler için ActiveX sarmalayıcıları belgede aşağıdaki yollarla sonraki açıldığında görünmesini önleyebilirsiniz.  
  
#### <a name="removing-activex-wrappers-when-the-document-is-opened"></a>Belge açıldığında ActiveX sarmalayıcıları kaldırma  
 Tüm ActiveX sarmalayıcıları kaldırmak için konak öğesi oluşturmak için GetVstoObject yöntemi çağrısı <xref:Microsoft.Office.Interop.Word.Document> veya <xref:Microsoft.Office.Interop.Excel.Workbook> , yeni açılan belgeyi temsil eder. Örneğin, bir Word belgesinden tüm ActiveX sarmalayıcıları kaldırmak için konak öğesi oluşturmak için GetVstoObject yöntemi çağırabilirsiniz <xref:Microsoft.Office.Interop.Word.Document> için olay işleyicisine geçirilen nesne <xref:Microsoft.Office.Interop.Word.ApplicationEvents4_Event.DocumentOpen> olay.  
  
 Bu yordam, VSTO eklentinin yüklü olan bilgisayarlarda belge açıldığında olduğunu bildiğiniz durumlarda kullanışlıdır. Belge VSTO eklentinin yüklü olmayan diğer kullanıcılara geçebilir, bunun yerine belgeyi kapatmadan önce denetimleri kaldırma düşünün.  
  
 Aşağıdaki kod örneğinde belge açıldığında GetVstoObject yöntemin nasıl çağrılacağını gösterir.  
  
 [!code-vb[Trin_WordAddInDynamicControls#11](../vsto/codesnippet/VisualBasic/trin_wordaddindynamiccontrols/ThisAddIn.vb#11)]
 [!code-csharp[Trin_WordAddInDynamicControls#11](../vsto/codesnippet/CSharp/Trin_WordAddInDynamicControls/ThisAddIn.cs#11)]  
  
 GetVstoObject yöntemi öncelikle çalışma zamanında yeni bir konak öğesi oluşturmak için kullanılsa da bu yöntem aynı zamanda belgedeki tüm ActiveX sarmalayıcıları için belirli bir belge olarak adlandırılan ilk kez temizler. GetVstoObject yöntemi kullanma hakkında daha fazla bilgi için bkz: [genişletme Word belgelerini ve Excel çalışma kitaplarını VSTO eklentileri çalışma zamanında](../vsto/extending-word-documents-and-excel-workbooks-in-vsto-add-ins-at-run-time.md).  
  
 Belge açıldığında VSTO eklentinizi Dinamik denetimleri oluşturursa, VSTO eklentinizi zaten GetVstoObject yöntemi denetimleri oluşturma işleminin bir parçası olarak çağıracaktır unutmayın. Bu senaryoda ActiveX sarmalayıcıları kaldırmak için GetVstoObject yöntemi ayrı bir çağrı ekleyin gerekmez.  
  
#### <a name="removing-the-dynamic-controls-before-the-document-is-closed"></a>Belge kapatılmadan önce Dinamik denetimleri kaldırma  
 Belge kapatılmadan önce VSTO eklentinizi açıkça her dinamik denetim belgeden kaldırabilirsiniz. Bu yordam, VSTO eklentinin yüklü olmayan diğer kullanıcılara geçirilen belgeler için kullanışlıdır.  
  
 Aşağıdaki kod örneğinde, belge kapatıldığında tüm Windows Forms denetimleri bir Word belgesinden kaldırmak gösterilmiştir.  
  
 [!code-vb[Trin_WordAddInDynamicControls#10](../vsto/codesnippet/VisualBasic/trin_wordaddindynamiccontrols/ThisAddIn.vb#10)]
 [!code-csharp[Trin_WordAddInDynamicControls#10](../vsto/codesnippet/CSharp/Trin_WordAddInDynamicControls/ThisAddIn.cs#10)]  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Office belgelerine çalışma zamanında denetimler ekleme](../vsto/adding-controls-to-office-documents-at-run-time.md)  
  
  