---
title: Kendi İşaretçilerimin Bellek Adresini Bozup Bozmadığını Nasıl Anlarım? | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology: vs-ide-debug
ms.topic: conceptual
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
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 8965ec268e5d236b9a33e5c3e8acfa35e51dcdb3
ms.sourcegitcommit: 3d10b93eb5b326639f3e5c19b9e6a8d1ba078de1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/18/2018
ms.locfileid: "31479318"
---
# <a name="how-can-i-find-out-if-my-pointers-corrupt-a-memory-address"></a>Kendi İşaretçilerimin Bellek Adresini Bozup Bozmadığını Nasıl Anlarım?
## <a name="problem-description"></a>Sorun açıklaması  
 Kendi işaretçilerimin birini 0x00408000 adresindeki bellek bozulmasını, düşünüyorum. Nasıl bulabilirim çıkışı olanlar var?  
  
## <a name="solution"></a>Çözüm  
  
#### <a name="check-for-heap-corruption"></a>Yığın bozulması denetle  
  
-   Çoğu bellek gerçekten yığın bozulması nedeniyle bozulmasıdır. Genel bayraklar yardımcı programını (gflags.exe) veya pageheap.exe kullanmayı deneyin. Bkz: [ http://support.microsoft.com/default.aspx?scid=kb; en-us; 286470](http://support.microsoft.com/default.aspx?scid=kb;en-us;286470).  
  
#### <a name="to-find-where-the-memory-address-is-modified"></a>Bellek adresini değiştiren burada Bul  
  
1.  Veri kesme noktası 0x00408000 ayarlayın. Bkz: [veri değişikliği kesme noktası (yalnızca yerel C++'da) ayarlamak](../debugger/using-breakpoints.md#BKMK_set_a_data_breakpoint_native_cplusplus_only).  
  
2.  Kesme noktası isabet kullanırsanız **bellek** bellek görüntülemek için pencere içeriği 0x00408000 başlatılıyor. Daha fazla bilgi için bkz: [bellek Windows](../debugger/memory-windows.md).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Yerel kod hata ayıklaması SSS](../debugger/debugging-native-code-faqs.md)   
 [Yerel kodda hata ayıklama](../debugger/debugging-native-code.md)