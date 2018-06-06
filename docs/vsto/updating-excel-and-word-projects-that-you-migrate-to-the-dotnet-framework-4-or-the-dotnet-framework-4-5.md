---
title: .NET Framework 4 veya .NET Framework 4. 5'e geçiş Excel ve Word projelerini güncelleştirme
ms.custom: ''
ms.date: 02/02/2017
ms.technology:
- office-development
ms.topic: conceptual
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- Office projects [Office development in Visual Studio], migrating to .NET Framework 4
author: TerryGLee
ms.author: tglee
manager: douge
ms.workload:
- office
ms.openlocfilehash: 38734366f5b7d19ef0780c8ef998efb19e50a46f
ms.sourcegitcommit: 4cd4aef53e7035d23e7d1d0f66f51ac8480622a1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/05/2018
ms.locfileid: "34767536"
---
# <a name="update-excel-and-word-projects-that-you-migrate-to-the-net-framework-4-or-the-net-framework-45"></a>.NET Framework 4 veya .NET Framework 4. 5'e geçiş Excel ve Word projelerini güncelleştirme
  Aşağıdaki özelliklerden herhangi birini kullanan bir Excel veya Word'den proje varsa, hedef Framework'ü değiştirilirse kodunuzu değiştirmelisiniz [!INCLUDE[net_v40_short](../sharepoint/includes/net-v40-short-md.md)] ya da daha sonra:  
  
