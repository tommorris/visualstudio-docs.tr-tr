---
title: SharePoint Proje ve proje öğesi şablonları | Microsoft Docs
ms.custom: ''
ms.date: 02/22/2017
ms.technology:
- office-development
ms.topic: conceptual
f1_keywords:
- VS.SharePointTools.SPE.FirstWizardPage
- VS.SharePointTools.SPE.ListInstance
- VS.SharePointTools.SPE.ListDefinition
- VS.SharePointTools.SPE.ListDefFromContentType
- VS.SharePointTools.SPE.ContentType
- SPE.Wizard
dev_langs:
- VB
- CSharp
- VB
- CSharp
helpviewer_keywords:
- SharePoint development in Visual Studio, project and project item templates
- SharePoint development in Visual Studio, templates
author: TerryGLee
ms.author: tglee
manager: douge
ms.workload:
- office
ms.openlocfilehash: ccff01afcb2556469453d4227b14ebe3b897de50
ms.sourcegitcommit: d9e4ea95d0ea70827de281754067309a517205a1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/29/2018
ms.locfileid: "37120452"
---
# <a name="sharepoint-project-and-project-item-templates"></a>SharePoint Proje ve proje öğesi şablonları
  Aşağıdaki bölümlerde kullanılabilir SharePoint Proje açıklar ve proje öğesi şablonları ve bunların nasıl kullanıldığı. 
  
## <a name="project-and-project-item-templates-overview"></a>Proje ve proje öğesi şablonları genel bakış
 Visual Studio'da yeni bir SharePoint projesi oluşturduğunuzda, bir SharePoint proje çözüme tüm bu proje türüne göre gerekli proje öğelerini birlikte eklenir. Örneğin, bir Silverlight Web Bölümü projesi oluşturursanız, Visual Studio Visual Web Bölümü proje öğesi ve bu proje öğeleri tarafından gerekli tüm dosyaların yanı sıra bir Silverlight uygulaması proje öğesi içeren bir çözüm oluşturur. Proje öğesi şablonları, bir olay alıcısı, site sütunu veya liste ekleme gibi mevcut bir SharePoint projesini, proje öğeleri eklemek için kullanılır.  
  
 SharePoint temelleri hakkında daha fazla bilgi için bkz: [SharePoint Foundation Yapı Taşları](http://go.microsoft.com/fwlink/?LinkId=179404). İleri düzey kullanıcılar özel Proje ve proje öğesi şablonları oluşturabilirsiniz. Daha fazla bilgi için bkz: [SharePoint Proje sistemini genişletme](../sharepoint/extending-the-sharepoint-project-system.md).  
  
## <a name="project-templates"></a>Proje şablonları
 SharePoint proje şablonları listesi verilmiştir. Visual Studio'da SharePoint proje şablonları görüntülemek için **yeni proje** iletişim kutusunda, genişletin **SharePoint** ya da düğümünde **Visual C#** veya  **Visual Basic**ve ardından **2010**.  
  
### <a name="sharepoint-2010-project"></a>SharePoint 2010 proje
 İçeriği bir *SharePoint 2010 proje* her SharePoint Proje şablonu dahil edilir. SharePoint 2010 proje içerir:  
  
-   Bir proje dosyası.  
  
-   Proje Özellikleri Sayfası.  
  
-   A **başvuruları** tüm derleme başvurularını projesinde listeleyen klasör.  
  
-   A **özellikleri** içeren klasörü bir *.feature* özellikler SharePoint sunucusuna dağıtmak için kullanılan yapılandırma dosyası.  
  
-   A **paket** içeren klasörü bir *Package.package* SharePoint'e çözümü dağıtmak için kullanılan dosya.  
  
-   Gelişmiş güvenlik için derleme güçlü bir ad ile imzalamak için kullanılan bir key.snk (tanımlayıcı ad anahtar) dosyası.  
  
### <a name="sharepoint-2010-silverlight-web-part"></a>SharePoint 2010 Silverlight web bölümü
 *SharePoint 2010 Silverlight Web Bölümü* projeleri etkinleştirme, Create web bölümleri için Silverlight uygulamaları görüntülemek için SharePoint. Bu proje oluşturduğunuzda, ona yeni bir Silverlight uygulaması ekleyin veya mevcut bir başvuru belirtebilirsiniz. Daha fazla bilgi için bkz: [için SharePoint web bölümleri oluşturma](../sharepoint/creating-web-parts-for-sharepoint.md) ve [izlenecek yol: SharePoint için OData görüntüleyen bir Silverlight web bölümü oluşturma](../sharepoint/walkthrough-creating-a-silverlight-web-part-that-displays-odata-for-sharepoint.md).  
  
### <a name="sharepoint-2010-visual-web-part"></a>SharePoint 2010 visual web bölümü
 A *SharePoint 2010 Visual Web Bölümü* proje içeren bir *Elements.xml* tanım dosyası, bir **Web Bölümü** öğesi ve bir **kullanıcı denetimi** öğesi . Visual web bölümü görünümünü sürükleyerek ya da Visual Studio araç Kutusu'ndan kullanıcı denetimi yüzeye denetimleri kopyalama tasarlayabilirsiniz. Daha fazla bilgi için bkz: [nasıl yapılır: Tasarımcı kullanarak bir SharePoint web bölümü oluşturma](../sharepoint/how-to-create-a-sharepoint-web-part-by-using-a-designer.md) ve [yapı taşı: Web Bölümleri](http://go.microsoft.com/fwlink/?LinkId=179438).  
  
### <a name="import-sharepoint-2010-solution-package"></a>SharePoint 2010 çözüm paketi İçeri Aktar
 *SharePoint 2010 çözüm paketi içe* projeleri, bir SharePoint çözüm dışarı mevcut bir SharePoint 2010 site bölümünü veya tümünü içe sağlar (*.wsp*) dosyasına Visual Studio. Visual Studio'ya içeri sonra öğelerinden özelleştirebilir ve bunları yeniden dağıtın. Daha fazla bilgi için bkz: [mevcut bir SharePoint sitesinden öğeleri içeri aktarma](../sharepoint/importing-items-from-an-existing-sharepoint-site.md).  
  
### <a name="import-reusable-sharepoint-2010-workflow"></a>Yeniden kullanılabilir SharePoint 2010 iş akışı alın
 *SharePoint 2010 yeniden kullanılabilir iş akışı alma* projeleri Visual Studio'ya SharePoint Designer 2010'da oluşturulan yeniden kullanılabilir, bildirim temelli bir iş akışını alma olanak sağlar. İş akışı SharePoint sitesinden dışa aktarılan bir *.wsp* dosya. Visual Studio'ya içeri sonra özelleştirin, kodu ekleyin ve bir SharePoint sitesine dağıtma. Daha fazla bilgi için bkz: [izlenecek yol: bir SharePoint Tasarımcısı yeniden kullanılabilir iş akışını Visual Studio'ya içeri aktarma](../sharepoint/walkthrough-import-a-sharepoint-designer-reusable-workflow-into-visual-studio.md).  
  
