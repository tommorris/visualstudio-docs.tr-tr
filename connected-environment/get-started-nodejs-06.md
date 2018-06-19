---
title: Bulut - adım 6 - Kubernetes kullanarak kapsayıcıları ile bir Node.js geliştirme ortamı oluşturmak team geliştirme hakkında bilgi edinin | Microsoft Docs
author: ghogen
ms.author: ghogen
ms.date: 02/20/2018
ms.topic: tutorial
ms.prod: visual-studio-dev15
ms.technology: vs-azure
description: Kapsayıcılar ve Azure üzerinde mikro ile hızlı Kubernetes geliştirme
keywords: Docker, Kubernetes, Azure, AKS, Azure kapsayıcı hizmeti, kapsayıcıları
manager: douge
ms.openlocfilehash: 6a17dfc3eeebccf1508ea3f69aecb53d067de7af
ms.sourcegitcommit: e13e61ddea6032a8282abe16131d9e136a927984
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/26/2018
ms.locfileid: "31883585"
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

