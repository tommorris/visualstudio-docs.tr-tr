---
title: VS Shell dağıtımı
ms.date: 11/04/2016
ms.topic: conceptual
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.technology: vs-ide-modeling
ms.openlocfilehash: 816997f971e90ddd27f8e24cdc1857559e04ff70
ms.sourcegitcommit: 4c0bc21d2ce2d8e6c9d3b149a7d95f0b4d5b3f85
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/20/2018
---
# <a name="vs-shell-deployment"></a>VS Shell dağıtımı

Yalıtılmış Kabuk hangi Visual Studio belirlemenize olanak tanır işlevselliği, etki alanına özgü dil ve bu çözümü nasıl görünmelidir etkileşime vermeniz gerekir. Yalıtılmış Visual Studio Kabuğu hakkında daha fazla bilgi için bkz: [yalıtılmış Kabuk özelleştirme](../extensibility/customizing-the-isolated-shell.md).

## <a name="to-set-a-visual-studio-shell-as-the-deployment-target"></a>Visual Studio Kabuğu dağıtım hedefi olarak ayarlamak için

1.  İçinde **DslPackage** proje, açık **source.extension.tt**.

2.  Altında `<SupportedProducts>` Ekle:

    ```
    <IsolatedShell Version="1.0">MyIsolatedShell</IsolatedShell>
    ```

     Değiştir *MyIsolatedShell* yalıtılmış Kabuk paketinizi adı.