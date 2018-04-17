---
title: Kendi Programımı Hata Ayıklayıcı Dışında Çalıştırırken Erişim İhlallerinde Nasıl Hata Ayıklayabilirim? | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-debug
ms.topic: conceptual
f1_keywords:
- vs.debug.access
dev_langs:
- CSharp
- VB
- FSharp
- C++
helpviewer_keywords:
- access violation debugging
- debugging [Visual Studio], access violations
ms.assetid: 780a298a-132e-4245-8370-8c82ca27c6c1
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 9f3e4a79ba90f887f11c3fd9a7bddf318ace35cc
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/16/2018
---
# <a name="how-can-i-debug-access-violations-when-running-my-program-outside-the-debugger"></a>Kendi Programımı Hata Ayıklayıcı Dışında Çalıştırırken Erişim İhlallerinde Nasıl Hata Ayıklayabilirim?
## <a name="problem-description"></a>Sorun açıklaması  
 Kendi programımı Visual Studio ortamında düzgün çalışıyor ancak ı tek başına Windows işletim sistemiyle çalıştırdığınızda, bir erişim ihlali üretir. Bu sorunu nasıl hata ayıklayabilirim?  
  
## <a name="solution"></a>Çözüm  
 Ayarlama [sadece zamanında hata ayıklama](../debugger/just-in-time-debugging-in-visual-studio.md) seçeneği ve erişim ihlali gerçekleşene kadar programınızı tek başına çalıştırın. Ardından **erişim ihlali** iletişim kutusunu tıklatabilirsiniz **iptal** hata ayıklayıcısını başlatın.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Yerel kod hata ayıklaması SSS](../debugger/debugging-native-code-faqs.md)   
 [Yerel kodda hata ayıklama](../debugger/debugging-native-code.md)