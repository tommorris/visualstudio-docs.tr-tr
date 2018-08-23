---
title: Görev açıklamaları
description: Kodunuza Görev açıklamalarını ekleme
author: conceptdev
ms.author: crdun
ms.date: 05/06/2018
ms.assetid: 562DCB46-D8FA-4DC4-AAEA-F274448C4CD2
ms.openlocfilehash: 44d82becfbf3a16ccd2158ac05e171e8530cd721
ms.sourcegitcommit: 2597236a481afbaf1ad4915743898ee1aee49760
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/10/2018
ms.locfileid: "42624426"
---
# <a name="task-comments"></a>Görev açıklamaları

Kod yazarken, tamamlanmamış veya şüpheli kod veya uyarılar ile Hızlı çözümler açıkça açıklama standart bir uygulamadır. Mac için Visual Studio tarafından sağlanan varsayılan sinyal TODO, HACK, FIXME ve UNDONE belirteçleridir. Kişiselleştirilmiş belirteçleri altında tanımlanabilir **Visual Studio > tercihleri... > ortam > görevleri**aşağıdaki görüntüde gösterildiği gibi:

 ![Görev listesi tercihleri](media/source-editor-image10.png)

Yeni görev açıklama eklemek için görev anahtar sözcüğü içeren bir açıklama ekleyin. Örneğin:

```csharp
//TODO: Finish this for all properties.
```

Mac için Visual Studio bu işaretleyicileri dikkat giderek görüntülenebilen görev listesi paneli vurgulayarak çizer **Görüntüle > doldurmalar > görev**:

![Görev listesi paneli](media/source-editor-image11.png)