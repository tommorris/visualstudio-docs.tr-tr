---
title: "Kendi Programımı Hata Ayıklayıcı Dışında Çalıştırırken Erişim İhlallerinde Nasıl Hata Ayıklayabilirim? | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: vs.debug.access
dev_langs:
- CSharp
- VB
- FSharp
- C++
helpviewer_keywords:
- access violation debugging
- debugging [Visual Studio], access violations
ms.assetid: 780a298a-132e-4245-8370-8c82ca27c6c1
caps.latest.revision: "19"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: d1b8a6e019725f95788b4988fbe1ddef18cb27cc
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2017
---
# <a name="how-can-i-debug-access-violations-when-running-my-program-outside-the-debugger"></a>Kendi Programımı Hata Ayıklayıcı Dışında Çalıştırırken Erişim İhlallerinde Nasıl Hata Ayıklayabilirim?
## <a name="problem-description"></a>Sorun açıklaması  
 Kendi programımı Visual Studio ortamında düzgün çalışıyor ancak ı tek başına Windows işletim sistemiyle çalıştırdığınızda, bir erişim ihlali üretir. Bu sorunu nasıl hata ayıklayabilirim?  
  
## <a name="solution"></a>Çözüm  
 Ayarlama [sadece zamanında hata ayıklama](../debugger/just-in-time-debugging-in-visual-studio.md) seçeneği ve erişim ihlali gerçekleşene kadar programınızı tek başına çalıştırın. Ardından **erişim ihlali** iletişim kutusunu tıklatabilirsiniz **iptal** hata ayıklayıcısını başlatın.  
  
 Ayrıca bkz. Bilgi Bankası makalesi Q133174, "Genel koruma (GP) arıza oluştuğu bulun nasıl." Bilgi Bankası makalelerini MSDN Kitaplığı CD'sindeki veya arayarak bulabilirsiniz [http://support.microsoft.com/](http://support.microsoft.com/).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Yerel kod hata ayıklaması SSS](../debugger/debugging-native-code-faqs.md)   
 [Yerel kodda hata ayıklama](../debugger/debugging-native-code.md)