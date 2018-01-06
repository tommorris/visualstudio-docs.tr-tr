---
title: "Hata ayıklayıcı genişletilebilirlik ile çalışmaya başlama | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- getting started, Debugging SDK
- debugging [Debugging SDK], getting started
- Debugging SDK, getting started
ms.assetid: d6ce6f43-1409-4bf7-93cd-f3464ca23504
caps.latest.revision: "17"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload: vssdk
ms.openlocfilehash: 964b6bcc18e74174aa59e7a1bb4441e24d3918d7
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/22/2017
---
# <a name="getting-started-with-debugger-extensibility"></a>Hata ayıklayıcı genişletilebilirlik ile çalışmaya başlama
[!INCLUDE[vsipsdk](../../extensibility/includes/vsipsdk_md.md)] Oluşturmak ve programların içinden hatalarını ayıklamak için kullanılan hata ayıklayıcı bileşenleri özelleştirmek için gereken bilgileri sağlar [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] ortamı.  
  
 [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)]hata ayıklama önceki üzerinde gerçekleştirilen sınama kapsamlı kullanılabilirlik türetilmiş geliştirmeleri ekledi [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] hata ayıklayıcıları. Kullanabileceğiniz [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] çok dilli uygulama veya aracılığıyla adım hata ayıklama uygulayabilirsiniz üzerinde-çalışma sırasında uygulamaları ve birden fazla dil çözümleri hata ayıklarken değişkenleri düzenleme.  
  
 [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)]hata ayıklama yürütülen zaman-işlem ayıklanacak programla ve bu nedenle uygulama işlemi alanında daha az müdahale. Sonuç olarak, hata ayıklama programınızı etkilemeden hata ayıklayıcısı ile etkileşim bileşenleri yazmak daha kolay olur.  
  
 En iyi [!INCLUDE[vsipsdk](../../extensibility/includes/vsipsdk_md.md)], aşağıdakilerle bilgi sahibi olmanız gerekir:  
  
-   [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] Tümleşik geliştirme ortamı (IDE)  
  
-   C++ programlama dili  
  
-   ATL COM  
  
## <a name="in-this-section"></a>Bu Bölümde  
 [Hata Ayıklayıcıyı Genişletmek için Yol Haritası](../../extensibility/debugger/roadmap-for-extending-the-debugger.md)  
 Uygulama, derleyici ve çıktısını bağlı olarak ürününüzün hata ayıklama işlemi açıklanmaktadır.  
  
 [Hata Ayıklayıcı Bileşenleri](../../extensibility/debugger/debugger-components.md)  
 Genel bir bakış sağlar [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] hata ayıklama altyapısı (DE), ifade değerlendiricisi (EE) ve simge işleyici (SH) dahil bileşenleri hata ayıklama.  
  
 [Hata Ayıklayıcı Kavramları](../../extensibility/debugger/debugger-concepts.md)  
 Ana hata ayıklama mimari kavramlarını açıklar.  
  
 [Hata Ayıklayıcı Bağlamları](../../extensibility/debugger/debugger-contexts.md)  
 Nasıl hata ayıklama altyapısı (DE) aynı anda kod, belgeler ve ifade değerlendirme bağlamı içinde çalıştığı açıklanmaktadır. , Her üç bağlamları, konum, konum veya değerlendirme için ilgili açıklar.  
  
 [Hata Ayıklama Görevleri](../../extensibility/debugger/debugging-tasks.md)  
 Bir program başlatma ve ifadeleri değerlendirme gibi çeşitli hata ayıklama görevlere bağlantılar içerir.