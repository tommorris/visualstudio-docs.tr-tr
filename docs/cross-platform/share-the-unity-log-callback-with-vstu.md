---
title: "VSTU ile Unity günlük geri paylaşma | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-unity-tools
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 5d71f906-6e50-4399-b59b-d38c6dfef7ee
author: conceptdev
ms.author: crdun
manager: crdun
ms.workload:
- unity
ms.openlocfilehash: da0a8b98e358060cf11de87d9af2edf7e6b15f58
ms.sourcegitcommit: 8cbe6b38b810529a6c364d0f1918e5c71dee2c68
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/28/2018
---
# <a name="share-the-unity-log-callback-with-vstu"></a>VSTU ile Unity Günlük Geri Çağırması paylaşma
Unity için Visual Studio Araçları ile Visual Studio, konsola akış yapabilmek için Unity günlük geri çağırma kaydeder. Düzenleyicisi komut dosyalarınızı ayrıca ile Unity günlük geri çağırma kaydeder, VSTU geri çağırma ile geri etkileyebilir. Bu olasılığını önlemek için kullanmak `VisualStudioIntegration.LogCallback` olay VSTU ile işbirliği yapar.

## <a name="demonstrates"></a>Gösteriler
 Unity için Visual Studio Araçları tarafından oluşturulan Unity günlük geri nasıl.

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

## <a name="see-also"></a>Ayrıca Bkz.
 [Örnek: Proje dosyası oluşturma](../cross-platform/customize-project-files-created-by-vstu.md)
