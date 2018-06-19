---
title: Görev açıklamaları
description: Kodunuzu görev açıklama ekleme
author: asb3993
ms.author: amburns
ms.date: 05/06/2018
ms.assetid: 562DCB46-D8FA-4DC4-AAEA-F274448C4CD2
ms.openlocfilehash: 23ce804476b6495d45e114728b287c1f5f85d1d9
ms.sourcegitcommit: 4c0db930d9d5d8b857d3baf2530ae89823799612
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/10/2018
ms.locfileid: "33956643"
---
# <a name="task-comments"></a>Görev açıklamaları

Kod yazarken, tamamlanmamış veya şüpheli kodu veya uyarılarla Hızlı çözümler açıkça açıklama standart bir uygulamadır. Mac için Visual Studio tarafından sağlanan varsayılan sinyal Yapılacaklar, KORSAN, FIXME ve UNDONE belirteçleridir. Kişiselleştirilmiş belirteçleri altında tanımlanabilir **Visual Studio > tercihleri... > ortamı > görevleri**aşağıdaki görüntüde gösterildiği gibi:

 ![Görev listesi tercihleri](media/source-editor-image10.png)

Yeni bir görev açıklama eklemek için görev anahtar sözcüğünü içeren bir açıklama ekleyin. Örneğin:

```csharp
//TODO: Finish this for all properties.
```

Mac için Visual Studio giderek görüntülenen görev listesi panelinde vurgulayarak bu işaretçileri dikkat çizer **Görünüm > klavye takımı > görev**:

![Görev listesi paneli](media/source-editor-image11.png)