---
title: Bir geliştirme ortamı paylaşma | Microsoft Docs
author: johnsta
ms.author: johnsta
ms.date: 3/12/2018
ms.topic: article
ms.technology: vsce-kubernetes
description: Kapsayıcılar ve Azure üzerinde mikro ile hızlı Kubernetes geliştirme
keywords: Docker, Kubernetes, Azure, AKS, Azure kapsayıcı hizmeti, kapsayıcıları
manager: ghogen
ms.openlocfilehash: 9808e1ac3a6d7b3381b807bc0ce209e15f3e97cf
ms.sourcegitcommit: e01ccb5ca4504a327d54f33589911f5d8be9c35c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/15/2018
---
# <a name="share-a-development-environment"></a>Bir geliştirme ortamı paylaşma

Bağlı bir ortam geliştirme ortamınızı başkalarıyla takımınızdaki paylaşabilirsiniz. Her geliştirici, kendi alanda başkalarının parçalamak, korkusu olmadan çalışabilir. Ayrıca, bir ortamda birlikte çalışmak, kod uçtan uca mocks oluşturmak veya bağımlılıkları benzetimini yapmak zorunda kalmadan test etmek etkinleştirebilirsiniz. Bkz: [takım geliştirme hakkında daha fazla bilgi](../get-started-nodejs-06.md) daha fazla bilgi için Kılavuzu.

Birden çok geliştiriciler için bir ortamı ayarlamak için:
1. [Bağlı bir ortam oluşturma](../get-started.md). Seçili Azure aboneliğinin sahibi veya katkıda erişiminizin olması gerekir.
1. Ortam yapılandırma **kaynak grubu** için [katkıda bulunan erişim](https://docs.microsoft.com/en-us/azure/active-directory/role-based-access-control-configure) her ekip üyesi için. Bir ortam kaynak grubu, şu komutu çalıştırarak denetleyebilirsiniz: `vsce env list`
1. Takım üyeleri için sorun **ortamı seçin** içinde geliştirmek için.
     * **Komut satırı veya VS Code**: Varolan bağlı ortamları görmek için erişiminiz: `vsce env list`. Bir ortam seçmek için: `vsce env select`.
     * **Visual Studio IDE**: Visual Studio'da seçin bir projeyi açın **bağlı ortam AKS için** öğesinden başlatma ayarları açılır. Açılan iletişim kutusunda, varolan bir geliştirme ortamı seçin.

![Visual Studio başlatma ayarları açılır](../images/LaunchSettings.png)