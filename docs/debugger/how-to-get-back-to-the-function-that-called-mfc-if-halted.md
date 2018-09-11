---
title: "Nasıl yapılır: durdurulduysa MFC'yi çağıran işleve geri dönmek | Microsoft Docs"
ms.custom: ''
ms.date: 11/04/2016
ms.technology: vs-ide-debug
ms.topic: conceptual
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
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: da15793027eb643078771d33464258fea73fec9d
ms.sourcegitcommit: 1ab675a872848c81a44d6b4bd3a49958fe673c56
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/10/2018
ms.locfileid: "44283398"
---
# <a name="how-to-get-back-to-the-function-that-called-mfc-if-halted"></a>Nasıl Yapılır: Durdurulduysa MFC'yi Çağıran İşleve Geri Dönme
> [!NOTE]
>  Gördüğünüz iletişim kutuları ve menü komutları, etkin ayarlarınıza ve ürün sürümüne bağlı olarak Yardım menüsünde açıklanana göre farklılık gösterebilir. Ayarlarınızı değiştirmek için Araçlar menüsünden içeri ve dışarı aktarma ayarları seçin. Daha fazla bilgi için [Visual Studio IDE'yi kişiselleştirme](../ide/personalizing-the-visual-studio-ide.md).  
  
 Kullandıysanız **sonu** komutunu **hata ayıklama** programı durdurmak için menü MFC'de sonuçlandı ve sorunu kodunuzda olduğundan eminseniz işlevinize geri gitmek için çağrı yığını penceresini kullanabilirsiniz. Daha fazla bilgi için [nasıl yapılır: çağrı yığını penceresinde kullanmak](../debugger/how-to-use-the-call-stack-window.md).  
  
 Bazen, kodunuzun içinde ileti pompası kesilebilir. Bu durumda, çağrı yığınındaki kullanıcı kodu yok. Bu sorunu önlemek için kesme noktaları (büyük olasılıkla ile koşullar ve isabet sayıları) yerine kullanabileceğiniz **sonu** komutu. Daha fazla bilgi için [kesme noktaları ve izleme noktaları](https://msdn.microsoft.com/library/fe4eedc1-71aa-4928-962f-0912c334d583).  
  
### <a name="to-navigate-to-the-function-from-which-mfc-was-called"></a>MFC çağrıldı işleve gidin  
  
-   Kullanım **çağrı yığını** penceresi.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Yerel kod hata ayıklaması SSS](../debugger/debugging-native-code-faqs.md)   
 [Yerel Kodda Hata Ayıklama](../debugger/debugging-native-code.md)