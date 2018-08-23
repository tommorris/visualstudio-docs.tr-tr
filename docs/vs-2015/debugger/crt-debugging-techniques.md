---
title: CRT hata ayıklama tekniklerine | Microsoft Docs
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-debug
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- c.runtime.debugging
dev_langs:
- FSharp
- VB
- CSharp
- C++
- C++
helpviewer_keywords:
- debugging [CRT]
- CRT, debugging
- debugging [C++], CRT debug support
ms.assetid: 9be561f6-14a8-44ff-925d-d911d5b8e6ff
caps.latest.revision: 23
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: d2743c7185f09f19353ca5fedab0327593dc33bb
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/22/2018
ms.locfileid: "42686349"
---
# <a name="crt-debugging-techniques"></a>CRT Hata Ayıklama Teknikleri
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Bu konuda en son sürümünü şu yolda bulunabilir: [CRT hata ayıklama teknikleri](https://docs.microsoft.com/visualstudio/debugger/crt-debugging-techniques).  
  
C çalışma zamanı kitaplığı kullanan bir programı hata ayıklaması yapıyorsanız, bu hata ayıklama teknikleri yararlı olabilir.  
  
## <a name="in-this-section"></a>Bu Bölümde  
 [CRT hata ayıklama kitaplığı kullanımı](../debugger/crt-debug-library-use.md)  
 C çalışma zamanı kitaplığı tarafından sağlanan hata ayıklama desteğini açıklar ve araçlara erişmek için yönergeler sağlar.  
  
 [Raporlama makroları](../debugger/macros-for-reporting.md)  
 Hakkında bilgi sağlar **_RPTn** ve **_RPTFn** makroları (CRTDBG içinde tanımlanır. Kullanımını değiştirin H) `printf` hata ayıklama için deyimleri.  
  
 [Yığın ayırma işlevleri hata ayıklama sürümleri](../debugger/debug-versions-of-heap-allocation-functions.md)  
 Yığın ayırma işlevleri dahil olmak üzere, özel hata ayıklama sürümlerini açıklar: CRT çağrıları, açıkça çağırma avantajları nasıl eşlendiğini nasıl önleneceğini dönüştürme, istemci bloklar ayırmaları ayrı türlerini ve tanımlamayarak _ sonuçlarını izleme HATA AYIKLAMA.  
  
 [CRT hata ayıklama öbeği ayrıntıları](../debugger/crt-debug-heap-details.md)  
 Bellek yönetimi ve hata ayıklama yığın, blok türlerine bağlantılar kullanarak hata ayıklama öbek, öbek durumu raporlama işlevleri ve yığın ayırma isteklerini izleme hata ayıklama yığınında sağlar.  
  
 [Hata ayıklama kanca işlevi yazma](../debugger/debug-hook-function-writing.md)  
 İstemci engelleme listeleri bağlantılar, İşlevler, atama kanca işlevleri, atama kancaları ve CRT bellek ayırmaları ve kanca işlevlerini raporlama bağlayın.  
  
 [CRT kitaplığını kullanarak bellek sızıntılarını bulma](../debugger/finding-memory-leaks-using-the-crt-library.md)  
 Algılama ve hata ayıklayıcı ve C çalışma zamanı kitaplığını kullanarak bellek sızıntılarını ayırma teknikleri kapsar.  
  
## <a name="related-sections"></a>İlgili Bölümler  
 [Yerel kodda hata ayıklama](../debugger/debugging-native-code.md)  
 Bazı yaygın hata ayıklama sorunları ve C ve C++ uygulamaları için teknikleri açıklar.  
  
 [Hata ayıklayıcısı güvenliği](../debugger/debugger-security.md)  
 Daha güvenli hata ayıklama için öneriler sağlar.



