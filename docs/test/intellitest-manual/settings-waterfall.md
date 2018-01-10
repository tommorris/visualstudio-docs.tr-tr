---
title: "Ayarları waterfall | Microsoft Intellitest Geliştirici Test aracı | Microsoft Docs"
ms.custom: 
ms.date: 05/02/2017
ms.reviewer: 
ms.suite: 
ms.technology: vs-devops-test
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: IntelliTest, Settings waterfall
ms.author: gewarren
manager: ghogen
ms.workload: multiple
author: gewarren
ms.openlocfilehash: b782987dd3bf1b96c063d43d80634289e5165af7
ms.sourcegitcommit: 7ae502c5767a34dc35e760ff02032f4902c7c02b
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/09/2018
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
