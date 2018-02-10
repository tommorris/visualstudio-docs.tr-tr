---
title: '&#39; teki MSBuild 15''deki yenilikler | Microsoft Docs'
ms.custom: 
ms.date: 03/01/2017
ms.reviewer: 
ms.suite: 
ms.technology: msbuild
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 9976b6fd-d052-4017-b848-35b5bf4b2f66
caps.latest.revision: 
author: Mikejo5000
ms.author: mikejo
manager: ghogen
ms.workload:
- multiple
ms.openlocfilehash: 19b7c821f708267d4827d06858b63128ce747ac3
ms.sourcegitcommit: 205d15f4558315e585c67f33d5335d5b41d0fcea
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/09/2018
---
# <a name="whats-new-in-msbuild-15"></a>MSBuild 15 yenilikler nelerdir?
MSBuild kullanılabilir olarak şimdi parçası [.NET Core SDK](https://www.microsoft.com/net/download/core) ve .NET Core projelerde Windows, macOS ve Linux oluşturabilirsiniz.  

## <a name="changed-path"></a>Değiştirilen yolu
 MSBuild, şimdi her sürümü Visual Studio'nun altında bir klasöre yüklenir. Örneğin, `C:\Program Files (x86)\Microsoft Visual Studio\2017\Enterprise\MSBuild`. MSBuild bulmak için aşağıdaki PowerShell modülünü de kullanabilirsiniz: [vssetup.powershell](https://github.com/Microsoft/vssetup.powershell).

 MSBuild artık Genel Derleme Önbelleği'nde yüklenir. MSBuild programlı olarak başvurmak için NuGet paketlerini kullanın.

## <a name="changed-properties"></a>Değiştirilen Özellikler  
 Aşağıdaki MSBuild özellikleri nedeniyle yeni sürüm numarasını güncelleştirildi.  

-   `MSBuildToolsVersion`Bu araçlar için 15.0 sürümüdür. Derleme 15.1.0.0 sürümüdür.

-   `MSBuildToolsPath`artık bir sabit konumu yok. Varsayılan olarak, Visual Studio yükleme konumuna göre MSBuild\15.0\Bin klasöründe bulunan, ancak yükleme konumu adresindeki değiştirilebilir Visual Studio yükleme süresi.

-   `ToolsVersion`değerleri, kayıt defterinde artık ayarlanır.  

-   `SDK35ToolsPath` Ve `SDK40ToolsPath` noktası özelliklerini (örneğin, 10.0A 4.X araçları için) Visual Studio'nun bu sürümü ile paketlenmiştir .NET Framework SDK'sının.  

## <a name="updates"></a>Güncelleştirmeler
- [Proje öğesi](../msbuild/project-element-msbuild.md) yeni bir sahip `SDK` özniteliği. Ayrıca `Xmlns` özniteliktir artık isteğe bağlı.
- [Madde öğesi](../msbuild/item-element-msbuild.md) dış hedefleri olan yeni bir `Update` özniteliği. Ayrıca, bir sınırlama `Remove` özniteliği ortadan kaldırılmıştır.
- `Directory.Build.props`bir dizini altındaki projelerine özelleştirmeleri sağlayan bir kullanıcı tarafından tanımlanan dosyasıdır. Bu dosya sürece Microsoft.Common.props otomatik olarak içeri aktarılır özelliği `ImportDirectoryBuildTargets` ayarlanır **false**. `Directory.Build.targets`Microsoft.Common.targets tarafından alınır.
- Herhangi bir meta veri öznitelikleri geçerli listesiyle çakışan olmayan bir ad ile isteğe bağlı olarak bir özniteliği olarak ifade edilebilir. Daha fazla bilgi için bkz: [öğe unsuru](../msbuild/item-element-msbuild.md).

## <a name="new-property-functions"></a>Yeni özellik işlevleri

- `EnsureTrailingSlash`zaten yoksa eğik bir yolu ekler.
- `NormalizePath`yol öğeleri birleştirir ve çıkış dizesi geçerli işletim sistemi için doğru dizin ayırıcı karakteri sahip olmasını sağlar.
- `NormalizeDirectory`yol öğelerini bir araya getirir, eğik sağlar ve çıkış dizesi geçerli işletim sistemi için doğru dizin ayırıcı karakteri sahip olmasını sağlar.
- `GetPathOfFileAbove`Bunu hemen önceki dosyasının yolunu döndürür. Arama için işlevsel olarak eşdeğerdir`<Import Project="$([MSBuild]::GetDirectoryNameOfFileAbove($(MSBuildThisFileDirectory), dir.props))\dir.props" />`

## <a name="see-also"></a>Ayrıca Bkz.
[MSBuild](../msbuild/msbuild.md)
