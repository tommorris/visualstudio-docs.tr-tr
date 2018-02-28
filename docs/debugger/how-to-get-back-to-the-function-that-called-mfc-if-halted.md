---
title: "Nasıl yapılır: durdurulduysa MFC'yi çağıran işleve geri alma | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- vs.debug.mfc
dev_langs:
- CSharp
- VB
- FSharp
- C++
helpviewer_keywords:
- functions [C++], debugging
- function calls, returning to calling function
- debugging [MFC], returning to calling function
- debugging [MFC], functions
- Break command
- programs, halting
- functions [debugger]
ms.assetid: d254a5a9-afbd-4923-9d7a-7422d824cabf
caps.latest.revision: 
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.workload:
- multiple
ms.openlocfilehash: 22ca8a71327f4d561d8fef2c0e2d6cbf82cd9061
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-get-back-to-the-function-that-called-mfc-if-halted"></a>Nasıl Yapılır: Durdurulduysa MFC'yi Çağıran İşleve Geri Dönme
> [!NOTE]
>  Gördüğünüz iletişim kutuları ve menü komutları, etkin ayarlarınıza ve ürün sürümüne bağlı olarak Yardım menüsünde açıklanana göre farklılık gösterebilir. Ayarlarınızı değiştirmek için Araçlar menüsünden içeri ve dışarı aktarma ayarları seçin. Daha fazla bilgi için bkz: [Visual Studio IDE'yi kişiselleştirme](../ide/personalizing-the-visual-studio-ide.md).  
  
 Kullandıysanız **bölün** komutunu **hata ayıklama** programı durdurmak için menü MFC'de sonuçlandı ve sorun olduğundan, kodunuzda emin işlevinizi geri gitmek için çağrı yığını penceresini kullanabilirsiniz. Daha fazla bilgi için bkz: [nasıl yapılır: çağrı yığını penceresinde kullanmak](../debugger/how-to-use-the-call-stack-window.md).  
  
 Bazen kodunuzu içinde ileti Pompalama kesilebilir. Bu durumda, çağrı yığınındaki kullanıcı kodu yok. Bu sorunu önlemek için kesme noktaları (büyük olasılıkla ile koşullar ve isabet) yerine kullanabileceğiniz **bölün** komutu. Daha fazla bilgi için bkz: [kesme noktaları ve Tracepoints](http://msdn.microsoft.com/en-us/fe4eedc1-71aa-4928-962f-0912c334d583)).  
  
### <a name="to-navigate-to-the-function-from-which-mfc-was-called"></a>MFC çağrıldı işlevi gidin  
  
-   Kullanım **çağrı yığını** penceresi.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Yerel kod hata ayıklaması SSS](../debugger/debugging-native-code-faqs.md)   
 [Yerel kodda hata ayıklama](../debugger/debugging-native-code.md)