---
title: "İzlenecek yol: bir SharePoint Tasarımcısı yeniden kullanılabilir iş akışını Visual Studio'ya içeri aktarma | Microsoft Docs"
ms.custom: ''
ms.date: 02/02/2017
ms.technology:
- office-development
ms.topic: conceptual
f1_keywords:
- VS.SharePointTools.WSPImport.ImportWF
dev_langs:
- VB
- CSharp
- VB
- CSharp
helpviewer_keywords:
- SharePoint development in Visual Studio, importing reusable workflows
- reusable workflows [SharePoint development in Visual Studio]
author: TerryGLee
ms.author: tglee
manager: douge
ms.workload:
- office
ms.openlocfilehash: 443502fdb6b018772e4dde833c5d53d27a68dbe8
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/16/2018
---
# <a name="walkthrough-import-a-sharepoint-designer-reusable-workflow-into-visual-studio"></a>İzlenecek yol: Bir SharePoint Tasarımcısı Yeniden Kullanılabilir İş Akışını Visual Studio'ya İçeri Aktarma
  Bu kılavuz, SharePoint Designer 2010'a oluşturulan bir yeniden kullanılabilir iş akışını içeri aktarmak gösterilmiştir bir [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)] SharePoint iş akışı projesinde.  
  
 SharePoint Tasarımcısı'nda oluşturulan iş akışı veya *bildirim temelli iş akışlarını*, oluşur [!INCLUDE[TLA2#tla_xml](../sharepoint/includes/tla2sharptla-xml-md.md)] kodu yerine deyimleri. SharePoint Designer 2010 tanıtır *yeniden kullanılabilir iş akışları*, SharePoint sitelerinde farklı listeleri tarafından kullanılan taşınabilir, bildirim temelli iş akışlarını olduğu.  
  
 Oluşturulan iş akışları [!INCLUDE[vs_dev11_long](../sharepoint/includes/vs-dev11-long-md.md)], sıralı ve Durum makinesi iş akışları gibi adlı *kod iş akışları*. Kod iş akışları, XML dosyalarını ve kullanıcılar iş akışının davranışı özelleştirebilir kod modülleri oluşur.  
  
 Visual Studio, SharePoint Designer 2010'da oluşturulan yeniden kullanılabilir iş akışlarını almak ve bunları SharePoint sitelerinizi kullanmak için kodu iş akışları Dönüştür olanak sağlar.  
  
 Bu kılavuz aşağıdaki görevler gösterilmiştir:  
  
-   Basit, yeniden kullanılabilir iş akışı SharePoint Tasarımcısı'nda oluşturma.  
  
-   SharePoint Tasarımcısı yeniden kullanılabilir iş akışı .wsp dosyaya ve SharePoint içine aktarma.  
  
-   .Wsp dosyasına içe [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)] alma yeniden kullanılabilir iş akışı projesinde kullanarak.  
  
-   İş akışı kodu ekleyerek değiştirme.  
  
-   Alınan iş akışı bir SharePoint sitesinde kullanma.  
  
 [!INCLUDE[note_settings_general](../sharepoint/includes/note-settings-general-md.md)]  
  
## <a name="prerequisites"></a>Önkoşullar  
 Bu izlenecek yolu tamamlamak için aşağıdaki bileşenlere ihtiyacınız vardır:  
  
