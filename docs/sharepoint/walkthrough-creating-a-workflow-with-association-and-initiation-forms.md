---
title: 'İzlenecek yol: İlişkilendirme ve başlatma formları ile iş akışı oluşturma | Microsoft Docs'
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
- SharePoint development in Visual Studio, workflows
- SharePoint development in Visual Studio, workflow association forms
- workflows [SharePoint development in Visual Studio]
- association forms [SharePoint development in Visual Studio]
- initiation forms [SharePoint development in Visual Studio]
- SharePoint development in Visual Studio, workflow initiation forms
author: TerryGLee
ms.author: tglee
manager: douge
ms.workload:
- office
ms.openlocfilehash: 92aefd2292976bd9dcb50603e93b460cdf2bf991
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/16/2018
---
# <a name="walkthrough-creating-a-workflow-with-association-and-initiation-forms"></a>İzlenecek yol: İlişkilendirme ve Başlatma Formları ile İş Akışı Oluşturma
  Bu kılavuzda ilişkilendirme ve başlatma formları kullanımını içeren bir temel sıralı iş akışının nasıl oluşturulacağını gösterir. Bunlar ilk olarak SharePoint Yöneticisi (ilişkilendirme form) tarafından ilişkilendirilmiş zaman ve iş akışı (başlatma formu) kullanıcı tarafından başlatıldığında bir iş akışına eklenecek parametrelerini etkinleştirme ASPX formları bulunabilir.  
  
 Bu kılavuzda, burada aşağıdaki gereksinimlere sahip bir onay iş akışı gider raporları oluşturmak için bir kullanıcının istediği bir senaryo özetlenmektedir:  
  
-   İş akışı bir listesi ile ilişkili olduğunda, yönetici dolar sınırı gider raporları için burada girmeleri ilişkilendirme formla istenir.  
  
-   Çalışanların gider raporlarının paylaşılan belgeler listesine karşıya yükleme, iş akışını başlatmak ve iş akışı başlatma biçiminde Toplam gider girin.  
  
-   Toplam çalışan gider raporu Yönetici'nin önceden tanımlanmış sınırını aşarsa, bir görev çalışanın Yöneticisi gider raporu onaylamak oluşturulur. Ancak, bir çalışanın gider raporu toplam harcama sınırı eşit veya daha az ise, bir otomatik onaylı iletisi iş akışı Geçmiş listesine yazılır.  
  
 Bu izlenecek yol aşağıdaki görevleri gösterir:  
  
-   Bir SharePoint listesi tanımı sıralı iş akışı projesinde oluşturma [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)].  
  
-   Bir iş akışı zamanlama oluşturma.  
  
-   İş akışı etkinlik olayları işleme.  
  
-   İş akışı ilişkilendirme ve başlatma formları oluşturma.  
  
-   İş akışı ilişkilendirme.  
  
-   El ile iş akışı başlatma.  
  
