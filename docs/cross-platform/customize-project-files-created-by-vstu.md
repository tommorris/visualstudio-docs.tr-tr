---
title: "VSTU tarafından oluşturulan proje dosyalarını özelleştirme | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-unity-tools
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 60b8cc1d-cacc-404d-b768-77e81bc354f8
author: conceptdev
ms.author: crdun
manager: crdun
ms.workload:
- unity
ms.openlocfilehash: d051210849f33794ace3aba9786bab3c0156fa74
ms.sourcegitcommit: 8cbe6b38b810529a6c364d0f1918e5c71dee2c68
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/28/2018
---
# <a name="customize-project-files-created-by-vstu"></a>VSTU Tarafından Oluşturulan Proje Dosyalarını Özelleştirme
Unity için Visual Studio Araçları Unity stili geri çağırma proje dosyası oluşturma sırasında sağlar. Kaydetme `VisualStudioIntegration.ProjectFileGeneration` yeniden oluşturulur her proje dosyasını değiştirmek için olay.

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

## <a name="see-also"></a>Ayrıca Bkz.
 [Örnek: Günlük geri çağırma](../cross-platform/share-the-unity-log-callback-with-vstu.md)
