---
title: "SharePoint için site tanımları oluşturma | Microsoft Docs"
ms.custom: 
ms.date: 02/02/2017
ms.reviewer: 
ms.suite: 
ms.technology: office-development
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- VB
- CSharp
- VB
- CSharp
helpviewer_keywords:
- SharePoint development in Visual Studio, site definitions
- site definitions [SharePoint development in Visual Studio]
ms.assetid: 83db570d-6b9f-4dab-9e71-db41f17b987a
caps.latest.revision: "21"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload: office
ms.openlocfilehash: 98be671e456c75c4be79994c84bf1ed6ae5114de
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/22/2017
---
# <a name="creating-site-definitions-for-sharepoint"></a>SharePoint için Site Tanımları Oluşturma
  SharePoint Site tanımı projesinde [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)] oluşturmanıza olanak tanır bir *site tanım*, hangi yeni bir SharePoint sitesi için bir temel olarak hizmet verir. Bu tanımları yalnızca görünümünü ve davranışını SharePoint sitesi, ancak aynı zamanda varsayılan içeriğini ve işlevleri belirler. Tanımı'nda, önceden yapılandırılmış listeleri, içerik türleri, Olay alıcıları, resimleri ve diğer öğeleri koyabilirsiniz. Örneğin, SharePoint BLOG gibi bazı site tanımları içerir. BLOG sitesi tanımına dayalı olarak bir site oluşturduğunuzda, site listeler, Web Bölümleri ve bir blog sitesi gerektiren diğer öğeleri içerir.  
  
 Site tanımları hakkında daha fazla bilgi için bkz: [Site şablonları ve tanımları](http://go.microsoft.com/fwlink/?LinkId=179134).  
  
## <a name="site-definition-projects"></a>Site Tanımı Projeleri  
 Site tanımı projelerinde [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)] bir SharePoint sitesi gereken temel dosyaları sağlar; herhangi bir varsayılan işlevsellik belirtmeyin. Dosyaları ve istediğiniz işlevselliği sağlamak için içeriği eklemeniz gerekir. Site oluşturma ve sizin için gereken dosyaları ekleyerek el ile oluşturabilirsiniz.  
  
