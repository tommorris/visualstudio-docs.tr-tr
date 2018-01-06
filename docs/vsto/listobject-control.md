---
title: ListObject denetimi | Microsoft Docs
ms.custom: 
ms.date: 02/02/2017
ms.reviewer: 
ms.suite: 
ms.technology: office-development
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: VST.Toolbox.List
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- lists, events
- ListObject control
- ListObject control, events
- ListObject control, data binding
- ListObject control, improving performance when bound to data
ms.assetid: 2bdecbf0-2a0f-48de-a544-dca12bb4a9a3
caps.latest.revision: "70"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload: office
ms.openlocfilehash: 3f203b7e350f30d27d88e27ff9688bdbdee2b3d8
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/22/2017
---
# <a name="listobject-control"></a>ListObject Denetimi
  <xref:Microsoft.Office.Tools.Excel.ListObject> Denetim olayları gösterir ve veriye bağlı bir listedir. Bir çalışma sayfasına listesini eklediğinizde, Visual Studio oluşturur bir <xref:Microsoft.Office.Tools.Excel.ListObject> dayalı Microsoft Office Excel nesne modeline çapraz geçiş yapmak zorunda kalmadan doğrudan programlama yapabilirsiniz denetim.  
  
 [!INCLUDE[appliesto_xlalldocapp](../vsto/includes/appliesto-xlalldocapp-md.md)]  
  
## <a name="creating-the-control"></a>Denetimi oluşturma  
 Belge düzeyi projelerine eklediğiniz <xref:Microsoft.Office.Tools.Excel.ListObject> denetimlerini tasarım zamanında veya çalışma zamanında çalışma. VSTO eklenti projelerinde eklediğiniz <xref:Microsoft.Office.Tools.Excel.ListObject> denetimlerini yalnızca çalışma zamanında çalışma sayfalarına. Daha fazla bilgi için bkz: [nasıl yapılır: çalışma sayfalarına ListObject denetimleri ekleme](../vsto/how-to-add-listobject-controls-to-worksheets.md).  
  
> [!NOTE]  
>  Varsayılan olarak, dinamik olarak oluşturulmuş liste nesneleri çalışma sayfasında sürdürülmeyen çalışma kapatıldığında konak kontrolü olarak. Daha fazla bilgi için bkz: [Office belgelerine çalışma zamanında denetimler ekleme](../vsto/adding-controls-to-office-documents-at-run-time.md).  
  
## <a name="binding-data-to-the-control"></a>Denetimine veri bağlama  
 A <xref:Microsoft.Office.Tools.Excel.ListObject> denetimi, basit ve karmaşık veri bağlamayı destekler. <xref:Microsoft.Office.Tools.Excel.ListObject> Denetimi kullanarak bir veri kaynağına bağlanabilir <xref:Microsoft.Office.Tools.Excel.ListObject.DataSource%2A> ve <xref:Microsoft.Office.Tools.Excel.ListObject.DataMember%2A> tasarım zamanında özelliklerini veya <xref:Microsoft.Office.Tools.Excel.ListObject.SetDataBinding%2A> çalışma zamanında yöntemi.  
  
