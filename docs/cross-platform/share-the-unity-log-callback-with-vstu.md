---
title: VSTU ile Unity günlük geri çağırması paylaşma | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology: vs-unity-tools
ms.topic: conceptual
ms.assetid: 5d71f906-6e50-4399-b59b-d38c6dfef7ee
author: conceptdev
ms.author: crdun
manager: crdun
ms.workload:
- unity
ms.openlocfilehash: 817bc7b53c9b8e9579e46158cfbc04b7cbcbdee1
ms.sourcegitcommit: 71b307ce86c4079cc7ad686d8d5f96a6a123aadd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/25/2018
ms.locfileid: "39252218"
---
# <a name="share-the-unity-log-callback-with-vstu"></a>VSTU ile Unity günlük geri çağırması paylaşma
Unity için Visual Studio Araçları ile Visual Studio, konsola akışını yapabilmek için Unity günlük geri çağırma kaydeder. Düzenleyici betiklerinizi Unity ile aynı zamanda günlük geri kaydolursanız, geri çağırma işleminizi VSTU geri çağırma etkileyebilir. Bu olasılığını önlemek için `VisualStudioIntegration.LogCallback` VSTU ile işbirliği yapmayı olay.

## <a name="demonstrates"></a>Gösteriler
 Unity için Visual Studio Araçları tarafından oluşturulan Unity günlük geri çağırması paylaşma yapma.

## <a name="example"></a>Örnek

```csharp
using System;

using UnityEngine;
using UnityEditor;

using SyntaxTree.VisualStudio.Unity.Bridge;

[InitializeOnLoad]
public class LogCallbackHook
{
    static LogCallbackHook()
    {
        VisualStudioIntegration.LogCallback += (string condition, string trace, LogType type) =>
        {
            // place code that implements your log callback here
        };
    }
}
```

## <a name="see-also"></a>Ayrıca bkz.
 [Örnek: Proje dosyası oluşturma](../cross-platform/customize-project-files-created-by-vstu.md)
