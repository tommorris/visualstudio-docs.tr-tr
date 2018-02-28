---
title: "Nasıl yapılır: Püskürtülen kodda hata ayıklama | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- vs.debug.injected
dev_langs:
- CSharp
- VB
- FSharp
- C++
helpviewer_keywords:
- assembly language, viewing
- debugging [C++], viewing assembly code
- debugging [C++], injected code
- debugging [C++], enabling source annotation
- injected code
- Show Source Code command [debugger]
- debugging [C++], using attributes
- disassembly code, debugging
ms.assetid: a1b4104d-d49e-451f-a91e-e39ceaf35875
caps.latest.revision: 
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.workload:
- multiple
ms.openlocfilehash: 2c06209d2c2774eb12c0e04d8f448b8ceb2de771
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-debug-injected-code"></a>Nasıl Yapılır: Püskürtülen Kodda Hata Ayıklama
> [!NOTE]
>  Gördüğünüz iletişim kutuları ve menü komutları, etkin ayarlarınıza ve ürün sürümüne bağlı olarak Yardım menüsünde açıklanana göre farklılık gösterebilir. Ayarlarınızı değiştirmek için Araçlar menüsünden içeri ve dışarı aktarma ayarları seçin. Daha fazla bilgi için bkz: [Visual Studio IDE'yi kişiselleştirme](../ide/personalizing-the-visual-studio-ide.md).  
  
 Öznitelikleri kullanarak C++ programlama büyük ölçüde basitleştirebilir. Daha fazla bilgi için bkz: [kavramları](/cpp/windows/attributed-programming-concepts). Bazı öznitelikler doğrudan derleyici tarafından değerlendirilir. Diğer öznitelikleri kod derleyici sonra derler program kaynak yerleştirir. Bu eklenen kod yazmak zorunda kod miktarını azaltarak daha kolay programlama yapar. Bazı durumlarda, ancak bir hata, uygulamanızın eklenen kodu yürütülürken başarısız olmasına neden olabilir. Bu gerçekleştiğinde, eklenen koda bakın isteyeceksiniz. Visual Studio eklenen kodu görmek iki yol sunar:  
  
-   Eklenen kod içinde görüntüleyebilirsiniz **ayrıştırılmış** penceresi.  
  
-   Kullanarak [/Fx](/cpp/build/reference/fx-merge-injected-code), özgün ve eklenen kodu içeren bir birleştirilmiş kaynak dosyası oluşturabilirsiniz.  
  
 **Ayrıştırılmış** penceresi kaynak kodu ve öznitelikleri tarafından eklenen kodu karşılık assembly dili yönergeleri gösterir. Ayrıca, **ayrıştırılmış** penceresi, kaynak kodu ek açıklama gösterebilir.  
  
### <a name="to-turn-on-source-annotation"></a>Kaynak ek açıklamayı kapatmak için  
  
-   Sağ **ayrıştırılmış** penceresinde ve **kaynak kodu Göster** kısayol menüsünden.  
  
     Bir kaynak penceresinde bir öznitelik konumunu biliyorsanız, eklenen kodunda bulmak için kısayol menüsünü kullanabilirsiniz **ayrıştırılmış** penceresi.  
  
### <a name="to-view-injected-code"></a>Eklenen kod görüntülemek için  
  
1.  Hata ayıklayıcı kesme modunda olması gerekir.  
  
2.  Bir kaynak kod penceresinde imleci eklenen kod görüntülemek istediğiniz özniteliği önüne yerleştirin.  
  
3.  Sağ tıklatın ve seçin **ayrıştırılmış Git** kısayol menüsünden.  
  
     Öznitelik konumu geçerli yürütme noktası ise, seçebileceğiniz **ayrıştırılmış** penceresinden **hata ayıklama** menüsü.  
  
### <a name="to-view-the-disassembly-code-at-the-current-execution-point"></a>Ayrıştırılmış kod geçerli yürütme noktada görüntülemek için  
  
1.  Hata ayıklayıcı kesme modunda olması gerekir.  
  
2.  Gelen **hata ayıklama** menüsünde seçin **Windows**, tıklatıp **ayrıştırılmış**.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Hata ayıklama güvenliği](../debugger/debugger-security.md)   
 [Yerel kodda hata ayıklama](../debugger/debugging-native-code.md)