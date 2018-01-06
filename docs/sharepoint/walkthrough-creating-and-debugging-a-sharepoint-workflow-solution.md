---
title: "İzlenecek yol: Oluşturma ve bir SharePoint iş akışı çözümü hata ayıklama | Microsoft Docs"
ms.custom: 
ms.date: 02/02/2017
ms.reviewer: 
ms.suite: 
ms.technology: office-development
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- VS.SharePointTools.Workflow.WorkflowConditions
- VS.SharePointTools.Workflow.WorkflowList
dev_langs:
- VB
- CSharp
- VB
- CSharp
helpviewer_keywords:
- SharePoint development in Visual Studio, workflows
- workflows [SharePoint development in Visual Studio]
ms.assetid: 81756490-ab5a-4fa4-96c6-eed2cfbf8374
caps.latest.revision: "28"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload: office
ms.openlocfilehash: dc016efd3d0a3525f733929c294946bf9376417b
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/22/2017
---
# <a name="walkthrough-creating-and-debugging-a-sharepoint-workflow-solution"></a>İzlenecek yol: Bir SharePoint İş Akışı Çözümü Oluşturma ve Hatalarını Ayıklama
  Bu kılavuz temel sıralı iş akışı şablonunun nasıl oluşturulacağını gösterir. İş akışı bir belgeyi gözden olup olmadığını belirlemek için paylaşılan bir belge kitaplığı özelliğini denetler. Belge gözden, iş akışı tamamlanır.  
  
 Bu izlenecek yol aşağıdaki görevleri gösterir:  
  
-   Bir SharePoint listesi tanımı sıralı iş akışı projesinde oluşturma [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)].  
  
-   İş akışı etkinlikleri oluşturuluyor.  
  
-   İş akışı etkinlik olayları işleme.  
  
> [!NOTE]  
>  Bu kılavuz bir sıralı iş akışı projesinde kullansa da, Durum makinesi iş akışı proje için özdeş bir işlemdir.  
>   
>  Ayrıca, bilgisayarınızın bazı Visual Studio kullanıcı için farklı adlar veya konumlar arabirimi öğelerinden aşağıdaki yönergelerde yer gösterebilir. Sahip olduğunuz Visual Studio sürümü ve kullandığınız ayarlar bu öğeleri belirler. Daha fazla bilgi için bkz: [Visual Studio IDE'yi kişiselleştirme](../ide/personalizing-the-visual-studio-ide.md).  
  
## <a name="prerequisites"></a>Önkoşullar  
 Bu izlenecek yolu tamamlamak için aşağıdaki bileşenlere ihtiyacınız vardır:  
  
-   Microsoft Windows ve SharePoint sürümleri desteklenir. Daha fazla bilgi için bkz: [SharePoint çözümleri geliştirmek için gereksinimleri](../sharepoint/requirements-for-developing-sharepoint-solutions.md).  
  
-   Visual Studio.  
  
## <a name="adding-properties-to-the-sharepoint-shared-documents-library"></a>Paylaşılan belgeler kitaplığı SharePoint'e Özellikler ekleme  
 Belgeleri gözden geçirme durumunu izlemek için **paylaşılan belgeler** kitaplığı, biz oluşturacak paylaşılan belgeler için üç yeni özellikleri SharePoint sitemizde: `Status`, `Assignee`, ve `Review Comments`. Bu özellikler, tanımlarız **paylaşılan belgeler** kitaplığı.  
  
#### <a name="to-add-properties-to-the-sharepoint-shared-documents-library"></a>Belgeler kitaplığı paylaşılan SharePoint özellikleri eklemek için  
  
1.  Http:// gibi bir SharePoint sitesi açmak\<sistem adı > / bir Web tarayıcısında SitePages/Home.aspx.  
  
2.  Hızlı Başlatma çubuğunda seçin **SharedDocuments**.  
  
3.  Seçin **Kitaplığı** üzerinde **kitaplık Araçları** Şerit ve ardından **oluşturma sütun** yeni bir sütun oluşturmak için Şerit'te düğmeye.  
  
4.  Sütun adı **belge durumu**, türünü ayarlamak **seçenek (aralarından seçim yapabileceğiniz menü)**, aşağıdaki üç seçeneği belirtin ve ardından **Tamam** düğmesi:  
  
    -   **Gereken gözden geçirme**  
  
    -   **Gözden geçirme tamamlandı**  
  
    -   **İstenen değişiklikleri**  
  
5.  İki sütun daha oluşturmak ve bunları **atanan** ve **açıklamaları gözden geçirin**. Tek satırlık metin olarak atanan sütun türü ve açıklamaları gözden geçirin sütun türü birkaç satırlık metin ayarlayın.  
  
## <a name="enabling-documents-to-be-edited-without-requiring-a-check-out"></a>Bir kullanıma gerek kalmadan düzenlenmesi belgeleri etkinleştirme  
 Bunları kullanıma gerek kalmadan belgeleri düzenleyebilirsiniz zaman iş akışı şablonu test daha kolaydır. Sonraki yordamda, etkinleştirmek için SharePoint sitesini yapılandırın.  
  
#### <a name="to-enable-documents-to-be-edited-without-checking-them-out"></a>Bunları kullanıma olmadan düzenlenmesi belgeleri etkinleştirmek için  
  
1.  Hızlı Başlatma çubuğunda seçin **paylaşılan belgeler** bağlantı.  
  
2.  Üzerinde **kitaplık Araçları** Şerit, seçin **Kitaplığı** sekmesini ve ardından **kitaplık ayarları** görüntülemek için düğmesini **belge kitaplığı ayarlarını** sayfası.  
  
3.  İçinde **genel ayarları** bölümünde, seçin **sürüm oluşturma ayarları** görüntülemek için bağlantıyı **sürüm oluşturma ayarları** sayfası.  
  
4.  Doğrulayın ayarını **belgelerin düzenlenmeden önce kullanıma alınması gerektir** olan **Hayır**. Değilse, değiştirmek **Hayır** ve ardından **Tamam** düğmesi.  
  
5.  Tarayıcıyı kapatın.  
  
## <a name="creating-a-sharepoint-sequential-workflow-project"></a>Bir SharePoint sıralı iş akışı projesi oluşturma  
 Sıralı iş akışı son etkinlik tamamlanana kadar sırayla yürütür adımları kümesidir. Bu yordamda, bizim paylaşılan belgeler listesine uygulanacak bir sıralı iş akışı oluşturun. İş akışı Sihirbazı iş akışı site tanımı veya liste tanımı ile ilişkilendirmenizi sağlar ve iş akışı başlayacağını belirlemenize olanak tanır.  
  
#### <a name="to-create-a-sharepoint-sequential-workflow-project"></a>Bir SharePoint sıralı iş akışı projesi oluşturmak için  
  
1.  Başlat [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)].  
  
