---
title: VSTU ile Unity günlük geri çağırması paylaşma | Microsoft Docs
ms.custom: ''
ms.date: 07/26/2018
ms.technology: vs-unity-tools
ms.topic: conceptual
ms.assetid: 5d71f906-6e50-4399-b59b-d38c6dfef7ee
author: conceptdev
ms.author: crdun
manager: crdun
ms.workload:
- unity
ms.openlocfilehash: 3bf25ed2764078f2d3e0424ab34f4e4a8e470ff5
ms.sourcegitcommit: e6ef03cc415ca67f75fd1f26e0e7b8846857166d
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/27/2018
ms.locfileid: "39310026"
---
# <a name="share-the-unity-log-callback-with-vstu"></a>VSTU ile Unity günlük geri çağırması paylaşma
Unity için Visual Studio Araçları ile Visual Studio, konsola akışını yapabilmek için Unity günlük geri çağırma kaydeder. Düzenleyici betiklerinizi Unity ile aynı zamanda günlük geri kaydolursanız, geri çağırma işleminizi VSTU geri çağırma etkileyebilir. Bu olasılığını önlemek için `VisualStudioIntegration.LogCallback` VSTU ile işbirliği yapmayı olay.

## <a name="demonstrates"></a>Gösteriler
 Unity için Visual Studio Araçları tarafından oluşturulan Unity günlük geri çağırması paylaşma yapma.

## <a name="example"></a>Örnek

```csharp
#if ENABLE_VSTU
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
#endif
```

## <a name="see-also"></a>Ayrıca bkz.
 [Örnek: Proje dosyası oluşturma](../cross-platform/customize-project-files-created-by-vstu.md)
