---
title: "Altyapısı hatalarını ayıklama | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: debug engines
ms.assetid: 148b1efc-ca07-4d8e-bdfc-c723a760c620
caps.latest.revision: "18"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload: vssdk
ms.openlocfilehash: 70e572b73f8474f77a17989c790f2e7336f9d7a5
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/22/2017
---
# <a name="debug-engine"></a>Altyapısı hata ayıklama
Hata ayıklama altyapısı (DE) yorumlayıcı veya işletim sistemi hata ayıklama Hizmetleri yürütme denetimi, kesme noktaları ve ifade değerlendirme gibi sunmak için birlikte çalışır. Ayıklanacak bir programın durumunu izlemek için DE sorumludur. Bunu gerçekleştirmek için CPU veya API çalışma zamanı tarafından sağlanan olup olmadığını ne olursa olsun yöntemleri desteklenen çalışma zamanında kullanabileceği DE kullanır.  
  
 Örneğin, ortak dil çalışma zamanı (CLR) çalışan bir program ICorDebugXXX arabirimleri aracılığıyla izlemek için mekanizma sağlar. CLR destekleyen SE uygun ICorDebugXXX arabirimleri ayıklanacak bir yönetilen kod programı izlemek için kullanır. Bu tür bilgilerini iletir oturum hata ayıklama Yöneticisi (SDM), ardından aktarır durumu değişiklikleri [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] IDE.  
  
> [!NOTE]
>  Hata ayıklama altyapısı belirli bir çalışma, diğer bir deyişle, hangi program olan çalışır hata ayıklaması sistem hedefler. CLR yönetilen kod için çalışma zamanı ve yerel Windows uygulamaları için Win32 çalışma zamanı şeklindedir. Oluşturduğunuz dil bu iki çalışma zamanları birini hedefleyebilirsiniz varsa [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] zaten gerekli hata ayıklama motorları sağlıyor. Tüm uygulamak için sahip bir ifade değerlendiricisi budur.  
  
## <a name="debug-engine-operation"></a>Altyapısı işlemi hata ayıklama  
 İzleme hizmetleri DE arabirimleri aracılığıyla uygulanır ve farklı işletimsel modlar arasında geçiş için hata ayıklama paket neden olabilir. Daha fazla bilgi için bkz: [işlem modları](../../extensibility/debugger/operational-modes.md). Genellikle çalışma zamanı ortamı başına yalnızca bir DE uygulama yok.  
  
> [!NOTE]
>  Transact-SQL için ayrı DE uygulamaları varken ve [!INCLUDE[jsprjscript](../../debugger/debug-interface-access/includes/jsprjscript_md.md)], VBScript ve [!INCLUDE[jsprjscript](../../debugger/debug-interface-access/includes/jsprjscript_md.md)] tek SE paylaşın.  
  
 [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)]hata ayıklama motorları iki yoldan biriyle çalıştırmak için hata ayıklama etkinleştirir: ya da aynı süreci [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] Kabuk ya da hedef programın aynı işlemde ayıklanacak. İkinci form genellikle ayıklanacak işlemi gerçekte bir yorumlayıcı altında çalışan bir komut dosyasıdır ve hata ayıklama altyapısı intimate yorumlayıcı betiği izlemek için bilmelidir ortaya çıkar. Bu durumda, yorumlayıcı gerçekte bir çalışma zamanı olduğunu unutmayın; hata ayıklama altyapıları için belirli çalışma zamanı uygulamalarıdır. Ayrıca, tek SE uygulaması (örneğin, uzaktan hata ayıklama) işlem ve makine sınırlarındaki bölünebilir.  
  
 DE ortaya çıkarır [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] hata ayıklama arabirimleri. COM tüm iletişimidir DE işlem içi, çıkış işleminin veya başka bir bilgisayarda yüklü olup olmadığını bileşen iletişimini etkilemez.  
  
 İfadenin sözdizimi anlamak bu belirli çalışma zamanı için DE etkinleştirmek için bir ifade değerlendiricisi bileşeni ile DE çalışır. DE dil derleyici tarafından üretilen simgesel hata ayıklama bilgileri erişmek için bir simge işleyici bileşeni ile de çalışır. Daha fazla bilgi için bkz: [ifade değerlendiricisi](../../extensibility/debugger/expression-evaluator.md) ve [simgesi sağlayıcısı](../../extensibility/debugger/symbol-provider.md).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Hata ayıklayıcı bileşenleri](../../extensibility/debugger/debugger-components.md)   
 [İfade değerlendirici](../../extensibility/debugger/expression-evaluator.md)   
 [Sembol Sağlayıcısı](../../extensibility/debugger/symbol-provider.md)