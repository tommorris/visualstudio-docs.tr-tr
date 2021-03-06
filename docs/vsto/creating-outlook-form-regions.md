---
title: Outlook form bölgeleri oluşturma
ms.custom: ''
ms.date: 02/02/2017
ms.technology:
- office-development
ms.topic: conceptual
f1_keywords:
- MICROSOFT.OFFICE.TOOLS.OUTLOOK.FORMREGION
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- form regions [Office development in Visual Studio]
- form regions [Office development in Visual Studio], creating
- Outlook [Office development in Visual Studio], form regions
author: TerryGLee
ms.author: tglee
manager: douge
ms.workload:
- office
ms.openlocfilehash: bc8b1af95596ba182c69956155105a42f92212bb
ms.sourcegitcommit: 209c2c068ff0975994ed892b62aa9b834a7f6077
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/17/2018
ms.locfileid: "34265556"
---
# <a name="create-outlook-form-regions"></a>Outlook form bölgeleri oluşturma
  Form bölgeleri, Microsoft Office Outlook formları özelleştirmek için kullanabilirsiniz. Visual Studio tasarlama, geliştirme ve form bölgeleri hata ayıklama kolaylaştıran gelişmiş araçlar sağlar.  
  
 [!INCLUDE[appliesto_olkallapp](../vsto/includes/appliesto-olkallapp-md.md)]  
  
 Bu konuda, aşağıdaki bilgiler sağlanmaktadır:  
  
