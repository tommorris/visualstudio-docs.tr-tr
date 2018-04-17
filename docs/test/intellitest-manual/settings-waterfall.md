---
title: Ayarları waterfall | Microsoft Intellitest Geliştirici Test aracı | Microsoft Docs
ms.date: 05/02/2017
ms.technology: vs-ide-test
ms.topic: conceptual
helpviewer_keywords:
- IntelliTest, Settings waterfall
ms.author: gewarren
manager: douge
ms.workload:
- multiple
author: gewarren
ms.openlocfilehash: 9265fd0ada4f966f5d5fba01591e10f5f0a4194f
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/16/2018
---
# <a name="settings-waterfall"></a>Ayarları waterfall

Kullanıcı ayarlarını belirtebilir ayarları waterfall kavramı anlamına gelir **derleme**, **donanımı** ve **araştırması** düzeyi: 

* Derleme - [PexAssemblySettings](attribute-glossary.md#pexassemblysettings)
* Donanımı - [PexClass](attribute-glossary.md#pexclass)
* Keşif - [PexExplorationAttributeBase](attribute-glossary.md#pexexplorationattributebase)

Konumunda belirtilen ayarları **derleme** düzeyi tüm Müştemilat ve bu derleme altında araştırması etkiler. Konumunda belirtilen ayarları **donanımı** düzeyi bu donanımı altındaki tüm explorations etkiler. Alt ayarları win: bir ayarı adresindeki tanımlanmışsa **derleme** ve **donanımı** düzeyleri, **donanımı** ayarları kullanılır.

Bazı ayarlar için belirli olduğuna dikkat edin **derleme** düzeyi veya **donanımı** düzeyi. 

**Örnek**

```
using Microsoft.Pex.Framework;

[assembly: PexAssemblySettings(MaxBranches = 1000)] // we override the default value of maxbranches

namespace MyTests
{
    [PexClass(MaxBranches = 500)] // we override the 1000 value and set maxbranches to 500 
    public partial class MyTests
    {
        [PexMethod(MaxBranches = 100)] // we override again, maxbranches = 100
        public void MyTest(...) { ... }
    }
}
```

## <a name="got-feedback"></a>Geri bildirim var mı?

Fikirlerinizi sonrası ve özellik istekleri  **[UserVoice](https://visualstudio.uservoice.com/forums/121579-visual-studio-2015/category/157869-test-tools?query=IntelliTest)**.
