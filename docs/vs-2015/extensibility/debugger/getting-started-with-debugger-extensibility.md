---
title: Hata ayıklayıcı genişletilebilirliği ile çalışmaya başlama | Microsoft Docs
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
- getting started, Debugging SDK
- debugging [Debugging SDK], getting started
- Debugging SDK, getting started
ms.assetid: d6ce6f43-1409-4bf7-93cd-f3464ca23504
caps.latest.revision: 18
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: f8f056ed8fff53eb166b37f2adba9daa17f12916
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/22/2018
ms.locfileid: "42689367"
---
# <a name="getting-started-with-debugger-extensibility"></a>Hata Ayıklayıcı Genişletilebilirliği ile Çalışmaya Başlama
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

Bu konuda en son sürümünü şu yolda bulunabilir: [hata ayıklayıcı genişletilebilirliği ile çalışmaya başlama](https://docs.microsoft.com/visualstudio/extensibility/debugger/getting-started-with-debugger-extensibility).  
  
[!INCLUDE[vsipsdk](../../includes/vsipsdk-md.md)] Oluşturma ve hata ayıklama bileşenlerinin içinden programlarda hata ayıklamak için kullanılan özelleştirme için gereken bilgileri sağlar [!INCLUDE[vsprvs](../../includes/vsprvs-md.md)] ortam.  
  
 [!INCLUDE[vsprvs](../../includes/vsprvs-md.md)] hata ayıklama geliştirmeleri önceki üzerinde gerçekleştirilen test kapsamlı kullanılabilirlik türetilen ekledi [!INCLUDE[vsprvs](../../includes/vsprvs-md.md)] hata ayıklayıcıları. Kullanabileceğiniz [!INCLUDE[vsprvs](../../includes/vsprvs-md.md)] çok dilli uygulama veya boyunca adım adım hata ayıklama uygulayabilirsiniz uygulamalar ve çok dilli çözümler hata ayıklama sırasında değişkenler üzerinde halindeyken düzenleme.  
  
 [!INCLUDE[vsprvs](../../includes/vsprvs-md.md)] hata ayıklama yürütülen giden işlem hataları ayıklanan programa ile ve bu nedenle uygulamanın işlem alanına daha az müdahale eden. Sonuç olarak, hata ayıklama programınızı etkilemeden hata ayıklayıcısı ile etkileşim kuran bileşenler yazmak kolaydır.  
  
 En iyi şekilde kullanmanız [!INCLUDE[vsipsdk](../../includes/vsipsdk-md.md)], aşağıdakiler konusunda bilgi sahibi olmanız gerekir:  
  
-   [!INCLUDE[vsprvs](../../includes/vsprvs-md.md)] Tümleşik geliştirme ortamı (IDE)  
  
-   C++ programlama dili  
  
-   ATL COM  
  
## <a name="in-this-section"></a>Bu Bölümde  
 [Hata Ayıklayıcıyı Genişletmek için Yol Haritası](../../extensibility/debugger/roadmap-for-extending-the-debugger.md)  
 Uygulamaya bağlı olarak, derleyici ve çıktısını ürününüzde hata ayıklama işlemi açıklanmaktadır.  
  
 [Hata Ayıklayıcı Bileşenleri](../../extensibility/debugger/debugger-components.md)  
 Genel bir bakış sağlar [!INCLUDE[vsprvs](../../includes/vsprvs-md.md)] hata ayıklama altyapısı (DE) ifade değerlendiricisi (EE) ve sembol işleyici (SH) bileşenleri, hata ayıklama.  
  
 [Hata Ayıklayıcı Kavramları](../../extensibility/debugger/debugger-concepts.md)  
 Hata ayıklama ana mimari kavramlarını açıklar.  
  
 [Hata Ayıklayıcı Bağlamları](../../extensibility/debugger/debugger-contexts.md)  
 Nasıl hata ayıklama altyapısı (DE) aynı anda kod, belgeler ve ifade değerlendirme bağlamı içinde çalıştığı açıklanmaktadır. , Her üç bağlamları, konumu, konum veya değerlendirme için ilgili açıklar.  
  
 [Hata Ayıklama Görevleri](../../extensibility/debugger/debugging-tasks.md)  
 Program başlatma ve ifadeleri değerlendirme gibi çeşitli hata ayıklama görevlerini bağlantılar içerir.

