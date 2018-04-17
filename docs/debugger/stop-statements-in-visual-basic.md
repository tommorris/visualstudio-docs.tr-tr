---
title: Stop deyimleri Visual Basic'te | Microsoft Docs
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
helpviewer_keywords:
- End statements
- breakpoints, Stop statements
- debugging managed code, Stop statements vs breakpoints
- Stop statements, about Stop statements
- debugging [Visual Basic], Stop statements vs. breakpoints
ms.assetid: 4ad3fe5c-3dfb-4913-b2eb-a0b635751c18
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 81cec4d677ef6b88774b172ee63c0142b286a2c6
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/16/2018
---
# <a name="stop-statements-in-visual-basic"></a>Visual Basic'de Durdur Deyimleri
Visual Basic Stop deyimi bir kesme noktası ayarlama için programlı bir alternatif sunar. Hata ayıklayıcı Stop deyimi karşılaştığında (kesme moduna girer) programın yürütülmesini keser. C# programcıları System.Diagnostics.Debugger.Break yapılan bir çağrı kullanılarak aynı sonucu elde edebilirsiniz.  
  
 Ayarlayın veya kaynak kodu düzenleyerek Stop deyimi kaldırın. Ayarlayın veya bir kesme noktası gibi hata ayıklayıcı komutlarını kullanarak Stop deyimleri temizleyin.  
  
 End deyimi, Stop ifadesi olmayan değişkenleri sıfırlama veya tasarım moduna geri. Uygulama çalıştırmaya devam etmek için hata ayıklama menüsünden devam seçebilirsiniz.  
  
 Visual Basic uygulamasında hata ayıklayıcı dışında çalıştırdıktan hemen zamanında, hata ayıklayıcı Stop deyimi başlatacak hata ayıklama etkinleştirilir. Zaman içinde sadece, hata ayıklama etkin değil, Stop deyimi yürütmeyi sonlandırma bir End deyimi değilmiş gibi davranır. Visual Basic uygulamasında yayın sürümüne ait tüm Stop deyimleri kaldırmanız gerekir böylece hiçbir QueryUnload veya Unload olayı oluşur. Daha fazla bilgi için bkz: [Just-In-Time hata ayıklama](../debugger/just-in-time-debugging-in-visual-studio.md).  
  
 Stop deyimleri kaldırmanın gerekliliğini önlemek için koşullu derleme kullanabilirsiniz:  
  
```  
#If DEBUG Then  
   Stop  
#Else  
   ' Don't stop  
#End If  
```  
  
 Başka bir alternatif bir onay deyimi yerine Stop deyimi kullanmaktır. Debug.Assert deyimi yürütme keser. yalnızca belirli bir koşul karşılanmamıştır ve yayın sürümünü oluşturduğunuzda otomatik olarak kaldırılır. Daha fazla bilgi için bkz: [yönetilen koddaki onaylar](../debugger/assertions-in-managed-code.md). Hata ayıklama sürümü her zaman yürütme keser bir onay deyimi istiyorsanız, bunu yapabilirsiniz:  
  
```  
Debug.Assert(false)  
```  
  
 Henüz başka bir alternatif Debug.Fail yöntemini kullanmaktır:  
  
```  
Debug.Fail("a clever output string goes here")  
```  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Hata ayıklama güvenliği](../debugger/debugger-security.md)   
 [C#, F # ve Visual Basic proje türleri](../debugger/debugging-preparation-csharp-f-hash-and-visual-basic-project-types.md)   
 [Yönetilen kodda hata ayıklama](../debugger/debugging-managed-code.md)