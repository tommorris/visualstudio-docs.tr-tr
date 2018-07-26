---
title: VSTU tarafından oluşturulan proje dosyalarını özelleştirme | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology: vs-unity-tools
ms.topic: conceptual
ms.assetid: 60b8cc1d-cacc-404d-b768-77e81bc354f8
author: conceptdev
ms.author: crdun
manager: crdun
ms.workload:
- unity
ms.openlocfilehash: 274b23eef51bfa86e961a850de7d4c33c217995c
ms.sourcegitcommit: 71b307ce86c4079cc7ad686d8d5f96a6a123aadd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/25/2018
ms.locfileid: "39252342"
---
# <a name="customize-project-files-created-by-vstu"></a>VSTU tarafından oluşturulan proje dosyalarını özelleştirme
Unity için Visual Studio Araçları proje dosyası oluşturma sırasında bir Unity stili geri çağırma sağlar. Kaydolmalı `VisualStudioIntegration.ProjectFileGeneration` yeniden oluşturuldu her proje dosyasını değiştirmek için olay.

## <a name="demonstrates"></a>Gösteriler
 Unity için Visual Studio Araçları tarafından oluşturulan Visual Studio proje dosyalarını özelleştirme yapma.

## <a name="example"></a>Örnek

```csharp
using System;
using System.IO;
using System.Linq;
using System.Text;
using System.Xml.Linq;

using UnityEngine;
using UnityEditor;

using SyntaxTree.VisualStudio.Unity.Bridge;

[InitializeOnLoad]
public class ProjectFileHook
{
    // necessary for XLinq to save the xml project file in utf8
    class Utf8StringWriter : StringWriter
    {
        public override Encoding Encoding
        {
            get { return Encoding.UTF8; }
        }
    }

    static ProjectFileHook()
    {
        ProjectFilesGenerator.ProjectFileGeneration += (string name, string content) =>
        {
            // parse the document and make some changes
            var document = XDocument.Parse(content);
            document.Root.Add(new XComment("FIX ME"));

            // save the changes using the Utf8StringWriter
            var str = new Utf8StringWriter();
            document.Save(str);

            return str.ToString();
        };
    }
}
```

## <a name="see-also"></a>Ayrıca bkz.
 [Örnek: Günlük geri çağırma](../cross-platform/share-the-unity-log-callback-with-vstu.md)
