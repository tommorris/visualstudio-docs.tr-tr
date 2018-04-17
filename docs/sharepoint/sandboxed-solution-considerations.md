---
title: Korumalı çözüm değerlendirmeleri | Microsoft Docs
ms.custom: ''
ms.date: 02/02/2017
ms.technology:
- office-development
ms.topic: conceptual
f1_keywords:
- VS.SharePointTools.Project.SandboxedSolutions
- VS.SharePointTools.Security.SandboxedSolutions
dev_langs:
- VB
- CSharp
- VB
- CSharp
helpviewer_keywords:
- SharePoint development in Visual Studio, sandboxed solutions
- sandboxed solutions [SharePoint development in Visual Studio]
- SharePoint development in Visual Studio, farm solutions
- farm solutions [SharePoint development in Visual Studio]
author: TerryGLee
ms.author: tglee
manager: douge
ms.workload:
- office
ms.openlocfilehash: ff85f3407fb24d6d49856bb11ff1852c544cad35
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/16/2018
---
# <a name="sandboxed-solution-considerations"></a>Korumalı Çözümle İlgili Konular
  *Korumalı çözümler* Microsoft SharePoint 2010'de, site koleksiyonu kullanıcıların kendi özel kod çözümleri yüklemesine olanak sağlayan bir özelliktir. Yaygın bir korumalı kullanıcılar kendi Web Bölümleri karşıya çözümüdür.  
  
 Korumalı bir SharePoint uygulama sınırlı bir Web grubu parçası erişimi güvenli, izlenen işlem çalıştırır. Microsoft SharePoint 2010 korumalı çözümler sağlamak için özellikler, çözüm galerileri, izleme çözümü ve doğrulama çerçevesinin bileşimini kullanır.  
  
## <a name="specifying-project-trust-level"></a>Proje güven düzeyi belirtme  
 [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)] korumalı çözümler Boolean proje özelliği aracılığıyla adlı destekler *Korumalı çözüm*. Projedeki herhangi bir zamanda bu özelliği ayarlayın veya projede oluşturduğunuzda belirtilebilir **SharePoint Özelleştirme Sihirbazı'nı**.  
  
> [!NOTE]  
>  Değiştirme *Korumalı çözüm* oluşturulduktan sonra bir projenin özellik doğrulama hatalarına neden olabilir.  
  
 Çözüm Grup kapsamlı bir çözüm varsa değerlendirilir *Korumalı çözüm* özelliği ayarlanmış **false** veya seçtiğiniz **Grup çözümü olarak dağıtma** seçeneği. Bununla birlikte, çözümü farklı bir grup çözümden anlamına gelir *Korumalı çözüm* özelliği ayarlanmış **true** veya seçtiğiniz **korumalı bir çözüm olarak dağıtma** Sihirbazı'nda seçeneği.  
  
## <a name="sharepoint-site-hierarchy"></a>SharePoint Site hiyerarşisi  
 Nasıl korumalı çözümler anlamak için iş yardımcı olan SharePoint siteleri kapsamda hiyerarşik olduğunu öğrenmek için. Üst öğesi Web grubu bilinir ve diğer öğeleri kendisine bağımlı:  
  
 Web grubu  
  
 Web uygulaması A  
  
 Site koleksiyonu A1  
  
 Site A1a  
  
 Web uygulaması B  
  
 Site koleksiyonu B1  
  
 Site B1a  
  
 Site B1b  
  
 Site koleksiyonu B2  
  
 Site B2a  
  
 Gördüğünüz gibi Web grupları buna karşılık, alt siteleri varsa ve benzeri bir veya daha fazla site koleksiyonları içerebilir, bir veya daha fazla Web uygulamaları içerebilir. Yalnızca koleksiyon site bir site koleksiyonu etkiyi yapılmış ve başka değiştirir. Ancak, Web grubu düzeyinde yapılan değişiklikler grubundaki tüm site koleksiyonlarında etkiler.  
  
 Windows SharePoint Services (WSS) 3.0, yalnızca grup düzeyine çözümlerini dağıtmak sağlar ancak [!INCLUDE[wss_14_long](../sharepoint/includes/wss-14-long-md.md)] grup düzeyinde (Grup çözümünün) ya da site koleksiyonu düzeyinde (Korumalı çözüm) dağıtmanıza olanak tanır.  
  
## <a name="why-sandboxed-solutions"></a>Neden korumalı çözümler?  
 WSS 3. 0'da, yalnızca grup düzeyinde çözümleri dağıtılamıyor. Bu, olası zararlı veya destabilizing çözümleri, etkilenen tüm Web grubu ve tüm diğer site koleksiyonları ve onun altında çalışan uygulamaları dağıtılamıyor olduğunu anlamına gelir. Ancak, korumalı çözümler kullanarak bir alt grup, belirli site koleksiyonu, bu alan için çözümlerinizi dağıtabilirsiniz. Ek koruma sağlamak üzere çözümün derlemesi ana yüklü değil [!INCLUDE[TLA2#tla_iis5](../sharepoint/includes/tla2sharptla-iis5-md.md)] işleminin (w3wp.exe). Bunun yerine, ayrı bir işlemde (SPUCWorkerProcess.exe) yüklenir. Bu işlem izlenir ve kotalar ve CPU döngülerini tüketebilir sıkı döngüler çalıştırma gibi zararlı etkinlikleri gerçekleştirmesine korumalı çözümler grubunu korumak için azaltma uygular.  
  
