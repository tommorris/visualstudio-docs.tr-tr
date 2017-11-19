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
ms.assetid: d23a9ee7-58e3-4e8b-a38c-b2207ea73fea
caps.latest.revision: "25"
ms.author: douge
manager: douge
ms.openlocfilehash: bb22521dc0c4f4a1a824c3554ce37297a61108c5
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2017
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
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Test Gezgini ile birim testleri çalıştırma](../test/run-unit-tests-with-test-explorer.md)   
 [Kodunuza birim testi](../test/unit-test-your-code.md)   
 [Visual Studio testleri için test ayarlarını belirtme](/devops-test-docs/test/specifying-test-settings-for-visual-studio-tests)
