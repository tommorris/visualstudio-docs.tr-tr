---
title: Proje ve çözüm özelliklerini yönetme
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
ms.technology: vs-ide-general
ms.topic: conceptual
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 96581fbaff9c2ddc85fbb92d73096f2a369d4c7b
ms.sourcegitcommit: 58052c29fc61c9a1ca55a64a63a7fdcde34668a4
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/04/2018
ms.locfileid: "34746318"
---
# <a name="manage-project-and-solution-properties"></a>Proje ve çözüm özelliklerini yönetme

Projeleri hata ayıklama, test etme ve dağıtma derleme pek çok görünüşünün yöneten özelliklere sahiptir. Bazı özellikler tüm proje türleri arasında ortak olan ve bazı belirli diller veya platformlar için benzersizdir. Proje Özellikleri'nde proje düğümüne sağ tıklayarak erişim **Çözüm Gezgini** ve seçme **özellikleri**, veya "Özellikler" içine yazarak **hızlı başlatma** Menü çubuğunda arama kutusu.

![Proje bağlam menüsü](../ide/media/vs2015_proj_prop_menu.gif)

.NET projeleri proje ağacı kendisini özellikleri düğümünü sahip olabilir.

![Çözüm Gezgini ağacındaki özellikler düğümü](../ide/media/vs2015_props_se.png)

## <a name="project-properties"></a>Proje Özellikleri

Proje Özellikleri gruplar halinde düzenlenir ve her grup kendi özellik sayfası içeriyor. Sayfaları farklı diller ve proje türleri için farklı olabilir.

### <a name="c-visual-basic-and-f-projects"></a>C#, Visual Basic ve Visual F # projeleri

C#, Visual Basic ve F # projelerinde özellikler de sağlanmaktadır **Proje Tasarımcısı**. Aşağıdaki çizimde gösterildiği **yapı** C# bir WPF projesi için özellik sayfası:

![Visual Studio Proje Tasarımcısı](../ide/media/vs2015_proppage_build.png)

Her bir özellik sayfaları hakkında bilgi için **Proje Tasarımcısı**, bkz: [proje özellikleri başvurusu](../ide/reference/project-properties-reference.md).

> [!TIP]
> Çözümleri birkaç özelliklere sahip ve bu nedenle öğeleri proje; Bu özellikleri erişilir [Özellikler penceresini](../ide/reference/properties-window.md)değil **Proje Tasarımcısı**.

### <a name="c-and-javascript-projects"></a>C++ ve JavaScript projeleri

C++ ve JavaScript projeleri proje özelliklerini yönetmek için farklı kullanıcı arabirimi sahiptir. Bu çizimde C++ projesi özellik sayfası gösterilir (JavaScript sayfaları benzer):

![Visual C&#43; &#43; proje özellikleri](../ide/media/vs2015_projprops_cpp.png)

C++ proje özellikleri hakkında daha fazla bilgi için bkz: [(C++) proje özellikleriyle çalışma](/cpp/ide/working-with-project-properties). JavaScript özellikleri hakkında daha fazla bilgi için bkz: [özellik sayfaları, JavaScript](../ide/reference/property-pages-javascript.md).

## <a name="solution-properties"></a>Çözüm özellikleri

Çözüm üzerinde özelliklere erişmek için sağ çözüm düğümünü tıklatın **Çözüm Gezgini** ve **özellikleri**. Proje yapılandırmaları için ayarlayabileceğiniz iletişim kutusunda, **hata ayıklama** veya **sürüm** derlemeleri, seçin başlangıç projeleri olmalıdır ne zaman proje **F5** basılı ve kod ayarlayın Çözümleme seçenekleri.

## <a name="see-also"></a>Ayrıca bkz.

- [Çözümler ve projeler Visual Studio'da](../ide/solutions-and-projects-in-visual-studio.md)
