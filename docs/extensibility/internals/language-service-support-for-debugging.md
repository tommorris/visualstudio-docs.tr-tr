---
title: "Hata ayıklama için dil hizmet desteği | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- debugger, language support
- language services, debugging support
ms.assetid: 7a44067f-a410-4a6a-84d2-bda5184140bc
caps.latest.revision: "15"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload: vssdk
ms.openlocfilehash: 955c8fd4e9499fbacfc0f97ba6112803ef1e6d4a
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/22/2017
---
# <a name="language-service-support-for-debugging"></a>Hata ayıklama için dil hizmeti desteği
Bir dil hizmeti aracılığıyla bir hata ayıklayıcı desteği özellikleri sağlayabilir <xref:Microsoft.VisualStudio.TextManager.Interop.IVsLanguageDebugInfo> arabirimi. Kesme noktaları doğrulama ve ifadeleri için listesini sağladığı bu özellikleri **otomobiller** penceresi.  
  
 Ancak, dilinizi hata ayıklamak için bir ifade değerlendiricisi olması gerekir. İfade değerlendirici, hata ayıklama sırasında değeri oluşturmak üzere ifadeleri değerlendirme için sorumludur. CLR ifade değerlendiricisi uygulama hakkında daha fazla bilgi için lütfen bkz.  
  
-   [CLR ifade değerlendiricisi](https://github.com/Microsoft/ConcordExtensibilitySamples/wiki/CLR-Expression-Evaluators)  
  
-   [Yönetilen ifade değerlendiricisi örnek](https://github.com/Microsoft/ConcordExtensibilitySamples/wiki/Managed-Expression-Evaluator-Sample)  
  
## <a name="compiler-output"></a>Derleyici çıktısı  
 Diliniz için hata ayıklama uygulamak için yapmanız gerekenler derleyici türünü belirler. Windows işletim sistemini hedefleyen ve .pdb dosyasını yazar, derleyici, Visual Studio'ya tümleşik altyapısı hata ayıklama yerel kod ile programları ayıklayabilirsiniz. Derleyici Microsoft Ara dili (MSIL) oluşturursa, Visual Studio'ya Ayrıca tümleşik altyapısı hata ayıklama yönetilen kod ile programları ayıklayabilirsiniz. Derleyici, özel bir işletim sistemi veya farklı bir çalışma zamanı ortamı hedefliyorsa, hata ayıklama altyapınız yazmanız gerekir.  
  
 Diliniz için hata ayıklama uygulama ile ilgili daha fazla bilgi için bkz: [Başlarken](../../extensibility/debugger/getting-started-with-debugger-extensibility.md) hata ayıklama Visual Studio SDK.