---
title: SharePoint iş akışı çözümleri oluşturma | Microsoft Docs
ms.custom: ''
ms.date: 02/02/2017
ms.technology:
- office-development
ms.topic: conceptual
f1_keywords:
- VSTO.NewSharePointWorkflowWizard.Page3
- VS.SharePointTools.Workflow.WorkflowName
- VSTO.NewSharePointWorkflowWizard.Page2
- VSTO.NewSharePointWorkflowWizard.Page1
dev_langs:
- VB
- CSharp
- VB
- CSharp
helpviewer_keywords:
- SharePoint development in Visual Studio, workflows
- workflows [SharePoint development in Visual Studio]
author: TerryGLee
ms.author: tglee
manager: douge
ms.workload:
- office
ms.openlocfilehash: 68f7bc59a47d6288f54d7bf1a5373b87acf7d993
ms.sourcegitcommit: 269b55b413d2c82e6aa56c6ab8e53da7926fb2e8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/08/2018
ms.locfileid: "35238130"
---
# <a name="create-sharepoint-workflow-solutions"></a>SharePoint iş akışı çözümleri oluşturma
  [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)] bir SharePoint Web sitesinde liste öğelerini ve belgeleri yaşam döngüsünü yönetme özel iş akışları oluşturmanıza yardımcı olacak araçlar sağlar. Sağlanan öğeler bir tasarımcı, etkinlik denetimleri kümesini ve gerekli derleme başvurularını içerir. [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)] Ayrıca içerir **SharePoint Özelleştirme Sihirbazı'nı**, oluşturma ve iş akışlarını yapılandırma yardımcı olacak.

 SharePoint proje oluşturmak için bir önkoşul listesi için [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)], bkz: [SharePoint çözümleri geliştirmek için gereksinimleri](../sharepoint/requirements-for-developing-sharepoint-solutions.md). SharePoint hakkında daha fazla bilgi için bkz: [Microsoft SharePoint Ürün ve teknolojileri](http://go.microsoft.com/fwlink/?LinkId=178470).

## <a name="workflows-in-sharepoint"></a>SharePoint iş akışları
 Bir iş akışı bir SharePoint kitaplığı veya listeye ekleyin, bir iş sürecini kitaplığı veya listedeki tüm öğelerde uygulayın. Bir iş akışı sistem veya kullanıcıların düzenlenmesi ve ardından gözden öğesi gönderme gibi her öğede gerçekleştirmesi gereken eylemleri açıklar. Olarak bilinen bu eylemleri *etkinlikleri*, iş akışının yapı taşlarıdır.

 SharePoint iş akışları oluşturabilirsiniz [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)] ve bunları bir SharePoint Web sitesine dağıtabilirsiniz. Bir iş akışı için SharePoint dağıtıldıktan sonra bir kitaplık veya liste ile ilişkilendirin. Bunu daha sonra otomatik olarak bir işlem tarafından veya el ile bir kullanıcı tarafından başlatılabilir. İş akışı işlemi hakkında daha fazla bilgi için bkz: [Visual Studio kullanarak geliştirme SharePoint iş akışlarını](https://docs.microsoft.com/sharepoint/dev/general-development/develop-sharepoint-workflows-using-visual-studio).

## <a name="create-custom-sharepoint-workflows"></a>Özel SharePoint iş akışlarını oluşturma
 Size iki SharePoint iş akışı projeleri kullanılabilir [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)]: **sıralı iş akışı** ve **Durum makinesi iş akışı**.

 A *sıralı iş akışı* bir dizi adımı temsil eder. Son Etkinlik tamamlanana kadar adımları birbiri ardından gerçekleştirilir. Sıralı her zaman kendi yürütme kesinlikle sıralı iş akışlarıdır. Çünkü bunlar dış olaylarını almak ve paralel mantığı akışları dahil tam yürütme sırasını farklılık gösterebilir. Aşağıdaki çizimde bir sıralı iş akışı örneği gösterilmektedir.

 ![Sıralı iş akışı](../sharepoint/media/sp-sequential.png "sıralı iş akışı")

 A *Durum makinesi iş akışı* durumları, geçişleri ve eylemleri kümesini temsil eder. Zaman uyumsuz olarak bir Durum makinesi iş akışı'ndaki adımları yürütün. Bu, bunlar ardına zorunlu olarak gerçekleştirilmez ancak eylemleri ve durumlarını tarafından tetiklenen anlamına gelir. Durum başlangıç durumu olarak atanır ve daha sonra bir olaya bağlı olarak, bir geçiş başka bir duruma yapılır. Durum makinesinin iş akışı sonuna belirleyen bir son duruma sahip olabilir. Aşağıdaki diyagramda bir Durum makinesi iş akışı örneği gösterilmektedir.

 ![Durum makinesi iş akışı](../sharepoint/media/sp-state.png "Durum makinesi iş akışı")

 İş akışı türleri hakkında daha fazla bilgi için bkz: [iş akışı türlerini](http://go.microsoft.com/fwlink/?LinkId=178995).

### <a name="use-the-wizard"></a>Sihirbazı'nı kullanma
 Bir SharePoint iş akışı projesinde oluşturduğunuzda [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)], önce kendi ayarlarında belirttiğiniz **SharePoint Özelleştirme Sihirbazı'nı**. Bir proje oluşturmak için bu ayarları Sihirbazı'nı kullanan **Çözüm Gezgini**. Bu proje bir kod dosyası, iş akışı dağıtmak için kullanılan birkaç dosyaları içerir ve özel bir SharePoint iş akışı oluşturmak için gerekli olan derlemeleri başvurur.

 İş akışını oluşturduktan sonra Özellikler penceresinde özelliklerini değiştirebilirsiniz. İş akışı özelliklerinin çoğu doğrudan Özellikleri penceresinde değiştirilebilir rağmen bazı üç nokta düğmesini gerektirir (![ASP.NET Mobil Tasarımcı elips](../sharepoint/media/mwellipsis.gif "ASP.NET Mobil Tasarımcı elips")) için değerlerini değiştirin. Bu düğmeye yeniden **SharePoint Özelleştirme Sihirbazı'nı**. Özellik değeri değişiklikleri, seçin yaptıktan sonra **son** bunları sonlandırmaya düğmesi.

