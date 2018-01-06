---
title: "CRT hata ayıklama teknikleri | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: c.runtime.debugging
dev_langs:
- CSharp
- VB
- FSharp
- C++
helpviewer_keywords:
- debugging [CRT]
- CRT, debugging
- debugging [C++], CRT debug support
ms.assetid: 9be561f6-14a8-44ff-925d-d911d5b8e6ff
caps.latest.revision: "20"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.workload: multiple
ms.openlocfilehash: 52f1847112741e90634ce0e68acbcfdd11b837db
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/22/2017
---
# <a name="crt-debugging-techniques"></a>CRT Hata Ayıklama Teknikleri
C çalışma zamanı kitaplığı kullanan bir program hata ayıklama, bu hata ayıklama teknikleri yararlı olabilir.  
  
## <a name="in-this-section"></a>Bu Bölümde  
 [CRT hata ayıklama kitaplığı kullanımı](../debugger/crt-debug-library-use.md)  
 C çalışma zamanı kitaplığı tarafından sağlanan hata ayıklama desteği açıklar ve araçlara erişmek için yönergeler sağlar.  
  
 [Raporlama makroları](../debugger/macros-for-reporting.md)  
 Hakkında bilgi sağlar **_RPTn** ve **_RPTFn** makroları (CRTDBG içinde tanımlanmıştır. Kullanımını Değiştir H) `printf` hata ayıklama için deyimleri.  
  
 [Yığın ayırma işlevleri sürümleri hata ayıklama](../debugger/debug-versions-of-heap-allocation-functions.md)  
 Yığın ayırma işlevleri dahil olmak üzere, özel hata ayıklama sürümleri açıklanır: CRT çağrıları, açıkça çağırma avantajlarını nasıl eşlendiğini dönüştürme, istemci bloktan ayırma ayrı türlerini ve tanımlama değil _ sonuçlarını izleme önleme HATA AYIKLAMA.  
  
 [CRT hata ayıklama öbeği ayrıntıları](../debugger/crt-debug-heap-details.md)  
 Bellek yönetimi ve hata ayıklama yığınını, blok türlerine bağlantılar kullanarak hata ayıklama yığınını, yığın durumu raporlama işlevleri ve yığın ayırma isteklerini izleme hata ayıklama yığınında sağlar.  
  
 [Hata ayıklama kanca işlevi yazma](../debugger/debug-hook-function-writing.md)  
 İstemci engelleme listeleri bağlantılar işlevleri, atama kanca işlevleri, ayırma kancaları ve CRT bellek ayırmaları ve kanca işlevlerini raporlama bağlayın.  
  
 [CRT kitaplığını kullanarak bellek sızıntılarını bulma](../debugger/finding-memory-leaks-using-the-crt-library.md)  
 Teknikleri algılama ve hata ayıklayıcısı ve C çalışma zamanı kitaplığını kullanarak bellek sızıntılarını yalıtma kapsar.  
  
## <a name="related-sections"></a>İlgili Bölümler  
 [Yerel kodda hata ayıklama](../debugger/debugging-native-code.md)  
 Bazı genel hata ayıklama sorunları ve C ve C++ uygulamaları için teknikleri açıklar.  
  
 [Hata ayıklama güvenliği](../debugger/debugger-security.md)  
 Daha güvenli hata ayıklama için öneriler sağlar.