2.  Menü çubuğunda seçin **dosya**, **yeni**, **proje** görüntülemek için **yeni proje** iletişim kutusu.  
  
3.  Genişletme **SharePoint** ya da düğümünde **Visual C#** veya **Visual Basic**ve ardından **2010** düğümü.  
  
4.  İçinde **şablonları** bölmesinde seçin **SharePoint 2010 proje** şablonu.  
  
5.  İçinde **adı** kutusuna **MySharePointWorkflow** ve ardından **Tamam** düğmesi.  
  
     **SharePoint Özelleştirme Sihirbazı'nı** görüntülenir.  
  
6.  İçinde **hata ayıklama için site ve güvenlik düzeyini belirtmek** sayfasında, **Grup çözümü olarak dağıtma** seçenek düğmesine ve ardından **son** kabul et düğmesi güven düzeyi ve varsayılan site.  
  
     Bu adım çözümü için güven düzeyini Grup çözümü, iş akışı projeleri için kullanılabilir tek seçenek olarak ayarlar. Daha fazla bilgi için bkz: [Korumalı çözüm değerlendirmeleri](../sharepoint/sandboxed-solution-considerations.md).  
  
7.  İçinde **Çözüm Gezgini**, proje düğümünü seçin ve ardından, menü çubuğunda, **proje**, **Yeni Öğe Ekle**.  
  
8.  Ya da altında **Visual C#** veya **Visual Basic**, genişletin **SharePoint** düğümünü ve ardından **2010** düğümü.  
  
9. İçinde **şablonları** bölmesinde seçin **sıralı iş akışı (yalnızca Grup çözümünün)** şablonu ve ardından **Ekle** düğmesi.  
  
     **SharePoint Özelleştirme Sihirbazı'nı** görüntülenir.  
  
10. İçinde **hata ayıklama için iş akışı adını** sayfasında, varsayılan adı kabul edin (**MySharePointWorkflow - Workflow1**). Varsayılan iş akışı şablon türü değeri tutmak **liste iş akışı**ve ardından **sonraki** düğmesi.  
  