> [!NOTE]
>  **İş akışı türü** özelliği salt okunurdur ve değiştirilemez. İş akışı türünü değiştirmek istiyorsanız, başka bir iş akışı oluşturmanız gerekir.

## <a name="design-a-sharepoint-workflow"></a>Bir SharePoint iş akışı tasarım
 İş işleminde tüm adımları tanımladıktan sonra kullanın [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)] SharePoint iş akışı tasarlamak için iş akışı Tasarımcısı. Workflow1.cs veya Workflow1.vb içinde Tasarımcısı'nı açmak için çift **Çözüm Gezgini**, veya ya da bu dosyaları kısayol menüsünü açın ve ardından **açmak**.

### <a name="activities"></a>Etkinlikler
 Bir iş akışı tasarım, etkinlikten eklemek **araç** için bir *iş akışı zamanlaması* tasarımcısında. Bir iş akışı zamanlama bunlar gerçekleştirilmesini sırayla etkinlikler dizisini içerir.

 İki tür etkinlik vardır:

-   *Basit etkinlikleri* iş, "Gecikme 1 gün" veya "Web hizmetini başlatın." gibi tek bir birim gerçekleştirin

-   *Bileşik etkinlikleri* diğer etkinlikleri içerir; örneğin, iki dalı koşullu bir etkinlik içerebilir.

 Her iki tür etkinlik mevcuttur **araç**.

 Etkinlikler, özellikleri, yöntemleri ve olayları olabilir. Kullanım **özellikleri** bir etkinlik özelliklerini ayarlamak için penceresi.

 Özel Etkinlik de oluşturabilirsiniz. Daha fazla bilgi için bkz: [izlenecek yol: özel Site iş akışı etkinliği oluşturma](../sharepoint/walkthrough-create-a-custom-site-workflow-activity.md).

 Etkinlikler, aşağıdaki sekmeleri düzenlenir **araç**:

-   **SharePoint iş akışı**

-   **Windows iş akışı v3.0**