## <a name="project-item-templates"></a>Proje öğesi şablonları
 SharePoint proje öğesi şablonları listesi verilmiştir. Proje öğesi şablonları site sütunları, listeler ve içerik türleri gibi SharePoint işlevleri desteklemek için SharePoint çözüm dosyalarını ekleyin. Örneğin, bir site sütunu çözümünüze ekleme içeren bir site sütunu proje ekler bir *Elements.xml* tanım dosyası. Visual web bölümü ekleme, visual web bölümü projesi içeren çözümünüzü ekler bir *Elements.xml* dosya, bir kullanıcı denetimi öğesi ve visual web bölümü öğesi.  
  
 SharePoint proje öğesi şablonları görüntülemek için **Çözüm Gezgini**, bir SharePoint proje için kısayol menüsünü açın ve ardından **Ekle**, **yeni öğe**. Genişletme **SharePoint** ya da düğümünde **Visual C#** veya **Visual Basic**ve ardından **2010**.  
  
### <a name="application-page-farm-solution-only"></a>Uygulama sayfası (yalnızca Grup çözümünün)
 Bir **(yalnızca Grup çözüm) uygulama sayfası** öğesi tasarlamanızı sağlar bir [!INCLUDE[vstecasp](../sharepoint/includes/vstecasp-md.md)] bir SharePoint sitesi için web sayfası. Uygulama sayfaları yalnızca küme çözümleri içinde kullanılabilir. Yalnızca küme çözümleri için bu proje öğesi ekleyebilirsiniz. Daha fazla bilgi için bkz: [nasıl yapılır: uygulama sayfası oluşturma](../sharepoint/how-to-create-an-application-page.md) ve [uygulama _layouts sayfa türü](http://go.microsoft.com/fwlink/?LinkId=179434).  
  
### <a name="business-data-connectivity-model-farm-solution-only"></a>İş Verileri Bağlantı Modeli (yalnızca Grup çözümünün)
 A **iş verileri bağlantı modeli (yalnızca Grup çözüm)** öğesi sağlar, tümleştirme iş verilerini SharePoint ile. İş verileri gelebilir arka uç sunucu uygulamalardan gibi [!INCLUDE[ssNoVersion](../sharepoint/includes/ssnoversion-md.md)], Siebel ve Service Advertising Protocol (SAP). İş verileri bağlantı modeli yalnızca küme çözümleri içinde kullanılabilir. Yalnızca küme çözümleri için bu proje öğesi ekleyebilirsiniz. Daha fazla bilgi için bkz: [nasıl yapılır: BDC modeli oluşturma](../sharepoint/how-to-create-a-bdc-model.md), [nasıl yapılır: yerelleştirilmiş adlar belirtin, özelliklerini ve izinlerini kaynak dosyasına kullanmak](../sharepoint/how-to-use-a-resource-file-to-specify-localized-names-properties-and-permissions.md), ve [yenilikler: iş bağlantısı Hizmetleri](http://go.microsoft.com/fwlink/?LinkId=179411).  
  
### <a name="content-type"></a>İçerik türü
 *İçerik türü* öğeleri, bir belge, duyuru ya da görev gibi varolan (Temel) içerik türüne göre özel içerik türleri oluşturmanıza olanak sağlar. Özel bir içerik türü, tanımladığınız tüm site sütunları (alanları) ile birlikte temel içerik türü olarak aynı öznitelikleri ve alanları sağlar. Örneğin, SharePoint'te gelen temel kişi içerik türü temel alan özel bir içerik kişi türü oluşturabilirsiniz. İçerik türü zaten temel içerik türde dahil olanlara daha fazla site sütun ekleme veya var olan site sütunlarını değiştirme özelleştirebilirsiniz.  
  
> [!NOTE]  
>  SharePoint sınırlamaları nedeniyle, bir korumalı çözüm içerik türüne göre grubu çözüm içerik türü oluşturulamıyor.  
  
 Daha fazla bilgi için bkz: [izlenecek yol: SharePoint için site sütunu, içerik türü ve liste oluşturma](../sharepoint/walkthrough-create-a-site-column-content-type-and-list-for-sharepoint.md) ve [yapı taşı: içerik türü](http://go.microsoft.com/fwlink/?LinkId=179413).  
  
### <a name="empty-element"></a>Boş öğesi
 *Boş öğeleri* çoğunlukla bir proje ya da Visual Studio Proje öğesi şablonu eksikliği SharePoint Proje öğeleri tanımlamak için kullanılır. Projeniz için boş bir öğe eklediğinizde, EmptyElement adlı bir düğüm [x](where [x] is a unique number\) is created. [X] EmptyElement içeren tek dosya başka bir deyişle adlandırılmış *Elements.xml.* Kullanım [!INCLUDE[TLA2#tla_xml](../sharepoint/includes/tla2sharptla-xml-md.md)] istenen öğeleri tanımlamak için deyimleri *Elements.xml*.  
  
### <a name="event-receiver"></a>Olay alıcısı
 *Olay alıcıları* SharePoint sitesindeki bir öğeyi listeye eklendiğinde, web öğesi silindiğinde veya bir iş akışı başladığında gibi öğeler için olaylarını işleme. Olay alıcı proje öğesi şablonu işlemenize olanak tanır  
  
-   Liste olayları  
  
-   Liste öğesi olayları  
  
-   Liste e-posta olayları  
  
-   Web olayları  
  
-   Liste iş akışı olayları  
  
 Olay alıcı proje öğesi oluşturur bir **olay alıcısı** belirtilen projede oluşturduğunuzda tüm olaylar için olay işleyicileri içeren tek bir sınıf dosyası klasörüyle **SharePoint özelleştirme Sihirbaz**. Olay alıcı sınıfı dosyaları, alanlar, öğeleri, listeler, ekleri, web bölümleri ve iş akışları gibi öğeleri eklendiğinde, güncelleştirilmiş, silinen, kaldırıldı veya SharePoint sitesinde meydana gelen olayları işleyebilir. Daha fazla bilgi için bkz: [nasıl yapılır: olay alıcısı oluşturma](../sharepoint/how-to-create-an-event-receiver.md) ve [yapı taşı: olay işleme](http://go.microsoft.com/fwlink/?LinkId=179416).  
  
### <a name="list"></a>List  
 Örneği yeniden kullanılabilir temel SharePoint listesi tanımı, bir takvim veya görev listesini gibi listelenmiştir. Çözümünüze bir liste eklendikten sonra liste Tasarımcısı site sütunları listeye ekleyin ve özel liste sütunları oluşturmanıza olanak sağlar. Bu içerik türlerinden site sütunları içerir. Belirleyebileceğiniz *Görünüm* listesi için listede görünür sütunlar belirler. Daha fazla bilgi için bkz: [izlenecek yol: SharePoint için site sütunu, içerik türü ve liste oluşturma](../sharepoint/walkthrough-create-a-site-column-content-type-and-list-for-sharepoint.md) ve [yapı taşı: listelerin ve belge kitaplıklarını](http://go.microsoft.com/fwlink/?LinkId=179421).  
  
### <a name="module"></a>Modül  
 *Modülleri* (ile karıştırılmamalıdır [!include[vbprvb](../sharepoint/includes/vbprvb-md.md)] modüller), görüntü veya notlar gibi SharePoint sunucusuna dağıtmak istediğiniz tüm dosyaları içerir. Modül proje öğesi içeren bir **Modülü** düğümü. İki proje öğesi şablonları modülü düğüm içerir: modül için bir bildirim görür, bir XML tanım dosyasını ve *örnek.txt* dosya, bir yer tutucu dosyası. Daha fazla bilgi için bkz: [dosyaları içerir çözümdeki kullanım modüllerini](../sharepoint/using-modules-to-include-files-in-the-solution.md) ve [modülleri](http://go.microsoft.com/fwlink/?LinkId=179425).  
  
### <a name="sequential-workflow-farm-solution-only"></a>Sıralı iş akışı (yalnızca Grup çözümünün)
 A *sıralı iş akışı* son adımı tamamlanana kadar sırayla gerçekleştirilen iş mantığı adımlar dizisidir. Sıralı iş akışları SharePoint öğeleri listeler ve belgeler gibi ilgili işlemleri yönetmek için kullanılır. Bir iş akışı otomatik olarak veya el ile başlayan seçebilirsiniz ve site düzeyinde (Genel) iş akışları veya liste düzeyini (yerel) iş akışları oluşturabilirsiniz. Bu proje öğesi, yalnızca küme çözümleri içinde kullanılabilir. Yalnızca küme çözümleri için bu proje öğesi ekleyebilirsiniz. Daha fazla bilgi için bkz: [oluşturma SharePoint iş akışı çözümleri](../sharepoint/creating-sharepoint-workflow-solutions.md), [SharePoint Server 2010 iş akışlarında](http://go.microsoft.com/fwlink/?LinkId=260555), ve [yenilikler: iş akışı geliştirmeleri](http://go.microsoft.com/fwlink/?LinkId=179418).  
  
### <a name="silverlight-web-part"></a>Silverlight web bölümü
 *Silverlight web bölümü* proje öğeleri etkinleştirmek, Create web bölümleri için Silverlight uygulamaları görüntülemek için SharePoint. Bu proje öğesi çözümünüze eklediğinizde, yeni bir Silverlight uygulaması eklemek veya mevcut bir daha sonra başvurmak seçebilirsiniz. Daha fazla bilgi için bkz: [için SharePoint web bölümleri oluşturma](../sharepoint/creating-web-parts-for-sharepoint.md) ve [izlenecek yol: SharePoint için OData görüntüleyen bir Silverlight web bölümü oluşturma](../sharepoint/walkthrough-creating-a-silverlight-web-part-that-displays-odata-for-sharepoint.md).  
  
### <a name="site-column"></a>Site sütunu
 A *site sütunu*, olarak da bilinen bir *alan*, bir SharePoint projesine ekleyebileceğiniz en temel öğeleri biridir. Bir site sütunu, bir telefon numarası, bir metin açıklama veya bir kişinin bir kişi listesinde şehir adı gibi veri türünü temsil eder. Daha fazla bilgi için bkz: [SharePoint için site sütunları, içerik türleri ve listeler oluşturma](../sharepoint/creating-site-columns-content-types-and-lists-for-sharepoint.md) ve [sütunları](http://go.microsoft.com/fwlink/?LinkId=226840).  
  
### <a name="site-definition-farm-solution-only"></a>Site tanımı (yalnızca Grup çözümünün)
 *Site tanımı* proje öğeleri aşağıdaki dosyaları içeren bir site tanımı klasör içerir:  
  
-   Site için varsayılan web sayfası olarak kullanılan bir varsayılan .aspx sayfası.  
  
-   Bir *onet.xml* site bileşenlerinin tanımlayan dosyası.  
  
-   Görünür site tanımı yapılandırmaları belirten bir webtemp xml dosyası **Şablon Seçimi** bölümünü **yeni SharePoint sitesi** sayfası.  
  
 Bir site tanımı ekledikten sonra kod ve işlevleri tanıtan dosyaları ekleyin. Bu proje öğesi, yalnızca küme çözümleri içinde kullanılabilir. Yalnızca küme çözümleri için bu proje öğesi ekleyebilirsiniz. Daha fazla bilgi için bkz: [SharePoint için site tanımları oluşturma](../sharepoint/creating-site-definitions-for-sharepoint.md) ve [Site tanımları ve yapılandırmaları](http://go.microsoft.com/fwlink/?LinkId=260554).  
  
### <a name="state-machine-workflow-farm-solution-only"></a>Durum makinesi iş akışı (yalnızca Grup çözümünün)
 A *Durum makinesi iş akışı* iş mantığı durumları ve geçişleri Eylemler kümesidir. Bir Durum makinesi iş akışı'ndaki adımları sırayla gerçekleştirilmez; Bunun yerine, bunlar eylemleri ve durumlarını tarafından tetiklenir. Sıralı iş akışı gibi durumu makine SharePoint öğeleri listeler ve belgeler gibi ile ilişkili iş akışlarıdır. Bir kez daha, site düzeyinde (Genel) iş akışları veya liste düzeyini (yerel) iş akışları oluşturabilirsiniz. Bir iş akışı otomatik olarak veya el ile başlayan de seçebilirsiniz. Bu proje öğesi, yalnızca küme çözümleri içinde kullanılabilir. Yalnızca küme çözümleri için bu proje öğesi ekleyebilirsiniz. Daha fazla bilgi için bkz: [oluşturma SharePoint iş akışı çözümleri](../sharepoint/creating-sharepoint-workflow-solutions.md), [SharePoint Server 2010 iş akışlarında](http://go.microsoft.com/fwlink/?LinkId=260555), ve [yenilikler: iş akışı geliştirmeleri](http://go.microsoft.com/fwlink/?LinkId=179418).  
  
### <a name="user-control-farm-solution-only"></a>Kullanıcı denetimi (yalnızca Grup çözümünün)
 A *kullanıcı denetimi* olduğu ekleyebileceğiniz diğer ASP.NET denetimleri ve SharePoint denetimleri yeniden kullanılabilir, özel bir denetim. Kullanıcı denetimi uygulama sayfaları ve SharePoint çalıştıran web bölümleri eklenebilir. Bu proje öğesi, yalnızca küme çözümleri içinde kullanılabilir. Yalnızca küme çözümleri için bu proje öğesi ekleyebilirsiniz. Daha fazla bilgi için bkz: [Web Bölümleri veya uygulama sayfaları için yeniden kullanılabilir denetimler oluşturma](http://go.microsoft.com/fwlink/?LinkId=226841).  
  
### <a name="visual-web-part"></a>Visual web bölümü
 A *visual web bölümü* proje öğesi içeren bir *Elements.xml* tanım dosyası, bir **Web Bölümü** öğesi ve bir **kullanıcı denetimi** öğesi. Visual web bölümü görünümünü sürükleyerek ya da Visual Studio araç Kutusu'ndan kullanıcı denetimi yüzeye denetimleri kopyalama tasarlayabilirsiniz. Daha fazla bilgi için bkz: [nasıl yapılır: Tasarımcı kullanarak bir SharePoint web bölümü oluşturma](../sharepoint/how-to-create-a-sharepoint-web-part-by-using-a-designer.md) ve [yapı taşı: Web Bölümleri](http://go.microsoft.com/fwlink/?LinkId=179438).  
  
### <a name="web-part"></a>Web kısmı
 A *web bölümü* özel türde bir Web Bölümü sayfası adlı sayfa içinde çalışan bir sunucu tarafı denetimdir. Bunlar bir SharePoint sitesinde sayfaları yapı taşlarıdır. Web bölümü öğesi, bir web bölümü bir SharePoint sitesi için tasarlamayı sağlayan dosyaları sağlar. Daha fazla bilgi için bkz: [nasıl yapılır: bir SharePoint web bölümü oluşturma](../sharepoint/how-to-create-a-sharepoint-web-part.md) ve [yapı taşı: Web Bölümleri](http://go.microsoft.com/fwlink/?LinkId=179438).  
  
## <a name="see-also"></a>Ayrıca bkz.
 [SharePoint çözümleri geliştirme](../sharepoint/developing-sharepoint-solutions.md)   
 [SharePoint Ürün ve teknolojileri](http://go.microsoft.com/fwlink/?LinkId=178818)  
  
  
