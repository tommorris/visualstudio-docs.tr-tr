---
title: Visual Studio başlama süresi geliştirmek
ms.date: 11/15/2017
ms.topic: conceptual
helpviewer_keywords:
- startup time [Visual Studio]
- optimizing performance [Visual Studio]
- speed up start time [Visual Studio]
ms.assetid: d1508121-8499-4084-8eb5-fa89fa7b17d3
author: gewarren
ms.author: gewarren
manager: douge
f1_keywords:
- vs.performancecenter
ms.prod: visual-studio-dev15
ms.technology: vs-ide-general
ms.workload:
- multiple
ms.openlocfilehash: 451238283e5f256f9c7c302bd81dd45ad2825cf4
ms.sourcegitcommit: f685fa5e2df9dc307bf1230dd9dc3288aaa408b5
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/19/2018
ms.locfileid: "36233814"
---
# <a name="optimize-visual-studio-startup-time"></a>Visual Studio başlangıç zamanı en iyi duruma getirme

Visual Studio olabildiğince çabuk ve mümkün olduğunca verimli bir şekilde başlaması için tasarlanmıştır. Ancak, bazı Visual Studio uzantıları ve aracı windows yüklenen olduklarında başlangıç zamanını olumsuz etkileyebilir. Yavaş uzantıları davranışını denetlemek ve aracı windows **yönetmek Visual Studio performans** iletişim kutusu. Performansı artırma hakkında daha fazla genel ipuçları için bkz: [Visual Studio performans ipuçları ve püf noktaları](../ide/visual-studio-performance-tips-and-tricks.md).

## <a name="startup-behavior"></a>Başlangıç davranışı

Başlangıç zamanı genişletme önlemek için Visual Studio 2017 uzantılarını kullanarak yükleyen bir _isteğe bağlı_ yaklaşım. Bu davranış uzantıları hemen sonra Visual Studio başlar ancak gerektiği düzenli olarak açmayın anlamına gelir. Ayrıca, bir önceki Visual Studio oturumunda açık bırakılıp araç pencereleri başlangıç zamanını yavaşlatabileceği için Visual Studio araç pencereleri başlangıç zamanını etkileyen önlemek için daha akıllı bir şekilde açar.

Visual Studio yavaş başlatma algılarsa, yavaşlama neden olan uzantı veya aracı pencereyi uyarı bir açılır ileti görüntülenir. İleti bir bağlantı sağlar **yönetmek Visual Studio performans** iletişim kutusu. Bu iletişim kutusunu seçerek de erişebilirsiniz **yardımcı** > **yönetmek Visual Studio performans** menü çubuğundan.

![Visual Studio performans - açılan okuma Yönet ' uzantısı... farkettik Visual Studio'nun yavaşlamasının '](../ide/media/vside_perfdialog_popup.png)

İletişim kutusu başlatma performansını etkileyen uzantıları ve Araçlar windows listeler. Başlangıç performansını artırmak için uzantı ve aracı penceresi ayarlarını değiştirebilirsiniz.

## <a name="a-nameextensions-to-change-extension-settings-to-improve-startup-solution-load-and-typing-performance"></a><a name="extensions" />Başlangıç, çözüm yük ve performans yazarak geliştirmek için uzantı ayarları değiştirmek için

1. Açık **yönetmek Visual Studio performans** seçerek iletişim kutusu **yardımcı** > **yönetmek Visual Studio performans** menü çubuğundan.

    Uzantı çözüm yüklenirken, Visual Studio Başlangıç yavaşlamasını veya yazarak, uzantı görünür **yönetmek Visual Studio performans** iletişim kutusunda altında **uzantıları**  >   **Başlangıç** (veya **çözüm yük** veya **yazarak**).

    ![Visual Studio performans - uzantıları görünümü yönetme](../ide/media/vside_perfdialog_extensions.png)

2. Devre dışı bırakın ve ardından istediğiniz uzantı seçin **devre dışı** düğmesi.

Her zaman uzantısı sonraki oturumlar için kullanarak yeniden etkinleştirebilirsiniz **Uzantı Yöneticisi** veya **yönetmek Visual Studio performans** iletişim kutusu.

## <a name="a-nametool-windows-to-change-tool-window-settings-to-improve-startup-time"></a><a name="tool-windows" />Başlangıç zamanını geliştirmek için araç penceresi ayarlarını değiştirmek için

1. Açık **yönetmek Visual Studio performans** seçerek iletişim kutusu **yardımcı** > **yönetmek Visual Studio performans** menü çubuğundan.

    Araç penceresi Visual Studio Başlangıç yavaşlamasının araç penceresi görünür **yönetmek Visual Studio performans** iletişim kutusunda altında **aracı Windows** > **başlangıç**.

2. Davranışını değiştirmek istediğiniz araç penceresi seçin.

3. Aşağıdaki üç seçenekten birini seçin:

    - **Varsayılan davranışını kullanın:** araç penceresi için varsayılan davranış. Bu seçenek tutma başlangıç performansı iyileştirir değil.

    - **Pencere başlatma sırasında gösterme:** Visual Studio açtığınızda, önceki bir oturumda açık bırakılmış olsa bile belirtilen araç penceresi her zaman kapalı. İhtiyacınız olduğunda, araç penceresi uygun menüsünden açabilirsiniz.

    - **Başlangıçta otomatik gizle penceresi:** araç penceresi önceki bir oturumda açık bırakılırsa, bu seçenek araç penceresi başlatma önlemek için aracı pencerenin Grup başlangıçta daraltır. Araç penceresi sık kullanıyorsanız bu seçeneği iyi bir seçimdir. Araç penceresi hala kullanılabilir, ancak Visual Studio başlangıç zamanını artık olumsuz etkiler.

    ![Visual Studio performansını yönetme - aracı windows görüntüleyin](../ide/media/vside_perfdialog_toolwindows.png)

> [!NOTE]
> Visual Studio 2017 bazı eski sürümleri adlı bir özelliği olan **basit çözüm yük**. Bu özellik artık ve sonrasında 15,5 Visual Studio 2017 sürümde kullanılabilir değildir. Visual Studio 2017 içinde 15,5 ve sonraki sürümleri, içeren büyük çözümlerde kod yükü çok daha hızlı daha önce basit çözüm yükü olmadan bile yönetilen.

## <a name="see-also"></a>Ayrıca bkz.

- [Visual Studio performansı en iyi duruma getirme](../ide/optimize-visual-studio-performance.md)
- [Visual Studio performans ipuçları ve püf noktaları](../ide/visual-studio-performance-tips-and-tricks.md)
- [Visual Studio günlüğü - Visual Studio 2017 sürüm 15,6 daha hızlı yük çözümleri](https://blogs.msdn.microsoft.com/visualstudio/2018/04/04/load-solutions-faster-with-visual-studio-2017-version-15-6/)