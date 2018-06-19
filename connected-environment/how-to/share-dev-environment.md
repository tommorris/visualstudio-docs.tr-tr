---
title: Bir geliştirme ortamı paylaşma | Microsoft Docs
author: ghogen
ms.author: ghogen
ms.date: 3/12/2018
ms.topic: conceptual
ms.prod: visual-studio-dev15
ms.technology: vs-azure
description: Kapsayıcılar ve Azure üzerinde mikro ile hızlı Kubernetes geliştirme
keywords: Docker, Kubernetes, Azure, AKS, Azure kapsayıcı hizmeti, kapsayıcıları
manager: douge
ms.openlocfilehash: 43d23caa039340345372076d02b3c4989cde5b01
ms.sourcegitcommit: e13e61ddea6032a8282abe16131d9e136a927984
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/26/2018
ms.locfileid: "31883169"
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