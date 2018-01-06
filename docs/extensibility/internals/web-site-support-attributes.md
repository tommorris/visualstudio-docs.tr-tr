---
title: "Web sitesi desteği öznitelikleri | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: web site projects, registration
ms.assetid: 46d52e2c-ca2a-4bbd-8500-5b0129768aec
caps.latest.revision: "9"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload: vssdk
ms.openlocfilehash: 868fe0785c90a174610b9fff837fc6fbfb084e83
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/22/2017
---
# <a name="web-site-support-attributes"></a>Web sitesi desteği öznitelikleri
[!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)]Web sitesi projesini Web desteği sağlamak için programlama dilleri genişletilebilir. Dil kendisiyle kaydetmelisiniz [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] böylece proje şablonları görüntülenebilir **yeni Web sitesi** dil seçildiğinde iletişim kutusu.  
  
 IronPython Studio örnek web sitesi desteği içerir. Yeni Web projeleri için arkasındaki koda dili olarak IronPython kaydetmek için aşağıdaki öznitelik sınıfları içerir.  
  
## <a name="websiteprojectattribute"></a>WebSiteProjectAttribute  
 Bu öznitelik dil projede yerleştirilir. Web programlama dilleri listesini dil ekler **dil** listesinde **yeni Web sitesi** iletişim kutusu. Örneğin, aşağıdaki IronPython listeye ekler:  
  
```  
[WebSiteProject("IronPython", "Iron Python")]public class PythonProjectPackage : ProjectPackage  
```  
  
 Bu öznitelik, ayrıca şablonları klasöre işaret edecek şekilde şablonları yolunu ayarlar. Şablonlar klasörünün konumu hakkında daha fazla bilgi için bkz: [Web sitesi desteği şablonları](../../extensibility/internals/web-site-support-templates.md).  
  
## <a name="websiteprojectrelatedfilesattribute"></a>WebSiteProjectRelatedFilesAttribute  
 Bu öznitelik dil projede yerleştirilir. İçinde başka bir dosya türü (birincil) altında bir dosya türü (ilgili) yerleştirmek Web sitesi projesini verir **Çözüm Gezgini**.  
  
 Örneğin:  
  
```  
[WebSiteProjectRelatedFiles("aspx", "py")]public class PythonProjectPackage : ProjectPackage  
```  
  
 bir IronPython arkasındaki koda dosyası .aspx dosyası için ilgili olduğunu belirtir. Yeni bir .aspx Web sayfası IronPython Web sitesi çözümünü oluşturulduğunda, yeni bir .py kaynak dosyası oluşturulur ve .aspx sayfası bir alt düğüm görünür.  
  
## <a name="provideintellisenseproviderattribute"></a>ProvideIntellisenseProviderAttribute  
 Bu öznitelik dil proje paketi yerleştirilir. Dili için IntelliSense sağlayıcısı seçer.  
  
 Örneğin:  
  
```  
[ProvideIntellisenseProvider(typeof(PythonIntellisenseProvider), "IronPythonCodeProvider", "Iron Python", ".py", "IronPython;Python", "IronPython")]public class PythonPackage : Package, IOleComponent  
```  
  
 belirleyen uygulayan PythonIntellisenseProvider örneği <xref:Microsoft.VisualStudio.Shell.Interop.IVsIntellisenseProject>, dil hizmetleri sağlamak için isteğe bağlı olarak oluşturulmalıdır.  
  
 IVsIntellisenseProject uygulama başvuruları işler ve bir Web sayfası koduna sahip istenen ancak önbelleğe alınmamış dil derleyici çağırır.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Web Sitesi Desteği](../../extensibility/internals/web-site-support.md)