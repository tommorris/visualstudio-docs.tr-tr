---
title: "SharePoint çözümleri geliştirme | Microsoft Docs"
ms.custom: 
ms.date: 02/02/2017
ms.reviewer: 
ms.suite: 
ms.technology:
- office-development
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- VS.SharePointTools.Project.ProjectProperties
- VS.SharePointTools.Project.ProjectItemProperties
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- SharePoint development in Visual Studio, overview
author: TerryGLee
ms.author: tglee
manager: ghogen
ms.workload:
- office
ms.openlocfilehash: 848ddab54dd9e7617cce7758fa06d939700f2c3b
ms.sourcegitcommit: f9fbf1f55f9ac14e4e5c6ae58c30dc1800ca6cda
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/10/2018
---
# <a name="developing-sharepoint-solutions"></a>SharePoint Çözümleri Geliştirme
  Birkaç SharePoint proje türü şablonları kullanılabilir [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)] SharePoint siteleri ve site öğeleri oluşturmak için. Kullanılabilir proje türleri listesi için bkz: [SharePoint Proje ve proje öğesi şablonları](../sharepoint/sharepoint-project-and-project-item-templates.md). Bir SharePoint Proje özelliklerini ve bir açıklama öğelerin aşağıda verilmiştir.  
  
 SharePoint 2013 ve SharePoint eklentiler hakkında daha fazla bilgi için bkz: [SharePoint 2013](http://msdn.microsoft.com/library/jj162979.aspx) ve [yapı SharePoint eklentiler](http://msdn.microsoft.com/library/office/apps/jj163230%28v=office.15%29.aspx).  
  
## <a name="elements-of-a-sharepoint-project"></a>Bir SharePoint Proje öğeleri  
 Bir SharePoint Proje düğümlerinde olarak da bilinir *SharePoint öğeleri*. SharePoint öğeleri olarak adlandırılan bir veya daha fazla alt dosyası, ayrıca içerebilir *SharePoint öğesi dosyalarını*, gibi [!INCLUDE[TLA2#tla_xml](../sharepoint/includes/tla2sharptla-xml-md.md)] yapılandırma dosyalarını, .aspx formlar ve daha fazlası.  
  
 Proje öğesi dosyalarıyla zaten doldurulmuş proje şablonları kullanarak projeleri oluşturmak yerine, kullanabilirsiniz **boş proje** şablonu boş bir SharePoint projesi oluşturun ve ardından Proje öğeleri el ile ekleyin. SharePoint projeleri Ayrıca isteğe bağlı olarak bir veya daha fazla özellik dosyalarını (etkinleştirme SharePoint) ve projeyi dağıtmak üzere bir paket dosyası içerebilir.  
  
### <a name="special-nodes"></a>Özel düğümler  
 Her SharePoint projesi, yeniden adlandırılmış, silinmiş, kesme, kopyalanamaz veya projeden sürüklenen iki düğüm içerir. Bu düğümler aşağıdaki gibidir:  
  
-   Özellikler  
  
-   Paket  
  
 Hiçbir özellikleri veya paketler için proje tanımlanan olsa bile her iki düğüm tüm SharePoint projelerde her zaman görüntülenir.  
  
#### <a name="features-node"></a>Özellikler düğümü  
 **Özellikleri** düğüm bir veya daha fazla SharePoint Proje özelliklerini içerir. Bir özellik uzantılarının SharePoint için bir kapsayıcıdır. Bir özelliğin SharePoint sunucusuna dağıtıldıktan sonra site tanımları dahil veya SharePoint sitelerinde SharePoint yöneticiler tarafından ayrı ayrı etkin. Daha fazla bilgi için bkz: [özellikleriyle çalışma](http://go.microsoft.com/fwlink/?LinkID=147704).  
  
 Bir SharePoint projesine bir içerik türü veya bir liste örneği gibi bir öğe eklediğinizde, bir özellik eklenir **özellikleri** düğümü. Öğe kapsamı için yeni veya var olan bir özellik eklenip eklenmediğini belirler. Yeni öğe aynı kapsamı var olan bir özellik varsa, bu özelliğe eklenir. Aksi takdirde, öğe için yeni bir özellik eklenir.  
  
 El ile bir özellik eklemek için yürütme **ekleme özelliği** özelliği düğümün kısayol menüsünde komutu. Görüntüleyebilir veya özellik Tasarımcısını kullanarak bir özelliği içeriğini değiştirebilirsiniz. Daha fazla bilgi için bkz: [nasıl yapılır: bir SharePoint özelliğini özelleştirme](../sharepoint/how-to-customize-a-sharepoint-feature.md).  
  
 Bir özelliği bir SharePoint projesine eklendiğinde görünür **Çözüm Gezgini** varsayılan bir düğüm olarak özellik adını*x*.feature, burada *x* benzersiz bir sayıdır. Bir özelliğin SharePoint sunucusuna dağıtıldıktan sonra bir SharePoint Yöneticisi, SharePoint sitesini kullanıcılar için kullanılabilir duruma etkinleştirebilirsiniz.  
  
#### <a name="package-node"></a>Paket düğümü  
 **Paket** düğümü SharePoint proje için dağıtım mekanizması olarak görev yapar tek bir dosya içerir. Olarak bilinen bu dosyayı bir *çözüm**paket*, değil. CAB tabanlı bir. WSP uzantısı. Bir çözüm paketi özellikleri, site tanımları ve SharePoint sitelerine Uygula ve etkinleştir veya tek tek devre dışı bırakan derlemeler kümesini içeren dağıtılabilir, yeniden kullanılabilir bir dosyadır. **Paket** düğüm ayrıca her zaman Package.wspdef, adlı bir dosyayı içeren bir [!INCLUDE[TLA2#tla_xml](../sharepoint/includes/tla2sharptla-xml-md.md)] paket tanımı dosyası. Bir paket SharePoint çalıştıran sunucuya dağıtıldıktan sonra SharePoint Yöneticisi yükleyin ve onun özelliklerini etkinleştirin.  
  
 Görüntülemek veya paket düğümünde çift tıklatarak veya kısayol menüsünü açarak ve ardından paket tasarımcısını paketin içeriğini değiştirme **açık**. Daha fazla bilgi için bkz: [SharePoint çözüm paketleri oluşturma](../sharepoint/creating-sharepoint-solution-packages.md).  
  
## <a name="sharepoint-project-and-project-item-properties"></a>SharePoint Proje ve proje öğesi özellikleri  
 SharePoint projeleri, olduğu gibi diğer [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)] projeleri, Özellikler penceresini ve Özellikler sayfasını özelliklerini görüntüleme. Görüntülenen özellikler, seçili düğümde bağlıdır.  
  
 Bir SharePoint Proje, proje öğesi veya proje öğesi dosya düğümü seçildiğinde **Çözüm Gezgini**, aşağıdaki özellikler Özellikler penceresini veya özellikler sayfasında görünür:  
  
### <a name="project-properties"></a>Proje Özellikleri  
  
|Özellik adı|Açıklama|  
|-------------------|-----------------|  
|Etkin dağıtım yapılandırması|Dağıtım sırasında gerçekleştirilen adımlar dizisi belirtir. Daha fazla bilgi için bkz: [nasıl yapılır: SharePoint dağıtım yapılandırmasını düzenleme](../sharepoint/how-to-edit-a-sharepoint-deployment-configuration.md).|  
|Derleme dağıtım hedefi|Nereye belirler *SharePoint uygulama derlemeleri* bulunur. Geçerli bir derleme konumu değerlerdir ya da *GlobalAssemblyCache* (varsayılan) veya *WebApplication*.<br /><br /> Varsa *Korumalı çözüm* özelliği ayarlanmış **doğru**, bu özellik devre dışı.|  
|Hata ayıklama sonra otomatik Ayıkla|Dağıtılan çözümü otomatik olarak SharePoint'ten hata ayıklama modunda uygulama çalıştırdıktan sonra geri çeker olup olmadığını belirtir [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)]. IDE hata ayıklama sonra Tasarım görünümüne geri gittiğinde seçili olduğunda, çözüm geri çeker. Bu onay kutusu temizlendiğinde, çözümünü Ayıkla değil. Daha fazla bilgi için bkz: [bir çözüm geri çekilen](http://go.microsoft.com/fwlink/?LinkId=183819).|  
|Yapılandırmaları Düzenle|Proje için kullanmak üzere dağıtım yapılandırma belirtir. Daha fazla bilgi için bkz: [nasıl yapılır: SharePoint dağıtım yapılandırmasını düzenleme](../sharepoint/how-to-edit-a-sharepoint-deployment-configuration.md) ve [dağıtma, yayımlama ve yükseltme SharePoint çözüm paketlerini](../sharepoint/deploying-publishing-and-upgrading-sharepoint-solution-packages.md).|  
|Silverlight'ta hata ayıklama (komut dosyası hata ayıklamayı yerine) etkinleştir|Seçili olduğunda, Silverlight hata ayıklayıcısı hata ayıklama işlemi ekler. Bu onay kutusu temizlendiğinde, komut dosyası hata ayıklayıcısı hata ayıklama işlemi ekler. Daha fazla bilgi için bkz: [Silverlight hata ayıklamaya genel bakış](http://go.microsoft.com/fwlink/?LinkId=179826).|  
|Derleme pakete dahil|Proje derleme veya derleme zamanında paketlenmiştir olup olmadığını belirtir.|  
|Dağıtım sonrası komut satırı|SharePoint çözüm dağıttıktan sonra çalıştırılacak komut belirtir. Bu satır, herhangi bir toplu komut MSBuild değişkenleri çözümleme destekler. Daha fazla bilgi için bkz: [nasıl yapılır: SharePoint dağıtım komutlarını ayarlama](../sharepoint/how-to-set-sharepoint-deployment-commands.md).|  
|Dağıtım öncesi komut satırı|SharePoint çözüm dağıtmadan önce çalıştırılacak komutları belirtir. Bu satır, herhangi bir toplu komut MSBuild değişkenleri çözümleme destekler. Daha fazla bilgi için bkz: [nasıl yapılır: SharePoint dağıtım komutlarını ayarlama](../sharepoint/how-to-set-sharepoint-deployment-commands.md).|  
|Proje Dosyası|Derleme, yapılandırma ve projeyle ilgili diğer bilgileri içeren dosyanın adı.|  
|Proje klasörü|Sistemdeki proje dosyasının konumu. (Salt okunur.)|  
|Korumalı Çözümle|Proje olarak dağıtılan olup olmadığını belirten bir *Korumalı çözüm*, olarak da bilinir bir *kullanıcı tarafından oluşturulan çözüm*. Korumalı çözümler mutlaka güvenilir değil. Değerini **true** proje Korumalı çözüm olarak, bir değeri dağıtılacağı anlamına gelir **false** proje grubu çözümü olarak dağıtılacağı anlamına gelir. Daha fazla bilgi için bkz: [Korumalı çözüm değerlendirmeleri](../sharepoint/sandboxed-solution-considerations.md) ve [korumalı arasındaki farklar ve küme çözümleri](../sharepoint/differences-between-sandboxed-and-farm-solutions.md).|  
|Site URL'si|Belirtir [!INCLUDE[TLA2#tla_url](../sharepoint/includes/tla2sharptla-url-md.md)] bu proje için hedef sitenin.|  
|Başlangıç öğesi|İlk öğeyi çalıştırmak için projede belirtir.|  
  
 Bir SharePoint öğesi dosyasını (örneğin, bir iş akışı veya özellikleri düğümünde bir özellik) seçtiğinizde, aşağıdaki özellikler Özellikleri penceresinde görünür:  
  
### <a name="project-item-properties"></a>Proje öğesi özellikleri  
  
|Özellik adı|Açıklama|  
|-------------------|-----------------|  
|Dağıtıma Çakışma Çözümlemesi|Bu sunucuda zaten bir öğenin özelliklerini özdeş bir proje öğesi dağıtırken gerçekleştirilecek eylemi belirtir. Daha fazla bilgi için bkz: [sorun giderme SharePoint paketleme ve dağıtım](../sharepoint/troubleshooting-sharepoint-packaging-and-deployment.md).|  
|Özellik özellikleri|SharePoint ile dağıtırken, bir özelliğiyle dahil edilen (anahtar/değer çiftleri olarak depolanır) değer kümesini belirtir. Özellik dağıtıldıktan sonra kodunuzda özellik değerlerini erişebilir. Daha fazla bilgi için bkz: [sağlama paketleme ve dağıtım bilgileri proje öğelerinde](../sharepoint/providing-packaging-and-deployment-information-in-project-items.md).|  
|Özellik alıcısı|Özellik için bir proje öğesi belirli olaylar oluştuğunda yürütülen kodu içeren sağlar. Daha fazla bilgi için bkz: [sağlama paketleme ve dağıtım bilgileri proje öğelerinde](../sharepoint/providing-packaging-and-deployment-information-in-project-items.md).|  
|Klasör adı|SharePoint proje öğesi klasörün adı.|  
|Proje çıktı başvuruları|Proje öğesi çalıştırmak için gereken bir derleme gibi bir bağımlılık belirtiyor. Daha fazla bilgi için bkz: [sağlama paketleme ve dağıtım bilgileri proje öğelerinde](../sharepoint/providing-packaging-and-deployment-information-in-project-items.md).|  
|Güvenli denetim girişleri|Güvenilmeyen kullanıcıların düzenlemek için güvenli denetimler belirtir. Daha fazla bilgi için bkz: [sağlama paketleme ve dağıtım bilgileri proje öğelerinde](../sharepoint/providing-packaging-and-deployment-information-in-project-items.md).|  
  
### <a name="project-item-file-properties"></a>Öğesi proje dosyası özellikleri  
  
|Özellik adı|Açıklama|  
|-------------------|-----------------|  
|Derleme eylemi|Dosyanın yapı ve dağıtım işlemleri ile ilişkilendirilme şekli belirtir. Daha fazla bilgi için bkz: [dosya özelliklerini](http://msdn.microsoft.com/library/0c6xyb66(v=vs.100).aspx).|  
|Çıktı Dizinine Kopyala|Kaynak dosyalar çıkış dizinine kopyalanacağını olup olmadığını belirtir. Aşağıdaki değerlerden biri olabilir:<br /><br /> -   *Kopyalamayın*<br />-   *Her zaman Kopyala*<br />-   *Yeniyse Kopyala*<br /><br /> Daha fazla bilgi için bkz: [dosya özelliklerini](http://msdn.microsoft.com/library/0c6xyb66(v=vs.100).aspx).|  
|Özel aracı|Bir aracı adı varsa, tasarım zamanında dosya dönüştüren ve bu dönüşümün çıktısını başka bir dosyaya koyar belirtir. Örneğin, bir veri kümesi (.[!INCLUDE[TLA2#tla_xsd](../sharepoint/includes/tla2sharptla-xsd-md.md)]) dosyası varsayılan özel bir araç vardır. Daha fazla bilgi için bkz: [dosya özelliklerini](http://msdn.microsoft.com/library/0c6xyb66(v=vs.100).aspx).|  
|Özel araç Namespace|Ad alanı içine özel aracın çıktısının kopyalanır. Daha fazla bilgi için bkz: [dosya özelliklerini](http://msdn.microsoft.com/library/0c6xyb66(v=vs.100).aspx).|  
|Dağıtım Konumu|SharePoint sunucusunda dosyasının tam yolu. Bu yol dağıtım kök ve dağıtım yolu alt özelliklerini oluşur.|  
|Dağıtım yolu|SharePoint Server dosyası Workflow1 gibi dosyasının göreli yol\\. Dosyanın tam yolunu birleştirerek oluşturulan *dağıtım yolu* değeri sonuna *dağıtım kök* değeri.<br /><br /> Değeri seçme *RootFile* için *dağıtım türü* özellik değişikliklerini *dağıtım kök* {SharePointRoot} özelliğine\\, sonuç olarak bir {SharePointRoot} \Workflow1 tam yolunu\\. Daha fazla bilgi için bkz: [paketleme ve dağıtma SharePoint çözümlerini](../sharepoint/packaging-and-deploying-sharepoint-solutions.md).|  
|Dağıtım kök|Dize. Dosya SharePoint sunucusu üzerinde dağıtıldığı kök klasörü. Örneğin, {SharePointRoot} \Template\Features\\{FeatureName}\\.<br /><br /> Değeri *dağıtım kök* özelliği tarafından belirlenir *dağıtım türü* ayarı.|  
|Dağıtım türü|Belirler dosyanın dağıtım türü kendi *dağıtım kök* değeri. Aşağıdaki değerlerden biri olabilir:<br /><br /> NoDeployment: \<hiçbir değer ><br /><br /> ElementManifest: {SharePointRoot} \Template\Features\\{FeatureName}\\<br /><br /> ElementFile: {SharePointRoot} \Template\Features\\{FeatureName}\\<br /><br /> TemplateFile: {SharePointRoot} \Template\\<br /><br /> RootFile: {SharePointRoot}\\<br /><br /> GlobalResource: {SharePointRoot} \Resources\\<br /><br /> ClassResource: {ClassResourcePath}\\<br /><br /> Daha fazla bilgi için bkz. <xref:Microsoft.VisualStudio.SharePoint.DeploymentType>.|  
|Dosya Adı|Dosya veya klasör adı öğesi dosyası için.|  
|Tam yolu|Öğesi için dosyanın konumu. (Salt okunur.)|  
  
## <a name="related-topics"></a>İlgili Konular  
  
|Başlık|Açıklama|  
|-----------|-----------------|  
|[SharePoint Projesi ve Proje Öğesi Şablonları](../sharepoint/sharepoint-project-and-project-item-templates.md)|SharePoint Proje ve proje öğesi şablonları size kullanılabilir açıklar [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)].|  
|[Nasıl yapılır: Bir SharePoint Projesine Öğeler Ekleme](../sharepoint/how-to-add-items-to-a-sharepoint-project.md)|Yeni veya var olan öğelerin nasıl eklendiğini açıklar bir [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)] SharePoint Proje.|  
|[İzlenecek yol: SharePoint için Site Sütunu, İçerik Türü ve Liste Oluşturma](../sharepoint/walkthrough-create-a-site-column-content-type-and-list-for-sharepoint.md)|Adım adım bir müşteri alan, içerik türü, liste tanımını ve liste örneği oluşturmada size yol gösterir.|  
|[Nasıl yapılır: Olay Alıcısı Oluşturma](../sharepoint/how-to-create-an-event-receiver.md)|Oluşturduğunuz proje için olay alıcı eklemeyi açıklar [izlenecek yol: bir Site sütunu, içerik türü ve SharePoint listesi oluşturma](../sharepoint/walkthrough-create-a-site-column-content-type-and-list-for-sharepoint.md).|  
|[SharePoint İş Akışı Çözümleri Oluşturma](../sharepoint/creating-sharepoint-workflow-solutions.md)|İş akışı ilişkilendirme formları ve iş akışı başlatma formları içeren iş akışı projeleri nasıl oluşturulacağını açıklar.|  
|[SharePoint için Sayfa Oluşturma](../sharepoint/creating-pages-for-sharepoint.md)|SharePoint için uygulama sayfaları, site sayfaları, ana sayfalar ve sayfa düzenleri gibi sayfaları nasıl oluşturabileceğiniz açıklanmaktadır.|  
|[SharePoint için Web Bölümleri Oluşturma](../sharepoint/creating-web-parts-for-sharepoint.md)|İçerik, Görünüm ve davranış SharePoint sitesi sayfalarının bir tarayıcı kullanarak doğrudan değiştirmek kullanıcıların denetimlerin nasıl ekleneceğini açıklar.|  
|[Web Bölümleri veya Uygulama Sayfaları için Yeniden Kullanılabilir Denetimler Oluşturma](../sharepoint/creating-reusable-controls-for-web-parts-or-application-pages.md)|Uygulama sayfaları ve SharePoint çalıştıran Web bölümleri tarafından kullanılabilecek kullanıcı denetimlerinin nasıl oluşturulduğunu açıklar.|  
|[İş Verilerini SharePoint ile Tümleştirme](../sharepoint/integrating-business-data-into-sharepoint.md)|Web Hizmetleri ve arka uç sunucu uygulamaları verilerden bir SharePoint uygulamasına tümleştirmeyi açıklamaktadır.|  
|[SharePoint için Site Tanımları Oluşturma](../sharepoint/creating-site-definitions-for-sharepoint.md)|Site tanımları oluşturmayı açıklar: SharePoint siteleri oluşturmak için kullanılan şablon.|  
|[Mevcut bir SharePoint Sitesinden Öğeleri İçeri Aktarma](../sharepoint/importing-items-from-an-existing-sharepoint-site.md)|Bir SharePoint sitesinden öğeleri gibi içerik türleri ve modülleri içe aktarmayı açıklar bir [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)] SharePoint Proje.|  
|[Çözüme Dosyaları Dahil Etmek için Modül Kullanma](../sharepoint/using-modules-to-include-files-in-the-solution.md)|Modülleri dosyalarından dağıtmak için nasıl kullanılacağını açıklar, [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)] proje SharePoint sitesi.|  
|[Sunucu Gezgini Kullanarak SharePoint Bağlantılarına Gözatma](../sharepoint/browsing-sharepoint-connections-using-server-explorer.md)|Sunucu Gezgini kullanarak yerel SharePoint sitelerine göz açıklar.|  
|[Proje Öğelerinde Paketleme ve Dağıtım Bilgileri Sağlama](../sharepoint/providing-packaging-and-deployment-information-in-project-items.md)|Proje öğesi özellikleri güvenli denetim girişleri, proje çıktı başvuruları ve özellik değerleri gibi projeleri için paketleme ve dağıtım bilgileri sağlamak için nasıl kullanılacağını açıklar.|  
|[Nasıl yapılır: Eşlenmiş Klasörler Ekleme ve Kaldırma](../sharepoint/how-to-add-and-remove-mapped-folders.md)|Nasıl eşlenen klasörler açıklar SharePoint kaynaklarını daha kolay erişim sağlamak için projenize eklenebilir.|  
|[Korumalı Çözümle İlgili Konular](../sharepoint/sandboxed-solution-considerations.md)|Korumalı çözümler ile ilişkili sorunlar açıklanmaktadır.|  
|[SharePoint Çözümleri için Güvenlik](../sharepoint/security-for-sharepoint-solutions.md)|SharePoint çözümleri geliştirmek için güvenlik konuları açıklar [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)].|  
|[URL Seçici iletişim kutusu &#40; SharePoint geliştirme Visual Studio &#41;](../sharepoint/url-picker-dialog-box-sharepoint-development-in-visual-studio.md)|Projenizdeki veya yerel SharePoint sunucusuna kaynaklara yolu başvurular eklemek için kullanabileceğiniz bir iletişim kutusu açıklar.|  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Başlarken &#40; SharePoint geliştirme Visual Studio &#41;](../sharepoint/getting-started-sharepoint-development-in-visual-studio.md)   
 [Sunucu Gezgini kullanarak SharePoint bağlantılarına gözatma](../sharepoint/browsing-sharepoint-connections-using-server-explorer.md)   
 [Derleme ve SharePoint çözümlerini hata ayıklama](../sharepoint/building-and-debugging-sharepoint-solutions.md)   
 [SharePoint Çözümlerini Paketleme ve Dağıtma](../sharepoint/packaging-and-deploying-sharepoint-solutions.md)  
  
  