-   [GetVstoObject ve HasVstoObject yöntemleri](#GetVstoObject)  
  
-   [Belge düzeyi projelerine oluşturulan sınıflar](#generatedclasses)  
  
-   [Belgelerindeki Windows Forms denetimleri](#winforms)  
  
-   [Word içerik denetimi olayları](#ccevents)  
  
-   [OLEObject ve OLEControl sınıfları](#ole)  
  
-   [Controls.Item(Object) özelliği](#itemproperty)  
  
-   [CollectionBase'den türetilen koleksiyonları](#collections)  
  
 Ayrıca kaldırmalısınız `Microsoft.Office.Tools.Excel.ExcelLocale1033Attribute` ve başvurular `Microsoft.Office.Tools.Excel.ExcelLocale1033Proxy` için güncellendiyse Excel projeleri sınıfından [!INCLUDE[net_v40_short](../sharepoint/includes/net-v40-short-md.md)] veya sonraki bir sürümü. Visual Studio bu öznitelik veya sınıf başvurusu sizin için kaldırmaz.  
  
## <a name="remove-the-excellocale1033-attribute-from-excel-projects"></a>Excel projeleri ExcelLocale1033 özniteliği Kaldır  
 `Microsoft.Office.Tools.Excel.ExcelLocale1033Attribute` Hedefleyen çözümler için kullanılan Office çalışma zamanı için Visual Studio 2010 Araçları kısmından kaldırılan [!INCLUDE[net_v40_short](../sharepoint/includes/net-v40-short-md.md)] veya sonraki bir sürümü. Ortak dil çalışma zamanı (CLR) [!INCLUDE[net_v40_short](../sharepoint/includes/net-v40-short-md.md)] ve daha sonra her zaman geçişleri yerel ayar kimliği 1033 Excel nesne modeline ve artık bu özniteliği bu davranışı devre dışı bırakmak için kullanabilirsiniz. Daha fazla bilgi için bkz: [Genelleştirme ve yerelleştirme Excel çözümlerini](../vsto/globalization-and-localization-of-excel-solutions.md).  
  
### <a name="to-remove-the-excellocale1033attribute"></a>ExcelLocale1033Attribute kaldırmak için  
  
1.  Projesini Visual Studio'da Aç açın **Çözüm Gezgini**.  
  
2.  Altında **özellikleri** düğümünü (C# ' ta) veya **My proje** düğümünü (Visual Basic) için kod düzenleyicisinde açmak için AssemblyInfo kod dosyasını çift tıklatın.  
  
    > [!NOTE]  
    >  Visual Basic projelerinde'ı tıklatmalısınız **tüm dosyaları göster** düğmesini **Çözüm Gezgini** AssemblyInfo kod dosyasını görmek için.  
  
3.  Bulun `Microsoft.Office.Tools.Excel.ExcelLocale1033Attribute` ve dosyadan kaldırın veya açıklamadan çıkarın.  
  
    ```vb  
    <Assembly: ExcelLocale1033Proxy(True)>  
    ```  
  
    ```csharp  
    [assembly: ExcelLocale1033Proxy(true)]  
    ```  
  
## <a name="remove-a-reference-to-the-excellocal1033proxy-class"></a>ExcelLocal1033Proxy sınıfının bir başvurusunu kaldırın  
 Microsoft Office sistemi için Microsoft Visual Studio 2005 araçları kullanılarak oluşturulan projeleri örneği Excel <xref:Microsoft.Office.Interop.Excel.Application> kullanarak nesne `Microsoft.Office.Tools.Excel.ExcelLocale1033Proxy` sınıfı. Bu sınıf çözümleri hedefleyen kullandığı Office çalışma zamanı için Visual Studio 2010 Araçları kısmı kaldırıldığı [!INCLUDE[net_v40_short](../sharepoint/includes/net-v40-short-md.md)] veya sonraki bir sürümü. Bu nedenle, kaldırın veya bu sınıf başvuran kod satırını açıklama satırı yapın.  
  
### <a name="to-remove-the-reference-to-the-excellocal1033proxy-class"></a>ExcelLocal1033Proxy sınıfı başvurusunu kaldırmak için  
  
1.  Visual Studio'da projeyi açın ve ardından açın **Çözüm Gezgini**.  
  
2.  İçinde **Çözüm Gezgini**, kısayol menüsünü açın *ThisAddIn.cs* için (C#) veya *ThisAddIn.vb* (için Visual Basic) ve ardından **görünümükodu**.  
  
3.  Kod Düzenleyicisi'nde, içinde `VSTO generated code` bölge, kaldırmak veya kod aşağıdaki satırını açıklama.  
  
    ```vb  
    Me.Application = CType(Microsoft.Office.Tools.Excel.ExcelLocale1033Proxy.Wrap(GetType(Excel.Application), Me.Application), Excel.Application)  
  
    ```  
  
    ```csharp  
    this.Application = (Excel.Application)Microsoft.Office.Tools.Excel.ExcelLocale1033Proxy.Wrap(typeof(Excel.Application), this.Application);  
  
    ```  
  
##  <a name="GetVstoObject"></a> GetVstoObject ve HasVstoObject yöntemlerini kullanan kodu güncelleştir  
 .NET Framework 3. 5'i hedefleyen projelerde `GetVstoObject` veya `HasVstoObject` projenizdeki yerel nesnelerini genişletme yöntemi olarak yöntemleri kullanılabilir: <xref:Microsoft.Office.Interop.Word.Document>, <xref:Microsoft.Office.Interop.Excel.Workbook>, <xref:Microsoft.Office.Interop.Excel.Worksheet>, veya <xref:Microsoft.Office.Interop.Excel.ListObject>. Bu yöntemleri çağırırken parametre geçirmek gerekmez. Aşağıdaki kod örneğinde bir Word VSTO .NET Framework 3.5 hedefleyen eklenti GetVstoObject yöntemi kullanmayı gösterir.  
  
```vb  
Dim vstoDocument as Microsoft.Office.Tools.Word.Document = _  
    Globals.ThisAddIn.Application.ActiveDocument.GetVstoObject()  
```  
  
```csharp  
Microsoft.Office.Tools.Word.Document vstoDocument =   
    Globals.ThisAddIn.Application.ActiveDocument.GetVstoObject();  
```  
  
 ' İ hedefleyen projelerde [!INCLUDE[net_v40_short](../sharepoint/includes/net-v40-short-md.md)] veya daha sonra bu yöntemler aşağıdaki yollardan biriyle erişmek üzere kodunuzu değiştirmeniz gerekir:  
  
-   Bu yöntemleri genişletme yöntemleri olarak üzerinde erişmeye devam edebilirsiniz <xref:Microsoft.Office.Interop.Word.Document>, <xref:Microsoft.Office.Interop.Excel.Workbook>, <xref:Microsoft.Office.Interop.Excel.Worksheet>, veya <xref:Microsoft.Office.Interop.Excel.ListObject> nesneleri. Bununla birlikte, artık tarafından döndürülen nesne geçmesi gereken `Globals.Factory` bu yöntemlere özelliği.  
  
    ```vb  
    Dim vstoDocument as Microsoft.Office.Tools.Word.Document = _  
        Globals.ThisAddIn.Application.ActiveDocument.GetVstoObject(Globals.Factory)  
    ```  
  
    ```csharp  
    Microsoft.Office.Tools.Word.Document vstoDocument =   
        Globals.ThisAddIn.Application.ActiveDocument.GetVstoObject(Globals.Factory);  
    ```  
  
-   Alternatif olarak, bu yöntem tarafından döndürülen nesne üzerinde erişebilir `Globals.Factory` özelliği. Bu yöntemlere bu yolla eriştiğinizde, yönteme genişletmek istediğiniz yerel nesne geçmesi gerekir.  
  
    ```vb  
    Dim vstoDocument as Microsoft.Office.Tools.Word.Document = _  
        Globals.Factory.GetVstoObject(Globals.ThisAddIn.Application.ActiveDocument)  
    ```  
  
    ```csharp  
    Microsoft.Office.Tools.Word.Document vstoDocument =   
        Globals.Factory.GetVstoObject(Globals.ThisAddIn.Application.ActiveDocument);  
    ```  
  
 Daha fazla bilgi için bkz: [genişletmek Word belgelerini ve Excel çalışma kitaplarını VSTO eklentileri çalışma zamanında](../vsto/extending-word-documents-and-excel-workbooks-in-vsto-add-ins-at-run-time.md).  
  
##  <a name="generatedclasses"></a> Belge düzeyi projelerine oluşturulan sınıfları kullanan kodu güncelleştir  
 .NET Framework 3.5 hedefleyen belge düzeyi projelerde aşağıdaki sınıflarda projelerindeki oluşturulan sınıflar türetmek [!INCLUDE[vsto_runtime](../vsto/includes/vsto-runtime-md.md)]:  
  
-   `ThisDocument`: <xref:Microsoft.Office.Tools.Word.Document>  
  
-   `ThisWorkbook`: <xref:Microsoft.Office.Tools.Excel.Workbook>  
  
-   `Sheet` *n*: <xref:Microsoft.Office.Tools.Excel.Worksheet>  
  
-   `Chart` *n*: <xref:Microsoft.Office.Tools.Excel.ChartSheet>  
  
 ' İ hedefleyen projelerde [!INCLUDE[net_v40_short](../sharepoint/includes/net-v40-short-md.md)] veya sonraki sürümlerde, türlerinde [!INCLUDE[vsto_runtime](../vsto/includes/vsto-runtime-md.md)] yukarıda listelenen, sınıfları yerine arabirimlerdir. Oluşturulan projeleri hedefleyen sınıfları [!INCLUDE[net_v40_short](../sharepoint/includes/net-v40-short-md.md)] veya daha sonra aşağıdaki yeni sınıflarda öğesinden türetilen [!INCLUDE[vsto_runtime](../vsto/includes/vsto-runtime-md.md)]:  
  
-   `ThisDocument`: <xref:Microsoft.Office.Tools.Word.DocumentBase>  
  
-   `ThisWorkbook`: <xref:Microsoft.Office.Tools.Excel.WorkbookBase>  
  
-   `Sheet` *n*: <xref:Microsoft.Office.Tools.Excel.WorksheetBase>  
  
-   `Chart` *n*: <xref:Microsoft.Office.Tools.Excel.ChartSheetBase>  
  
 Projenizdeki kod türetildiği temel sınıf olarak oluşturulan sınıflar birinin örneğine başvuruyorsa, kodu değiştirmeniz gerekir.  
  
 Örneğin, .NET Framework 3.5 hedefleyen bir Excel çalışma kitabı projesinde, oluşturulan örneklerinde bazı çalışma gerçekleştirir yardımcı bir yöntem olabilir `Sheet` *n* projenizdeki sınıfları.  
  
```vb  
Private Sub DoSomethingToSheet(ByVal worksheet As Microsoft.Office.Tools.Excel.Worksheet)  
    ' Do something to the worksheet object.  
End Sub  
```  
  
```csharp  
private void DoSomethingToSheet(Microsoft.Office.Tools.Excel.Worksheet worksheet)  
{  
    // Do something to the worksheet object.  
}  
```  
  
 Projeyi yeniden hedefleyin varsa [!INCLUDE[net_v40_short](../sharepoint/includes/net-v40-short-md.md)] veya daha sonra şu değişikliklerden birini kodunuzu yapmanız gerekir:  
  
-   Çağıran herhangi bir kod değiştirme `DoSomethingToSheet` geçirmek için yöntemini <xref:Microsoft.Office.Tools.Excel.WorksheetBase.Base%2A> özelliği bir <xref:Microsoft.Office.Tools.Excel.WorksheetBase> projenizdeki nesnesi. Bu özellik döndürür bir <xref:Microsoft.Office.Tools.Excel.Worksheet> nesnesi.  
  
    ```vb  
    DoSomethingToSheet(Globals.Sheet1.Base)  
    ```  
  
    ```csharp  
    DoSomethingToSheet(Globals.Sheet1.Base);  
    ```  
  
-   Değiştirme `DoSomethingToSheet` beklenir yöntem parametresi bir <xref:Microsoft.Office.Tools.Excel.WorksheetBase> yerine nesne.  
  
    ```vb  
    Private Sub DoSomethingToSheet(ByVal worksheet As Microsoft.Office.Tools.Excel.WorksheetBase)  
        ' Do something to the worksheet object.  
    End Sub  
    ```  
  
    ```csharp  
    private void DoSomethingToSheet (Microsoft.Office.Tools.Excel.WorksheetBase worksheet)  
    {  
        // Do something to the worksheet object.  
    }  
    ```  
  
##  <a name="winforms"></a> Belgelerindeki Windows Forms denetimleri kullanan kodu güncelleştir  
 Eklemelisiniz bir **kullanarak** (C#) veya **içeri aktarmalar** (Visual Basic) deyimini <xref:Microsoft.Office.Tools.Excel> veya <xref:Microsoft.Office.Tools.Word> Windows Forms eklemek için denetimleri özelliği kullanan herhangi bir kod dosyasının en üstüne ad alanı Belge ya da çalışma sayfasına program aracılığıyla denetler.  
  
 Windows Forms denetimleri ekleme yöntemleri .NET Framework 3.5 hedefleyen projelerde (gibi `AddButton` yöntemi) içinde tanımlanan <xref:Microsoft.Office.Tools.Excel.ControlCollection> ve <xref:Microsoft.Office.Tools.Word.ControlCollection> sınıfları.  
  
 ' İ hedefleyen projelerde [!INCLUDE[net_v40_short](../sharepoint/includes/net-v40-short-md.md)] ya da daha sonra bu yöntemleri denetimleri özelliği kullanılabilir genişletme yöntemleri. Bu uzantı yöntemleri kullanmak için yöntemleri kullanın kod dosyası olması gerekir bir **kullanarak** veya **içeri aktarmalar** bildirimi <xref:Microsoft.Office.Tools.Excel> veya <xref:Microsoft.Office.Tools.Word> ad alanı. Bu bildirimi hedefleyen yeni projelerde otomatik olarak oluşturulan [!INCLUDE[net_v40_short](../sharepoint/includes/net-v40-short-md.md)] veya sonraki bir sürümü. Projenizin hedefini değiştirdiğinizde eklemelisiniz ancak, bu deyimi otomatik olarak projelerinde .NET Framework 3.5 hedefleyen eklenmez.  
  
 Daha fazla bilgi için bkz: [Office belgelerine çalışma zamanında denetimler ekleme](../vsto/adding-controls-to-office-documents-at-run-time.md).  
  
##  <a name="ccevents"></a> Word içerik denetimi olayları işleyen kodu güncelleştir  
 .NET Framework 3.5 hedefleyen projelerde, Word içerik denetimlerinin olayları genel tarafından işlenen <xref:System.EventHandler%601> temsilci. ' İ hedefleyen projelerde [!INCLUDE[net_v40_short](../sharepoint/includes/net-v40-short-md.md)] veya daha sonra bu olaylar diğer temsilciler tarafından işlenir.  
  
 Aşağıdaki tabloda Word içerik denetimi olayları ve hedefleyen projelerde bunlarla ilişkili temsilciler listelenmektedir [!INCLUDE[net_v40_short](../sharepoint/includes/net-v40-short-md.md)] veya sonraki bir sürümü.  
  
|Olay|Kullanılacak temsilci [!INCLUDE[net_v40_short](../sharepoint/includes/net-v40-short-md.md)] ve sonraki projeleri|  
|-----------|---------------------------------------------------------------------------------------------------|  
|<xref:Microsoft.Office.Tools.Word.ContentControlBase.Added>|<xref:Microsoft.Office.Tools.Word.ContentControlAddedEventHandler>|  
|<xref:Microsoft.Office.Tools.Word.ContentControlBase.ContentUpdating>|<xref:Microsoft.Office.Tools.Word.ContentControlContentUpdatingEventHandler>|  
|<xref:Microsoft.Office.Tools.Word.ContentControlBase.Deleting>|<xref:Microsoft.Office.Tools.Word.ContentControlDeletingEventHandler>|  
|<xref:Microsoft.Office.Tools.Word.ContentControlBase.Entering>|<xref:Microsoft.Office.Tools.Word.ContentControlEnteringEventHandler>|  
|<xref:Microsoft.Office.Tools.Word.ContentControlBase.Exiting>|<xref:Microsoft.Office.Tools.Word.ContentControlExitingEventHandler>|  
|<xref:Microsoft.Office.Tools.Word.ContentControlBase.StoreUpdating>|<xref:Microsoft.Office.Tools.Word.ContentControlStoreUpdatingEventHandler>|  
  
##  <a name="ole"></a> OLEObject ve OLEControl sınıfları kullanan kodu güncelleştir  
 .NET Framework 3.5 hedefleyen projelerde, özel denetimler (örneğin, Windows Forms kullanıcı denetimi) bir belge veya çalışma sayfasını kullanarak ekleyebileceğiniz `Microsoft.Office.Tools.Excel.OLEObject` ve `Microsoft.Office.Tools.Word.OLEControl` sınıfları.  
  
 ' İ hedefleyen projelerde [!INCLUDE[net_v40_short](../sharepoint/includes/net-v40-short-md.md)] veya daha sonra bu sınıfları tarafından değiştirilmiş <xref:Microsoft.Office.Tools.Excel.ControlSite> ve <xref:Microsoft.Office.Tools.Word.ControlSite> arabirimleri. Başvurduğu kodu değiştirmeniz gerekir `Microsoft.Office.Tools.Excel.OLEObject` ve `Microsoft.Office.Tools.Word.OLEControl` başvuracak şekilde <xref:Microsoft.Office.Tools.Excel.ControlSite> ve <xref:Microsoft.Office.Tools.Word.ControlSite>. Yeni adları dışında bu denetimler, .NET Framework 3.5 hedefleyen projelerde aynı şekilde davranır.  
  
 Daha fazla bilgi için bkz: [Office belgelerine çalışma zamanında denetimler ekleme](../vsto/adding-controls-to-office-documents-at-run-time.md).  
  
##  <a name="itemproperty"></a> Controls.Item(Object) özelliği kullanan kodu güncelleştir  
 .NET Framework 3.5 hedefleyen projelerde, Microsoft.Office.Tools.Excel.Worksheet.Controls Item(Object) özelliğinin kullanabilirsiniz veya `Microsoft.Office.Tools.Excel.Worksheet.Controls` belge veya çalışma belirli bir denetimi olup olmadığını belirlemek için koleksiyon.  
  
 ' İ hedefleyen projelerde [!INCLUDE[net_v40_short](../sharepoint/includes/net-v40-short-md.md)] veya daha sonra bu koleksiyonları Item(Object) özelliği kaldırıldı. Belge veya çalışma belirtilen denetim içerip içermediğini belirlemek için Contains(System.Object) yöntemini kullanmak <xref:Microsoft.Office.Tools.Word.Document.Controls%2A> veya <xref:Microsoft.Office.Tools.Excel.Worksheet.Controls%2A> koleksiyon yerine.  
  
 Belgeleri çalışma sayfaları ve denetimleri toplama ile ilgili daha fazla bilgi için bkz: [Office belgelerine çalışma zamanında denetimler ekleme](../vsto/adding-controls-to-office-documents-at-run-time.md).  
  
##  <a name="collections"></a> CollectionBase'den türetilen koleksiyonları kullanır kodunu güncelleştirin  
 .NET Framework 3.5 hedefleyen projelerde, birkaç koleksiyon türleri içinde [!INCLUDE[vsto_runtime](../vsto/includes/vsto-runtime-md.md)] öğesinden türetilen <xref:System.Collections.CollectionBase> gibi sınıfı `Microsoft.Office.Tools.SmartTagCollection`, `Microsoft.Office.Tools.Excel.ControlCollection`, ve `Microsoft.Office.Tools.Word.ControlCollection`.  
  
 ' İ hedefleyen projelerde [!INCLUDE[net_v40_short](../sharepoint/includes/net-v40-short-md.md)] ya da daha sonra bu koleksiyon türleri şimdi öğesinden türetilen değil arabirimleri <xref:System.Collections.CollectionBase>. Bazı üyeler artık gibi bu koleksiyon türlerinde kullanılabilir <xref:System.Collections.CollectionBase.Capacity%2A>, <xref:System.Collections.CollectionBase.List%2A>, ve <xref:System.Collections.CollectionBase.InnerList%2A>.  
  
## <a name="see-also"></a>Ayrıca bkz.  
 [Office çözümlerini .NET Framework 4 veya sonraki bir sürümüne geçirme](../vsto/migrating-office-solutions-to-the-dotnet-framework-4-or-later.md)   
 [İçerik denetimleri](../vsto/content-controls.md)   
 [Word belgelerini ve Excel çalışma kitaplarını VSTO eklentileri çalışma zamanında genişletme](../vsto/extending-word-documents-and-excel-workbooks-in-vsto-add-ins-at-run-time.md)   
 [Office belgelerine çalışma zamanında denetimler ekleme](../vsto/adding-controls-to-office-documents-at-run-time.md)   
 [Office projelerindeki nesnelere genel erişim](../vsto/global-access-to-objects-in-office-projects.md)  
  
  