---
title: "Kendi İşaretçilerimin Bellek Adresini Bozup Bozmadığını Nasıl Anlarım? | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- CSharp
- VB
- FSharp
- C++
helpviewer_keywords:
- addresses, pointers corrupting memory address
- memory, corruption
- pointers, corrupting memory addresses
- memory address corruption by pointers
- debugging [C++], memory corruption
- corrupted memory address
ms.assetid: a147c939-4fb1-415c-8410-cf303781e9e8
caps.latest.revision: "19"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 863acbf45268330e106360dd7778acab94b670de
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2017
---
# <a name="how-can-i-find-out-if-my-pointers-corrupt-a-memory-address"></a>Kendi İşaretçilerimin Bellek Adresini Bozup Bozmadığını Nasıl Anlarım?
## <a name="problem-description"></a>Sorun açıklaması  
 Kendi işaretçilerimin birini 0x00408000 adresindeki bellek bozulmasını, düşünüyorum. Nasıl bulabilirim çıkışı olanlar var?  
  
## <a name="solution"></a>Çözüm  
  
#### <a name="check-for-heap-corruption"></a>Yığın bozulması denetle  
  
-   Çoğu bellek gerçekten yığın bozulması nedeniyle bozulmasıdır. Genel bayraklar yardımcı programını (gflags.exe) veya pageheap.exe kullanmayı deneyin. Bkz: [http://support.microsoft.com/default.aspx?scid=kb;en-us;286470](http://support.microsoft.com/default.aspx?scid=kb;en-us;286470).  
  
#### <a name="to-find-where-the-memory-address-is-modified"></a>Bellek adresini değiştiren burada Bul  
  
1.  Veri kesme noktası 0x00408000 ayarlayın. Bkz: [veri değişikliği kesme noktası (yalnızca yerel C++'da) ayarlamak](../debugger/using-breakpoints.md#BKMK_set_a_data_breakpoint_native_cplusplus_only).  
  
2.  Kesme noktası isabet kullanırsanız **bellek** bellek görüntülemek için pencere içeriği 0x00408000 başlatılıyor. Daha fazla bilgi için bkz: [bellek Windows](../debugger/memory-windows.md).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Yerel kod hata ayıklaması SSS](../debugger/debugging-native-code-faqs.md)   
 [Yerel kodda hata ayıklama](../debugger/debugging-native-code.md)