-   [Form bölgeleri kullanmanın yararları](#Enhance)  
  
-   [Outlook form bölgesi projenize ekleyin](#Adding)  
  
-   [Form bölgesi tasarımcısını kullanın](#UsingFormRegionDesigner)  
  
-   [Outlook'ta tasarlanan form bölgesini kullanın](#UsingFormRegionDesignedOutlook)  
  
-   [Bir form bölgesi için özel kod ekleme](#AddingCustomCode)  
  
-   [Proje derleme](#Building)  
  
-   [Bir form bölgesi hata ayıklama](#Debugging)  
  
-   [Form bölgesini dağıtma](#Deploying)  
  
##  <a name="Enhance"></a> Form bölgeleri kullanmanın yararları  
 Form bölgeleri geleneksel Outlook Form geliştirmesine birçok iyileştirme sunar:  
  
-   Herhangi bir standart formun varsayılan sayfasını özelleştirin.  
  
-   En fazla 12 ek sayfa herhangi bir standart forma ekleyin.  
  
-   Değiştirin veya herhangi bir standart biçimde geliştirebilirsiniz.  
  
-   Özel kullanıcı Arabirimi denetçiler okuma bölmesinde görüntüle.  
  
 Daha fazla bilgi için bkz: [özelleştirme form sayfaları ve form bölgeleri](http://msdn.microsoft.com/library/office/ff869060.aspx).  
  
##  <a name="Adding"></a> Outlook form bölgesi projenize ekleyin  
 Kullanabileceğiniz **yeni Outlook Form bölgesi** yeni bir form bölgesi tasarlama veya Outlook'ta tasarlanan form bölgesini içeri aktarmak için Sihirbazı. Ayrıca, Outlook VSTO eklenti başka bir projede kullanıldı bir form bölgesi varsa, varolan form bölgenizi yeniden kullanabilirsiniz.  
  
###  <a name="CreatingFormRegion"></a> Sihirbazı kullanarak yeni bir form bölgesi oluşturma  
 Bir form bölgesi oluşturmak için Ekle bir **Outlook Form bölgesi** Outlook VSTO eklenti projesindeki öğesine. Bu başlatır **yeni Outlook Form bölgesi** Sihirbazı.  
  
 Sihirbazın yeni bir form bölgesi tasarlama veya Outlook'ta tasarlanan form bölgesini içeri isteyip istemediğinizi belirtmek için kullanın. Yeni bir form bölgesi tasarlama hakkında daha fazla bilgi için bkz: [form bölgesi tasarımcısını kullanmak](#UsingFormRegionDesigner). Outlook'ta tasarlanan form bölgesini kullanma hakkında daha fazla bilgi için bkz: [Outlook'ta tasarlanan form bölgesini içeri aktarma](#UsingFormRegionDesignedOutlook).  
  
 Oluşturmak istediğiniz form bölgesi türünü belirtmek için Sihirbazı'nı kullanın. Aşağıdaki tabloda her bir form bölgesinin türünü açıklar.  
  
|Bölge türü|Açıklama|  
|-----------------|-----------------|  
|Ayrı|Form bölgesini Outlook form yeni bir sayfa olarak ekler.|  
|Bitişik|Form bölgesini Outlook formun varsayılan sayfanın altına ekler.|  
|Değiştirme|Form bölgesini Outlook form varsayılan sayfanın yerini alan yeni bir sayfa olarak ekler.|  
|Tümünü Değiştir|Tüm Outlook formunu form bölgesi ile değiştirir.|  
  
 Sihirbazı, görüntü koşullar belirtin ve genişletmek için form türünü seçmek için de kullanabilirsiniz. Daha fazla bilgi için bkz: [nasıl yapılır: bir Outlook eklenti projesine form bölgesi ekleme](../vsto/how-to-add-a-form-region-to-an-outlook-add-in-project.md).  
  
 Sihirbazda yaptığınız seçimler diğer sihirbaz sayfalarında kullanılabilir olan seçenekler etkiler. Örneğin, **sayfasındaki bitişik** veya **ayrı** içinde **yeni bir Outlook Form bölgesi oluşturmak** sayfasında, sonra **başlık** ve **Açıklama** alanlardır kullanılamaz **açıklayıcı metin sağlayın ve görüntüleme tercihlerini seçin** sayfası. Outlook bitişik veya ayrı bir form bölgesini görüntülediğinde, bu alanların kullanmadığından budur.  
  
#### <a name="form-region-files"></a>Form bölgesi dosyaları  
 Tamamlandığında, **yeni Outlook Form bölgesi** sihirbazında, Visual Studio otomatik olarak aşağıdaki dosyaları projenize ekler:  
  
-   Form bölgesi kod dosyası. Bu dosya için belirttiğiniz ada sahip **Outlook Form bölgesi** öğesi **Yeni Öğe Ekle** iletişim kutusu. Bu dosya için form bölgesi olayları işlemek için kodu ekleyin.  
  
-   Form bölgesi tasarımcı kod dosyası. Bu dosya form bölgesi tasarımcısı tarafından oluşturulan kodu içerir ve doğrudan düzenlenmemelidir.  
  
-   Outlook Form Depolama (*.ofs*) dosyası.  
  
    > [!NOTE]  
    >  Outlook'ta tasarlanan form bölgesini içeri aktarırsanız bu dosya yalnızca projeye eklenir.  
  
#### <a name="form-region-factory-class"></a>Form bölgesi üretici sınıfı  
 Form bölgesi kod dosyası uygulayan bir parçalı sınıf içeren <xref:Microsoft.Office.Tools.Outlook.IFormRegionFactory> arabirimi. Bu form bölgesi üretici sınıfıdır. Form bölgesi üretici sınıfı, form bölgesini yeni örneklerini oluşturulmasından sorumludur.  
  
 Bu sınıf genişleterek bulabilirsiniz **Form bölgesi fabrikası** bölge.  
  
 **Yeni Outlook Form bölgesi** sihirbaz form bölgesini iç adını belirleyen bu sınıf ve form bölgesini görüntüleyen ileti sınıfları için öznitelikler ekler. Dosya projeye eklendikten sonra bu öznitelikler el ile değiştirebilirsiniz.  
  
 Form bölgesi üretici sınıfı çoğunu form bölgesi tasarımcı dosyasında uygulanır. Ancak, `FormRegionInitializing` olay işleyicisi form bölgesi kod dosyasında gösterilir. Outlook form bölgesi görüntüleyip görüntülemeyeceğini belirtmek için bu olay işleyicisi kullanabilirsiniz. Daha fazla bilgi için bkz: [form bölgesi olaylarını işleme](#HandlingFormRegionEvents).  
  
###  <a name="AddingExistingFormRegion"></a> Varolan bir form bölgesi projenize ekleyin  
 Başka bir Outlook projesinde kullanılan bir Outlook form bölgesi varsa, onu geçerli Outlook VSTO eklenti projenizde kullanarak tekrar kullanabilirsiniz **varolan öğeyi Ekle** iletişim kutusu.  
  
 Varolan form bölgesi kod dosyası olması gerekir (*.vb* veya *.cs*); Outlook Form Depolama eklenemiyor (*.ofs*) kullanarak dosyaları **varolan öğeyi Ekle** iletişim kutusu. Ancak, bir Outlook Form Depolama dosyasını içeri aktararak yeni bir form bölgesi oluşturabilirsiniz. Daha fazla bilgi için bkz: [nasıl yapılır: bir Outlook eklenti projesine form bölgesi ekleme](../vsto/how-to-add-a-form-region-to-an-outlook-add-in-project.md).  
  
##  <a name="UsingFormRegionDesigner"></a> Form bölgesi tasarımcısını kullanın  
 Form bölgesi tasarımcısını bir form bölgesi görünümünü ve düzeni tasarlamanıza yardımcı olur. Yönetilen denetimleri Tasarımcı yüzeyine sürükleyin, olay işleyicilerini açmak için denetimleri çift tıklayın ve kümesinde özellikleri **özellikleri** penceresi.  
  
> [!NOTE]  
>  Form bölgesini Outlook görünümünü etkileyen özellikler bulabilirsiniz **bildirim** düğümünde **özellikleri** penceresi.  
  
 Form bölgesi tasarımcısını yalnızca seçerseniz kullanılabilir **yeni bir Form Bölgesi Tasarlama** içinde **nasıl form bölgesi oluşturmak istediğinizi seçin** sayfasında **yeni Outlook Form bölgesi** Sihirbazı.  
  
 Form bölgesi tasarımcısını açmak için üç yolu vardır:  
  
-   İçinde **Çözüm Gezgini**, form bölgesi kod dosyasına çift tıklayın.  
  
-   İçinde **Çözüm Gezgini**, form bölgesi kod dosyasına sağ tıklayın ve ardından **Görünüm Tasarımcısı**.  
  
-   İçinde **Çözüm Gezgini**, form bölgesi kod dosyası seçin ve ardından **Görünüm** menüsünde tıklatın **Tasarımcısı**.  
  
 Sadece yönetilen denetimleri form bölgesi tasarımcı destekler. Yerel Outlook denetimlerini ekleyemezsiniz.  
  
##  <a name="UsingFormRegionDesignedOutlook"></a> Outlook'ta tasarlanan form bölgesini içeri aktarma  
 Outlook'ta tasarlarken, yerel Outlook denetimleri form bölgesine ekleyebilirsiniz. Yerel Outlook denetimleri, tasarım zamanında Outlook'a veri bağlamanıza olanak sağlar. Ancak, yönetilen denetimleri eklemek veya form bölgesini tasarımını değiştirmek için ardından form bölgesi tasarımcısını kullanamazsınız.  
  
 Form bölgeleri kullanarak bir Outlook VSTO eklenti projesine içeri aktarabilirsiniz **yeni Outlook Form bölgesi** Sihirbazı. Üzerinde **nasıl form bölgesi oluşturmak istediğinizi seçin** sayfasında **bir Outlook Form Depolama (.ofs) dosyasını içeri**. Ardından bir Outlook Form Depolama dosyasının konumuna göz atabilirsiniz (*.ofs*) dosyası. (Outlook form bölgeleri olarak kaydeder *.ofs* dosyaları.)  
  
 **Yeni Outlook Form bölgesi** Sihirbazı kopyaları *.ofs* dosya proje dizinine ve denetim başvurularını form bölgesi tasarımcısı dosyasına ekler. Ardından, denetim olayları form bölgesi kod dosyasında işleyebilir.  
  
 Visual Basic projesinde olayları işlemek için Kod Düzenleyicisi'nin üstünde yöntemi adı listesinden bir olay seçin.  
  
 C# projesinde olayları işlemek için denetim olayları abone <xref:Microsoft.Office.Tools.Outlook.FormRegionControl.FormRegionShowing> yöntemi. Daha fazla bilgi için bkz: [nasıl yapılır: abone olaylara ve aboneliği kaldırma &#40;C&#35; Programlama Kılavuzu&#41;](/dotnet/csharp/programming-guide/events/how-to-subscribe-to-and-unsubscribe-from-events).  
  
 Form bölgesi özelliklerini değiştirebilirsiniz `InitializeManifest` form bölgesi üretici sınıfı yöntemi.  
  
> [!NOTE]  
>  Form bölgesini içeri aktarmak için geliştirme bilgisayarınızda yüklü olan Outlook aynı sürümü hedefleyen bir projede çalışıyor olmalıdır. Outlook 2010 yüklüyse, örneğin, form bölgesi yalnızca iş projesinde alma kullanılarak oluşturulmuş **Outlook 2010 Eklentisi** proje şablonu.  
  
### <a name="update-an-imported-form-regions-design"></a>Bir içe aktarılan form bölgesinin tasarımını güncelleştir  
 Eklemek, kaldırmak veya form bölgesini denetimlere değiştirin. Bunu yapabilmeniz için form bölgesi kod dosyası eklediğiniz herhangi bir kod yedekleyin. Ardından, açın *.ofs* dosya Outlook'ta, form bölgesini değiştirin ve değişiklikleri kaydedin. Kullanım **yeni Outlook Form bölgesi** değiştirilmiş içeri aktarmak için Sihirbazı *.ofs* dosya. Sonra kodunuzu yeni form bölgesi kod dosyası yapıştırabilirsiniz.  
  
##  <a name="AddingCustomCode"></a> Bir form bölgesi için özel kod ekleme  
 <xref:Microsoft.Office.Tools.Outlook> Ad alanı form bölgesini temsil eden sınıflar, form bölgesini görüntüleyen Outlook öğesi ve diğer yararlı öğelere erişim sağlar. **Outlook Form bölgesi** öğesine otomatik olarak projede bu derleme için bir başvuru ekler ve uygun ekler **kullanarak** veya **içeri aktarmalar** en üstündeki deyimi Form bölgesi kod dosyası.  
  
 Sınıfları, yöntemleri ve özellikleri kullanabilirsiniz `Microsoft.Office.Interop.Outlook` , Outlook programlama görevlerinin çoğunu gerçekleştirmek için ad alanı. Outlook nesne modeli hakkında daha fazla bilgi için bkz: [Outlook nesne modeline genel bakış](../vsto/outlook-object-model-overview.md). Outlook nesne modelini kullanmak için bkz: yapan tipik görev örnekleri için [Outlook çözümleri](../vsto/outlook-solutions.md).  
  
###  <a name="HandlingFormRegionEvents"></a> Form bölgesi olaylarını işleme  
 **Outlook Form bölgesi** öğesi aşağıdaki üç olay işleyicileri için form bölgesi kod dosyası otomatik olarak ekler.  
  
|Olay|Açıklama|  
|-----------|-----------------|  
|FormRegionInitializing|Form bölgesi başlatılmadan önce gerçekleşir. Outlook form bölgesi görüntüleyip görüntülemeyeceğini belirlemek için bu olay işleyicisi koşullarında kontrol edebilirsiniz. Daha fazla bilgi için bkz: [nasıl yapılır: Outlook form bölgesini görüntülemesini engelleme](../vsto/how-to-prevent-outlook-from-displaying-a-form-region.md).|  
|FormRegionShowing|Form bölgesini örneği oluşturulur ancak form bölgesi görünmeden önce sonra gerçekleşir.|  
|FormRegionClosed|Form bölgesi kapatılmadan önce gerçekleşir.|  
  
##  <a name="Building"></a> Proje derleme  
 Form bölgesi içeren Outlook VSTO eklenti projesi derlerken, Visual Studio aşağıdaki bilgileri kayıt defterine ekler:  
  
-   Bir veya daha fazla form bölgeleri ile ilişkili her ileti sınıfı için bir anahtar.  
  
-   Her form bölgesi ve Outlook VSTO eklenti adını temsil eden ilişkili bir değer için bir giriş.  
  
 Outlook form bölgeleri yüklemek için bu bilgileri kullanır.  
  
##  <a name="Debugging"></a> Bir form bölgesi hata ayıklama  
 Outlook VSTO yalnızca hatalarını, diğer gibi bir form bölgesi içeren eklenti ayıklayabilirsiniz [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)] projeleri. Başlattığınızda [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)] hata ayıklayıcı, Visual Studio otomatik olarak Outlook'u başlatır.  
  
 Form bölgesini görüntülemek için uygun Outlook öğesini açmanız gerekir. Bitişik bir form bölgesi bir posta öğesinin altına eklenirse, örneğin, bir posta öğesini açın.  
  
##  <a name="Deploying"></a> Form bölgesini dağıtma  
 Form bölgeleri ilişkili Outlook VSTO eklentisi ile otomatik olarak dağıtılır. Bu nedenle, form bölgesini dağıtmak için herhangi bir özel görevi gerçekleştirmeniz gerekmez. VSTO eklentileri dağıtma hakkında daha fazla bilgi için bkz: [Office çözümü dağıtma](../vsto/deploying-an-office-solution.md).  
  
## <a name="related-topics"></a>İlgili konular  
  
|Başlık|Açıklama|  
|-----------|-----------------|  
|[Yönergeler için Outlook form bölgeleri oluşturma](../vsto/guidelines-for-creating-outlook-form-regions.md)|Form bölgeleri en iyi duruma getirme ve olası sorunları önlemenize yardımcı olabilecek bilgiler sağlar.|  
|[Nasıl yapılır: bir Outlook eklenti projesine form bölgesi ekleme](../vsto/how-to-add-a-form-region-to-an-outlook-add-in-project.md)|Standart veya özel bir Microsoft Office Outlook form kullanarak genişletmek için bir form bölgesi oluşturulacağını gösterir **yeni Outlook Form bölgesi** Sihirbazı.|  
|[Form bölgesini Outlook ileti sınıfıyla ilişkilendirme](../vsto/associating-a-form-region-with-an-outlook-message-class.md)|Form bölgesini her öğenin ileti sınıfıyla ilişkilendirme tarafından Microsoft Office Outlook öğeleri form bölgesini görüntüleneceğini belirtme açıklanmaktadır.|  
|[İzlenecek yol: Outlook form bölgesi tasarlama](../vsto/walkthrough-designing-an-outlook-form-region.md)|Bir kişi öğesinin Inspector penceresinde yeni bir sayfa olarak görünen özel form bölgesi tasarlama gösterilmektedir.|  
|[İzlenecek yol: Outlook'ta tasarlanan form bölgesini içeri aktarma](../vsto/walkthrough-importing-a-form-region-that-is-designed-in-outlook.md)|Microsoft Office Outlook form bölgesi tasarlama ve ardından form bölgesini kullanarak bir Outlook VSTO eklenti projesine içeri gösterilmektedir **yeni Outlook Form bölgesi** Sihirbazı.|  
|[Form bölgesine çalışma zamanında erişme](../vsto/accessing-a-form-region-at-run-time.md)|Gösterme, gizleme veya form bölgesini denetimlere değiştirmek için kod yazma ve kullanıcıların kullanarak kodu projenizdeki diğer bölgelerden çalıştırmasına olanak açıklar `Globals` sınıfı.|  
|[Nasıl yapılır: Outlook form bölgesini görüntülemesini engelleme](../vsto/how-to-prevent-outlook-from-displaying-a-form-region.md)|Microsoft Office Outlook belirli bir öğe için bir form bölgesini görüntülemesini engelleme gösterilmektedir.|  
|Bir form bölgesi göründüğü Outlook öğesine erişim gösterilmektedir.|  
|[Outlook form bölgelerindeki özel eylemler](../vsto/custom-actions-in-outlook-form-regions.md)|Bir Outlook öğesine yanıt vermesine olanak sağlayan açıklar.|  
  
