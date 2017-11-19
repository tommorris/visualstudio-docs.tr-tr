---
title: "Visual Studio hata ayıklayıcısı genişletilebilirliği | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- debugging [Visual Studio], Debugging SDK
- Debugging SDK
ms.assetid: c088b6a2-c3ad-446b-830d-9c6f41b2934b
caps.latest.revision: "32"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: b9a14f95fbed47670b3c5b5db19e4e0e6b8ba074
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2017
---
# <a name="visual-studio-debugger-extensibility"></a>Visual Studio hata ayıklayıcısı genişletilebilirliği
Visual Studio tamamen etkileşimli kaynak kod hataları programınızdaki aşağı izlemek için güçlü ve kullanımı kolay bir aracı sağlayan hata ayıklayıcı, içerir. Hata ayıklayıcı tam destek Visual Basic, C#, C/C++ ve JavaScript sahiptir. Bununla birlikte, [!INCLUDE[vsipsdk](../../extensibility/includes/vsipsdk_md.md)], yani kullanılabilir [Microsoft Download Center](http://go.microsoft.com/fwlink/?LinkId=214453), hata ayıklayıcı aynı zengin özelliklere sahip başka bir programlama dili desteklenir.  
  
 [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] Hata ayıklayıcı içinde ayıklanacak dile özgü kapatma olan hata ayıklama bileşenleri ortak ön uç (diğer bir deyişle, kullanıcı arabirimi) etmektir. İçin gerekli olan tüm yeni dilleri için destek [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] hata ayıklayıcısı hata ayıklama altyapısı (DE) gibi gerekli arka uç bileşenleri oluşturma etmektir. Where olan [!INCLUDE[vsipsdk](../../extensibility/includes/vsipsdk_md.md)] devreye girer.  
  
 [!INCLUDE[vsipsdk](../../extensibility/includes/vsipsdk_md.md)] Tüm tam bir başvuru içeriyor [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] yeni SE oluşturmak için gereken öğeler. Ayrıca, örnekler ve başlamanıza yardımcı olacak öğreticiler vardır.  
  
 Hata ayıklama desteği ile bir dil proje sisteminin bir uçtan uca örnek için bkz: [IronPython örnek](http://msdn.microsoft.com/en-us/4c41695c-12c1-4670-b43b-d8d84c9e4089).  
  
 Hata ayıklayıcı kullanarak genişletmek nasıl aşağıdaki bölümlerde [!INCLUDE[vsipsdk](../../extensibility/includes/vsipsdk_md.md)].  
  
## <a name="in-this-section"></a>Bu Bölümde  
 [Başlarken](../../extensibility/debugger/getting-started-with-debugger-extensibility.md)  
 Açıklanmaktadır [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] sunar ve SDK yükleme hata ayıklama.  
  
 [Bir özel hata ayıklama altyapısı oluşturma](../../extensibility/debugger/creating-a-custom-debug-engine.md)  
 Programınızı SE DE ayırmak için hazırlama özel DE işlemin, belgeler.  
  
 [Bir CLR ifade değerlendiricisi yazma](../../extensibility/debugger/writing-a-common-language-runtime-expression-evaluator.md)  
 Bir ifade değerlendiricisi yazma olup olmadığını açıklar.  
  
 [Hata ayıklama Engine uygulaması stratejisini seçme](../../extensibility/debugger/choosing-a-debug-engine-implementation-strategy.md)  
 Sizin DE uygulamak nasıl ele alınmaktadır.  
  
 [Başvuru](../../extensibility/debugger/reference/reference-visual-studio-debugging-apis.md)  
 Belgeleri [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] hata ayıklama API'si.  
  
 [Örnekleri](../../extensibility/debugger/visual-studio-debugging-samples.md)  
 Ortak dil çalışma zamanı ifade değerlendiricisi örnek ve hata ayıklama altyapısı örnek bağlantılar içerir.