> [!NOTE]  
>  <xref:Microsoft.Office.Tools.Excel.ListObject> Gibi bir veri kaynağına bağlı olduğu zaman otomatik olarak güncelleştirilir bir <xref:System.Data.DataTable>, veriler değiştiğinde olayları başlatır. Bağlarsanız <xref:Microsoft.Office.Tools.Excel.ListObject> veriler değiştiğinde olayı oluşturmaz bir veri kaynağı için çağırmalısınız <xref:Microsoft.Office.Tools.Excel.ListObject.RefreshDataRow%2A> veya <xref:Microsoft.Office.Tools.Excel.ListObject.RefreshDataRows%2A> güncelleştirmek için yöntemi <xref:Microsoft.Office.Tools.Excel.ListObject>.  
  
 Eklediğinizde bir <xref:Microsoft.Office.Tools.Excel.ListObject> o hücreye tekrarlanan bir şema öğesi eşleyerek bir çalışma sayfası hücresi için Visual Studio otomatik olarak eşlenir <xref:Microsoft.Office.Tools.Excel.ListObject> üretilen veri kümesi için. Ancak, <xref:Microsoft.Office.Tools.Excel.ListObject> verileri otomatik olarak bağlı değil. Bağlamak üzere adım atabilirsiniz <xref:Microsoft.Office.Tools.Excel.ListObject> tasarım zamanında veya belge düzeyi projesindeki çalışma zamanında veri kümesi için. Program aracılığıyla bağlayabilirsiniz <xref:Microsoft.Office.Tools.Excel.ListObject> veri kümesine çalışma zamanında VSTO eklenti.  
  
 Verileri ayrı olduğundan <xref:Microsoft.Office.Tools.Excel.ListObject>, eklemeli ve verileri bağlı veri kümesi ve aracılığıyla doğrudan kaldırma <xref:Microsoft.Office.Tools.Excel.ListObject>. Veri bağlama kümesindeki herhangi bir mekanizma aracılığıyla güncelleştirdiyseniz <xref:Microsoft.Office.Tools.Excel.ListObject> denetimi otomatik olarak değişiklikleri yansıtır. Daha fazla bilgi için bkz: [Office çözümlerinde denetimlere veri bağlama](../vsto/binding-data-to-controls-in-office-solutions.md).  
  
 Hızlı bir şekilde doldurmak için bir <xref:Microsoft.Office.Tools.Excel.ListObject> bağlayarak denetim <xref:Microsoft.Office.Tools.Excel.ListObject> bir veri kaynağına. Veri bağlama verileri düzenlerseniz <xref:Microsoft.Office.Tools.Excel.ListObject>, otomatik olarak da veri kaynağına yapılan değişiklikler. Doldurmak istiyorsanız bir <xref:Microsoft.Office.Tools.Excel.ListObject> ve verileri değiştirmek kullanıcı etkinleştirme <xref:Microsoft.Office.Tools.Excel.ListObject> kullanabileceğiniz veri kaynağını değiştirmeden <xref:Microsoft.Office.Tools.Excel.ListObject.Disconnect%2A> ayırmak için yöntemi <xref:Microsoft.Office.Tools.Excel.ListObject> veri kaynağından. Daha fazla bilgi için bkz: [nasıl yapılır: ListObject denetimlerini veri ile doldurma](../vsto/how-to-fill-listobject-controls-with-data.md).  
  
> [!NOTE]  
>  Veri bağlama desteklenmiyor çakışan üzerinde <xref:Microsoft.Office.Tools.Excel.ListObject> kontrol eder.  
  
### <a name="improving-performance-in-listobject-controls"></a>ListObject denetimleri performansı iyileştirme  
 Veri bağlama bir XML dosyası okunurken <xref:Microsoft.Office.Tools.Excel.ListObject> denetim eğilimlidir denetimi ilk bağlamak ve ardından arama yavaş olacak şekilde <xref:System.Data.DataSet.ReadXml%2A> veri kümesini doldurmak için. Performansı artırmak için arama <xref:System.Data.DataSet.ReadXml%2A> denetimi bağlamadan önce.  
  
### <a name="disconnecting-listobject-controls-from-the-data-source"></a>ListObject denetimlerini veri kaynağından bağlantıyı kesme  
 Doldurduktan sonra bir <xref:Microsoft.Office.Tools.Excel.ListObject> denetim listesi nesnesi verilerde yapılan değişiklikler veri kaynağını etkilemez böylece bir veri kaynağına bağlayarak veri ile kesebilirsiniz. Daha fazla bilgi için bkz: [nasıl yapılır: ListObject denetimlerini veri ile doldurma](../vsto/how-to-fill-listobject-controls-with-data.md).  
  