11. İçinde **iş akışı bir hata ayıklama oturumu otomatik olarak ilişkilendirmek için Visual Studio ister misiniz?** sayfasında, **sonraki** düğmesi tüm varsayılan ayarları kabul edin.  
  
     Bu adım, iş akışı paylaşılan belgeler kitaplığı ile otomatik olarak ilişkilendirir.  
  
12. İçinde **akışınızı nasıl başlatılacağını koşullarını belirtmeniz** sayfasında, varsayılan seçenekleri seçili bırakın **nasıl iş akışının başlamasını istediğiniz?** bölümünde ve seçin **Son** düğmesi.  
  
     Bu sayfa, iş akışı başlatıldığında belirtmenize olanak sağlar. Bir kullanıcı el ile SharePoint veya iş akışının ilişkili olan bir öğe oluşturulduğunda başlatıldığında varsayılan olarak, iş akışı ya da başlar.  
  
## <a name="creating-workflow-activities"></a>İş akışı etkinlikleri oluşturma  
 İş akışlarınızı içeren bir veya daha fazla *etkinlikleri* gerçekleştirilecek eylemler temsil eder. Bir iş akışı etkinlikleri düzenlemek için iş akışı Tasarımcısı'nı kullanın. Bu yordamda, iki etkinlik iş akışına ekleyeceğiz: HandleExternalEventActivity ve OnWorkFlowItemChanged. Bu etkinlikler belgeleri gözden geçirme durumunu izleme **paylaşılan belgeler** listesi  
  
#### <a name="to-create-workflow-activities"></a>İş akışı etkinlikleri oluşturmak için  
  
1.  İş akışını iş akışı Tasarımcısı'nda görüntülenmesi gerekir. Değilse, ya da açmak **Workflow1.cs** veya **Workflow1.vb** içinde **Çözüm Gezgini**.  
  
2.  Tasarımcıda seçin **OnWorkflowActivated1** etkinlik.  
  
3.  İçinde **özellikleri** penceresinde girin **onWorkflowActivated** yanındaki **Invoked** özelliği ve ardından Enter tuşuna seçin.  
  
     Kod Düzenleyicisi'ni açar ve onWorkflowActivated adlı bir olay işleyicisi yöntemi Workflow1 kod dosyasına eklenir.  
  
4.  Geçiş iş akışı Tasarımcısı, araç kutusunu açın ve ardından **Windows iş akışı v3.0** düğümü.  
  
5.  İçinde **Windows iş akışı v3.0** düğümünün **araç**, aşağıdaki adımlardan birini gerçekleştirin:  
  
    1.  Kısayol menüsünü açın **sırada** etkinlik ve ardından **kopya**. Kısayol menüsünün altında çizgiyi iş akışı Tasarımcısı'nda açmak **onWorkflowActivated1** etkinlik ve ardından **Yapıştır**.  
  
    2.  Sürükleme **sırada** etkinliğinden **araç** iş akışı Tasarımcısı için ve etkinlik satırının altında bağlanmak **onWorkflowActivated1** etkinlik.  
  
6.  Seçin **WhileActivity1** etkinlik.  
  
7.  İçinde **özellikleri** penceresindeki ayarlayın **koşulu** kod koşulu.  
  
8.  Genişletin **koşulu** özelliği girin **isWorkflowPending** alt yanındaki **koşulu** özelliği ve ardından Enter tuşuna seçin.  
  
     Kod Düzenleyicisi'ni açar ve isWorkflowPending adlı bir yöntem Workflow1 kod dosyasına eklenir.  
  
9. Geçiş iş akışı Tasarımcısı, araç kutusunu açın ve ardından **SharePoint iş akışı** düğümü.  
  
10. İçinde **SharePoint iş akışı** düğümünün **araç**, aşağıdaki adımlardan birini gerçekleştirin:  
  
    -   Kısayol menüsünü açın **OnWorkflowItemChanged** etkinlik ve ardından **kopya**. İş Akışı Tasarımcısı'nda içine satır için kısayol menüsünü açın **whileActivity1** etkinlik ve ardından **Yapıştır**.  
  
    -   Sürükleme **OnWorkflowItemChanged** etkinliğinden **araç** iş akışı Tasarımcısı için ve etkinlik içine satır bağlanmak **whileActivity1** etkinlik.  
  
