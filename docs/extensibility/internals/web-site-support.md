---
title: "Web sitesi desteği | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- web site projects
ms.assetid: ce9f4266-bb64-4c09-be88-4bd6413f60d0
caps.latest.revision: 
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload:
- vssdk
ms.openlocfilehash: 09b43963d657e8d1fe7aa24e98632d2ca46240c6
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/22/2017
---
# <a name="web-site-support"></a>Web sitesi desteği
Bir Web sitesi proje sistemi Web projeleri oluşturan bir proje sistemidir. Web projeleri, Web uygulamaları sırayla oluşturun. Bir Web sitesi projesini kod ilişkili her Web sayfası için bir yürütülebilir dosyası oluşturur. Başka bir yürütülebilir dosya kaynak kodu dosyalarından /App_Code klasöründe oluşturulur.  
  
 Web sitesi proje sistemleri, şablonları ve kayıt öznitelikleri varolan bir proje sistemine ekleyerek oluşturulur. Dili için IntelliSense sağlayıcısı özniteliklerden birini seçer. IntelliSense sağlayıcı uygulaması başvuruları işler ve önbelleğe alınmamış akıllı bir Web sayfası istendiğinde dil derleyici çağırır.  
  
 Web sayfaları derlemek için kullanılan dil derleyicisi ile kaydedilmelidir [!INCLUDE[vstecasp](../../code-quality/includes/vstecasp_md.md)]. Kullanabileceğiniz [ \<derleyici > öğesi](/dotnet/framework/configure-apps/file-schema/compiler/compiler-element) aşağıdaki örnekteki gibi derleyici kaydetmek için Web.config dosyasında:  
  
```  
<system.codedom>  <compilers>    <compiler language="py;IronPython" extension=".py"       type="IronPython.CodeDom.PythonProvider, IronPython,       Version=1.0.2391.18146, Culture=neutral,       PublicKeyToken=b03f5f7f11d50a3a" />  </compilers></system.codedom>  
```  
  
## <a name="in-this-section"></a>Bu Bölümde  
 [Web Sitesi Destek Şablonları](../../extensibility/internals/web-site-support-templates.md)  
 Yeni Web sitesi projeleri ve ilişkili öğeleri oluşturmak için kullanabileceğiniz şablonlarını listeler.  
  
 [Web Sitesi Destek Öznitelikleri](../../extensibility/internals/web-site-support-attributes.md)  
 Bir Web sitesi projesine bağlanmak kayıt öznitelikleri gösterir [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] ve [!INCLUDE[vstecasp](../../code-quality/includes/vstecasp_md.md)].  
  
## <a name="related-sections"></a>İlgili Bölümler  
 [Web Projeleri](../../extensibility/internals/web-projects.md)  
 Web projeleri, Web sitesi projeleri ve Web Uygulama projeleri iki tür genel bir bakış sunar.