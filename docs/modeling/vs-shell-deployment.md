---
title: "VS Kabuk dağıtımı | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload: multiple
ms.openlocfilehash: 26b5075c36b152ecc44d65428521e191e6053609
ms.sourcegitcommit: 69b898d8d825c1a2d04777abf6d03e03fefcd6da
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/25/2018
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