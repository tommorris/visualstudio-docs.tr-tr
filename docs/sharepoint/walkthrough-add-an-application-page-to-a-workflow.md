---
title: 'İzlenecek yol: bir uygulama sayfasını bir iş akışına ekleme | Microsoft Docs'
ms.custom: ''
ms.date: 02/02/2017
ms.technology:
- office-development
ms.topic: conceptual
dev_langs:
- VB
- CSharp
- VB
- CSharp
helpviewer_keywords:
- SharePoint development in Visual Studio, adding applications page to workflow
- application page [SharePoint development in Visual Studio]
author: TerryGLee
ms.author: tglee
manager: douge
ms.workload:
- office
ms.openlocfilehash: 97c720ded65e46e85f8d9f20f9f509b31f2cebbb
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/16/2018
---
# <a name="walkthrough-add-an-application-page-to-a-workflow"></a>İzlenecek yol: Bir Uygulama Sayfasını Bir İş Akışına Ekleme
  Bu izlenecek bir iş akışını bir iş akışı projesine türetilmiş verileri görüntüleyen bir uygulama sayfasını nasıl ekleneceğini gösterir. Konu başlığı altında açıklanan projede derlemeler [izlenecek yol: İlişkilendirme ve başlatma formları ile iş akışı oluşturma](../sharepoint/walkthrough-creating-a-workflow-with-association-and-initiation-forms.md).  
  
 Bu kılavuz aşağıdaki görevler gösterilmiştir:  
  
-   ASPX uygulama sayfası, bir SharePoint iş akışı projesine ekleniyor.  
  
-   İş akışı projeden veri almak ve bunu düzenleme.  
  
-   Uygulama sayfasında bir tablodaki verileri görüntüleme.  
  
 [!INCLUDE[note_settings_general](../sharepoint/includes/note-settings-general-md.md)]  
  
## <a name="prerequisites"></a>Önkoşullar  
 Bu izlenecek yolu tamamlamak için aşağıdaki bileşenlere ihtiyacınız vardır:  
  