## <a name="site-collection-solution-gallery"></a>Site koleksiyonu çözüm Galerisi  
 [!INCLUDE[sharepointShort](../sharepoint/includes/sharepointshort-md.md)] 2010 "site koleksiyonu çözüm Galerisi." bilinen bir özelliği vardır Bu özellik SharePoint 2010 Yönetim Merkezi sayfasından veya açarak erişebilir **Site eylemleri** menüsünde seçerek **Site Ayarları**ve ardından **çözümleri** altında bağlantı **galerileri** SharePoint sitesi. Çözüm galerileri kendi site koleksiyonlarında çözümleri yönetmek site koleksiyonu yöneticileri sağlayan çözümleri depolarının ' dir.  
  
 Çözüm Galerisi Web SharePoint sitesinin kök dizininde depolanmış bir Belge Kitaplığı ' dir. Çözüm Galerisi site şablonları değiştirir ve çözüm paketlerini destekler. Bir SharePoint çözüm paketi (.wsp) dosyası karşıya yüklendiğinde, korumalı bir çözüm olarak işlenir.  
  
## <a name="sandboxed-solution-limitations"></a>Korumalı çözüm sınırlamaları  
 Korumalı bir çözüm dağıtıldığında, SharePoint işlevsellik için kullanılabilir bir dizi yakınlarında herhangi bir güvenlik açığını azaltmaya yardımcı olmak için sınırlıdır. Bu sınırlamalara bazıları şunlardır:  
  
-   Korumalı çözümler kullanabilecekleri dağıtılabilir çözüm öğelerinin sınırlı bir alt vardır. Site tanımları ve iş akışları gibi savunmasız olabilecek SharePoint proje şablonları kullanılabilir değil.  
  
-   SharePoint çalıştıran Korumalı çözüm kodu bir işlemde (SPUCWorkerProcess.exe) ana ayrı [!INCLUDE[TLA2#tla_iis5](../sharepoint/includes/tla2sharptla-iis5-md.md)] uygulama havuzunun (w3wp.exe) işlemi.  
  
-   Eşlenen klasörler projeye eklenemez.  
  
-   Türlerini [!INCLUDE[moss_14_long](../sharepoint/includes/moss-14-long-md.md)] derleme Microsoft.Office.Server korumalı alan çözümlerinde kullanılamaz. Ayrıca, yalnızca türlerini [!INCLUDE[wss_14_long](../sharepoint/includes/wss-14-long-md.md)] derleme Microsoft.SharePoint korumalı alan çözümlerinde kullanılabilir.  
  
 Korumalı bir çözüm, SharePoint sunucusu üzerine herhangi bir etkisi yoktur, bir SharePoint çözüm belirten gibi dikkate almak önemlidir; yalnızca SharePoint Proje SharePoint'ten nasıl dağıtıldığını belirler [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)] ve hangi derlemelerin, bağlanır. Oluşturulan .wsp dosyası etkilemez ve doğrudan için karşılık gelen veri .wsp dosyası yok *Korumalı çözüm* özelliği.  
  
## <a name="capabilities-and-elements-in-sandboxed-solutions"></a>Özellikler ve öğeler korumalı alana alınan çözümler  
 Korumalı çözümler aşağıdaki özellikleri ve öğeleri destekler:  
  
-   İçerik türleri/alanları  
  
-   Özel Eylemler  
  
-   Bildirim temelli iş akışları  
  
-   Olay alıcıları  
  
-   Özellik belirtme  
  
-   Liste tanımları  
  
-   Liste Örnekleri  
  
-   Modül/dosyaları  
  
-   Gezinme  
  
-   onet.XML  
  
-   SPItemEventReceiver  
  
-   SPListEventReceiver  
  
-   SPWebEventReceiver  
  
-   Öğesinden türetilen tüm Web bölümleri için destek `System.Web.UI.WebControls.WebParts.WebPart`  
  
-   Web Bölümleri  
  
-   LCID'sine özellik öğeleri (yerine Webtemp.xml)  
  
-   Visual Web Bölümleri  
  
 Korumalı çözümler, aşağıdaki özellikleri ve öğeleri desteklemez:  
  
-   Uygulama sayfaları  
  
-   Özel eylem grubu  
  
-   Grup kapsamlı özellikler  
  
-   `HideCustomAction` öğesi  
  
-   Web uygulama kapsamlı özellikleri  
  
-   Kod ile iş akışları  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Korumalı arasındaki farklar ve Grup çözümleri](../sharepoint/differences-between-sandboxed-and-farm-solutions.md)   
 [SharePoint Çözümleri Geliştirme](../sharepoint/developing-sharepoint-solutions.md)  
  
  