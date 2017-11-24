---
title: "Proje ve çözüm özelliklerini yönetme | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-general
ms.tgt_pltfrm: 
ms.topic: article
caps.latest.revision: "6"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: d9242bf08b879e415af658696b2be75a55dc5075
ms.sourcegitcommit: eb954434c34b4df6fd2264266381b23ce9e6204a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/22/2017
---
# <a name="managing-project-and-solution-properties"></a>Proje ve Çözüm Özelliklerini Yönetme

Projeleri hata ayıklama, test etme ve dağıtma derleme pek çok görünüşünün yöneten özelliklere sahiptir. Bazı özellikler tüm proje türleri arasında ortak olan ve bazı belirli diller veya platformlar için benzersizdir. Çözüm Gezgini'nde proje düğümüne sağ tıklayıp seçerek proje özelliklerini erişim **özellikleri**, veya özelliklerini yazarak **hızlı başlatma** menü çubuğunda arama kutusu.

![Proje bağlam menüsü](../ide/media/vs2015_proj_prop_menu.gif "vs2015_proj_prop_menu")

.NET projeleri proje ağacı kendisini özellikleri düğümünü sahip olabilir.

![Çözüm Gezgini ağacının özellikleri düğümünde](../ide/media/vs2015_props_se.png "VS2015_Props_SE")

> [!TIP]
> Çözümleri birkaç özelliklere sahip ve bu nedenle öğeleri proje; Bu özellikleri erişilir [Özellikler penceresini](../ide/reference/properties-window.md)değil **Proje Tasarımcısı**.

## <a name="project-properties"></a>Proje Özellikleri

Proje Özellikleri gruplar halinde düzenlenir ve her grubun kendi özellik sayfası vardır ve sayfalar farklı diller ve proje türleri için farklı olabilir.

### <a name="c-visual-basic-and-f-projects"></a>C#, Visual Basic ve Visual F # projeleri

C#, Visual Basic ve F # projelerinde özellikler de sağlanmaktadır **Proje Tasarımcısı**. Aşağıdaki çizimde bir WPF projesi derleme özellik sayfasında C# dilinde gösterir:

![Visual Studio Proje Tasarımcısı](../ide/media/vs2015_proppage_build.png "VS2015_PropPage_Build")

Her bir Proje Tasarımcısı'nda özellik sayfaları hakkında daha fazla bilgi için bkz: [proje özellikleri başvurusu](../ide/reference/project-properties-reference.md).

### <a name="c-and-javascript-projects"></a>C++ ve JavaScript projeleri

C++ ve JavaScript projeleri proje özelliklerini yönetmek için farklı kullanıcı arabirimi sahiptir. Bu çizimde C++ projesi özellik sayfası gösterilir (JavaScript sayfaları benzer):

![Visual C# 43; &#43; Proje Özellikleri](../ide/media/vs2015_projprops_cpp.png "VS2015_ProjProps_cpp")

C++ proje özellikleri hakkında daha fazla bilgi için bkz: [proje özellikleri (C++) ile çalışma](/cpp/ide/working-with-project-properties). JavaScript özellikleri hakkında daha fazla bilgi için bkz: [özellik sayfaları, JavaScript](../ide/reference/property-pages-javascript.md).

## <a name="solution-properties"></a>Çözüm özellikleri

Çözüm üzerinde özelliklere erişmek için sağ çözüm düğümünü tıklatın **Çözüm Gezgini** ve **özellikleri**. İletişim kutusunda, hata ayıklama için proje yapılandırmaları ayarlayabilirsiniz veya yayın oluşturur, F5 basılı ve kod çözümleme seçenekleri ayarladığınızda, projeleri başlangıç projesi olmalıdır'ı seçin.

## <a name="see-also"></a>Ayrıca bkz.

[Çözümler ve projeler Visual Studio'da](../ide/solutions-and-projects-in-visual-studio.md)
