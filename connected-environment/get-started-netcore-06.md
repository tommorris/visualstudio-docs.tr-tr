---
title: .NET Core geliştirme ortamı Kubernetes - adım 6 - bulutta kullanarak kapsayıcıları oluşturmak team geliştirme hakkında bilgi edinin | Microsoft Docs
author: johnsta
ms.author: johnsta
ms.date: 02/20/2018
ms.topic: get-started-article
ms.technology: vsce-kubernetes
description: Kapsayıcılar ve Azure üzerinde mikro ile hızlı Kubernetes geliştirme
keywords: Docker, Kubernetes, Azure, AKS, Azure kapsayıcı hizmeti, kapsayıcıları
manager: ghogen
ms.openlocfilehash: 80e02e6ce1299278ba1abf530f38cb10b9f36c51
ms.sourcegitcommit: 900ed1e299cd5bba56249cef8f5cf3981b10cb1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/19/2018
---
# <a name="get-started-on-connected-environment-with-net-core"></a>.NET Core bağlı ortamıyla kullanmaya başlama

Önceki adımda: [başka bir kapsayıcı çağırın](get-started-netcore-05.md)

[!INCLUDE[](includes/team-development-1.md)]

Şimdi eylemde bakın:
1. VS Code penceresine gidin `mywebapi` ve düzenlemek için bir kod `string Get(int id)` yöntemi, örneğin:

```csharp
[HttpGet("{id}")]
public string Get(int id)
{
    return "mywebapi now says something new";
}
```

[!INCLUDE[](includes/team-development-2.md)]

> [!div class="nextstepaction"]
> [Next](get-started-netcore-07.md)
