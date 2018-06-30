---
title: 'Nasıl yapılır: bir kullanıcı denetimi oluşturmak için SharePoint uygulama sayfası veya Web Bölümü | Microsoft Docs'
ms.custom: ''
ms.date: 02/02/2017
ms.technology:
- office-development
ms.topic: conceptual
dev_langs:
- VB
- CSharp
- VB
- CSharp
helpviewer_keywords:
- user controls [SharePoint development in Visual Studio], creating
- user controls [SharePoint development in Visual Studio], adding
author: TerryGLee
ms.author: tglee
manager: douge
ms.workload:
- office
ms.openlocfilehash: 98333049f711e9d28d7adb1ad0c17cfc8514e4ad
ms.sourcegitcommit: d9e4ea95d0ea70827de281754067309a517205a1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/29/2018
ms.locfileid: "37120418"
---
# <a name="how-to-create-a-user-control-for-a-sharepoint-application-page-or-web-part"></a>Nasıl yapılır: bir SharePoint uygulama sayfası veya web bölümü için bir kullanıcı denetimi oluşturma
  SharePoint çözümünüz için özel işlevler sağlayan özel kullanıcı denetimleri oluşturabilirsiniz ve bu işlevselliği, projeyi yeniden kullanabilirsiniz. Bir web bölümü veya uygulama kullanıcı denetimlerini içerebilir sayfasında, diğer ASP.NET denetimleri ve SharePoint denetimleri ekleme ve denetim için özellikleri ve yöntemleri tanımlar. Kullanıcı denetimleri hakkında daha fazla bilgi için bkz: [web bölümleri veya uygulama sayfaları için yeniden kullanılabilir denetimler oluşturma](../sharepoint/creating-reusable-controls-for-web-parts-or-application-pages.md) ve [kullanıcı denetimleri ve SharePoint Server denetimleri](http://blogs.msdn.com/b/kaevans/archive/2011/04/28/user-controls-and-server-controls-in-sharepoint.aspx).  
  
### <a name="to-create-a-user-control-for-sharepoint"></a>SharePoint için bir kullanıcı denetimi oluşturmak için  
  
1.  Visual Studio'da açın veya bir SharePoint projesi oluşturun.  
  
     Bkz: [SharePoint projesi ve proje öğesi şablonları](../sharepoint/sharepoint-project-and-project-item-templates.md).  
  
2.  İçinde **Çözüm Gezgini**, proje düğümünü seçin.  
  
3.  Menü çubuğunda seçin **proje** > **Yeni Öğe Ekle**.  
  
     **Yeni Öğe Ekle** iletişim kutusu açılır.  
  
4.  İçinde **yüklü** bölmesinde seçin **Office/SharePoint** düğümü.  
  
5.  SharePoint şablonları listesinden seçip **kullanıcı denetimi (yalnızca Grup çözüm)**.  
  
    > [!NOTE]  
    >  Kullanıcı denetimleri, yalnızca küme çözümleri içinde çalışır.  
  
6.  İçinde **adı** kutusunda kullanıcı denetimi için bir ad belirtin ve ardından **Ekle** düğmesi.  
  
     Visual Studio birkaç klasörleri ve dosyaları projenize ekler. Bu dosyalar hakkında daha fazla bilgi için bkz: [web bölümleri veya uygulama sayfaları için yeniden kullanılabilir denetimler oluşturma](../sharepoint/creating-reusable-controls-for-web-parts-or-application-pages.md).  
  
     Varsayılan olarak, kullanıcı Denetim dosyası görünür **kaynak** Visual Web Developer Designer görünüm. Bu görünümde, denetimin XML Biçimlendirme düzenleyebilirsiniz. Geçiş yapabilirsiniz **tasarım** denetimlerden sürükleyerek denetim görsel olarak tasarlamak istiyorsanız görüntülemek **araç**. Bkz: [Tasarım görünümü, Web sayfası tasarımcısı](http://msdn.microsoft.com/en-us/d8f2270a-357d-40a4-9b39-1a3f2366216d).  
  
7.  Denetimde meydana gelen olayları işlemek istiyorsanız, kodu kullanıcı denetimini kod dosyasına ekleyin.  
  
     Bu dosyayı görünür **Çözüm Gezgini** kullanıcı denetiminin dosya altında ve bir *.cs* veya *.vb* projenin dili bağlı olarak uzantısı.  
  
## <a name="see-also"></a>Ayrıca bkz.
 [Web bölümleri veya uygulama sayfaları için yeniden kullanılabilir denetimler oluşturma](../sharepoint/creating-reusable-controls-for-web-parts-or-application-pages.md)   
 [SharePoint için uygulama sayfaları oluşturma](../sharepoint/creating-application-pages-for-sharepoint.md)   
 [SharePoint Web bölümleri oluşturma](../sharepoint/creating-web-parts-for-sharepoint.md)  
  