### <a name="restoring-column-and-row-order"></a>Geri yükleme sütun ve satır sırası  
 Veri bağlama ne zaman bir <xref:Microsoft.Office.Tools.Excel.ListObject> belgeye tasarım zamanında Visual Studio çalışma kitabı kaydedildiği zaman sütun ve satır sırası izler eklendi denetim. Bir kullanıcı taşırsa <xref:Microsoft.Office.Tools.Excel.ListObject> sütunlara veya satırlara sırasında çalışma zamanında, yeni sıra çalışma kitabını sonraki açılışında korunur ve <xref:Microsoft.Office.Tools.Excel.ListObject> denetimini veri kaynağına yeniden bağlar.  
  
 Geri yüklemek istiyorsanız <xref:Microsoft.Office.Tools.Excel.ListObject> kendi özgün sütun ve satır sırası için çağırabilirsiniz <xref:Microsoft.Office.Tools.Excel.ListObject.ResetPersistedBindingInformation%2A> yöntemi. Bu yöntem sütunla ilişkili özel belge özelliklerini kaldırır ve satır sırasını belirtilen <xref:Microsoft.Office.Tools.Excel.ListObject>. Bu yöntemi çağırın <xref:Microsoft.Office.Tools.Excel.Workbook.Shutdown> sütun ve satır sırasını korumak istemiyorsanız çalışma kitabının olay <xref:Microsoft.Office.Tools.Excel.ListObject>.  
  
## <a name="formatting"></a>Biçimlendirme  
 Uygulanabilir biçimlendirme bir <xref:Microsoft.Office.Interop.Excel.ListObject> uygulanabilir bir <xref:Microsoft.Office.Tools.Excel.ListObject> denetim. Bu kenarlıklar, yazı tipi, numara biçimi ve stilleri içerir. Son kullanıcılar verilere bağlı sütunlar yeniden <xref:Microsoft.Office.Tools.Excel.ListObject>, ve bu değişiklikleri sağlanan belgeyle kalıcıdır <xref:Microsoft.Office.Tools.Excel.ListObject> belgeye tasarım zamanında eklenir. Belgenin bir sonraki açılışında liste nesnesi aynı veri kaynağına bağlı, ancak sütun sırasını kullanıcıların değişiklikleri yansıtır.  
  
## <a name="adding-and-removing-columns-at-run-time"></a>Ekleme ve çalışma zamanında sütunları kaldırma  
 El ile ekleyemez veya verilere bağlı sütunlar kaldırmak <xref:Microsoft.Office.Tools.Excel.ListObject> çalışma zamanında denetim. Bir sütun silmek bir son kullanıcı çalışırsa, hemen geri yüklenir ve eklenen sütunlar kaldırılacak. Bu nedenle, neden bunlar gerçekleştiremez bu eylemler üzerinde kullanıcılara açıklayan kod yazmak önemli bir <xref:Microsoft.Office.Tools.Excel.ListObject> verilere bağımlı. Visual Studio üzerinde çeşitli olaylarını sağlayan bir <xref:Microsoft.Office.Tools.Excel.ListObject> veri bağlama ile ilgili. Örneğin, kullanabileceğiniz <xref:Microsoft.Office.Tools.Excel.ListObject.OriginalDataRestored> bunlar silmeye çalıştı veri silinemez ve geri yüklendi kullanıcıları uyarmak için olay.  
  
## <a name="adding-and-removing-rows-at-run-time"></a>Ekleme ve çalışma zamanında satırları kaldırma  
 El ile eklemek ve veri bağlama satırları Kaldır <xref:Microsoft.Office.Tools.Excel.ListObject> denetlemek veri kaynağı kümesi yeni satırların eklenmesini sağlar ve salt okunur olmadığından sağlanan. Olaylara dayalı kod gibi yazma <xref:Microsoft.Office.Tools.Excel.ListObject.BeforeAddDataBoundRow> verileri doğrulamak için. Daha fazla bilgi için bkz: [nasıl yapılır: ListObject denetimine doğrulamak veri olduğunda bir yeni satır eklenir](../vsto/how-to-validate-data-when-a-new-row-is-added-to-a-listobject-control.md).  
  
 Bazen listesi nesnesinin veri kaynağı ilişkisi rutin hatalarına neden olur. Örneğin, görünmesini istediğiniz sütunları eşleyebilirsiniz <xref:Microsoft.Office.Tools.Excel.ListObject>, null değerler kabul etmeyen bir alan gibi kısıtlamaları olan sütunları atlarsanız, bir satır her oluşturulduğunda hatalar ortaya çıkar. Bir olay işleyicisi için eksik değerleri eklemek üzere kod yazabilirsiniz <xref:Microsoft.Office.Tools.Excel.ListObject.ErrorAddDataBoundRow> olay.  
  
