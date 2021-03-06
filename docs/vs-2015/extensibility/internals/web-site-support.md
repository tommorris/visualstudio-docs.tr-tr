---
title: Web sitesi desteği | Microsoft Docs
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
- web site projects
ms.assetid: ce9f4266-bb64-4c09-be88-4bd6413f60d0
caps.latest.revision: 18
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 128c5d94bbb508e6cf168f3de5662ba88b9d6193
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/22/2018
ms.locfileid: "42688928"
---
# <a name="web-site-support"></a>Web Sitesi Desteği
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

Bu konuda en son sürümünü şu yolda bulunabilir: [Web sitesi desteği](https://docs.microsoft.com/visualstudio/extensibility/internals/web-site-support).  
  
Bir Web sitesi proje sistemi Web projeleri oluşturan bir proje sistemidir. Web projeleri sırayla Web uygulamaları oluşturun. Bir Web sitesi projesi kod ilişkili her bir Web sayfası için bir yürütülebilir dosya oluşturur. Ek yürütülebilir dosyalar /App_Code klasöründeki kaynak kodu dosyasından oluşturulur.  
  
 Web sitesi proje sistemleri, varolan bir proje sistemine şablonları ve kaydı öznitelikleri ekleyerek oluşturulur. Bu öznitelikler dil için IntelliSense sağlayıcı seçer. IntelliSense sağlayıcı uygulaması başvuruları işler ve önbelleğe alınmamış akıllı bir Web sayfası istenen dil derleyicisini çağırır.  
  
 Web sayfaları derlemek için kullanılan dil derleyici ile kaydedilmelidir [!INCLUDE[vstecasp](../../includes/vstecasp-md.md)]. Kullanabileceğiniz [ \<derleyici > öğesi](http://msdn.microsoft.com/library/7a151659-b803-4c27-b5ce-1c4aa0d5a823) Web.config dosyasında aşağıdaki örnekte olduğu gibi derleyici kaydetmek için:  
  
```  
<system.codedom>  <compilers>    <compiler language="py;IronPython" extension=".py"       type="IronPython.CodeDom.PythonProvider, IronPython,       Version=1.0.2391.18146, Culture=neutral,       PublicKeyToken=b03f5f7f11d50a3a" />  </compilers></system.codedom>  
```  
  
## <a name="in-this-section"></a>Bu Bölümde  
 [Web Sitesi Destek Şablonları](../../extensibility/internals/web-site-support-templates.md)  
 Yeni Web sitesi projeleri ve ilişkili öğeleri oluşturmak için kullanabileceğiniz şablonları listeler.  
  
 [Web Sitesi Destek Öznitelikleri](../../extensibility/internals/web-site-support-attributes.md)  
 Bir Web sitesi projesine bağlanmak kaydı öznitelikleri gösterir [!INCLUDE[vsprvs](../../includes/vsprvs-md.md)] ve [!INCLUDE[vstecasp](../../includes/vstecasp-md.md)].  
  
## <a name="related-sections"></a>İlgili Bölümler  
 [Web Projeleri](../../extensibility/internals/web-projects.md)  
 Web projeleri, Web sitesi projeleri ve Web Uygulama projeleri iki tür genel bir bakış sunar.

