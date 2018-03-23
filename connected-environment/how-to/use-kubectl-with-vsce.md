---
title: Bağlı bir ortamla kubectl kullanma | Microsoft Docs
author: johnsta
ms.author: johnsta
ms.date: 03/12/2018
ms.topic: article
ms.technology: vsce-kubernetes
description: Kapsayıcılar ve Azure üzerinde mikro ile hızlı Kubernetes geliştirme
keywords: Docker, Kubernetes, Azure, AKS, Azure kapsayıcı hizmeti, kapsayıcıları
manager: ghogen
ms.openlocfilehash: 46c69f80e58a4265aa5e4320e731c3ad241a8116
ms.sourcegitcommit: e01ccb5ca4504a327d54f33589911f5d8be9c35c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/15/2018
---
# <a name="use-kubectl-with-a-connected-environment"></a>Kullanım `kubectl` bağlı ortamı

Bağlı bir ortamda Kubernetes küme erişebilir ve varolan Kubernetes araçlarını kullanın ister `kubectl`.

Çalışan `vsce env create` veya `vsce env select` otomatik olarak ekleyecek bir `kubectl` , kubectl VSCE Kubernetes kümenize zaten bağlı olması böylece için yapılandırma bağlamı. Örnekler:
- Geçerli bağlam onaylayın: `kubectl config current-context`
- Tüm kullanılabilir bağlamları listesinde: `kubectl config get-contexts`. VSCE tarafından oluşturulan bir kubernetes küme aşağıdakine benzer olarak adlandırılacaktır "vsce -<guid>".
- Bağlam değiştirin: `kubectl config use-context <context-name>`
- Kubernetes Panoyu görebilmek: çalıştırmak `kubectl proxy`, ardından bu komut yayar adresine tarayıcınızı açın (append `/ui` Kubernetes panoya gitmek için URL).
- Çalışan hizmetleri adlı varsayılan VSCE alanı listesi *mainline*: `kubectl get services --namespace=mainline`

