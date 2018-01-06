---
title: "Hata ayıklayıcı genişletmek için yol haritası | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- debugging [Debugging SDK], roadmap
- Debugging SDK, roadmap
ms.assetid: 1f4096a8-f7aa-4dfa-84e1-6d59263e70bb
caps.latest.revision: "16"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload: vssdk
ms.openlocfilehash: 612017888c78f0994a83a10e3628fc10b667f8d0
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/22/2017
---
# <a name="roadmap-for-extending-the-debugger"></a>Hata ayıklayıcı genişletmek için yol haritası
Bu belge genişletmek için kılavuz ve başvuru bilgileri sağlar [!INCLUDE[vs_current_short](../../code-quality/includes/vs_current_short_md.md)] ile hata ayıklayıcı [!INCLUDE[vsipsdk](../../extensibility/includes/vsipsdk_md.md)].  
  
 [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)]Belge hata ayıklama örnekleri, kapsamlı bir başvuru ve hata ayıklayıcı özelleştirmek için tipik yol göstermek birkaç Temsilcisi Senaryo içerir.  
  
 Derleyici ve çıktısını ürününüzü hata ayıklama uygulamak için yapmanız gerekenleri belirleyin. Varsa, derleyici:  
  
-   Windows yerel işletim sistemini hedefleyen ve yazan bir. PDB dosyası hata ayıklama programları içine tümleştirilmiştir yerel kod hata ayıklama altyapısı (DE) ile [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)]. Bir DE ya da ifade değerlendiricisi uygulamak gerekmez. İfade değerlendirici C++ programlama dili sözdizimi için yazılmıştır.  
  
-   Ara dil (MSIL) çıkışı, hata ayıklama programlar da içine tümleştirilmiştir yönetilen kodda hata ayıklama altyapı DE, ile Microsoft üreten [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)]. Bu nedenle, yalnızca bir ifade değerlendiricisi uygulaması. Bir örnek ifade değerlendiricisi sizin için sağlanır. Daha fazla bilgi için aşağıdaki konulara bakın:  
  
     [İfade değerlendirme](../../extensibility/debugger/expression-evaluation-visual-studio-debugging-sdk.md)  
  
     [İfadeleri Değerlendirme](../../extensibility/debugger/evaluating-expressions.md)  
  
     [İfade Değerlendirme Bağlamı](../../extensibility/debugger/expression-evaluation-context.md)  
  
     [Kesme Modunda İfade Değerlendirme](../../extensibility/debugger/expression-evaluation-in-break-mode.md)  
  
     [Ortak Dil Çalışma Zamanı İfade Değerlendiricisi Yazma](../../extensibility/debugger/writing-a-common-language-runtime-expression-evaluator.md)  
  
-   İşletim sistemi veya başka bir çalışma zamanı ortamında özel bir hedefleri, kendi DE yazmanız gerekir. ATL COM kullanarak basit bir DE oluşturan bir Öğreticisi sağlanır. Daha fazla bilgi için aşağıdaki konulara bakın:  
  
     [Özel Hata Ayıklama Altyapısı Oluşturma](../../extensibility/debugger/creating-a-custom-debug-engine.md)  
  
     [Öğretici: ATL COM kullanarak hata ayıklama altyapısı oluşturma](http://msdn.microsoft.com/en-us/9097b71e-1fe7-48f7-bc00-009e25940c24)  
  
     [Bağlantı Noktası Sağlayıcısı Uygulama](../../extensibility/debugger/implementing-a-port-supplier.md)  
  
     [Örnekler](../../extensibility/debugger/visual-studio-debugging-samples.md)  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Başlarken](../../extensibility/debugger/getting-started-with-debugger-extensibility.md)