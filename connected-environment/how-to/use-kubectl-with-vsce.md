---
title: Bağlı bir ortamla kubectl kullanma | Microsoft Docs
author: ghogen
ms.author: ghogen
ms.date: 03/12/2018
ms.topic: conceptual
ms.prod: visual-studio-dev15
ms.technology: vs-azure
description: Kapsayıcılar ve Azure üzerinde mikro ile hızlı Kubernetes geliştirme
keywords: Docker, Kubernetes, Azure, AKS, Azure kapsayıcı hizmeti, kapsayıcıları
manager: douge
ms.openlocfilehash: 138dce09e0d53dc47703b9c6f56a7efda4adc255
ms.sourcegitcommit: e13e61ddea6032a8282abe16131d9e136a927984
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/26/2018
ms.locfileid: "31883533"
---
# <a name="use-kubectl-with-a-connected-environment"></a>Kullanım `kubectl` bağlı ortamı

Bağlı bir ortamda Kubernetes küme erişebilir ve varolan Kubernetes araçlarını kullanın ister `kubectl`.

Çalışan `vsce env create` veya `vsce env select` otomatik olarak ekleyecek bir `kubectl` , kubectl VSCE Kubernetes kümenize zaten bağlı olması böylece için yapılandırma bağlamı. Örnekler:
- Geçerli bağlam onaylayın: `kubectl config current-context`
- Tüm kullanılabilir bağlamları listesinde: `kubectl config get-contexts`. VSCE tarafından oluşturulan bir kubernetes küme aşağıdakine benzer olarak adlandırılacaktır "vsce -<guid>".
- Bağlam değiştirin: `kubectl config use-context <context-name>`
- Kubernetes Panoyu görebilmek: çalıştırmak `kubectl proxy`, ardından bu komut yayar adresine tarayıcınızı açın (append `/ui` Kubernetes panoya gitmek için URL).
- Çalışan hizmetleri adlı varsayılan VSCE alanı listesi *mainline*: `kubectl get services --namespace=mainline`