## <a name="feature-stapling"></a>Özellik Zımbalama  
 Site tanımları oluşturma yararlarından biri [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)] otomatik olarak kullandıkları olan *özelliği Zımbalı*. Özellik Zımbalama işlevselliğini site tanımı kendisi yerine site tanımı bir özellik ekler. Bunun yapılması, özgün site tanımı değiştirmeden site tanımı kullanılarak oluşturulan herhangi bir siteye özelliği eklemenizi sağlar. Daha fazla bilgi için bkz: [özelliği Zımbalı](http://go.microsoft.com/fwlink/?LinkID=119283).  
  
## <a name="site-definition-project-components"></a>Site Tanımı Proje Bileşenleri  
 Bir site tanımı çözüm oluşturduğunuzda aşağıdaki varsayılan dosyaları eklenir, **SiteDefinition** düğümü.  
  
|Dosya Adı|Açıklama|  
|---------------|-----------------|  
|Default.aspx|Yeni SharePoint sitesi için varsayılan ASPX giriş sayfası.|  
|onet.XML|Yeni sitenin yapılandırmasını, bileşenlerini site tanımı şablonu ve varsayılan davranışını belirtir. Bu ayarlar, öznitelikler etkinleştirilen, içerik türleri gibi varsayılan liste görünümleri belge şablonu dosyaları içerir ve Web sitesiyle dahil bölümleri. Varsayılan olarak, `Modules` bölümü SharePoint sitesine ve nasıl yapılandırıldıklarına eklenecek dosyalar listeler.|  
|webtemp_*SiteDefinitionName*.xml|Görünür site tanımı yapılandırmaları belirtir **Şablon Seçimi** bölümünü **yeni SharePoint sitesi** sayfası.|  
  
 Varsayılan olarak, tüm site tanımları depolanmış *sürücü:*\Program Files\Microsoft Shared\Web Server Extensions\14\TEMPLATE\SiteTemplates klasör. Her bir site tanımı kendi alt vardır.  
  
## <a name="related-topics"></a>İlgili Konular  
  
|Başlık|Açıklama|  
|-----------|-----------------|  
|[İzlenecek yol: Temel bir Site Tanımı Projesi Oluşturma](../sharepoint/walkthrough-create-a-basic-site-definition-project.md)|Adım adım bir temel site tanımı projesi oluşturma aracılığıyla sizi [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)].|  
|[Nasıl yapılır: özel Site Tanım ve yapılandırma oluşturma](http://go.microsoft.com/fwlink/?LinkId=183309)|Varolan bir site tanımı kopyalama ve bu kopyayı değiştirerek bir özel site tanımı SharePoint'te oluşturmayı açıklar.|  
|[WebTemp.xml](http://go.microsoft.com/fwlink/?LinkId=183310)|Kullanılabilir site tanımları belirtir özgün dosya anlatılmakta **Şablon Seçimi** bölümünü **yeni SharePoint sitesi** sayfası.|  
|[SharePoint Çözümlerini Yerelleştirme](../sharepoint/localizing-sharepoint-solutions.md)|SharePoint çözümlerini genel kullanım için hazırlamayı açıklar.|  
|[SharePoint için Web Bölümleri Oluşturma](../sharepoint/creating-web-parts-for-sharepoint.md)|Kullanıcılar değiştirebilir bir SharePoint sayfasına bölümlerini nasıl oluşturabileceğiniz açıklanmaktadır.|  
|[Web Bölümleri veya Uygulama Sayfaları için Yeniden Kullanılabilir Denetimler Oluşturma](../sharepoint/creating-reusable-controls-for-web-parts-or-application-pages.md)|Uygulama sayfaları ve Web Bölümleri çalıştıran yeniden kullanılabilir denetimler nasıl oluşturabileceğiniz açıklanmaktadır.|  
|[Visual Web Developer](http://go.microsoft.com/fwlink/?LinkId=178725)|Projenizde bir Web sayfasını açtığınızda görüntülenen tasarımcının nasıl kullanılacağı açıklanmaktadır.|  
|[ASP.NET Web sayfaları genel bakış](http://go.microsoft.com/fwlink/?LinkId=178726)|Yapısı hakkında genel bilgi sağlar [!INCLUDE[vstecasp](../sharepoint/includes/vstecasp-md.md)] Web sayfaları, sayfa tarafından nasıl işleneceğini [!INCLUDE[vstecasp](../sharepoint/includes/vstecasp-md.md)]ve nasıl [!INCLUDE[vstecasp](../sharepoint/includes/vstecasp-md.md)] sayfalarını görüntüleme XHTML standartlarıyla uyumlu biçimlendirme.|  
|[ASP.NET Web sayfası sözdizimi](http://go.microsoft.com/fwlink/?LinkId=178727)|Bir ASP.NET sayfasını oluştururlar biçimlendirme öğelerini açıklar.|  
|[Programlama ASP.NET Web sayfaları](http://go.microsoft.com/fwlink/?LinkId=178728)|Olay işleyicileri oluşturma hakkında bilgi sağlar [!INCLUDE[vstecasp](../sharepoint/includes/vstecasp-md.md)] sayfaları ve istemci komut dosyası ile çalışmaya nasıl.|  
|[Windows SharePoint Services programlama](http://go.microsoft.com/fwlink/?LinkId=178729)|Sağlanan yönetilen nesne modeli kullanmayı açıklar [!INCLUDE[sharepointShort](../sharepoint/includes/sharepointshort-md.md)].|  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [SharePoint Çözümleri Geliştirme](../sharepoint/developing-sharepoint-solutions.md)  
  
  