-   Desteklenen sürümleri [!INCLUDE[TLA#tla_win](../sharepoint/includes/tlasharptla-win-md.md)] ve SharePoint. Daha fazla bilgi için bkz: [SharePoint çözümleri geliştirmek için gereksinimleri](../sharepoint/requirements-for-developing-sharepoint-solutions.md).  
  
-   Visual Studio.  
  
-   Microsoft [!INCLUDE[TLA2#tla_office](../sharepoint/includes/tla2sharptla-office-md.md)] SharePoint Designer 2010.  
  
## <a name="create-target-sharepoint-subsites"></a>Hedef SharePoint Alt Siteleri Oluşturma  
 İlk olarak, iki yeni SharePoint siteleri oluşturun: dönüştürülen iş akışlarını barındırmak için başka bir SharePoint Tasarımcısı'ndan yeniden kullanılabilir iş akışlarını barındırmak için.  
  
#### <a name="to-create-sharepoint-subsites"></a>SharePoint alt siteleri oluşturmak için  
  
1.  Menü çubuğunda, SharePoint Designer 2010'da seçin **dosya**, **yeni boş Web sitesi**.  
  
2.  İçinde **yeni boş Web sitesi** iletişim kutusunda, iş akışını oluşturmak veya http:// değerini kullanmak istediğiniz SharePoint sitesine gözatın*SystemName*/ ve ardından **Tamam** düğme.  
  
     Giriş sayfası görüntülenir.  
  
3.  İçinde **siteleri** bölümünde, seçin **yeni** düğmesi.  
  
4.  İçinde **yeni** iletişim kutusunda, seçin **SharePoint şablonları** sol bölmede, listeden seçin **ekip sitesi** sağ bölmede listeden.  
  
5.  İçinde **Web sitesinin konumunu belirtin** kutusunda, sözcüğü değiştirmek **alt** ile URL'de **SPD1**ve ardından **Tamam** düğmesi.  
  
     Bu, yeni alt SharePoint Designer siteye açar. SharePoint Designer'ın bu örneğinin kapatın ve ilk örneği (üst düzey site) geri dönün.  
  
6.  İkinci alt word değiştirerek bu kez oluşturmak için 3 ile 5 arasındaki adımları yineleyin **alt** içinde [!INCLUDE[TLA2#tla_url](../sharepoint/includes/tla2sharptla-url-md.md)] ile **SPD2**.  
  
## <a name="create-a-sharepoint-designer-reusable-workflow"></a>SharePoint Designer Yeniden Kullanılabilir İş Akışı Oluşturma  
 SharePoint Bu örnek için kullanabileceğiniz tüm yeniden kullanılabilir iş akışları içermediği bir oluşturur. Bir kullanıcı belirli bir başlık olan görev listesinde yeni bir görev girdiğinde basit bu iş akışındaki görev bu kullanıcıya atanır.  
  
#### <a name="to-create-a-sharepoint-designer-reusable-workflow"></a>SharePoint Designer yeniden kullanılabilir iş akışı oluşturmak için  
  
1.  İçinde **siteleri** bölümünde, seçin **SPD1** değiştirmek için site.  
  
2.  Şerit'te seçin **yeniden kullanılabilir iş akışı** düğmesi.  
  
     Yeniden kullanılabilir iş akışı oluşturma sihirbazı görünür.  
  
3.  İçinde **adı** kutusuna **SPD görev iş akışı**.  
  
4.  İçinde **içerik türü** listesinde, seçin **görev**ve ardından **Tamam** düğmesi.  
  
     İş akışı SharePoint Designer iş akışı Tasarımcısı'nda açılır.  
  
5.  İş Akışı Tasarımcısı'nda 1. Adım'ı seçin ve ardından, Şerit'te **koşulu** düğmesi.  
  
6.  Koşullar listesinden seçip **geçerli öğe alanı değere eşitse**.  
  
     Bu adım adlı bir koşul ekler **alanı değere eşitse**.  
  
7.  İçinde **alanı değere eşitse** koşul, seçin **alan** bağlantı.  
  
8.  Değerleri listesinden seçip **başlık**.  
  
9. İçinde **alanı değere eşitse** koşul, seçin **değeri** bağlantı.  
  
10. Kutusuna **yeni görev**.  
  
     Koşul deyimi şimdi okur **varsa geçerli öğe: Başlık eşittir yeni görev**.  
  
11. Koşul deyimi altında satır seçin ve ardından Şeritteki **eylem** düğmesi.  
  
12. Eylemler listesinden seçip **geçerli öğe kümesi alanında**.  
  
13. İçinde **değer kümesi alanıyla** eylemi seçin **alan** bağlamak ve ardından, listede **atanan**.  
  
14. İçinde **değer kümesi alanıyla** eylemi seçin **değeri** bağlamak ve ardından, var olan kullanıcılar ve gruplar listesinde **öğesini oluşturan kullanıcı**.  
  
15. Seçin **Ekle** düğmesine tıklayın ve ardından **Tamam** düğmesi.  
  
     Eylem deyimi şimdi okur **atanan ayarlanacak için geçerli öğe: tarafından oluşturuldu**.  
  
## <a name="save-and-deploy-the-reusable-workflow"></a>Yeniden Kullanılabilir İş Akışını Kaydetme ve Dağıtma  
 Çünkü [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)] yalnızca .wsp dosyalarını içeri aktarabilirsiniz, yeniden kullanılabilir iş akışını .wsp dosyası olarak kaydedin ve içine almadan önce SharePoint'e dağıtmak [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)].  
  
> [!IMPORTANT]  
>  Aşağıdaki yordamı gerçekleştirmeden çalışma zamanı hatası alırsanız, SharePoint sitesine erişimi olan bir sistemde yordamı yapmanız gerekir.  
  
#### <a name="to-save-and-deploy-the-reusable-workflow"></a>Yeniden kullanılabilir iş akışını kaydetmek ve dağıtmak için  
  
1.  SharePoint Designer üstünde seçin **kaydetmek** ilerleme durumunuzu Kaydet düğmesine ve ardından **Yayımla** akışına dağıtmak için düğmesini **SPD1** SharePoint sitesi .  
  
2.  Gezinti Bölmesi'nde seçin **iş akışları** nesnesi.  
  
3.  Altında **yeniden kullanılabilir iş akışı**, seçin **SPD görev iş akışı**.  
  
4.  Şerit'te seçin **şablon olarak Kaydet** düğmesi iş akışını .wsp dosyası olarak kaydedin.  
  
5.  Açık **SPD1** SharePoint'te .wsp dosyayı görüntülemek için tarayıcıda SharePoint sitesi.  
  
6.  Hızlı Başlatma çubuğunda seçin **kitaplıkları** bağlantı.  
  
7.  İçinde **belge kitaplıkları** bölümünde, seçin **sitesi varlıklarını** bağlantı.  
  
     **SPD görev iş akışı** dosya ile diğer site varlıkları listelenir.  
  
8.  Dosya listesinde, bu dosyanın adını seçin  
  
9. İçinde **dosyasını indirin** iletişim kutusunda, seçin **kaydetmek** düğmesi yerel sisteminizde .wsp dosyasını kaydedin.  
  
## <a name="import-the-wsp-file-into-visual-studio"></a>.wsp Dosyasını Visual Studio'ya Aktarma  
 .wsp aktarmak [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)] alma yeniden kullanılabilir iş akışı projesinde kullanarak. Bu proje iş akışını yeniden kullanılabilir, bildirim temelli bir iş akışından bir kod akışına dönüştürür. İş akışı dönüştürüldükten sonra davranışını değiştirmek için kodunu kullanır.  
  
#### <a name="to-import-a-workflow-from-a-wsp-file-and-modify-it"></a>Bir iş akışını .wsp dosyasından içeri aktarmak ve değiştirmek için  
  
1.  İçinde [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)], menü çubuğunda seçin **dosya**, **yeni**, **proje**.  
  
2.  İçinde **yeni proje** iletişim kutusunda, genişletin **SharePoint** ya da düğümünde **Visual C#** veya **Visual Basic**ve ardından seçin**2010** düğümü.  
  
3.  İçinde **şablonları** bölmesinde seçin **alma yeniden kullanılabilir SharePoint 2010 iş akışı** şablon projesinin adı bırakın **WorkflowImportProject1**ve ardından seçin **Tamam** düğmesi.  
  
     SharePoint Özelleştirme Sihirbazı görünür.  
  
4.  Üzerinde **hata ayıklama için site ve güvenlik düzeyini belirtmek** want [!INCLUDE[TLA2#tla_url](../sharepoint/includes/tla2sharptla-url-md.md)] daha önce oluşturduğunuz ikinci SharePoint alt site için: http://*sistem adı*/SPD2.  
  
5.  İçinde **bu SharePoint çözüm için güven düzeyini nedir?** bölümünde, seçin **Grup çözümü olarak dağıtma** seçenek düğmesine ve ardından **sonraki** düğmesi.  
  
     Korumalı hakkında daha fazla bilgi için küme çözümleri bkz [Korumalı çözüm değerlendirmeleri](../sharepoint/sandboxed-solution-considerations.md).  
  
6.  İçinde **yeni proje kaynak** sayfasında, sistemde daha önce kaydettiğiniz .wsp dosyanın konumuna göz atın, dosyayı açın ve ardından **sonraki** düğmesi.  
  
    > [!NOTE]  
    >  Seçin **son** .wsp dosyasındaki tüm kullanılabilir öğeleri içe aktarmak için düğmeyi.  
  
     Yeniden kullanılabilir iş akışlarını içeri aktarmak için kullanılabilir bir listesini görüntüler.  
  
7.  İçinde **almak için öğeleri seçin** kutusunda, seçin **SPD görev iş akışı** iş akışı ve ardından **son** düğmesi.  
  
     İçeri aktarma işlemi tamamlandıktan sonra proje adlı **WorkflowImportProject1** adlı bir iş akışı içeren oluşturulan **SPD_Workflow_TestFT**. Bu iş akışı tanımı dosyası Elements.xml ve iş akışı Tasarımcısı dosyasına (.xoml) klasöründedir. Tasarımcı iki dosya içerir: kural dosyası (.rules) ve arka plan kod dosyası (.cs veya .vb projenizin programlama dili bağlı olarak).  
  
8.  İçinde **Çözüm Gezgini**, silme **diğer içe aktarılan dosyaları** klasör.  
  
9. Elements.xml dosyasını silin `InstantiationURL="_layouts/IniErkflIP.sspx"`.  
  
10. İçinde **Çözüm Gezgini**, seçin **WorkflowImportProject1**ve ardından, menü çubuğunda, **proje**, **başlangıç projesi olarak ayarla** için ayarlama **WorkflowImportProject1** başlangıç öğesi olarak.  
  
     Hemen projenin hata ayıklamasını yaparken bu listede görüntülenir.  
  
11. Çünkü **yeniden kullanılabilir SharePoint 2010 iş akışı alma** şablonu alınan iş akışı ilişkilendirme özellik değerlerini alma değil, bunları girmeniz gerekir. Bunu yapmak için:  
  
    1.  İçinde **Çözüm Gezgini**, seçin **SPD_Workflow_TestFT** düğümü.  
  
    2.  Üç nokta seçin (![ASP.NET Mobil Tasarımcı elips](../sharepoint/media/mwellipsis.gif "ASP.NET Mobil Tasarımcı elips")) gibi bir liste özellikleri yanındaki düğmesini **hedef listesi** özelliği.  
  
    3.  SharePoint Özelleştirme Sihirbazı'nda eksik değerleri doldurun ve ardından **son** düğmesi.  
  
12. .Xoml dosyası seçin ve ardından, menü çubuğunda, **Görünüm**, **Tasarımcısı** alınan iş akışını iş akışı Tasarımcısı'nda görüntülemek için.  
  
13. İçinde **Windows iş akışı v3.0** düğümünün **araç**, aşağıdaki adımlardan birini gerçekleştirin:  
  
    -   Kısayol menüsünü açın **kod** etkinlik ve ardından **kopya**. Kısayol menüsünün altında çizgiyi iş akışı Tasarımcısı'nda açmak **SequenceActivity1** etkinlik ve ardından **Yapıştır**.  
  
    -   Sürükleme **kod** etkinliğinden **araç** iş akışı Tasarımcısı için ve altındaki satıra bağlamak **SequenceActivity1** etkinlik.  
  
     Bu etkinlik adlı iş akışı Tasarımcısı ekler **CodeActivity1**. Bu etkinlikte kullanıcı iş akışı başlatıldığında Duyurular listesinde bulunan duyuruyu oluşturan bir kod eylemi ekleyeceksiniz.  
  
14. Aşağıdaki adım kümelerinden birini uygulayın:  
  
    -   Çift **CodeActivity1** olay işleyicisi oluşturup kodunu görüntüleyin.  
  
    -   İçinde **özellikleri** penceresi **CodeActivity1**, değerini **ExecuteCode** özelliğine **codeActivity_ExecuteCode**.  
  
15. Varolan altında aşağıdaki ekleyin **kullanarak** veya **içeri aktarmalar** deyimleri:  
  
     [!code-csharp[SP_SPDWFImport#1](../sharepoint/codesnippet/CSharp/workflowimportproject1/workflows/spd_task_workflowft/spd task workflow.xoml.cs#1)]
     [!code-vb[SP_SPDWFImport#1](../sharepoint/codesnippet/VisualBasic/workflowimportproject1/workflows/spd_task_workflowft/spd task workflow.xoml.vb#1)]  
  
16. Değiştir `codeActivity1_ExecuteCode` aşağıdaki:  
  
     [!code-csharp[SP_SPDWFImport#2](../sharepoint/codesnippet/CSharp/workflowimportproject1/workflows/spd_task_workflowft/spd task workflow.xoml.cs#2)]
     [!code-vb[SP_SPDWFImport#2](../sharepoint/codesnippet/VisualBasic/workflowimportproject1/workflows/spd_task_workflowft/spd task workflow.xoml.vb#2)]  
  
## <a name="deploy-the-project-and-associate-the-workflow"></a>Projeyi Dağıtma ve İş Akışını İlişkilendirme  
 Ardından, WorkflowImportProject1 çalıştırmak bir SharePoint sitesine dağıtma ve ardından iş akışını görüntülemek ve değiştirilmiş, test etmek için görev listesi ile ilişkilendirmek için iş akışı dönüştürülür.  
  
#### <a name="to-deploy-the-project-and-associate-the-workflow"></a>Projeyi dağıtmak ve iş akışını ilişkilendirmek için  
  
1.  İçinde [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)], çalıştırmak ve dönüştürülen akışı projeyi dağıtmak için F5 tuşuna seçin.  
  
2.  Hızlı Başlatma çubuğunda seçin **görevleri** Görevler listesini görüntülemek için bağlantı.  
  
3.  Üzerinde **liste Araçları** sekmesinde, seçin **öğeleri** düğmesine tıklayın ve ardından **yeni öğe** düğmesi.  
  
     **Görevler - yeni öğe** iletişim kutusu açılır.  
  
4.  İçinde **başlık** kutusuna **yeni görev**ve ardından **kaydetmek** düğmesi.  
  
5.  Üzerinde **liste Araçları** sekmesinde, seçin **listesi** düğmesine tıklayın ve ardından **listesi ayarları** düğmesi.  
  
     **Listesi ayarları** sayfası görüntülenir.  
  
6.  İçinde **izinler ve Yönetim** bölümünde, seçin **iş akışı ayarları** bağlantı.  
  
     **İş akışı ayarları** sayfası görüntülenir.  
  
7.  Seçin **bir iş akışı Ekle** bağlantı.  
  
8.  İçinde **iş akışı** listesinde, seçin **WorkflowImportProject1 - SPD iş akışı Test**.  
  
9. İçinde **adı** kutusuna **SPD iş akışı Test**ve ardından **Tamam** düğmesi.  
  
10. Hızlı Başlatma çubuğunda seçin **görevleri** listesi.  
  
11. Oku seçin **yeni görev**ve ardından, listede **iş akışları**.  
  
12. İçinde **yeni bir iş akışı Başlat** bölüm, bağlantısına seçin **SPD iş akışı Test**ve ardından **Başlat** iş akışını başlatmak için düğmesi.  
  
    > [!NOTE]  
    >  Alternatif olarak, otomatik-bir iş akışı bir listesiyle iş akışı ayarları Sihirbazı'nı çalıştıran ve otomatik ilişkilendirme iş akışının ayarlama ilişkilendirme.  
  
     İki eylem iş akışı tarafından gerçekleştirilen dikkat edin: adınızı görevin içinde görünür **atanan** sütun ve duyuru görünür **duyuruları** listesi.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Mevcut bir SharePoint sitesinden öğeleri içeri aktarma](../sharepoint/importing-items-from-an-existing-sharepoint-site.md)   
 [SharePoint çözümleri geliştirme](../sharepoint/developing-sharepoint-solutions.md)   
 [Web Bölümleri veya Uygulama Sayfaları için Yeniden Kullanılabilir Denetimler Oluşturma](../sharepoint/creating-reusable-controls-for-web-parts-or-application-pages.md)  
  
  