> [!NOTE]  
>  Bu kılavuz bir sıralı iş akışı projesinde kullansa da, işlem durumu makine iş akışları için aynıdır.  
>   
>  Ayrıca, bilgisayarınız bazıları için farklı adlar veya konumlar gösterebilir [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)] kullanıcı arabirimi öğeleri aşağıdaki yönergeleri. [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)] Sahip sürümü ve kullandığınız ayarlar bu öğeleri belirler. Daha fazla bilgi için bkz: [Visual Studio IDE'yi kişiselleştirme](../ide/personalizing-the-visual-studio-ide.md).  
  
## <a name="prerequisites"></a>Önkoşullar  
 Bu izlenecek yolu tamamlamak için aşağıdaki bileşenlere ihtiyacınız vardır:  
  
-   Desteklenen sürümleri [!INCLUDE[TLA#tla_win](../sharepoint/includes/tlasharptla-win-md.md)] ve SharePoint. Daha fazla bilgi için bkz: [SharePoint çözümleri geliştirmek için gereksinimleri](../sharepoint/requirements-for-developing-sharepoint-solutions.md).  
  
-   Visual Studio.  
  
## <a name="creating-a-sharepoint-sequential-workflow-project"></a>Bir SharePoint sıralı iş akışı projesi oluşturma  
 İlk olarak, bir sıralı iş akışı projesinde oluşturun [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)]. Sıralı iş akışı son etkinlik tamamlanana kadar sırayla yürütülen bir dizi adımı kullanılıyor. Bu yordamda, SharePoint'te paylaşılan belgeler listesine uygulayan bir sıralı iş akışı oluşturur. İş akışının Sihirbazı iş akışı site veya liste tanımı ile ilişkilendirmenizi sağlar ve iş akışı başlayacağını belirlemenize olanak tanır.  
  
#### <a name="to-create-a-sharepoint-sequential-workflow-project"></a>Bir SharePoint sıralı iş akışı projesi oluşturmak için  
  
1.  Menü çubuğunda seçin **dosya**, **yeni**, **proje** görüntülemek için **yeni proje** iletişim kutusu.  
  
2.  Genişletme **SharePoint** ya da düğümünde **Visual C#** veya **Visual Basic**ve ardından **2010** düğümü.  
  
3.  İçinde **şablonları** bölmesinde seçin **SharePoint 2010 proje** proje şablonu.  
  
4.  İçinde **adı** kutusuna **ExpenseReport** ve ardından **Tamam** düğmesi.  
  
     **SharePoint Özelleştirme Sihirbazı'nı** görüntülenir.  
  
5.  İçinde **hata ayıklama için site ve güvenlik düzeyini belirtmek** sayfasında, **Grup çözümü olarak dağıtma** seçenek düğmesine ve ardından **son** kabul et düğmesi güven düzeyi ve varsayılan site.  
  
     Bu adım, çözüm için güven düzeyini ayrıca seçeneği yalnızca kullanılabilir iş akışı projeleri için Grup çözümü olarak ayarlar.  
  
6.  İçinde **Çözüm Gezgini**, proje düğümünü seçin.  
  
7.  Menü çubuğunda seçin **proje**, **Yeni Öğe Ekle**.  
  
8.  Ya da altında **Visual C#** veya **Visual Basic**, genişletin **SharePoint** düğümünü ve ardından **2010** düğümü.  
  
9. İçinde **şablonları** bölmesinde seçin **sıralı iş akışı (yalnızca Grup çözümünün)** şablonu ve ardından **Ekle** düğmesi.  
  
     **SharePoint Özelleştirme Sihirbazı'nı** görüntülenir.  
  
10. İçinde **hata ayıklama için iş akışı adını** sayfasında, varsayılan adı kabul edin (**ExpenseReport - Workflow1**). Varsayılan iş akışı şablon türü değeri tutun (**liste iş akışı)**. Seçin **sonraki** düğmesi.  
  
11. İçinde **iş akışı bir hata ayıklama oturumu otomatik olarak ilişkilendirmek için Visual Studio ister misiniz?** sayfasında, bu işaretlenirse, iş akışı şablonunuzu otomatik olarak ilişkilendirir kutusunun işaretini kaldırın.  
  
     Bu adım el ile ilişkilendirme formu görüntüleyen bir iş akışı daha sonra paylaşılan belgeler listesiyle ilişkilendirmenizi sağlar.  
  
12. Seçin **son** düğmesi.  
  
## <a name="adding-an-association-form-to-the-workflow"></a>Bir ilişkilendirme formu iş akışına ekleme  
 Ardından, oluşturun bir. SharePoint Yöneticisi bir harcama raporu belgeyle iş akışı ilk ilişkilendirildiğinde görüntülenen ASPX ilişkilendirme formu.  
  
#### <a name="to-add-an-association-form-to-the-workflow"></a>Bir ilişkilendirme formu iş akışına eklemek için  
  
1.  Seçin **Workflow1** düğümünde **Çözüm Gezgini**.  
  
2.  Menü çubuğunda seçin **proje**, **Yeni Öğe Ekle** görüntülemek için **Yeni Öğe Ekle** iletişim kutusu.  
  
3.  İletişim kutusu ağaç görünümünde genişletin **Visual C#** veya **Visual Basic** (Proje dilinizi bağlı olarak), genişletin **SharePoint** düğümü ve ardından seçin**2010** düğümü.  
  
4.  Şablonları listesinden seçip **iş akışı ilişkilendirme formu** şablonu.  
  
5.  İçinde **adı** metin kutusuna **ExpenseReportAssocForm.aspx**.  
  
6.  Seçin **Ekle** projeye form ekleme düğmesi.  
  
## <a name="designing-and-coding-the-association-form"></a>Tasarlama ve ilişkilendirme formu kodlama  
 Bu yordamda, denetimleri ile kod ekleyerek ilişkilendirme formu işlevsellik tanıtmaktadır.  
  
#### <a name="to-design-and-code-the-association-form"></a>Tasarım ve kod ilişkilendirme formu  
  
1.  İlişkilendirme biçiminde (ExpenseReportAssocForm.aspx) bulun `asp:Content` olan öğeyi `ID="Main"`.  
  
2.  Doğrudan ilk satırında sonra bu content öğesi, bir etiket ve gider onay sınırını ister textbox oluşturmak için aşağıdaki kodu ekleyin (*AutoApproveLimit*):  
  
    ```  
    <asp:Label ID="lblAutoApproveLimit" Text="Auto Approval Limit:" runat="server" />  
  
    <asp:TextBox ID="AutoApproveLimit" runat="server" />  
    <br /><br />  
    ```  
  
3.  Genişletme **ExpenseReportAssocForm.aspx** dosyasını **Çözüm Gezgini** bağımlı dosyaları görüntülemek için.  
  
    > [!NOTE]  
    >  Projenizi ise [!INCLUDE[vbprvb](../sharepoint/includes/vbprvb-md.md)], seçmeniz gerekir **tüm dosyaları görüntüle** bu adımı gerçekleştirmek için düğmesi.  
  
4.  ExpenseReportAssocForm.aspx dosyası için kısayol menüsünü açın ve seçin **görünümü kodu**.  
  
5.  Değiştir `GetAssociationData` yöntemiyle:  
  
    ```vb  
    Private Function GetAssociationData() As String  
        ' TODO: Return a string that contains the association data that   
        ' will be passed to the workflow. Typically, this is in XML   
        ' format.  
        Return Me.AutoApproveLimit.Text  
    End Function  
    ```  
  
    ```csharp  
    private string GetAssociationData()  
    {  
        // TODO: Return a string that contains the association data that   
        // will be passed to the workflow. Typically, this is in XML   
        // format.  
        return this.AutoApproveLimit.Text;  
    }  
    ```  
  
## <a name="adding-an-initiation-form-to-the-workflow"></a>İş akışına bir başlatma formu ekleme  
 Ardından, kullanıcıların gider raporlarının karşı iş akışını çalıştırdığınızda görüntülenen başlatma formu oluşturun.  
  
#### <a name="to-create-an-initiation-form"></a>Başlatma formu oluşturmak için  
  
1.  Seçin **Workflow1** düğümünde **Çözüm Gezgini**.  
  
2.  Menü çubuğunda seçin **proje**, **Yeni Öğe Ekle** görüntülemek **Yeni Öğe Ekle** iletişim kutusu.  
  
3.  İletişim kutusu ağaç görünümünde genişletin **Visual C#** veya **Visual Basic** (Proje dilinizi bağlı olarak), genişletin **SharePoint** düğümü ve ardından seçin**2010** düğümü.  
  
4.  Şablonları listesinden seçip **iş akışı başlatma formu** şablonu.  
  
5.  İçinde **adı** metin kutusuna **ExpenseReportInitForm.aspx**.  
  
6.  Seçin **Ekle** projeye form ekleme düğmesi.  
  
## <a name="designing-and-coding-the-initiation-form"></a>Tasarlama ve başlatma formu kodlama  
 Ardından, başlatma formu işlevsellik denetimleri ile kod ekleyerek tanıtır.  
  
#### <a name="to-code-the-initiation-form"></a>Kod başlatma formu  
  
1.  Başlatma biçiminde (ExpenseReportInitForm.aspx) bulun `asp:Content` içeren öğeyi `ID="Main"`.  
  
2.  Doğrudan bu içerik öğesindeki ilk satırından sonra bir etiket ve gider onay limiti görüntüler textbox oluşturmak için aşağıdaki kodu ekleyin (*AutoApproveLimit*) ilişkilendirme formun ve başka bir etiket girildi ve textbox için harcama toplam istemek için (*ExpenseTotal*):  
  
    ```  
    <asp:Label ID="lblAutoApproveLimit" Text="Auto Approval Limit:" runat="server" />  
  
    <asp:TextBox ID="AutoApproveLimit" ReadOnly="true" runat="server" />  
    <br /><br />  
    <asp:Label ID="lblExpenseTotal" Text="Expense Total:" runat="server" />  
  
    <asp:TextBox ID="ExpenseTotal" runat="server" />  
    <br /><br />  
    ```  
  
3.  Genişletme **ExpenseReportInitForm.aspx** dosyasını **Çözüm Gezgini** bağımlı dosyaları görüntülemek için.  
  
4.  ExpenseReportInitForm.aspx dosyası için kısayol menüsünü açın ve seçin **görünümü kodu**.  
  
5.  Değiştir `Page_Load` aşağıdaki örnek yöntemiyle:  
  
    ```vb  
    Protected Sub Page_Load(ByVal sender As Object, ByVal e As   
      EventArgs) Handles Me.Load  
        InitializeParams()  
        Me.AutoApproveLimit.Text = workflowList.WorkflowAssociations(New   
          Guid(associationGuid)).AssociationData  
        ' Optionally, add code here to pre-populate your form fields.  
    End Sub  
    ```  
  
    ```csharp  
    protected void Page_Load(object sender, EventArgs e)  
    {  
        InitializeParams();  
        this.AutoApproveLimit.Text =   
          workflowList.WorkflowAssociations[new   
          Guid(associationGuid)].AssociationData;  
    }  
    ```  
  
6.  Değiştir `GetInitiationData` aşağıdaki örnek yöntemiyle:  
  
    ```vb  
    ' This method is called when the user clicks the button to start the workflow.  
    Private Function GetInitiationData() As String  
        Return Me.ExpenseTotal.Text  
        ' TODO: Return a string that contains the initiation data that   
        ' will be passed to the workflow. Typically, this is in XML   
        ' format.  
        Return String.Empty  
    End Function  
    ```  
  
    ```csharp  
    // This method is called when the user clicks the button to start the workflow.          
    private string GetInitiationData()  
    {  
        // TODO: Return a string that contains the initiation data that   
        // will be passed to the workflow. Typically, this is in XML   
        // format.  
        return this.ExpenseTotal.Text;  
    }  
    ```  
  
## <a name="customizing-the-workflow"></a>İş akışını özelleştirme  
 Ardından, iş akışını özelleştirme. Daha sonra iş akışı için iki forms ilişkilendireceğiniz.  
  
#### <a name="to-customize-the-workflow"></a>İş akışını özelleştirmek için  
  
1.  İş akışı, iş akışı Tasarımcısı'nda projede Workflow1 açarak görüntüler.  
  
2.  İçinde **araç**, genişletin **Windows iş akışı v3.0** düğümü ve bulun **Ifelse** etkinlik.  
  
3.  Bu etkinliği iş akışı için aşağıdaki adımlardan birini gerçekleştirerek ekleyin:  
  
    -   Kısayol menüsünü açın **Ifelse** etkinliği seçin **kopya**, satırın altında için kısayol menüsünü açın **onWorkflowActivated1** etkinliği iş akışı Tasarımcısı'nda ve ardından **Yapıştır**.  
  
    -   Sürükleme **Ifelse** etkinliğinden **araç**ve altındaki satıra bağlamak **onWorkflowActiviated1** etkinliği iş akışı Tasarımcısı'nda.  
  
4.  Araç kutusunda genişletin **SharePoint iş akışı** düğümü ve bulun **CreateTask** etkinlik.  
  
5.  Bu etkinliği iş akışı için aşağıdaki adımlardan birini gerçekleştirerek ekleyin:  
  
    -   Kısayol menüsünü açın **CreateTask** etkinliği seçin **kopya**, iki biri için kısayol menüsünü açın **etkinlikleri Buraya Bırak** alanları  **IfElseActivity1** iş akışı Tasarımcısı'nda ve ardından **Yapıştır**.  
  
    -   Sürükleme **CreateTask** etkinliğinden **araç** iki birini üzerine **etkinlikleri Buraya Bırak** alanları **IfElseActivity1**.  
  
6.  İçinde **özellikleri** penceresinde, özellik değeri girin *taskToken* için **CorrelationToken** özelliği.  
  
7.  Genişletme **CorrelationToken** artı işaretini seçerek özelliği (![TreeView artı](../sharepoint/media/plus.gif "TreeView artı")) yanında.  
  
8.  Aşağı açılan okunu seçin **OwnerActivityName** sub özelliği ve ayarlayın *Workflow1* değeri.  
  
9. Seçin **Taskıd** özelliği ve ardından üç nokta (![ASP.NET Mobil Tasarımcı elips](../sharepoint/media/mwellipsis.gif "ASP.NET Mobil Tasarımcı elips")) görüntülemekiçindüğmesini**Özelliği bağlamak** iletişim kutusu.  
  
10. Seçin **bağlamak için yeni bir üye** sekmesinde, seçin **alanı oluştur** seçenek düğmesine ve ardından **Tamam** düğmesi.  
  
11. seçin **TaskProperties** özelliği ve ardından üç nokta (![ASP.NET Mobil Tasarımcı elips](../sharepoint/media/mwellipsis.gif "ASP.NET Mobil Tasarımcı elips")) düğmesini görüntülemekiçin **Özelliği bağlamak** iletişim kutusu.  
  
12. Seçin **bağlamak için yeni bir üye** sekmesinde, seçin **alanı oluştur** seçenek düğmesine ve ardından **Tamam** düğmesi.  
  
13. İçinde **araç**, genişletin **SharePoint iş akışı** düğümünü ve bulun **LogToHistoryListActivity** etkinlik.  
  
14. Bu etkinliği iş akışı için aşağıdaki adımlardan birini gerçekleştirerek ekleyin:  
  
    -   Kısayol menüsünü açın **LogToHistoryListActivity** etkinliği seçin **kopya**, diğeri için kısayol menüsünü açın **etkinlikleri Buraya Bırak** ucunuzu**IfElseActivity1** iş akışı Tasarımcısı'nda ve ardından **Yapıştır**.  
  
    -   Sürükleme **LogToHistoryListActivity** etkinliğinden **araç**ve diğer bırakma **etkinlikleri Buraya Bırak** ucunuzu **IfElseActivity1** .  
  
## <a name="adding-code-to-the-workflow"></a>İş akışı için kod ekleme  
 Ardından, iş akışına işlevselliği sağlamak için kodu ekleyin.  
  
#### <a name="to-add-code-to-the-workflow"></a>İş akışına kodu eklemek için  
  
1.  Kısayol menüsünü açın **createTask1** etkinliği iş akışı Tasarımcısı'nda ve ardından **görünümü kodu**.  
  
2.  Aşağıdaki yöntemi ekleyin:  
  
    ```vb  
    Private Sub createTask1_MethodInvoking(ByVal sender As   
      System.Object, ByVal e As System.EventArgs)  
        createTask1_TaskId1 = Guid.NewGuid  
        createTask1_TaskProperties1.AssignedTo = "somedomain\\someuser"  
        createTask1_TaskProperties1.Description = "Please approve the   
          expense report"  
        createTask1_TaskProperties1.Title = "Expense Report Approval   
          Needed"  
    End Sub   
    ```  
  
    ```csharp  
    private void createTask1_MethodInvoking(object sender, EventArgs e)  
    {  
        createTask1_TaskId1 = Guid.NewGuid();  
        createTask1_TaskProperties1.AssignedTo = "somedomain\\someuser";  
        createTask1_TaskProperties1.Description = "Please approve the   
          expense report";  
        createTask1_TaskProperties1.Title = "Expense Report Approval   
          Needed";  
    }   
    ```  
  
    > [!NOTE]  
    >  Kodla `somedomain\\someuser` için bir görev oluşturulacağı, gibi bir etki alanı ve kullanıcı adı ile "`Office\\JoeSch`". Test etmek için ile geliştirdiğiniz hesabı kullanmak en kolay yoludur.  
  
3.  Aşağıda `MethodInvoking` yöntemi, aşağıdaki örnekte ekleyin:  
  
    ```vb  
    Private Sub checkApprovalNeeded(ByVal sender As Object, ByVal e As   
      ConditionalEventArgs)  
        Dim approval As Boolean = False  
        If (Convert.ToInt32(workflowProperties.InitiationData) >   
          Convert.ToInt32(workflowProperties.AssociationData)) Then  
            approval = True  
        End If  
        e.Result = approval  
    End Sub   
    ```  
  
    ```csharp  
    private void checkApprovalNeeded(object sender, ConditionalEventArgs   
      e)  
    {  
        bool approval = false;  
        if (Convert.ToInt32(workflowProperties.InitiationData) >   
          Convert.ToInt32(workflowProperties.AssociationData))  
        {  
            approval = true;  
        }  
        e.Result = approval;  
    }   
    ```  
  
4.  İş Akışı Tasarımcısı'nda seçin **ifElseBranchActivity1** etkinlik.  
  
5.  İçinde **özellikleri** penceresinde, aşağı açılan okunu seçin **koşulu** özelliğini ayarlayın ve ardından *kod koşulu* değeri.  
  
6.  Genişletme **koşulu** artı işaretini seçerek özelliği (![TreeView artı](../sharepoint/media/plus.gif "TreeView artı")) yanında ve değerini ayarlama *checkApprovalNeeded* .  
  
7.  İş Akışı Tasarımcısı'nda kısayol menüsünü açın **logToHistoryListActivity1** etkinlik ve ardından **oluşturmak işleyicileri** için boş bir yöntemi oluşturmak için `MethodInvoking` olay.  
  
8.  Değiştir `MethodInvoking` kodu aşağıdakilerle:  
  
    ```vb  
    Private Sub logToHistoryListActivity1_MethodInvoking(ByVal sender As   
      System.Object, ByVal e As System.EventArgs)  
        Me.logToHistoryListActivity1.HistoryOutcome = ("Expense was auto   
          approved for " + workflowProperties.InitiationData)  
    End Sub   
    ```  
  
    ```csharp  
    private void logToHistoryListActivity1_MethodInvoking(object sender,   
      EventArgs e)  
    {  
        this.logToHistoryListActivity1.HistoryOutcome = "Expense was   
          auto approved for " + workflowProperties.InitiationData;  
    }   
    ```  
  
9. Program hata ayıklamak için F5 tuşuna seçin.  
  
     Bu uygulama derler, bu paketleri, dağıttığı, özelliklerini etkinleştirir, geri dönüştürüldüğünde [!INCLUDE[TLA2#tla_iis5](../sharepoint/includes/tla2sharptla-iis5-md.md)] uygulama havuzu ve belirtilen konumda tarayıcı içinde sonra başlar **Site URL'si** özelliği.  
  
## <a name="associating-the-workflow-to-the-documents-list"></a>Belgeler listesine iş akışı ilişkilendirme  
 Ardından, iş akışı ile ilişkilendirerek iş akışı ilişkilendirme formu görüntüleyin **SharedDocuments** SharePoint sitesinde listesi.  
  
#### <a name="to-associate-the-workflow"></a>İş akışı ilişkilendirmek için  
  
1.  Seçin **paylaşılan belgeler** Hızlı Başlatma çubuğunda bağlantı.  
  
2.  Seçin **Kitaplığı** bağlantı **kitaplık Araçları** sekmesini ve ardından **kitaplık ayarları** Şerit düğmesi.  
  
3.  İçinde **izinler ve Yönetim** bölümünde, seçin **iş akışı ayarları** bağlamak ve ardından **bir iş akışı Ekle** bağlantı **işakışları** sayfası.  
  
4.  İş akışı ayarları sayfasına dön listesinde seçin **ExpenseReport - Workflow1** şablonu.  
  
5.  Sonraki alanına **ExpenseReportWorkflow** ve ardından **sonraki** düğmesi.  
  
     Bu iş akışı ile ilişkilendirir **paylaşılan belgeler** listelemek ve iş akışı ilişkilendirme formu görüntüler.  
  
6.  İçinde **otomatik onay limiti** metin kutusuna **1200** ve ardından **ilişkilendirme iş akışı** düğmesi.  
  
## <a name="starting-the-workflow"></a>İş akışı başlatma  
 Ardından, iş akışı belgelerde birine ilişkilendirmek **paylaşılan belgeler** iş akışı başlatma formu görüntülemek için liste.  
  
#### <a name="to-start-the-workflow"></a>İş akışını başlatmak için  
  
1.  SharePoint sayfasında seçin **giriş** düğmesi.  
  
2.  Seçin **paylaşılan belgeler** görüntülemek için Hızlı Başlatma çubuğunda bağlantı **paylaşılan belgeler** listesi.  
  
3.  Seçin **belgeleri** bağlantı **kitaplık Araçları** sayfanın en üstünde sekmesini ve ardından **Belgeyi Karşıya Yükle** içine yeni bir belge karşıya yüklemek için Şerit'te düğmesi **Paylaşılan belgeler** listesi.  
  
4.  İçinde **Belgeyi Karşıya Yükle** iletişim kutusunda, seçin **Gözat** düğmesi, herhangi bir belge dosyayı seçin, seçin **açık** düğmesine tıklayın ve ardından **Tamam** düğmesi.  
  
     Bu iletişim kutusunda belge ayarlarını değiştirmek, ancak bunları seçerek varsayılan değerlerinde bırakın **kaydetmek** düğmesi.  
  
5.  Karşıya yüklenen belge seçin, görünür ve ardından aşağı açılan okunu seçin **iş akışları** öğesi.  
  
6.  Görüntü ExpenseReportWorkflow yanındaki seçin.  
  
     Bu iş akışı başlatma formu görüntüler. (Değer görüntülenen Not **otomatik onay limiti** kutusudur salt okunur ilişki formunda girdiğinizden.)  
  
7.  İçinde **gider toplam** metin kutusuna **1600**ve ardından **iş akışı Başlat** düğmesi.  
  
     Bu görüntüler **paylaşılan belgeler** yeniden listeleyin. Adlı yeni bir sütun **ExpenseReportWorkflow** değerle **tamamlandı** iş akışını yalnızca başlatan öğesine eklenir.  
  
8.  Karşıya yüklenen belge yanında aşağı açılan okunu seçin ve ardından **iş akışları** iş akışı durum sayfasını görüntülemek için öğeyi. Seçin **tamamlandı** altındaki **tamamlanan iş akışı**. Görevi altında listelenen **görevleri** bölümü.  
  
9. Görev ayrıntılarını görüntülemek için görev başlığını seçin.  
  
10. Geri dönerek **SharedDocuments** listesinde ve aynı belge ya da farklı bir kullanarak iş akışını yeniden başlatın.  
  
11. İlişkilendirme sayfasında girilen tutar küçük veya ona eşit başlatma sayfasında bir miktar girin (**1200**).  
  
     Bu durumda, geçmiş listesinde bir girişi yerine bir görev oluşturulur. Giriş görüntüler **iş akışı geçmişi** iş akışı durumu sayfasının bölümünde. İletide Not **sonucu** geçmişi olay sütunu. Girilen metin içeren `logToHistoryListActivity1.MethodInvoking` otomatik onaylı tutarın içeren olay.  
  
## <a name="next-steps"></a>Sonraki Adımlar  
 Aşağıdaki konulardan iş akışı şablonları oluşturma hakkında daha fazla bilgi edinebilirsiniz:  
  
-   SharePoint iş akışları hakkında daha fazla bilgi için bkz: [Windows SharePoint Services iş akışlarında](http://go.microsoft.com/fwlink/?LinkID=166275).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [SharePoint iş akışı çözümleri oluşturma](../sharepoint/creating-sharepoint-workflow-solutions.md)   
 [İzlenecek yol: Bir Uygulama Sayfasını Bir İş Akışına Ekleme](../sharepoint/walkthrough-add-an-application-page-to-a-workflow.md)  
  
  