-   **Windows iş akışı v3.5**

 Tüm temel iş akışı etkinlikleri SharePoint tarafından desteklenir. Daha fazla bilgi için bkz: [iş akışı etkinlikleri için Windows SharePoint Services Genel Bakış](http://go.microsoft.com/fwlink/?LinkID=156094).

#### <a name="sharepoint-workflow-activities"></a>SharePoint iş akışı etkinlikleri
 **SharePoint iş akışı** sekmeler içeren özel etkinlikleri kullanmak için [!INCLUDE[wss_14_long](../sharepoint/includes/wss-14-long-md.md)]. Bu etkinlikler basitleştirmek ve belge ömrünü iş akışları geliştirilmesini kolaylaştırır. Listelenen etkinlikleri hakkında daha fazla bilgi için **SharePoint iş akışı** sekmesinde bkz [iş akışı etkinlikleri için Windows SharePoint Services Genel Bakış](http://go.microsoft.com/fwlink/?LinkID=156094).

#### <a name="windows-workflow-activities"></a>Windows iş akışı etkinlikleri
 **Windows iş akışı** sekmeler içeren tarafından sağlanan etkinlikler [!INCLUDE[TLA#tla_workflow](../sharepoint/includes/tlasharptla-workflow-md.md)]. Bu etkinlikler Windows iş akışı uygulama herhangi bir tür için iş akışı zamanlama oluşturmak için kullanabilirsiniz.

 Listelenen etkinlikleri hakkında daha fazla bilgi için **Windows iş akışları** sekmesinde bkz [Windows Workflow Foundation etkinlikleri](http://go.microsoft.com/fwlink/?LinkID=156096). Windows Workflow Foundation hakkında daha fazla bilgi için bkz: [Windows Workflow Foundation genel bakış](http://go.microsoft.com/fwlink/?LinkID=128632).

### <a name="work-with-activities-in-the-designer"></a>Tasarımcıda etkinliklerle çalışma
 İş akışı zamanlamanızı Windows iş akışı etkinlikleri ve SharePoint iş akışı etkinlikleri bir birleşimini içerebilir.

 Tasarımcı getirin ve etkinlikleri doğru şekilde yapılandırmanıza yardımcı olması için görsel ipuçları görüntüler. Sürükleyin ya da bir etkinliği iş akışı zamanlaması üzerine Kopyala Tasarımcı bu etkinlik için geçerli konumları iş akışı içinde Göster yeşil artı işareti (+) simgeleri görüntüler. Burada, geçerli olmaz bir konumda etkinlik getirin olamaz. Örneğin, bir dinleme etkinlik şube Gönder etkinliği ilk etkinlik olarak konumlandırın olamaz. Daha fazla bilgi için bkz: [SharePoint Designer Geliştirici Merkezi](http://go.microsoft.com/fwlink/?LinkId=178476).

## <a name="collect-information-during-the-workflow"></a>İş akışı sırasında bilgileri toplama
 Kullanıcılardan bilgi toplamak isteyebilirsiniz, iş akışı kez önceden tanımlanmış. Formlar veya öğe özelliklerini kullanarak bilgi toplayabilir.

### <a name="forms"></a>Formlar
 Kullanıcıların sorularınıza yanıt vermek yollar sağlar ve soruları içeren iletişim kutuları gibi formları bulunabilir.

 Bir iş akışında kullanılabilir forms dört tür vardır:

-   İlişkilendirme

-   Başlatma

-   Değişiklik

-   Görev

 Bu, [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)] ilişkilendirme ve başlatma formları için öğe şablonları içerir. Örnek olarak bir *ilişkilendirme formu* iş akışı yükleme yönetici olanak sağlayan bir girin gider iş akışı için bir harcama sınırına gibi iş akışı ile ilgili parametreler. Örnek olarak bir *başlatma formu* harcadıkları tutar iş akışına girin kullanıcı bir iş giderlerden akışının sağlayan biridir. Formları bu türleri hakkında daha fazla bilgi için bkz: [SharePoint Proje ve proje öğesi şablonları](../sharepoint/sharepoint-project-and-project-item-templates.md).

### <a name="item-properties"></a>Öğe özellikleri
 Ayrıca, SharePoint kitaplığı veya listedeki bir öğe özelliklerini kullanarak da kullanıcılardan bilgi toplayabilirsiniz. Ana kod dosyasının (Workflow1.cs veya Workflow1.vb) adlı Microsoft.SharePoint.Workflow.SPWorkflowActivationProperties.WorkflowProperties sınıfının bir örneği bildirir `workflowProperties`. Kullanım `workflowProperties` kitaplığı veya kod listesinde özelliklerine erişmek için nesne. Bir örnek için bkz: [izlenecek yol: oluşturma ve bir SharePoint iş akışı çözümü hata ayıklama](../sharepoint/walkthrough-creating-and-debugging-a-sharepoint-workflow-solution.md).

## <a name="debug-a-sharepoint-workflow-template"></a>Bir SharePoint iş akışı şablonu hata ayıklama
 Diğer hata ayıklama gibi bir SharePoint iş akışı projesinde aynı ayıklanabilmesi [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)] Web tabanlı projeler. Başlattığınızda [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)] hata ayıklayıcı, [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)] belirttiğiniz ayarları kullanan **SharePoint Özelleştirme Sihirbazı'nı** uygun SharePoint Web sitesini açın ve iş akışı şablonu otomatik olarak ilişkilendirmek için uygun kitaplığı veya listesi. [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)] Ayrıca iliştirir [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)] için hata ayıklayıcı [!INCLUDE[wss_14_long](../sharepoint/includes/wss-14-long-md.md)] adlı işlem *w3wp.exe*.

 İş akışı sınamak için el ile başlatmanız gerekir. Daha fazla bilgi için "Hata ayıklama iş akışlarının" bölümüne bakın [hata ayıklama SharePoint çözümlerini](../sharepoint/debugging-sharepoint-solutions.md). Hakkında daha fazla bilgi için [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)] Web uygulamasında hata ayıklama için bkz: [hata ayıklama Web uygulamaları ve komut dosyası](../debugger/debugging-web-applications-and-script.md).

## <a name="deploy-a-sharepoint-workflow-template"></a>SharePoint iş akışı şablon dağıtma
 [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)] SharePoint iş akışı projeleri yalnızca diğer gibi dağıtmak [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)] SharePoint projeleri. Daha fazla bilgi için bkz: [paketleme ve dağıtma SharePoint çözümlerini](../sharepoint/packaging-and-deploying-sharepoint-solutions.md).

