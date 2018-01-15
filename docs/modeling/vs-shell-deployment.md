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
ms.openlocfilehash: cbd972609f06f9ce7d3a7745b33b8d0d78dcad2e
ms.sourcegitcommit: f89ed5fc2e5078213e30a6ade4604e34df48181f
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/13/2018
---
# <a name="vs-shell-deployment"></a>VS Shell dağıtımı
Yalıtılmış Kabuk hangi Visual Studio belirlemenize olanak tanır işlevselliği, etki alanına özgü dil ve bu çözümü nasıl görünmelidir etkileşime vermeniz gerekir. Yalıtılmış Visual Studio Kabuğu hakkında daha fazla bilgi için bkz: [yalıtılmış Kabuk özelleştirme](../extensibility/customizing-the-isolated-shell.md). Yalıtılmış Kabuk özelleştirme hakkında daha fazla bilgi bulabilirsiniz [yalıtılmış Kabuk özelleştirme](http://msdn.microsoft.com/en-us/d75463cd-1155-42e4-8b7a-046ed6becbbf).  
  
### <a name="to-set-a-visual-studio-shell-as-the-deployment-target"></a>Visual Studio Kabuğu dağıtım hedefi olarak ayarlamak için  
  
1.  İçinde **DslPackage** proje, açık **source.extension.tt**.  
  
2.  Altında `<SupportedProducts>` Ekle:  
  
    ```  
    <IsolatedShell Version="1.0">MyIsolatedShell</IsolatedShell>  
    ```  
  
     Değiştir *MyIsolatedShell* yalıtılmış Kabuk paketinizi adı.