---
title: DebugBreak ve __debugbreak | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- DebugBreak
dev_langs:
- CSharp
- VB
- FSharp
- C++
helpviewer_keywords:
- debugging [C++], DebugBreak function
- DebugBreak function
- breakpoints, DebugBreak function
ms.assetid: 9787c795-df94-4f48-bc8d-3bf899b67421
caps.latest.revision: 
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.workload:
- multiple
ms.openlocfilehash: 83128e4d5bd274013db1e7195e8182d021c257d5
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/22/2017
---
# <a name="debugbreak-and-debugbreak"></a>DebugBreak ve __debugbreak
DebugBreak Win32 işlevi çağırabilir veya [__debugbreak](/cpp/intrinsics/debugbreak) kodunuzda herhangi bir noktada iç. `DebugBreak`ve `__debugbreak` bu konumda bir kesme noktası ayarlama aynı etkiye sahiptir.  
  
 Çünkü `DebugBreak` sistem hata ayıklama simgeleri yüklü, doğru çağrı yığını bilgileri sonra kesme görüntülendiğinden emin olmak için bir sistem işlevi çağrısı. Aksi takdirde, hata ayıklayıcı tarafından görüntülenen çağrı yığını bilgileri kapalı bir çerçeve tarafından olabilir. Kullanırsanız `__debugbreak`, simgeler gerekli değildir.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Derleyici iç bilgileri](/cpp/intrinsics/compiler-intrinsics)   
 [Hata ayıklama güvenliği](../debugger/debugger-security.md)   
 [Yerel kodda hata ayıklama](../debugger/debugging-native-code.md)   
 [Simge (.pdb) belirtin ve kaynak dosyaları](../debugger/specify-symbol-dot-pdb-and-source-files-in-the-visual-studio-debugger.md)