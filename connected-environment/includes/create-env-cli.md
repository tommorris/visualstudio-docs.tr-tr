---
ms.topic: include
ms.openlocfilehash: 97f9885780c9f697cfc6a58b78054761fdcd725d
ms.sourcegitcommit: 928885ace538bef5b25961358d4f166d648f196a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/27/2018
---
## <a name="create-a-kubernetes-development-environment-in-azure"></a>Kubernetes geliştirme ortamı oluşturma
Bağlı bir ortam tamamen Azure tarafından yönetilen ve geliştirme için optimize edilmiş Kubernetes tabanlı ortamları oluşturabilirsiniz. Komut adlı bir ortam oluşturur `mydevenvironment` içinde `eastus`.
```cmd
vsce env create --name mydevenvironment --location eastus
```

Desteklenen konumlar: `eastus`, `westeurope`

> [!Note]
> Bu komut, yaklaşık 6 dakika sürer. Bu kılavuz bekleme olmadan devam edebilirsiniz.
