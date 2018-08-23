---
title: VS Shell dağıtımı | Microsoft Docs
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-tfs-dev14
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: be8f2ffe-a322-4ac0-9c9e-873bd28e5d5e
caps.latest.revision: 4
author: gewarren
ms.author: gewarren
manager: douge
ms.openlocfilehash: e1a1bd92d1a0b91aa01d940695cd780f7e63c098
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/22/2018
ms.locfileid: "42692841"
---
# <a name="vs-shell-deployment"></a>VS Shell dağıtımı
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Bu konuda en son sürümünü şu yolda bulunabilir: [VS Shell dağıtımı](https://docs.microsoft.com/visualstudio/modeling/vs-shell-deployment).  
  
Bir yalıtılmış Kabuk hangi Visual Studio belirlemenize olanak tanır işlevselliğe gereksinim, etki alanına özgü dil ve bu çözümü nasıl görüneceğini ile etkileşim kurmak. Visual Studio yalıtılmış Kabuk hakkında daha fazla bilgi için bkz. [yalıtılmış Kabuğu özelleştirme](../extensibility/customizing-the-isolated-shell.md). Yalıtılmış Kabuğu özelleştirme hakkında daha fazla bilgi bulabilirsiniz [yalıtılmış Kabuğu özelleştirme](http://msdn.microsoft.com/en-us/d75463cd-1155-42e4-8b7a-046ed6becbbf).  
  
### <a name="to-set-a-visual-studio-shell-as-the-deployment-target"></a>Bir Visual Studio Shell dağıtım hedefi olarak ayarlamak için  
  
1.  İçinde **DslPackage** projesini açarsanız **source.extension.tt**.  
  
2.  Altında `<SupportedProducts>` ekleyin:  
  
    ```  
    <IsolatedShell Version="1.0">MyIsolatedShell</IsolatedShell>  
    ```  
  
     Değiştirin *MyIsolatedShell* yalıtılmış Kabuk paketinizin ada sahip.



