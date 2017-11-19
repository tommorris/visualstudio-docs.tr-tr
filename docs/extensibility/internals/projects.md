---
title: Projeleri | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- solutions [Visual Studio]
- custom tools [Visual Studio SDK]
- project subtypes [Visual Studio SDK]
- projects [Visual Studio SDK]
- project types [Visual Studio SDK]
ms.assetid: 237742e4-a638-4d5b-a9b3-6a69d627763c
caps.latest.revision: "43"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: c175d85b55734df841f30d131639c3bfeed40361
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2017
---
# <a name="projects"></a>Projeler
Visual Studio'da projeler geliştiricilerin kaynak kodu dosyaları ve görünen diğer kaynakları düzenlemek için kullandığınız kapsayıcılardır **Çözüm Gezgini**. Genellikle, projeler kaynak kodu dosyaları ve bit eşlem dosyaları gibi kaynaklara başvurular depolayan (örneğin, C# projesi için .csproj dosyasını) dosyalarıdır. Düzenleme, yapı, hata ayıklama ve kaynak kodu dağıtmanıza olanak sağlayan projeleri, Web Hizmetleri ve veritabanları ve diğer kaynaklara başvuruyor. VSPackages Visual Studio Proje sistemi üç temel şekilde genişletebilir: *proje türleri*, *proje subtypes*, ve *özel Araçlar*.  
  
## <a name="in-this-section"></a>Bu Bölümde  
 [Proje türleri](../../extensibility/internals/project-types.md)  
 *Proje türleri* projelerin programlama dilleri gibi yeni türleri için destek ekleyin. Örneğin, Visual Studio destekleyen her bir dilin kendi proje türü var ve IronPython tümleştirme örneği IronPython dil için bir proje türü içeriyor. C# veya Visual Basic nasıl öğeler yerleşik, hata ayıklaması, dağıtılan ve görüntülenen özelleştirmek için başka diller için bir proje türü oluşturmalısınız **Çözüm Gezgini**. Daha fazla bilgi için bkz: [proje türleri](../../extensibility/internals/project-types.md).  
  
 [Proje alt türleri](../../extensibility/internals/project-subtypes.md)  
 *Proje subtypes* proje türlerine dayanan bazı ve projeleri yerleşik, hata ayıklaması ve dağıtılan biçimini özelleştirmek üzere kullanılabilir. Visual Studio proje türlerinde akıllı aygıt projeleri ile kullanır; Bunlar, dağıtım yeni oluşturulmuş bir program geliştirme bilgisayarından ile hedef aygıta kopyalayarak özelleştirin. C# ve Visual Basic proje türleri temel olarak proje alt türleri için kullanılabilir; C++ proje türleri olamaz. Kendi proje türleri, proje alt türleri için temel olarak da kullanılabilir. Daha fazla bilgi için bkz: [proje Subtypes](../../extensibility/internals/project-subtypes.md).  
  
 [Web projeleri](../../extensibility/internals/web-projects.md)  
 Sırayla Web uygulamaları oluşturmak Web projesi açıklanmaktadır.  
  
 [Yeni proje oluşturma: başlık altında bir bölüm](../../extensibility/internals/new-project-generation-under-the-hood-part-one.md) ve [yeni proje oluşturma: başlık altında iki bölüm](../../extensibility/internals/new-project-generation-under-the-hood-part-two.md)  
 Yeni bir proje oluşturduğunuzda, gerçekten neler olduğunu açıklar.  
  
 [VSSDK örnekleri](http://aka.ms/vs2015sdksamples)  
 Projeler ve çözümler ile ilgilenir VSSDK örneklerinde içerir.  
  
## <a name="related-sections"></a>İlgili Bölümler  
 [Visual Studio SDK içinde](../../extensibility/internals/inside-the-visual-studio-sdk.md)  
 Visual Studio genişletilebilirlik farklı yönlerini açıklanmaktadır.