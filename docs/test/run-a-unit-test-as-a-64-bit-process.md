---
title: "Visual Studio'da 64 bitlik bir işlem olarak birim testi çalıştırma | Microsoft Docs"
ms.date: 11/04/2016
ms.technology: vs-ide-test
ms.topic: article
helpviewer_keywords:
- unit tests, creating
- unit tests, running
ms.author: gewarren
manager: ghogen
ms.workload:
- multiple
author: gewarren
ms.openlocfilehash: fa7b467be269466170962944e9fbf8bd3a9889f0
ms.sourcegitcommit: 900ed1e299cd5bba56249cef8f5cf3981b10cb1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/19/2018
---
# <a name="run-a-unit-test-as-a-64-bit-process"></a>64 bitlik bir işlem olarak birim testi çalıştırma

Bir 64-bit makine varsa, birim testleri çalıştırma ve kod kapsamı bilgilerini 64 bitlik bir işlem olarak yakalayın.

## <a name="to-run-a-unit-test-as-a-64-bit-process"></a>64-bit işlem olarak birim testi çalıştırmak için

1. Kod ya da testler 32-bit/x86 derlendi ancak şimdi 64-bit işlem olarak çalıştırmak istiyorsanız, bunları yeniden derleyin **herhangi bir CPU**, veya isteğe bağlı olarak **64-bit**.

    > [!TIP]
    > Test projelerinizi maksimum esneklik için derleme **herhangi bir CPU** yapılandırma. Ardından, 32 bit ve 64-bit aracısında çalıştırabilirsiniz. Test projeleriyle derleme avantajlı yoktur **64-bit** yapılandırma.

2. Visual Studio menüsünden **Test**, ardından **ayarları**ve ardından **İşlemci mimarisi**. Seçin **x64** testleri 64-bit işlem olarak çalıştırmak için.

   - veya -

   Belirtin `<TargetPlatform>x64</TargetPlatform>` içinde bir *.runsettings* dosya. Bu yöntemin farklı dosyalarında ayar gruplarını belirtin ve hızlı bir şekilde farklı ayarlar arasında geçiş avantajlıdır. Ayrıca, ayarları çözümleri arasında kopyalayabilirsiniz. Daha fazla bilgi için bkz: [.runsettings dosyasını kullanarak birim testlerini yapılandırma](../test/configure-unit-tests-by-using-a-dot-runsettings-file.md).

## <a name="see-also"></a>Ayrıca bkz.

- [Test Gezgini ile birim testleri çalıştırma](../test/run-unit-tests-with-test-explorer.md)
- [Kodunuza Birim Testi Uygulama](../test/unit-test-your-code.md)
