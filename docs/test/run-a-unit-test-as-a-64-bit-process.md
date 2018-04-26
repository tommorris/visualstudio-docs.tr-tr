---
title: Visual Studio'da 64 bitlik bir işlem olarak birim testi çalıştırma
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
ms.technology: vs-ide-test
ms.topic: conceptual
helpviewer_keywords:
- unit tests, creating
- unit tests, running
ms.author: gewarren
manager: douge
ms.workload:
- multiple
author: gewarren
ms.openlocfilehash: 2b6e44ae9b0587a044cb1a8a0d62db068dfc76d6
ms.sourcegitcommit: e13e61ddea6032a8282abe16131d9e136a927984
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/26/2018
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
