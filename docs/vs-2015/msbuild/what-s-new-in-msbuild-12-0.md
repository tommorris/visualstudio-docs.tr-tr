---
title: Hangi&#39;s MSBuild 12.0'deki yenilikler | Microsoft Docs
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 9976a6ad-c052-4017-b848-35b5ae4a2f66
caps.latest.revision: 26
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: d91ec9044461cf57bba8bb36a0d2e029635155c5
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/22/2018
ms.locfileid: "42693104"
---
# <a name="what39s-new-in-msbuild-120"></a>Hangi&#39;s MSBuild 12.0'deki yenilikler
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Bu konuda en son sürümünü şu yolda bulunabilir: [Visual Studio 2017 belgeleri](https://docs.microsoft.com/visualstudio/).  
  
MSBuild artık .NET Framework'ün bir parçası olarak değil, Visual Studio'nun bir parçası olarak yüklenir. Geçerli MSBuild sürümü numarası 12.0 ' dir. MSBuild ayrı olarak yüklemek istiyorsanız, yükleme paketinden indirme [MSBuild indirme](http://go.microsoft.com/fwlink/?LinkId=309745).  
  
## <a name="changed-path"></a>Değiştirilen yolu  
 MSBuild doğrudan altında artık yüklüdür *% ProgramFiles %*— Örneğin, C:\Program Files\MSBuild içinde\\.  
  
## <a name="changed-properties"></a>Özellikleri değiştirilmiş  
 Aşağıdaki MSBuild özellikleri, yeni bir sürüm numarası sonucu olarak değiştirilir:  
  
-   `MSBuildToolsVersion` Bu araçlar için 12.0 sürümüdür.  
  
-   `MSBuildToolsPath` 32 bit işletim sistemlerinde %ProgramFiles%\MSBuild\12.0\bin veya %ProgramFiles%\MSBuild\12.0\bin\amd64 64-bit işletim sistemlerinde sunulmuştur.  
  
-   `ToolsVersion` değerleri, 32-bit işletim sistemleri için HKLM\SOFTWARE\Microsoft\MSBuild\ToolsVersions\12.0 ya da 64-bit işletim sistemleri için HKLM\SOFTWARE\Wow6432Node\Microsoft\MSBuild\ToolsVersions\12.0 bulunabilir.  
  
-   `SDK35ToolsPath` Ve `SDK40ToolsPath` noktası özelliklerini (örneğin, 8 4.X araçları için.1a) Visual Studio'nun bu sürümü ile paketlenmiştir .NET Framework SDK'sına.  
  
## <a name="new-properties"></a>Yeni Özellikler  
  
-   `MSBuildFrameworkToolsPath` 32 bit işletim sistemlerinde %windir%\Microsoft.NET\Framework\v4.0.30319 veya 64-bit işletim sistemlerinde %windir%\Microsoft.NET\Framework64\v4.0.30319 değerini içeren yeni bir özelliktir. Bu bir ardılı olan `MSBuildToolsPath` .NET Framework Araçları ve yardımcı programları işaret edecek şekilde kullanılabilir.  
  
-   `MSBuildToolsPath` ve `MSBuildFrameworkToolsPath` 32-bit eşdeğerleri —`MSBuildToolsPath32` ve `MSBuildFrameworkToolsPath32`— her zaman noktasında 32 bit veya 64-bit MSBuild kullanılıp kullanılmadığı bağımsız olarak 32-bit konumuna.

## <a name="see-also"></a>Ayrıca Bkz.
[MSBuild](msbuild.md)


