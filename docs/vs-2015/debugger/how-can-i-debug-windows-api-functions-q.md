---
title: Windows API İşlevlerinde Nasıl Hata Ayıklayabilirim? | Microsoft Docs
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
- vs.debug.api
dev_langs:
- FSharp
- VB
- CSharp
- C++
- C++
helpviewer_keywords:
- debugging [C++], Windows API functions
- NT symbols and debugging Windows API functions
- Windows API functions, debugging
- Windows API, debugging API functions
- APIs, debugging
ms.assetid: 7c126f57-62ab-4d94-9805-632d696ba1f0
caps.latest.revision: 23
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: c6b0f06ddaadef8f462b59c9f445a0ae02d0123e
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/22/2018
ms.locfileid: "42686429"
---
# <a name="how-can-i-debug-windows-api-functions"></a>Windows API İşlevlerinde Nasıl Hata Ayıklayabilirim?
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Bu konuda en son sürümünü şu yolda bulunabilir: [nasıl kaldırabilirim Windows API işlevlerinde hata ayıklama?](https://docs.microsoft.com/visualstudio/debugger/how-can-i-debug-windows-api-functions-q).  
  
NT sembolleri yüklü olan bir Windows API işlev hata ayıklamak istiyorsanız, aşağıdakileri yapmanız gerekir.  
  
### <a name="to-set-a-breakpoint-on-a-windows-api-function-with-nt-symbols-loaded"></a>NT sembolleri ile bir Windows API işlevi üzerinde bir kesme noktası ayarlamak için yüklendi  
  
-   İşlevin yer aldığı DLL adı ile birlikte bir işlev adı girin. 32-bit kod içinde düzenlenmiş formu işlev adını kullanın. Bir kesme noktası ayarlamak için **MessageBeep**, örneğin, aşağıdaki girmeniz gerekir.  
  
    ```  
    {,,USER32.DLL}_MessageBeep@4  
    ```  
  
     Düzenlenmiş adı almak için bkz: [düzenlenmiş adları görüntüleme](http://msdn.microsoft.com/en-us/f79e2717-a4db-4d12-a689-69830cce2be0).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Yerel kod hata ayıklaması SSS](../debugger/debugging-native-code-faqs.md)   
 [Yerel kodda hata ayıklama](../debugger/debugging-native-code.md)



