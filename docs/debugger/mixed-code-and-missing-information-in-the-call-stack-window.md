---
title: Kod ve eksik bilgiler çağrı yığını penceresinde karışık | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-debug
ms.topic: conceptual
dev_langs:
- CSharp
- VB
- FSharp
- C++
- JScript
- SQL
helpviewer_keywords:
- managed code, stepping
- Call Stack window, mixed-mode debugging
- Call Stack window, troubleshooting
- native frames
- managed call stacks
- mixed-mode debugging, call stack
- stepping, out of managed code
ms.assetid: dd628427-e8d6-4fc2-b524-9d6393ea5376
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 580fc3b87173a120480f708e8b349fbb6942bbdb
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/16/2018
---
# <a name="mixed-code-and-missing-information-in-the-call-stack-window"></a>Çağrı Yığını Penceresinde Karışık Kod ve Eksik Bilgiler
Çağrı yığınları yönetilen ve yerel kodu arasındaki farklar nedeniyle, hata ayıklayıcı kodu karışımı yazdığında tam çağrı yığını her zaman gösterilemiyor. Yerel kod yönetilen kod aradığında, aşağıdaki tutarsızlıklar karşılaşabilirsiniz **çağrı yığını** penceresi:  
  
-   Yönetilen kod yukarıda hemen yerel çerçeve eksik **çağrı yığını** penceresi. Daha fazla bilgi için bkz: [nasıl yapılır: yerel çerçeveler çağrı yığını penceresinde olmadığında yönetilen kodların dışına Adımlama](../debugger/how-to-step-out-of-managed-code-when-native-frames-are-missing-from-the-call-stack-window.md).  
  
-   Hata ayıklayıcı dışında başlatılan karışık mod uygulamaları için **çağrı yığını** pencere, yalnızca yönetilen kod görüntüleyebilir ve yerel çerçeveler hiçbiri görünür olacaktır.  
  
 Her iki durumda oldukça seyrek kullanılır. Yönetilen kod için en yerel çağrılarında çağrı yığınları doğru görünür.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Nasıl yapılır: çağrı yığını penceresini kullanma](../debugger/how-to-use-the-call-stack-window.md)