11. Seçin **onWorkflowItemChanged1** etkinlik.  
  
12. İçinde **özellikleri** penceresinde, aşağıdaki tabloda gösterildiği gibi özellikleri ayarlayın.  
  
    |Özellik|Değer|  
    |--------------|-----------|  
    |**CorrelationToken**|**workflowToken**|  
    |**Çağrılan**|**onWorkflowItemChanged**|  
  
## <a name="handling-activity-events"></a>Etkinlik olayları işleme  
 Son olarak, her etkinlik belgeden durumunu denetleyin. Belge gözden, iş akışı sona erer.  
  
#### <a name="to-handle-activity-events"></a>Etkinlik olayları işlemek için  
  
1.  Workflow1.cs veya Workflow1.vb, aşağıdaki alana en üst kısmına ekleyin `Workflow1` sınıfı. Bu alan bir etkinlik iş akışı tamamlanıp tamamlanmadığını belirlemek için kullanılır.  
  
    ```vb  
    Dim workflowPending As Boolean = True  
    ```  
  
    ```csharp  
    Boolean workflowPending = true;  
    ```  
  
2.  Aşağıdaki yöntemi ekleyin `Workflow1` sınıfı. Bu yöntem denetler `Document Status` belgeyi gözden olup olmadığını belirlemek için belgeleri listenin özelliği. Varsa `Document Status` özelliği ayarlanmış `Review Complete`, sonra `checkStatus` yöntemi kümeleri `workflowPending` alanı **false** iş akışını tamamlamak hazır olduğunu belirtmek için.  
  
    ```vb  
    Private Sub checkStatus()  
        If CStr(workflowProperties.Item("Document Status")) = "Review Complete" Then  
            workflowPending = False  
        End If  
    End Sub   
    ```  
  
    ```csharp  
    private void checkStatus()  
    {  
        if ((string)workflowProperties.Item["Document Status"] == "Review Complete")  
        workflowPending = false;  
    }  
    ```  
  
3.  Aşağıdaki kodu ekleyin `onWorkflowActivated` ve `onWorkflowItemChanged` çağrılacak yöntemlerin `checkStatus` yöntemi. İş akışı başlatıldığında, `onWorkflowActivated` yöntem çağrılarını `checkStatus` belge zaten gözden olup olmadığını belirlemek amacıyla yöntemi. Bu gözden geçirilmemiştir varsa, iş akışı devam eder. Belge kaydedildiğinde `onWorkflowItemChanged` yöntem çağrılarını `checkStatus` yeniden belgeyi gözden olup olmadığını belirlemek amacıyla yöntemi. Sırada `workflowPending` alan ayarlanmış **doğru**, iş akışı çalışmaya devam eder.  
  
    ```vb  
    Private Sub onWorkflowActivated(ByVal sender As System.Object, ByVal e As System.Workflow.Activities.ExternalDataEventArgs)  
        checkStatus()  
    End Sub  
  
    Private Sub onWorkflowItemChanged(ByVal sender As System.Object, ByVal e As System.Workflow.Activities.ExternalDataEventArgs)  
        checkStatus()  
    End Sub  
    ```  
  
    ```csharp  
    private void onWorkflowActivated(object sender, ExternalDataEventArgs e)  
    {  
        // Check the status.  
        checkStatus();  
    }  
  
    private void onWorkflowItemChanged(object sender, ExternalDataEventArgs e)  
    {  
        // Check the status.  
        checkStatus();  
    }  
    ```  
  
4.  Aşağıdaki kodu ekleyin `isWorkflowPending` durumunu denetlemek için yöntem `workflowPending` özelliği. Belge kaydedildiğinde, her zaman **whileActivity1** etkinlik çağrıları `isWorkflowPending` yöntemi. Bu yöntem inceler <xref:System.Workflow.Activities.ConditionalEventArgs.Result%2A> özelliği <xref:System.Workflow.Activities.ConditionalEventArgs> belirlemek için nesne olup olmadığını **WhileActivity1** etkinlik devam veya son gerekir. Özellik ayarlanmışsa **doğru**, etkinlik devam eder. Aksi takdirde etkinlik tamamlandıktan ve iş akışı tamamlanır.  
  
    ```vb  
    Private Sub isWorkflowPending(ByVal sender As System.Object, ByVal e As System.Workflow.Activities.ConditionalEventArgs)  
        e.Result = workflowPending  
    End Sub  
    ```  
  
    ```csharp  
    private void isWorkflowPending(object sender, ConditionalEventArgs e)  
    {  
        e.Result = workflowPending;  
    }  
    ```  
  
