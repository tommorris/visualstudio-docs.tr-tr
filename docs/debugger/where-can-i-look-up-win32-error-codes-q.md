---
title: Win32 Hata Kodlarına Nereden Bakabilirim? | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology: vs-ide-debug
ms.topic: conceptual
f1_keywords:
- vc.errors
dev_langs:
- CSharp
- VB
- FSharp
- C++
helpviewer_keywords:
- error codes, Win32
- Win32, error codes
ms.assetid: 8fb4ff42-b8eb-4152-b49e-b802d194b05e
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 81d919733f1caf654460cf342da05f2549dfa167
ms.sourcegitcommit: 3d10b93eb5b326639f3e5c19b9e6a8d1ba078de1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/18/2018
ms.locfileid: "31476217"
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