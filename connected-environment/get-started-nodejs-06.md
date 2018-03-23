---
title: Bulut - adım 6 - Kubernetes kullanarak kapsayıcıları ile bir Node.js geliştirme ortamı oluşturmak team geliştirme hakkında bilgi edinin | Microsoft Docs
author: johnsta
ms.author: johnsta
ms.date: 02/20/2018
ms.topic: get-started-article
ms.technology: vsce-kubernetes
description: Kapsayıcılar ve Azure üzerinde mikro ile hızlı Kubernetes geliştirme
keywords: Docker, Kubernetes, Azure, AKS, Azure kapsayıcı hizmeti, kapsayıcıları
manager: ghogen
ms.openlocfilehash: 4db1d71c96da29a06884e562a277a7ca427910d4
ms.sourcegitcommit: 900ed1e299cd5bba56249cef8f5cf3981b10cb1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/19/2018
---
# <a name="get-started-on-connected-environment-with-nodejs"></a>Node.js ile bağlı ortam kullanmaya başlama

Önceki adımda: [ayrı bir kapsayıcıda çalışan bir hizmete çağrı](get-started-nodejs-05.md)

[!INCLUDE[](includes/team-development-1.md)]

Şimdi eylemde bakın:
1. VS Code penceresine gidin `mywebapi` ve varsayılan GET Düzenle Kodu'nu `/` işleyici, örneğin:

```javascript
app.get('/', function (req, res) {
    res.send('mywebapi now says something new');
});
```

[!INCLUDE[](includes/team-development-2.md)]

> [!div class="nextstepaction"]
> [Next](get-started-nodejs-07.md)

