---
title: VS Shell dağıtımı
ms.date: 11/04/2016
ms.topic: conceptual
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.prod: visual-studio-dev15
ms.technology: vs-ide-modeling
ms.openlocfilehash: e7df1991832e954def71a6cee5bd5516dfd4e961
ms.sourcegitcommit: e13e61ddea6032a8282abe16131d9e136a927984
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/26/2018
ms.locfileid: "31946994"
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