## <a name="import-globally-reusable-workflows"></a>Genel olarak yeniden kullanılabilir iş akışlarını içeri aktarma
 Siteye yeniden kullanılabilir iş akışlarını oluşturmaya ek olarak, SharePoint Designer oluşturmanızı sağlayan *genel yeniden kullanılabilir iş akışları*, herhangi bir SharePoint sitesinin tarafından kullanılabilir iş akışları olduğu. İçeri aktarma yeniden kullanılabilir iş akışı projesinde [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)] genel yeniden kullanılabilir iş akışları şu anda almaz. Ancak, genel olarak yeniden kullanılabilir iş akışı yeniden kullanılabilir iş akışı ile dönüştürmek için SharePoint Designer kullanın, veya iş akışı Dönüştürülmeyen bildirim temelli iş akışı olarak alın. Daha fazla bilgi için bkz: [var olan bir SharePoint sitesinden öğeleri içeri aktarma](../sharepoint/importing-items-from-an-existing-sharepoint-site.md).

## <a name="related-topics"></a>İlgili konular

|Başlık|Açıklama|
|-----------|-----------------|
|[İzlenecek yol: Bir SharePoint İş Akışı Çözümü Oluşturma ve Hatalarını Ayıklama](../sharepoint/walkthrough-creating-and-debugging-a-sharepoint-workflow-solution.md)|Oluşturma ve basit bir hata ayıklama üzerinden adım adım sizi [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)] iş akışı.|
|[İzlenecek yol: İlişkilendirme ve Başlatma Formları ile İş Akışı Oluşturma](../sharepoint/walkthrough-creating-a-workflow-with-association-and-initiation-forms.md)|Adım adım daha tam özellikli oluşturmak için sizi [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)] iş akışı ilişkilendirme ve başlatma formları ile tamamlayın.|
|[İzlenecek yol: Bir Uygulama Sayfasını Bir İş Akışına Ekleme](../sharepoint/walkthrough-add-an-application-page-to-a-workflow.md)|Konunun derlemeler [izlenecek yol: İlişkilendirme ve başlatma formları ile iş akışı oluşturma](../sharepoint/walkthrough-creating-a-workflow-with-association-and-initiation-forms.md) ek ekleyerek *.aspx* iş akışına girilen verilerin raporları uygulama sayfası.|
|[İzlenecek yol: Özel Site İş Akışı Faaliyeti Oluşturma](../sharepoint/walkthrough-create-a-custom-site-workflow-activity.md)|İki anahtar görevlerinin nasıl gerçekleştirileceğini gösterir: bir site düzeyinde iş akışı oluşturmak ve bir özel iş akışı etkinliği oluşturma.|
|[İzlenecek yol: Bir SharePoint Tasarımcısı Yeniden Kullanılabilir İş Akışını Visual Studio'ya İçeri Aktarma](../sharepoint/walkthrough-import-a-sharepoint-designer-reusable-workflow-into-visual-studio.md)|SharePoint Designer 2010'a oluşturulan yeniden kullanılabilir bildirim temelli iş akışlarını içeri aktarma gösteren bir [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)] SharePoint Proje.|

## <a name="see-also"></a>Ayrıca bkz.

- [SharePoint Çözümleri Geliştirme](../sharepoint/developing-sharepoint-solutions.md)
- [SharePoint Çözümleri Oluşturma ve Hatalarını Ayıklama](../sharepoint/building-and-debugging-sharepoint-solutions.md)
- [SharePoint için Uygulama Sayfaları Oluşturma](../sharepoint/creating-application-pages-for-sharepoint.md)