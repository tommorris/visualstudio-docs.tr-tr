---
title: .NET Core geliştirme ortamı Kubernetes - adım 6 - bulutta kullanarak kapsayıcıları oluşturmak team geliştirme hakkında bilgi edinin | Microsoft Docs
author: ghogen
ms.author: ghogen
ms.date: 02/20/2018
ms.topic: tutorial
ms.prod: visual-studio-dev15
ms.technology: vs-azure
description: Kapsayıcılar ve Azure üzerinde mikro ile hızlı Kubernetes geliştirme
keywords: Docker, Kubernetes, Azure, AKS, Azure kapsayıcı hizmeti, kapsayıcıları
manager: douge
ms.openlocfilehash: 4da5051b760a12f8fd8837072ada44c8c5a9b239
ms.sourcegitcommit: e13e61ddea6032a8282abe16131d9e136a927984
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/26/2018
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