5.  Projeyi kaydedin.  
  
## <a name="testing-the-sharepoint-workflow-template"></a>SharePoint iş akışı şablonu test etme  
 Hata ayıklayıcı başlatıldığında [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)] iş akışı şablonu SharePoint sunucusuna dağıtır ve iş akışı ile ilişkilendirir **paylaşılan belgeler** listesi. İş akışı test etmek için iş akışı örneği bir belge başlangıç **paylaşılan belgeler** listesi.  
  
#### <a name="to-test-the-sharepoint-workflow-template"></a>SharePoint iş akışı şablonu sınamak için  
  
1.  Workflow1.cs veya Workflow1.vb, bir kesme noktası yanına ayarlamak **onWorkflowActivated** yöntemi.  
  
2.  Derleme ve çözümü çalıştırmak için F5 tuşuna seçin.  
  
     SharePoint sitesi görüntülenir.  
  
3.  SharePoint Gezinti bölmesinde seçin **paylaşılan belgeler** bağlantı.  
  
4.  İçinde **paylaşılan belgeler** sayfasında, **belgeleri** bağlantı **kitaplık Araçları** sekmesini ve ardından **Belgeyi Karşıya Yükle** düğmesi .  
  
5.  İçinde **Belgeyi Karşıya Yükle** iletişim kutusunda, seçin **Gözat** düğmesi, herhangi bir belge dosyayı seçin, seçin **açık** düğmesine tıklayın ve ardından **Tamam** düğmesi.  
  
     Bu seçili belgeye yükler **paylaşılan belgeler** listesinde ve iş akışı başlar.  
  
6.  İçinde [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)], hata ayıklayıcı kesme noktasında yanına durur doğrulayın `onWorkflowActivated` yöntemi.  
  
7.  Yürütme devam etmek için F5 tuşuna seçin.  
  
8.  Belge burada ayarlarını değiştirmek, ancak bunları varsayılan değerlerde seçerek şimdilik bırakın **kaydetmek** düğmesi.  
  
     Bu, olanak verir **paylaşılan belgeler** varsayılan SharePoint Web sitesinin sayfası.  
  
9. İçinde **paylaşılan belgeler** sayfasında, değerin altında **MySharePointWorkflow - Workflow1** sütunu olarak ayarlanmış **sürüyor**. Bu iş akışı devam ediyor ve gözden geçirme bekleyen belge gösterir.  
  
10. İçinde **paylaşılan belgeler** sayfasında, belge seçin, görünür ve ardından oku **özelliklerini Düzenle** menü öğesi.  
  
11. Ayarlama **belge durumu** için **gözden geçirme tam**ve ardından **kaydetmek** düğmesi.  
  
     Bu, olanak verir **paylaşılan belgeler** varsayılan SharePoint Web sitesinin sayfası.  
  
12. İçinde **paylaşılan belgeler** sayfasında, değerin altında **belge durumu** sütunu olarak ayarlanmış **gözden geçirme tam**. Yenileme **paylaşılan belgeler** sayfasında ve doğrulayın değerin altında **MySharePointWorkflow - Workflow1** sütunu olarak ayarlanmış **tamamlandı**. Bu belirten iş akışı tamamlandığında ve belgeyi gözden.  
  
## <a name="next-steps"></a>Sonraki Adımlar  
 Aşağıdaki konulardan iş akışı şablonları oluşturma hakkında daha fazla bilgi edinebilirsiniz:  
  
-   SharePoint iş akışı etkinlikleri hakkında daha fazla bilgi için bkz: [SharePoint Foundation iş akışı etkinlikleri](http://go.microsoft.com/fwlink/?LinkId=178992).  
  
-   Windows Workflow Foundation etkinlikleri hakkında daha fazla bilgi için bkz: [System.Workflow.Activities Namespace](http://go.microsoft.com/fwlink/?LinkId=178993).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [SharePoint iş akışı çözümleri oluşturma](../sharepoint/creating-sharepoint-workflow-solutions.md)   
 [SharePoint Proje ve proje öğesi şablonları](../sharepoint/sharepoint-project-and-project-item-templates.md)   
 [SharePoint Çözümleri Oluşturma ve Hatalarını Ayıklama](../sharepoint/building-and-debugging-sharepoint-solutions.md)  
  
  