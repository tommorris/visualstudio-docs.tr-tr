---
title: "VS Kabuk dağıtımı | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.topic: article
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload:
- multiple
ms.technology: vs-ide-modeling
ms.openlocfilehash: eb5446c8c3090624f327c234a1b518dc1928b6c9
ms.sourcegitcommit: 205d15f4558315e585c67f33d5335d5b41d0fcea
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/09/2018
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