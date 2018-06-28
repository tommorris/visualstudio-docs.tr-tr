---
title: Windows API İşlevlerinde Nasıl Hata Ayıklayabilirim? | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology: vs-ide-debug
ms.topic: conceptual
f1_keywords:
- vs.debug.api
dev_langs:
- CSharp
- VB
- FSharp
- C++
helpviewer_keywords:
- debugging [C++], Windows API functions
- NT symbols and debugging Windows API functions
- Windows API functions, debugging
- Windows API, debugging API functions
- APIs, debugging
ms.assetid: 7c126f57-62ab-4d94-9805-632d696ba1f0
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 042f243c0469b8b37e301cf5c9f2410cf201f7be
ms.sourcegitcommit: 0bf2aff6abe485e3fe940f5344a62a885ad7f44e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/27/2018
ms.locfileid: "37058619"
---
# <a name="how-can-i-debug-windows-api-functions"></a>Windows API İşlevlerinde Nasıl Hata Ayıklayabilirim?
NT sembolleri yüklü olan bir Windows API işlev hata ayıklama istiyorsanız, aşağıdakileri yapmanız gerekir.  
  
### <a name="to-set-a-breakpoint-on-a-windows-api-function-with-nt-symbols-loaded"></a>NT sembolleri Windows API işleviyle bir kesme noktası ayarlamak için yüklendi  
  
-   İşlevin yer DLL adını birlikte işlev adını girin. 32 bit kod içinde işlev adı düzenlenmiş biçimini kullanın. Bir kesme noktası ayarlamak için **MessageBeep**, örneğin, aşağıdaki girmeniz gerekir.  
  
    ```cpp
    {,,USER32.DLL}_MessageBeep@4  
    ```  
  
     Düzenlenmiş adı almak için bkz: [donatılmış adları görüntüleme](http://msdn.microsoft.com/en-us/f79e2717-a4db-4d12-a689-69830cce2be0).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Yerel kod hata ayıklaması SSS](../debugger/debugging-native-code-faqs.md)   
 [Yerel kodda hata ayıklama](../debugger/debugging-native-code.md)
