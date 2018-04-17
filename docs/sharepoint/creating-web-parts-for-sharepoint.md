---
title: SharePoint için Web bölümleri oluşturma | Microsoft Docs
ms.custom: ''
ms.date: 02/02/2017
ms.technology:
- office-development
ms.topic: conceptual
f1_keywords:
- Microsoft.SharePoint.WebControls.DateTimeControl
- Microsoft.SharePoint.WebControls.CssLink
- Microsoft.SharePoint.WebControls.RssLink
- Microsoft.SharePoint.WebControls.Theme
- Microsoft.SharePoint.WebControls.AspMenu
- Microsoft.SharePoint.WebControls.ListProperty
- Microsoft.SharePoint.WebControls.ProjectProperty
- Microsoft.SharePoint.WebControls.FormsDigest
- Microsoft.SharePoint.WebControls.ScriptLink
dev_langs:
- VB
- CSharp
- VB
- CSharp
helpviewer_keywords:
- SharePoint development in Visual Studio, Web Parts
- Web Parts [SharePoint development in Visual Studio], designing
author: TerryGLee
ms.author: tglee
manager: douge
ms.workload:
- office
ms.openlocfilehash: 52f35f095c91422f8882724074c54ad48edd88f9
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/16/2018
---
# <a name="creating-web-parts-for-sharepoint"></a>SharePoint için Web Bölümleri Oluşturma
  Web Bölümleri'ni kullanarak, içerik, Görünüm ve bir SharePoint sitesinin sayfalarının davranışını bir tarayıcı kullanarak değiştirebilirsiniz. Web Bölümleri olan bir web bölümü sayfası içinde çalışan sunucu tarafı denetimleri: bir SharePoint sitesinde sayfaları yapı taşlarını oldukları. Bkz: [yapı taşı: Web Bölümleri](http://go.microsoft.com/fwlink/?LinkID=182097).  
  
 Oluşturun ve Visual Studio şablonlarını kullanarak bir SharePoint sitesinde web bölümleri hata ayıklama.  
  
## <a name="creating-a-web-part-in-visual-studio"></a>Visual Studio'da Web Bölümü Oluşturma  
 Ekleyerek web bölümü oluşturma bir **Web Bölümü** herhangi bir SharePoint proje öğesi. Kullanabileceğiniz bir **Web Bölümü** korumalı bir çözüm veya bir Grup çözümü öğe.  
  
 Tasarımcı kullanarak bir web bölümü görsel olarak tasarlamak için oluşturmak istiyorsanız, bir **Visual Web Bölümü** proje veya ekleme **Visual Web Bölümü** herhangi bir SharePoint proje öğesi. Kullanabileceğiniz bir **Visual Web Bölümü** yalnızca bir Grup çözümü öğesinde.  
  
### <a name="web-part-item"></a>Web Bölümü Öğesi  
 A **Web Bölümü** öğesi bir SharePoint sitesi için bir web bölümü tasarlamak için kullanabileceğiniz dosyaları sağlar. Eklediğinizde bir **Web Bölümü** öğesi, Visual Studio projenizi bir klasör oluşturur ve ardından klasörüne birkaç dosyaları ekler. Aşağıdaki tabloda, her dosya açıklanmaktadır.  
  
|Dosya|Açıklama|  
|----------|-----------------|  
|Elements.XML|Projenizdeki Özellik tanım dosyası web bölümünü dağıtmak için kullandığı bilgileri içerir.|  
|.WebPart dosyası|SharePoint web bölümü Galerisi'nde, web bölümünü görüntülemek için gereken bilgileri sağlar.|  
|Kod dosyası|Web bölümü için denetimler ekleme ve özel içerik web bölümü içinde oluşturma yöntemleri içerir.|  
  
 Daha fazla bilgi için bkz: [nasıl yapılır: bir SharePoint Web Bölümü oluşturma](../sharepoint/how-to-create-a-sharepoint-web-part.md).  
  
### <a name="visual-web-part-item"></a>Visual Web Bölümü Öğesi  
 Visual web bölümü Visual Studio'da Visual Web Developer Tasarımcısı'nı kullanarak oluşturduğunuz web bir parçasıdır. Visual web bölümü aynı herhangi bir web parçası olarak çalışır. Denetimler, düğmeler ve metin kutuları gibi bir web bölümü eklemek için bir XML dosyasına kodu ekleyin. Ancak, denetimleri visual web bölümü için sürükleyerek ya da Visual Studio'dan kopyalayarak web bölümü eklemeniz **araç**. Tasarımcı sonra XML dosyasında gerekli kod oluşturur. Bkz: [nasıl yapılır: Tasarımcı kullanarak bir SharePoint Web Bölümü oluşturma](../sharepoint/how-to-create-a-sharepoint-web-part-by-using-a-designer.md).  
  
