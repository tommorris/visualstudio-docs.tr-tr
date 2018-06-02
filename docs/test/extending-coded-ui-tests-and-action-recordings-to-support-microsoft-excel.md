---
title: Kodlanmış UI testleri ve eylem kayıtları genişletme
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
ms.technology: vs-ide-test
ms.topic: conceptual
ms.author: gewarren
manager: douge
ms.workload:
- multiple
author: gewarren
ms.openlocfilehash: bc4e500c401c148f9eb01c1dedd56f89ba534df8
ms.sourcegitcommit: 0aafcfa08ef74f162af2e5079be77061d7885cac
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/01/2018
ms.locfileid: "34692063"
---
# <a name="extend-coded-ui-tests-and-action-recordings"></a>Kodlanmış UI testleri ve eylem kayıtları genişletme

Kodlanmış UI testleri ve eylem kayıtları için test çerçevesi her kullanıcı arabirimini desteklemiyor. Test etmek istediğiniz belirli kullanıcı Arabirimi desteklemiyor olabilir. Örneğin, hemen kodlanmış UI testi veya bir eylem için Microsoft Excel elektronik tablosu kaydı oluşturamazsınız. Ancak, kendi uzantısı kodlanmış UI test çerçevesi genişletilebilirlik yararlanarak belirli UI destekleyen kodlanmış UI test çerçevesi oluşturabilirsiniz.

![UI testi mimarisi](../test/media/ui_testarch.png)

## <a name="sample-extension-to-test-microsoft-excel"></a>Microsoft Excel test etmek için örnek uzantısı

Bu [blog gönderisi](https://blogs.msdn.microsoft.com/gautamg/2010/01/05/3-introducing-sample-excel-extension/) bir bağlantı içeren bir [örnek uzantısı](https://msdnshared.blob.core.windows.net/media/MSDNBlogsFS/prod.evol.blogs.msdn.com/CommunityServer.Components.PostAttachments/00/09/94/38/24/ExcelPluginSample.zip) kodlanmış UI test çerçevesi için. Ayrıca tüm görüntüleyebilirsiniz [blog gönderisine seri için kodlanmış UI test genişletilebilirlik](https://blogs.msdn.microsoft.com/gautamg/2010/01/05/series-on-coded-ui-test-extensibility/).

> [!NOTE]
> Örnek Microsoft Excel 2010 ile kullanılmak üzere tasarlanmıştır. Diğer Excel sürümleriyle çalışmayabilir veya olabilir.

## <a name="see-also"></a>Ayrıca bkz.

- <xref:Microsoft.VisualStudio.TestTools.UITesting.UITestPropertyProvider>
- <xref:Microsoft.VisualStudio.TestTools.UITest.Extension.UITechnologyElement>
- <xref:Microsoft.VisualStudio.TestTools.UITest.Common.UITestActionFilter>
- <xref:Microsoft.VisualStudio.TestTools.UITest.Extension.UITestExtensionPackage>
- [Kodunuzu Test Etmek için UI Otomasyonunu Kullanma](../test/use-ui-automation-to-test-your-code.md)
- [Kodlanmış UI Testleri için En İyi Yöntemler](../test/best-practices-for-coded-ui-tests.md)
- [Kodlanmış UI Testleri ve Eylem Kayıtları için Desteklenen Yapılandırmalar ve Platformlar](../test/supported-configurations-and-platforms-for-coded-ui-tests-and-action-recordings.md)