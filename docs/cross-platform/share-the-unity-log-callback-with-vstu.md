---
title: "VSTU ile Unity günlük geri paylaşma | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: tgt-pltfrm-cross-plat
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 5d71f906-6e50-4399-b59b-d38c6dfef7ee
caps.latest.revision: "2"
author: conceptdev
ms.author: crdun
manager: crdun
ms.openlocfilehash: 7aae3c7bc11cdde209ef4d663793f25fa1e9e67e
ms.sourcegitcommit: 5f5587a1bcf4aae995c80d54a67b4b461f8695f3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/29/2017
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