## <a name="sharepoint-controls"></a>SharePoint Denetimleri  
 Visual Studio, uygulama sayfaları gibi SharePoint sayfaları oluşturmak için bazı denetimler sağlar. Bu denetimler görünür **araç** altında **SharePoint denetimleri**. Bu denetimler için işlevsellik türetilen [Microsoft.SharePoint.WebControls](http://go.microsoft.com/fwlink/?LinkId=235315) SharePoint site ve liste sayfalarında kullanılan ASP.NET sunucu denetimleri içeren ad alanı.  
  
|Denetim adı|Açıklama|  
|------------------|-----------------|  
|[AspMenu](http://go.microsoft.com/fwlink/?LinkId=235307)|Bir ASP menüsü ekler. Daha fazla bilgi için bkz: [Menü denetimine genel bakış](http://go.microsoft.com/fwlink/?LinkId=235316).|  
|[CssLink](http://go.microsoft.com/fwlink/?LinkId=235308)|Ekler bir **bağlantı** .aspx sayfası bir öğeye ve bir veya daha fazla dış stil sayfası tarafından tanımlandı geçerlidir **CssRegistration**.|  
|[DateTimeControl](http://go.microsoft.com/fwlink/?LinkId=235306)|DateTime denetim .aspx sayfasına ekler.|  
|[FormDigest](http://go.microsoft.com/fwlink/?LinkId=235309)|Güvenlik doğrulaması .aspx sayfasına ekler|  
|[ListProperty](http://go.microsoft.com/fwlink/?LinkId=235310)|Bir özelliği, belirtilen bir liste döndürür.|  
|[ProjectProperty](http://go.microsoft.com/fwlink/?LinkId=235311)|Genel özellik geçerli Web sitesinin döndürür.|  
|[RssLink](http://go.microsoft.com/fwlink/?LinkId=235312)|Bir RSS .aspx sayfasına bir bağlantı ekler.|  
|[ScriptLink](http://go.microsoft.com/fwlink/?LinkId=235313)|Özellikleri ve sayfa işlendiğinde bunlar istenebilir bir sayfadaki komut dosyaları gibi kaynakları kaydetme için yöntemleri sağlar.|  
|[Tema](http://go.microsoft.com/fwlink/?LinkId=235314)|Bir temayı .aspx sayfasına uygular.|  
  
## <a name="debugging-a-web-part"></a>Web Bölümünde Hata Ayıklama  
 Diğer Visual Studio projeleri debug gibi bir web bölümünü içeren bir SharePoint Proje ayıklayabilirsiniz. Visual Studio hata ayıklayıcısını başlattığınızda, Visual Studio SharePoint sitesini açar.  
  
 Kodunuzdaki hataları ayıklamanıza başlamak için SharePoint web bölümü sayfasına web bölümü ekleyin.  
  
 SharePoint projeleri hata ayıklama hakkında daha fazla bilgi için bkz: [SharePoint çözümlerinde sorun giderme](../sharepoint/troubleshooting-sharepoint-solutions.md).  
  
## <a name="visual-web-part-limitations"></a>Visual Web Bölümü Sınırlamaları  
 Visual Studio ile başlayarak, korumalı SharePoint çözümleri ve küme çözümleri için visual web bölümleri ekleyebilirsiniz. Ancak, visual web bölümleri, aşağıdaki sınırlamalara sahiptir:  
  
-   Visual web bölümleri değiştirilebilir parametreler desteklemez. Daha fazla bilgi için bkz: [değiştirilebilir parametreler](../sharepoint/replaceable-parameters.md).  
  
-   Kullanıcı denetimleri veya visual web bölümleri sürüklenen ve bırakılan veya değiştirilemez visual web bölümleri kopyalanır. Bu eylem bir yapı hatasına neden olur.  
  
-   Visual web bölümleri SharePoint server belirteçleri $SPUrl gibi doğrudan desteklemez. Daha fazla bilgi için "Belirteci kısıtlamaları içinde korumalı Visual Web Bölümleri" konusuna bakın. [SharePoint çözümlerinde sorun giderme](../sharepoint/troubleshooting-sharepoint-solutions.md).  
  
-   Visual web bölümleri korumalı bir çözümde bazen alma hatası, "korumalı kod ana bilgisayar hizmeti isteği işlemek için çok meşgul olduğundan korumalı kod yürütme isteği reddedildi." Bu hata hakkında daha fazla bilgi için bu postasına bakın [SharePoint geliştirici ekibi blogu](http://go.microsoft.com/fwlink/?LinkId=225932).  
  
-   Sunucu tarafı JavaScript hata ayıklama Visual Studio'da desteklenmez, ancak istemci tarafı JavaScript hata ayıklama desteklenir.  
  
     Satır içi JavaScript bir sunucu tarafı biçimlendirme dosyasına ekleyebilirsiniz, ancak hata ayıklama kesme noktaları biçimlendirme eklenen için desteklenmiyor. JavaScript hata ayıklama için dış JavaScript dosyası biçimlendirme dosyasındaki başvuru ve ardından JavaScript dosyasında kesme noktaları ayarlayın.  
  
-   Satır içi hata ayıklama [!INCLUDE[vstecasp](../sharepoint/includes/vstecasp-md.md)] kod işaretleme dosyasının yerine oluşturulan kod dosyasında yapılması gerekir.  
  
-   Visual web bölümleri kullanımını desteklemez `<@ Assembly Src=` yönergesi.  
  
-   SharePoint web denetimleri ve bazı [!INCLUDE[vstecasp](../sharepoint/includes/vstecasp-md.md)] denetimleri SharePoint korumalı ortamında desteklenmez. Desteklenmeyen denetimler visual web bölümü hata korumalı bir çözümde kullanılan "'Tema' 'Microsoft.SharePoint.WebControls' ad alanında yok türü veya ad alanı adı" görüntülenir.  
  
 Korumalı çözümler hakkında daha fazla bilgi için bkz: [korumalı arasındaki farklar ve küme çözümleri](../sharepoint/differences-between-sandboxed-and-farm-solutions.md).  
  
## <a name="creating-older-style-sharepoint-based-web-parts"></a>Eski Stil SharePoint Tabanlı Web Bölümleri Oluşturma  
 Özel oluşturmak için Visual Studio şablonları kullanabilirsiniz [!INCLUDE[vstecasplong](../sharepoint/includes/vstecasplong-md.md)] için SharePoint web bölümleri. [!INCLUDE[vstecasplong](../sharepoint/includes/vstecasplong-md.md)] Web Bölümleri üstünde yerleşiktir [!INCLUDE[vstecasp](../sharepoint/includes/vstecasp-md.md)] web bölümü altyapı ve yeni projeler için önerilen türüdür.  
  
 Çok az durumlarda, SharePoint tabanlı web bölümü eski stil kullanarak bir web bölümü oluşturma gerekebilir. Web bölümleri'nin bu türleri oluşturmak için Visual Studio'yu kullanabilirsiniz, ancak Visual Studio özellikle bunları oluşturmanıza yardımcı olmak için tasarlanmış şablonları sağlamaz.  
  
 Ne zaman daha eski olan bir stil SharePoint tabanlı web bölümü oluşturmak isteyebilirsiniz hakkında daha fazla bilgi için bkz: [Windows SharePoint Services Web Bölümü altyapısında](http://go.microsoft.com/fwlink/?LinkId=169290). Eski stil SharePoint tabanlı web bölümünü kullanarak bir web bölümü oluşturma hakkında daha fazla bilgi için bkz: [temel bir SharePoint Web Bölümü oluşturma izlenecek](http://go.microsoft.com/fwlink/?LinkId=169288).  
  
## <a name="related-topics"></a>İlgili Konular  
  
|Başlık|Açıklama|  
|-----------|-----------------|  
|[Nasıl yapılır: Bir SharePoint Web Bölümü Oluşturma](../sharepoint/how-to-create-a-sharepoint-web-part.md)|SharePoint sayfaları için web bölümleri oluşturulacağı gösterilmektedir.|  
|[Nasıl Yapılır: Tasarımcı Kullanarak SharePoint Web Bölümü Oluşturma](../sharepoint/how-to-create-a-sharepoint-web-part-by-using-a-designer.md)|Görsel tasarım yüzeyini kullanarak SharePoint için web bölümleri oluşturulacağı gösterilmektedir.|  
|[Nasıl yapılır: SharePoint Uygulama Sayfası veya Web Bölümü için Kullanıcı Denetimi Oluşturma](../sharepoint/how-to-create-a-user-control-for-a-sharepoint-application-page-or-web-part.md)|Uygulama sayfaları ve SharePoint çalıştıran web bölümleri tarafından kullanılabilecek özel, yeniden kullanılabilir denetimler oluşturma gösterir.|  
|[İzlenecek yol: SharePoint için bir Web Bölümü Oluşturma](../sharepoint/walkthrough-creating-a-web-part-for-sharepoint.md)|Bir web bölümü SharePoint için tasarım konuları açıklanmaktadır.|  
|[İzlenecek Yol: Tasarımcı Kullanarak SharePoint için bir Web Bölümü Oluşturma](../sharepoint/walkthrough-creating-a-web-part-for-sharepoint-by-using-a-designer.md)|Denetimleri görsel tasarım yüzeyine sürükleyerek bir web bölümü SharePoint için tasarım konuları açıklanmaktadır.|  
|[İzlenecek yol: SharePoint için OData Görüntüleyen bir Silverlight Web Parçası Oluşturma](../sharepoint/walkthrough-creating-a-silverlight-web-part-that-displays-odata-for-sharepoint.md)|Bir web bölümü Silverlight uygulamasını barındıran ve SharePoint listeleri verileri görüntüleyen bir SharePoint için tasarım konuları açıklanmaktadır.|  
  
  