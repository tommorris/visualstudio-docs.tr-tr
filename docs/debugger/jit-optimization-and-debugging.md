---
title: "JIT iyileştirmesi ve hata ayıklama | Microsoft Docs"
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
- debugging [Visual Studio], optimized code
- optimized code, debugging
ms.assetid: 19bfabf3-1a2e-49dc-8819-a813982e86fd
caps.latest.revision: "13"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.workload: multiple
ms.openlocfilehash: 2c3dcd57568bdfaac3ba0f7aff33cefca8a0ee32
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/22/2017
---
# <a name="jit-optimization-and-debugging"></a>JIT İyileştirmesi ve Hata Ayıklaması
Yönetilen bir uygulamanın hata ayıklamasını yaparken [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] iyileştirme tam zamanında (JIT) kodunun varsayılan olarak gizler. En iyi duruma getirme, JIT gizleme olmayan iyileştirilmiş kodda hata ayıklama anlamına gelir. Kod değil iyileştirilmiştir, ancak hata ayıklama deneyiminizi daha kapsamlı olduğundan biraz daha yavaş çalışır. İyileştirilmiş kodda hata ayıklama daha zor olduğu ve yalnızca en iyi duruma getirilmiş kodunda oluşan ancak iyileştirilmemiş sürümünde çoğaltılamayan hata karşılaşmanız halinde önerilir.  
  
 JIT iyileştirmesi denetlenir [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] tarafından **bastırmak JIT iyileştirmesi modülü yükü** seçeneği. Bu seçenek bulabilirsiniz **genel** altında sayfa **hata ayıklama** düğümünde **seçenekleri** iletişim kutusu.  
  
 Silerseniz **bastırmak JIT iyileştirmesi modülü yükü** seçeneği, en iyi duruma getirilmiş JIT kodda hata ayıklama, ancak en iyi duruma getirilmiş kod kaynak kodu eşleşmediği için hata ayıklama yeteneğinizi sınırlı olabilir. Sonuç olarak, windows gibi hata ayıklayıcı **Yereller** ve **otomobiller** penceresi olmayan iyileştirilmiş kodda hata ayıklama durumda kadar bilgi görüntülenmeyebilir.  
  
 Başka bir önemli fark sorunları sadece kendi kodumu ile hata ayıklama. Sadece kendi kodumu ile hata ayıklama, en iyi duruma getirilmiş kod hata ayıklarken görüntülenmemelidir kullanıcı olmayan kod, hata ayıklayıcı göz önünde bulundurur. Hata ayıklama en iyi duruma getirilmiş JIT kodu varsa, sonuç olarak, büyük olasılıkla sadece kendi kodumu kapatmak istediğiniz. Daha fazla bilgi için bkz: [sadece kendi kodumu atlama sınırla](../debugger/navigating-through-code-with-the-debugger.md#BKMK_Restrict_stepping_to_Just_My_Code).  
  
 Unutmayın **bastırmak JIT iyileştirmesi modülü yükü** seçeneği modülleri yüklendiğinde kodu en iyi duruma getirilmesi gizler. Zaten çalışan bir işlemin eklerseniz, zaten yüklü, JIT derlenmiş ve en iyi duruma getirilmiş kodu içerebilir. **Bastırmak JIT iyileştirmesi modülü yükü** seçeneği üzerinde etkisi yoktur bu kodların rağmen ekledikten sonra yüklenen modülleri etkiler. Ayrıca, **bastırmak JIT iyileştirmesi modülü yükü** seçeneği NGEN ile oluşturulan gibi modüller WinForms.dll, etkilemez.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Yönetilen kodda hata ayıklama](../debugger/debugging-managed-code.md)   
 [Hata ayıklayıcısı ile kodlarda gezinme](../debugger/navigating-through-code-with-the-debugger.md)   
 [Çalıştırma işlemine iliştirme](../debugger/attach-to-running-processes-with-the-visual-studio-debugger.md)   
 [Yönetilen Yürütme İşlemi](/dotnet/standard/managed-execution-process)