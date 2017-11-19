---
title: "SharePoint için uygulama sayfaları oluşturma | Microsoft Docs"
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
- SharePoint development in Visual Studio, Web pages
- SharePoint development in Visual Studio, content pages
- SharePoint development in Visual Studio, application pages
- application pages [SharePoint development in Visual Studio], developing
- application pages [SharePoint development in Visual Studio], creating
ms.assetid: a6e97149-15dd-4bdb-8d75-3b53f886f76c
caps.latest.revision: "36"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: 858df05759f1c3b4205d4cbcd0bbad2cdfb6e034
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2017
---
# <a name="creating-application-pages-for-sharepoint"></a>SharePoint için Uygulama Sayfaları Oluşturma
  Bir *uygulama sayfası* bir SharePoint Web sitesinde kullanılmak üzere tasarlanmış bir ASP.NET Web sayfası. Uygulama sayfaları, ASP.NET sayfası özel türüdür. Uygulama sayfası ve standart bir ASP.NET sayfası arasındaki birincil fark, bir uygulama sayfasını bir SharePoint ana sayfa ile birleştirilmiş içeriğin bulunduğu ' dir. Bir ana sayfa diğer sayfalarda bir site olarak aynı görünümü ve davranışı paylaşmak uygulama sayfaları sağlar.  
  
 Visual Studio Tasarımcı kullanarak uygulama sayfaları tasarlamanızı sağlar. Tasarımcı içerik alanı bir ana sayfada tanımlı her içerik bir yer tutucu görüntüler. Bu içerik alanlarına denetimlerini sürükleyerek uygulama sayfası tasarlayabilirsiniz.  
  
## <a name="application-pages"></a>Uygulama sayfaları  
 Belirli bir siteye site sayfasıdır ancak uygulama sayfaları sunucudaki tüm siteler arasında paylaşılır. Daha fazla bilgi için [SharePoint sayfası türleri](http://go.microsoft.com/fwlink/?LinkID=211584).  
  
 Varsayılan olarak, bir SharePoint sitesi oluşturduğunuzda görüntülenen sayfaların çoğu site sayfalarıdır. Bir site sayfası bir SharePoint sayfası kitaplığına eklenebilir. Kullanıcılar, SharePoint Designer gibi araçları kullanarak bir site sayfasını özelleştirebilirsiniz. Bir site sayfası dinamik Web Bölümleri ve Web Bölümü bölgeleri gibi özellikleri de barındırabilir.  
  
 Uygulama sayfaları bunlardan yapamazsınız. Ancak uygulama sayfası sayfası sayfasının özel kod içerecek biçimde istiyorsanız oluşturmak için en iyi türüdür. Bir site sayfasına özel kod eklemesi mümkün olsa da, kodu kullanıcı SharePoint Designer gibi araçları kullanarak sayfa özelleştirir zaman çalışmayı durdurur.  
  
> [!NOTE]  
>  Visual Studio sağlamaz yardımcı şablonları bir SharePoint sitesi için site sayfaları oluşturun. Daha fazla bilgi için bkz: [SharePoint sayfası türleri](http://go.microsoft.com/fwlink/?LinkID=211584).  
  
## <a name="creating-an-application-page"></a>Uygulama Sayfası Oluşturma  
 Uygulama sayfası oluşturma, ekleme bir **uygulama sayfası** bir SharePoint proje öğesi. Uygulama sayfası oluşturduğunuzda, Visual Studio aşağıdaki klasörler projenize ekler:  
  
|Klasör|Açıklama|  
|------------|-----------------|  
|Düzenleri|SharePoint dosya sisteminin _layouts sanal dizin eşlenir.|  
|Düzenleri alt|Uygulama sayfasını oluştururlar dosyalarını içerir. Varsayılan olarak, bu klasör projenizi aynı ada sahiptir. Bu klasörü herhangi bir zamanda yeniden adlandırabilirsiniz. Visual Studio Proje çalıştırdığınızda, bu klasör SharePoint dosya sistemi _layouts sanal dizinine dağıtır.|  
  
 Visual Studio aşağıdaki dosyaları projenize ekler:  
  
|Dosya|Açıklama|  
|----------|-----------------|  
|ASP.NET sayfası dosyası (.aspx)|Sayfayı tanımlayan XML biçimlendirme içeriyor.|  
|Uygulama sayfası kod dosyası|Uygulama sayfası arka plan kod içerir. Bu dosyaya olayları işleyen kodu ekleyin.|  
|Uygulama sayfası tasarımcı kod dosyası|Tasarımcı tarafından oluşturulan kodu içerir. Doğrudan bu dosyayı düzenlemeyin.|  
  
## <a name="designing-and-debugging-an-application-page"></a>Tasarlama ve uygulama sayfası hata ayıklama  
 Visual Studio'da Tasarımcı görünümünü kullanarak bir uygulama sayfasının içeriği tasarlayın. Projenizde uygulama sayfasını açtığınızda bu Tasarımcısı görünür (çift tıklatarak veya kısayol menüsünü açarak ve ardından seçme **açmak**) ve ardından **tasarım** alt kısmındaki düğmesi Düzenleyici.  
  
> [!NOTE]  
>  Sayfa tasarlayabilirsiniz yalnızca **kaynak** Designer görünüm. **Tasarım** uygulama sayfaları için Görünüm Tasarımcısı'nın devre dışı.  
  
 Visual Studio'da diğer SharePoint Proje öğeleri debug gibi bir uygulama sayfasını ayıklayabilirsiniz. Visual Studio hata ayıklayıcısını başlattığınızda, Visual Studio SharePoint sitesini açar.  
  
 Uygulama sayfasını görüntülemek için el ile uygulama sayfası konuma gitmeniz gerekir (örneğin: http://*sunucu_adı*/_layouts/*Project_Name*/ApplicationPage1.aspx).  
  
 SharePoint projeleri hata ayıklama hakkında daha fazla bilgi için bkz: [SharePoint çözümlerinde sorun giderme](../sharepoint/troubleshooting-sharepoint-solutions.md).  
  
## <a name="choosing-a-master-page"></a>Bir ana sayfa seçme  
 Varsayılan olarak, bir **uygulama sayfası** öğesine başvuruyor, projenizin hatalarını ayıklamak için kullanmakta olduğunuz sitenin ana sayfa. Sayfa v4.master adlı ve onu listelenen bulabilirsiniz **Ana Sayfa Galerisi** SharePoint sitesi.  
  
 Hangi ana sayfa ayarlayarak uygulama sayfa tarafından kullanılan açıkça değiştirebilirsiniz `MasterPageFile` özniteliği uygulamanın `Page` öğesi. (Örneğin: `MasterPageFile="~/_layouts/applicationv4.master"`). Aslında, dinamik ana sayfalar SharePoint sunucusu üzerinde etkin değilse, bu öznitelik ayarlamanız gerekir. SharePoint ana sayfalar hakkında daha fazla bilgi için bkz: [ana sayfalar](http://go.microsoft.com/fwlink/?LinkID=169281).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [SharePoint Foundation geliştirme derinlemesine](http://go.microsoft.com/fwlink/?LinkID=182103)   
 [ASP.NET genel bakış](/aspnet/overview)   
 [ASP.NET Web sayfaları](/aspnet/web-pages/index)   
  
  