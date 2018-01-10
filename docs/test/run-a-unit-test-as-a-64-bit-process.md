---
title: "Bir 64-bit işlem olarak birim testi çalıştırma | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-devops-test
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- unit tests, creating
- unit tests, running
ms.author: gewarren
manager: ghogen
ms.workload: multiple
author: gewarren
ms.openlocfilehash: 36a33e9be37255e6bcf199e612a44f65ca243a1e
ms.sourcegitcommit: 7ae502c5767a34dc35e760ff02032f4902c7c02b
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/09/2018
---
# <a name="run-a-unit-test-as-a-64-bit-process"></a>64 bitlik bir işlem olarak birim testi çalıştırma
Bir 64-bit makine varsa, birim testleri çalıştırma ve kod kapsamı bilgilerini 64 bitlik bir işlem olarak yakalayın.  
  
## <a name="running-a-unit-test-as-a-64-bit-process"></a>Bir 64-bit işlem olarak birim testi çalıştırma  
  
#### <a name="to-run-a-unit-test-as-a-64-bit-process"></a>64-bit işlem olarak birim testi çalıştırmak için  
  
1.  Kod ya da testler 32-bit/x86 derlendi ancak şimdi 64-bit işlem olarak çalıştırmak istiyorsanız, bunları yeniden derleyin **herhangi bir CPU**, veya isteğe bağlı olarak **64-bit**.  
  
    > [!TIP]
    >  Maksimum esneklik için test projelerinizi derleme **herhangi bir CPU** yapılandırma. Ardından, 32 ve 64 bit aracıların çalıştırabilirsiniz. Test projeleriyle derleme avantajlı yoktur **64-bit** yapılandırma.  
  
2.  Visual Studio menüsünden **Test**, ardından **ayarları**ve ardından **İşlemci mimarisi**. Seçin **x64** testleri 64-bit işlem olarak çalıştırmak için.  
  
     \-veya -  
  
     Belirtin `<TargetPlatform>x64</TargetPlatform>` .runsettings dosyasını içinde. Bu yöntemin farklı dosyalarında ayar gruplarını belirtin ve hızlı bir şekilde farklı ayarlar arasında geçiş avantajlıdır. Ayrıca, ayarları çözümleri arasında kopyalayabilirsiniz. Daha fazla bilgi için bkz: [.runsettings dosyasını kullanarak birim testlerini yapılandırma](../test/configure-unit-tests-by-using-a-dot-runsettings-file.md).  
  
## <a name="see-also"></a>Ayrıca bkz.

[Test Gezgini ile birim testleri çalıştırma](../test/run-unit-tests-with-test-explorer.md)  
[Kodunuza Birim Testi Uygulama](../test/unit-test-your-code.md)  