-   Desteklenen sürümleri [!INCLUDE[TLA#tla_win](../sharepoint/includes/tlasharptla-win-md.md)] ve SharePoint. Daha fazla bilgi için bkz: [SharePoint çözümleri geliştirmek için gereksinimleri](../sharepoint/requirements-for-developing-sharepoint-solutions.md).  
  
-   Visual Studio.  
  
-   Ayrıca projenin konusunda tamamlamanız gereken [izlenecek yol: İlişkilendirme ve başlatma formları ile iş akışı oluşturma](../sharepoint/walkthrough-creating-a-workflow-with-association-and-initiation-forms.md).  
  
## <a name="amending-the-workflow-code"></a>İş akışı kodu düzeltme  
 İlk olarak, gider raporu miktarını sonucu sütunun değeri ayarlamak için iş akışı için bir kod satırı ekleyin. Bu değer daha sonra gider raporu Özet hesaplamadaki kullanılır.  
  
#### <a name="to-set-the-value-of-the-outcome-column-in-the-workflow"></a>İş akışında sonucu sütunun değeri ayarlamak için  
  
1.  Projeyi konusundan yük [izlenecek yol: İlişkilendirme ve başlatma formları ile iş akışı oluşturma](../sharepoint/walkthrough-creating-a-workflow-with-association-and-initiation-forms.md) içine [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)].  
  
2.  Kod Workflow1.cs veya Workflow1.vb (programlama diliniz bağlı olarak) açın.  
  
3.  Altına `createTask1_MethodInvoking` yöntemi, aşağıdaki kodu ekleyin:  
  
    ```vb  
    createTask1_TaskProperties1.ExtendedProperties("Outcome") =   
      workflowProperties.InitiationData  
    ```  
  
    ```csharp  
    createTask1_TaskProperties1.ExtendedProperties["Outcome"] =   
      workflowProperties.InitiationData;  
    ```  
  
## <a name="creating-an-application-page"></a>Uygulama Sayfası Oluşturma  
 Ardından, bir ASPX form projeye ekleyin. Bu form gider raporu iş akışı projeden alınan veriler görüntülenir. Bunu yapmak için bir uygulama sayfasını ekleyeceksiniz. Uygulama sayfası aynı ana sayfayı diğer sayfalar SharePoint sitesinde benzer anlamı diğer SharePoint sayfaları olarak kullanır.  
  
#### <a name="to-add-an-application-page-to-the-project"></a>Uygulama sayfası projeye eklemek için  
  
1.  ExpenseReport projesini seçin ve ardından, menü çubuğunda, **proje**, **Yeni Öğe Ekle**.  
  
2.  İçinde **şablonları** bölmesinde seçin **uygulama sayfası** Şablonu proje öğesi için varsayılan adı kullanın (**ApplicaitonPage1.aspx**) ve seçin**Ekle** düğmesi.  
  
3.  İçinde [!INCLUDE[TLA2#tla_xml](../sharepoint/includes/tla2sharptla-xml-md.md)] ApplicationPage1.aspx yerine `PlaceHolderMain` aşağıdaki bölümde:  
  
    ```  
    <asp:Content ID="Main" ContentPlaceHolderID="PlaceHolderMain" runat="server">  
        <asp:Label ID="Label1" runat="server" Font-Bold="True"   
            Text="Expenses that exceeded allotted amount" Font-Size="Medium"></asp:Label>  
        <br />  
        <asp:Table ID="Table1" runat="server">  
        </asp:Table>  
    </asp:Content>  
    ```  
  
     Bu kod bir tablo başlık birlikte sayfasına ekler.  
  
4.  Uygulama sayfası için bir başlık değiştirerek eklemek `PlaceHolderPageTitleInTitleArea` aşağıdaki bölümde:  
  
    ```  
    <asp:Content ID="PageTitleInTitleArea" ContentPlaceHolderID="PlaceHolderPageTitleInTitleArea" runat="server" >  
        Expense Report Summary  
    </asp:Content>  
    ```  
  
## <a name="coding-the-application-page"></a>Uygulama sayfası kodlama  
 Ardından, harcama raporu Özet uygulama sayfası için kodu ekleyin. Kod sayfasını açtığınızda, ayrılmış harcama sınırı aştı giderleri SharePoint görev listesinde tarar. Rapor her öğesi giderleri toplamı ile birlikte listeler.  
  
#### <a name="to-code-the-application-page"></a>Kod uygulama sayfası  
  
1.  Seçin **ApplicationPage1.aspx** düğümünü ve ardından, menü çubuğunda, **Görünüm**, **kod** uygulama sayfası arka plan kod görüntülemek için.  
  
2.  Değiştir **kullanarak** veya **alma** aşağıdaki sınıfıyla üstündeki deyimleri (bağlı olarak programlama diliniz):  
  
    ```vb  
    Imports System  
    Imports Microsoft.SharePoint  
    Imports Microsoft.SharePoint.WebControls  
    Imports System.Collections  
    Imports System.Data  
    Imports System.Web.UI  
    Imports System.Web.UI.WebControls  
    Imports System.Web.UI.WebControls.WebParts  
    Imports System.Drawing  
    Imports Microsoft.SharePoint.Navigation  
    ```  
  
    ```csharp  
    using System;  
    using Microsoft.SharePoint;  
    using Microsoft.SharePoint.WebControls;  
    using System.Collections;  
    using System.Data;  
    using System.Web.UI;  
    using System.Web.UI.WebControls;  
    using System.Web.UI.WebControls.WebParts;  
    using System.Drawing;  
    using Microsoft.SharePoint.Navigation;  
    ```  
  
3.  Aşağıdaki kodu ekleyin `Page_Load` yöntemi:  
  
    ```vb  
    Try  
        ' Reference the Tasks list on the SharePoint site.  
        ' Replace "TestServer" with a valid SharePoint server name.  
        Dim site As SPSite = New SPSite("http://TestServer")  
        Dim list As SPList = site.AllWebs(0).Lists("Tasks")  
        ' string text = "";  
        Dim sum As Integer = 0  
        Table1.Rows.Clear()  
        ' Add table headers.  
        Dim hr As TableHeaderRow = New TableHeaderRow  
        hr.BackColor = Color.LightBlue  
        Dim hc1 As TableHeaderCell = New TableHeaderCell  
        Dim hc2 As TableHeaderCell = New TableHeaderCell  
        hc1.Text = "Expense Report Name"  
        hc2.Text = "Amount Exceeded"  
        hr.Cells.Add(hc1)  
        hr.Cells.Add(hc2)  
        ' Add the TableHeaderRow as the first item   
        ' in the Rows collection of the table.  
        Table1.Rows.AddAt(0, hr)  
        ' Iterate through the tasks in the Task list and collect those    
        ' that have values in the "Related Content" and "Outcome" fields   
        ' - the fields written to when expense approval is required.  
        For Each item As SPListItem In list.Items  
            Dim s_relContent As String = ""  
            Dim s_outcome As String = ""  
            Try  
                ' Task has the fields - treat as expense report.  
                s_relContent = item.GetFormattedValue("Related Content")  
                s_outcome = item.GetFormattedValue("Outcome")  
            Catch erx As System.Exception  
                ' Task does not have fields - skip it.  
                Continue For  
            End Try  
            ' Convert amount to an int and keep a running total.  
            If (Not String.IsNullOrEmpty(s_relContent) And Not   
              String.IsNullOrEmpty(s_outcome)) Then  
                sum = (sum + Convert.ToInt32(s_outcome))  
                Dim relContent As TableCell = New TableCell  
                relContent.Text = s_relContent  
                Dim outcome As TableCell = New TableCell  
                outcome.Text = ("$" + s_outcome)  
                Dim dataRow2 As TableRow = New TableRow  
                dataRow2.Cells.Add(relContent)  
                dataRow2.Cells.Add(outcome)  
                Table1.Rows.Add(dataRow2)  
            End If  
        Next  
        ' Report the sum of the reports in the table footer.  
        Dim tfr As TableFooterRow = New TableFooterRow  
        tfr.BackColor = Color.LightGreen  
        ' Create a TableCell object to contain the   
        ' text for the footer.  
        Dim ftc1 As TableCell = New TableCell  
        Dim ftc2 As TableCell = New TableCell  
        ftc1.Text = "TOTAL: "  
        ftc2.Text = ("$" + Convert.ToString(sum))  
        ' Add the TableCell object to the Cells  
        ' collection of the TableFooterRow.  
        tfr.Cells.Add(ftc1)  
        tfr.Cells.Add(ftc2)  
        ' Add the TableFooterRow to the Rows  
        ' collection of the table.  
        Table1.Rows.Add(tfr)  
    Catch errx As Exception  
        System.Diagnostics.Debug.WriteLine(("Error: " + errx.ToString))  
    End Try  
    ```  
  
    ```csharp  
    try  
    {  
        // Reference the Tasks list on the SharePoint site.  
        // Replace "TestServer" with a valid SharePoint server name.  
        SPSite site = new SPSite("http://TestServer");  
        SPList list = site.AllWebs[0].Lists["Tasks"];  
  
        // string text = "";  
        int sum = 0;  
  
        Table1.Rows.Clear();  
  
        // Add table headers.  
        TableHeaderRow hr = new TableHeaderRow();  
        hr.BackColor = Color.LightBlue;  
        TableHeaderCell hc1 = new TableHeaderCell();  
        TableHeaderCell hc2 = new TableHeaderCell();  
        hc1.Text = "Expense Report Name";  
        hc2.Text = "Amount Exceeded";  
        hr.Cells.Add(hc1);  
        hr.Cells.Add(hc2);  
        // Add the TableHeaderRow as the first item   
        // in the Rows collection of the table.  
        Table1.Rows.AddAt(0, hr);  
  
        // Iterate through the tasks in the Task list and collect those   
        // that have values in the "Related Content" and "Outcome"   
        // fields - the fields written to when expense approval is   
        // required.  
        foreach (SPListItem item in list.Items)  
        {  
            string s_relContent = "";  
            string s_outcome = "";  
  
            try  
            {  
                // Task has the fields - treat as expense report.  
                s_relContent = item.GetFormattedValue("Related   
                  Content");  
                s_outcome = item.GetFormattedValue("Outcome");  
            }  
            catch  
            {  
                // Task does not have fields - skip it.  
                continue;  
            }  
  
            if (!String.IsNullOrEmpty(s_relContent) &&   
              !String.IsNullOrEmpty(s_outcome))  
            {  
                // Convert amount to an int and keep a running total.  
                sum += Convert.ToInt32(s_outcome);  
                TableCell relContent = new TableCell();  
                relContent.Text = s_relContent;  
                TableCell outcome = new TableCell();  
                outcome.Text = "$" + s_outcome;  
                TableRow dataRow2 = new TableRow();  
                dataRow2.Cells.Add(relContent);  
                dataRow2.Cells.Add(outcome);  
                Table1.Rows.Add(dataRow2);  
            }  
        }  
  
        // Report the sum of the reports in the table footer.  
           TableFooterRow tfr = new TableFooterRow();  
        tfr.BackColor = Color.LightGreen;  
  
        // Create a TableCell object to contain the   
        // text for the footer.  
        TableCell ftc1 = new TableCell();  
        TableCell ftc2 = new TableCell();  
        ftc1.Text = "TOTAL: ";  
        ftc2.Text = "$" + Convert.ToString(sum);  
  
        // Add the TableCell object to the Cells  
        // collection of the TableFooterRow.  
        tfr.Cells.Add(ftc1);  
        tfr.Cells.Add(ftc2);  
  
        // Add the TableFooterRow to the Rows  
        // collection of the table.  
        Table1.Rows.Add(tfr);  
    }  
  
    catch (Exception errx)  
    {  
        System.Diagnostics.Debug.WriteLine("Error: " + errx.ToString());  
    }  
    ```  
  
    > [!WARNING]  
    >  Kod içinde "TestServer" SharePoint çalıştıran geçerli bir sunucu adı ile değiştirdiğinizden emin olun.  
  
## <a name="testing-the-application-page"></a>Uygulama Sayfasını Sınama  
 Ardından, uygulama sayfası gider veri doğru görüntülenip görüntülenmeyeceğini belirler.  
  
#### <a name="to-test-the-application-page"></a>Uygulama sayfasını sınamak için  
  
1.  Çalıştırın ve SharePoint'e projeyi dağıtmak için F5 tuşuna seçin.  
  
2.  Seçin **giriş** düğmesine tıklayın ve ardından **paylaşılan belgeler** SharePoint sitesinde paylaşılan belgeler listesini görüntülemek için Hızlı Başlatma çubuğunda bağlantı.  
  
3.  Bu örneğin gider raporları temsil etmek için bazı yeni belgeler belgeler listesine seçerek karşıya **belgeleri** bağlantı **LibraryTools** sayfa ve seçmeüstündekisekmesi **Belgeyi Karşıya Yükle** araç şeridinde düğmesi.  
  
4.  Bazı belgeleri karşıya yüklemesine sonra seçerek iş akışı örneği **Kitaplığı** bağlantı **LibraryTools** sekme sayfası ve ardından seçme üstündeki **kitaplık ayarları**araç şeridinde düğmesi.  
  
5.  İçinde **belge kitaplığı ayarlarını** sayfasında, **iş akışı ayarları** bağlamak **izinler ve Yönetim** bölümü.  
  
6.  İçinde **iş akışı ayarları** sayfasında, **bir iş akışı Ekle** bağlantı.  
  
7.  İçinde **bir iş akışını Ekle** sayfasında, **ExpenseReport - Workflow1** iş akışı, iş akışı için bir ad girin **ExpenseTest**ve ardından **Sonraki** düğmesi.  
  
     İş akışı ilişkilendirme formu görüntülenir. Harcama sınırı miktarı bildirmek için kullanın.  
  
8.  İlişkilendirme biçiminde girin **1000** içine **otomatik onay limiti** kutusuna ve ardından **ilişkilendirme iş akışı** düğmesi.  
  
9. Seçin **ev** düğmesi SharePoint giriş sayfasına dönün.  
  
10. Seçin **paylaşılan belgeler** Hızlı Başlatma çubuğunda bağlantı.  
  
11. Aşağı açılan okunu görüntülemek, onu seçin ve ardından karşıya yüklenen belgeleri birini **iş akışları** öğesi.  
  
12. İş akışı başlatma formu görüntülemek için ExpenseTest yanındaki görüntü seçin.  
  
13. İçinde **gider toplam** metin kutusu, 1000'den büyük bir değer girin ve ardından **iş akışı Başlat** düğmesi.  
  
     Bildirilen gider ayrılmış gider miktarını aşarsa, bir görev görev listesine eklenir. Adlı bir sütun **ExpenseTest** değerle **tamamlandı** gider raporu öğeyi paylaşılan belgeler listesinde de eklenir.  
  
14. Paylaşılan belgeler listesinde diğer belgelerle 11-13 arasındaki adımları yineleyin. (Tam sayı belgelerin önemli değildir.)  
  
15. Aşağıdaki URL'yi bir Web tarayıcısında açarak gider raporu Özet uygulama sayfasını görüntüleyin: **http://***SystemName***/_layouts/ExpenseReport/ApplicationPage1.aspx**.  
  
     Harcama raporu Özet sayfası tüm ayrılmış miktarını aştı gider raporları, tarafından aşıldı tutar ve tüm raporların toplam miktarı listeler.  
  
## <a name="next-steps"></a>Sonraki Adımlar  
 SharePoint uygulama sayfaları hakkında daha fazla bilgi için bkz: [oluşturma uygulama sayfaları SharePoint'in](../sharepoint/creating-application-pages-for-sharepoint.md).  
  
 Visual Studio'da aşağıdaki konulardan görsel Web Tasarımcı kullanarak SharePoint sayfası içeriği tasarlamak hakkında daha fazla bilgi edinebilirsiniz:  
  
-   [SharePoint için Web bölümleri oluşturma](../sharepoint/creating-web-parts-for-sharepoint.md).  
  
-   [Web Bölümleri veya uygulama sayfaları için yeniden kullanılabilir denetimler oluşturma](../sharepoint/creating-reusable-controls-for-web-parts-or-application-pages.md).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [İzlenecek yol: İlişkilendirme ve başlatma formları ile iş akışı oluşturma](../sharepoint/walkthrough-creating-a-workflow-with-association-and-initiation-forms.md)   
 [Nasıl yapılır: uygulama sayfası oluşturma](../sharepoint/how-to-create-an-application-page.md)   
 [SharePoint için uygulama sayfaları oluşturma](../sharepoint/creating-application-pages-for-sharepoint.md)   
 [SharePoint Çözümleri Geliştirme](../sharepoint/developing-sharepoint-solutions.md)  
  
  