---
title: Web sitesi destek öznitelikleri | Microsoft Docs
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- web site projects, registration
ms.assetid: 46d52e2c-ca2a-4bbd-8500-5b0129768aec
caps.latest.revision: 10
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 3fd60c1ffcb6bb4d3c386cf55fb1f33540bb3dd2
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/22/2018
ms.locfileid: "42686594"
---
# <a name="web-site-support-attributes"></a>Web Sitesi Destek Öznitelikleri
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

Bu konuda en son sürümünü şu yolda bulunabilir: [Web sitesi destek öznitelikleri](https://docs.microsoft.com/visualstudio/extensibility/internals/web-site-support-attributes).  
  
[!INCLUDE[vsprvs](../../includes/vsprvs-md.md)] Web sitesi projesi Web desteği sağlamak için programlama genişletilebilir. Dil kendisi ile kaydetmelisiniz [!INCLUDE[vsprvs](../../includes/vsprvs-md.md)] böylece proje şablonları görünebilen **yeni Web sitesi** dil seçildiğinde iletişim kutusu.  
  
 IronPython Studio örnek web sitesi desteği içerir. İle bulabilirsiniz [VSSDK örnekleri](../../misc/vssdk-samples.md). Bu, IronPython, yeni Web projeleri için bir codebehind dili olarak kaydetmek için aşağıdaki öznitelik sınıfları içerir.  
  
## <a name="websiteprojectattribute"></a>WebSiteProjectAttribute  
 Bu öznitelik, dil projede yer alır. Web programlama dilleri listesini dili ekler **dil** listesinde **yeni Web sitesi** iletişim kutusu. Örneğin, aşağıdaki IronPython listeye ekler:  
  
```  
[WebSiteProject("IronPython", "Iron Python")]public class PythonProjectPackage : ProjectPackage  
```  
  
 Bu öznitelik, ayrıca şablonları klasörüne işaret edecek şekilde şablonları yolunu ayarlar. Şablonları klasörünün konumu hakkında daha fazla bilgi için bkz. [Web sitesi destek şablonları](../../extensibility/internals/web-site-support-templates.md).  
  
## <a name="websiteprojectrelatedfilesattribute"></a>WebSiteProjectRelatedFilesAttribute  
 Bu öznitelik, dil projede yer alır. Bir dosya türü (ilgili) içine yerleştirmek Web sitesi projesi başka bir dosya türü altında (birincil) verir **Çözüm Gezgini**.  
  
 Örneğin:  
  
```  
[WebSiteProjectRelatedFiles("aspx", "py")]public class PythonProjectPackage : ProjectPackage  
```  
  
 bir .aspx dosyasına bir IronPython codebehind dosya ilgili olup olmadığını belirtir. Yeni bir .aspx Web sayfası bir IronPython Web sitesini çözümde oluşturulduğunda, yeni .py kaynak dosyası oluşturulur ve .aspx sayfasına bir alt düğüm olarak görünür.  
  
## <a name="provideintellisenseproviderattribute"></a>ProvideIntellisenseProviderAttribute  
 Bu öznitelik dil proje pakete yerleştirildi. Bu dil için IntelliSense sağlayıcısı seçer.  
  
 Örneğin:  
  
```  
[ProvideIntellisenseProvider(typeof(PythonIntellisenseProvider), "IronPythonCodeProvider", "Iron Python", ".py", "IronPython;Python", "IronPython")]public class PythonPackage : Package, IOleComponent  
```  
  
 belirten bir örneğini uygulayan PythonIntellisenseProvider <xref:Microsoft.VisualStudio.Shell.Interop.IVsIntellisenseProject>, dil hizmetleri sağlamak amacıyla isteğe bağlı olarak oluşturulmalıdır.  
  
 IVsIntellisenseProject uygulama başvuruları işler ve bir Web sayfası koduna sahip istenen ancak önbelleğe alınmamış dil derleyicisini çağırır.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Web Sitesi Desteği](../../extensibility/internals/web-site-support.md)

