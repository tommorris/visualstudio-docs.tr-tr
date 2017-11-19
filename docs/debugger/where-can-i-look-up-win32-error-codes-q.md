---
title: "Win32 Hata Kodlarına Nereden Bakabilirim? | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: vc.errors
dev_langs:
- CSharp
- VB
- FSharp
- C++
helpviewer_keywords:
- error codes, Win32
- Win32, error codes
ms.assetid: 8fb4ff42-b8eb-4152-b49e-b802d194b05e
caps.latest.revision: "16"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 508b741dcac0662d41e58b37ecaf177a2245010f
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2017
---
# <a name="where-can-i-look-up-win32-error-codes"></a>Win32 Hata Kodlarına Nereden Bakabilirim?
WINERROR. Varsayılan sistem yüklemenizin INCLUDE dizininde H Win32 API işlevleri için hata kodu tanımlarını içerir.  
  
 Kodda yazarak bir hata kodunu bakabilirsiniz **izleme** penceresi veya **QuickWatch** iletişim kutusu. Örneğin:  
  
```  
0x80000004,hr  
```  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Yerel kod hata ayıklaması SSS](../debugger/debugging-native-code-faqs.md)   
 [Yerel kodda hata ayıklama](../debugger/debugging-native-code.md)