## <a name="renaming-listobject-controls-in-excel"></a>Excel'de ListObject denetimlerini yeniden adlandırma  
 Excel kullanarak çalışma zamanında Excel tabloları adını değiştirmek kullanıcıların sağlar **tasarım** sekmesi. Ancak, <xref:Microsoft.Office.Tools.Excel.ListObject> denetimi bu özelliği desteklemez. Bir kullanıcı için karşılık gelen bir Excel tablosu yeniden adlandırmaya çalışırsa bir <xref:Microsoft.Office.Tools.Excel.ListObject>, çalışma kitabı kaydedildiğinde Excel tablosunun adı özgün adına otomatik olarak döner.  
  
## <a name="events"></a>Olaylar  
 Aşağıdaki olaylar kullanılabilir <xref:Microsoft.Office.Tools.Excel.ListObject> denetimi:  
  
-   <xref:Microsoft.Office.Tools.Excel.ListObject.BeforeAddDataBoundRow>  
  
-   <xref:Microsoft.Office.Tools.Excel.ListObject.BeforeDoubleClick>  
  
-   <xref:Microsoft.Office.Tools.Excel.ListObject.BeforeRightClick>  
  
-   <xref:Microsoft.Office.Tools.Excel.ListObject.BindingContextChanged>  
  
-   <xref:Microsoft.Office.Tools.Excel.ListObject.Change>  
  
-   <xref:Microsoft.Office.Tools.Excel.ListObject.DataBindingFailure>  
  
-   <xref:Microsoft.Office.Tools.Excel.ListObject.DataMemberChanged>  
  
-   <xref:Microsoft.Office.Tools.Excel.ListObject.DataSourceChanged>  
  
-   <xref:Microsoft.Office.Tools.Excel.ListObject.Deselected>  
  
-   <xref:Microsoft.Office.Tools.Excel.ListObject.ErrorAddDataBoundRow>  
  
-   <xref:Microsoft.Office.Tools.Excel.ListObject.OriginalDataRestored>  
  
-   <xref:Microsoft.Office.Tools.Excel.ListObject.Selected>  
  
-   <xref:Microsoft.Office.Tools.Excel.ListObject.SelectedIndexChanged>  
  
-   <xref:Microsoft.Office.Tools.Excel.ListObject.SelectionChange>  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Genişletilmiş nesneleri kullanarak Excel'i otomatikleştirme](../vsto/automating-excel-by-using-extended-objects.md)   
 [Nasıl yapılır: çalışma sayfalarına ListObject denetimleri ekleme](../vsto/how-to-add-listobject-controls-to-worksheets.md)   
 [Nasıl yapılır: ListObject denetimlerinin boyutunu değiştirme](../vsto/how-to-resize-listobject-controls.md)   
 [Nasıl yapılır: ListObject denetimine yeni bir satır eklendiğinde veri doğrulama](../vsto/how-to-validate-data-when-a-new-row-is-added-to-a-listobject-control.md)   
 [Nasıl yapılır: ListObject sütunlarıyla verileri eşleme](../vsto/how-to-map-listobject-columns-to-data.md)   
 [Nasıl yapılır: ListObject denetimlerini veri ile doldurma](../vsto/how-to-fill-listobject-controls-with-data.md)   
 [Office geliştirme örnekleri ve izlenecek yollar](../vsto/office-development-samples-and-walkthroughs.md)   
 [Office çözümlerinde denetimlere veri bağlama](../vsto/binding-data-to-controls-in-office-solutions.md)   
 [Genişletme Word belgelerini ve Excel çalışma kitaplarını çalışma zamanında VSTO eklentileri](../vsto/extending-word-documents-and-excel-workbooks-in-vsto-add-ins-at-run-time.md)   
 [Office belgelerindeki denetimler](../vsto/controls-on-office-documents.md)   
 [Office belgelerine çalışma zamanında denetimler ekleme](../vsto/adding-controls-to-office-documents-at-run-time.md)   
 [Nasıl yapılır: çalışma sayfalarını veritabanı verileriyle doldurma](../vsto/how-to-populate-worksheets-with-data-from-a-database.md)   
 [Konak Denetimlerinin ve Konak Öğelerinin Programlama Sınırlamaları](../vsto/programmatic-limitations-of-host-items-and-host-controls.md)  
  
  