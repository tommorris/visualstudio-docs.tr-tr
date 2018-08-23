---
title: .NET Framework uzantılarını kaydetme | Microsoft Docs
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- Add References dialog box, registering extensions of the .NET Framework
- MSBuild, registering extensions of the .NET Framework
- .NET Framework extensions, registering
ms.assetid: deee6f53-ea87-4b88-a120-bea589822e03
caps.latest.revision: 8
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 2a2d3e281562be5234e0a70a877a6c169c346995
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/22/2018
ms.locfileid: "42674968"
---
# <a name="registering-extensions-of-the-net-framework"></a>.NET Framework Uzantılarını Kaydetme
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Bu konuda en son sürümünü şu yolda bulunabilir: [.NET Framework uzantılarını kaydetme](https://docs.microsoft.com/visualstudio/msbuild/registering-extensions-of-the-dotnet-framework).  
  
  
Belirli bir .NET Framework sürümünü genişleten bir derleme geliştirebilirsiniz. Visual Studio'da görüntülenecek derleme etkinleştirmek için **Add References** iletişim kutusu, sistem kayıt defterine içeren klasöre eklemeniz gerekir.  
  
 Örneğin, Trey Research şirket .NET Framework 4 genişletir ve Kütüphane derlemelerini görünmesini istediği bir kitaplığı geliştirmiştir varsayın **Add References** iletişim kutusuna bir proje .NET Framework 4 hedefliyor. Ayrıca derlemelerin 32 bit bilgisayar veya 64 bit bilgisayarda çalışan 64-bit derlemeler üzerinde çalışan 32 bit derlemeleri olduğundan ve bunların C:\TreyResearch\Extensions4\ klasörüne yükleneceğini varsayılır.  
  
 Bu klasör, bu anahtarı kullanarak kaydedin: HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\\. NETFramework\v4.0.21006\AssemblyFoldersEx\TreyResearch\\. Bu varsayılan değerin anahtarı ayarlayın: C:\TreyResearch\Extensions4.  
  
> [!NOTE]
>  .NET Framework sürümünün derleme numarası farklı olabilir.  
  
 Bir 64 bit bilgisayarda 32 bit derleme kaydetmek için Wow6432 düğümü, örneğin kullanın: HKEY_LOCAL_MACHINE\SOFTWARE\Wow6432Node\Microsoft\\. NETFramework\v4.0.21006\AssemblyFoldersEx\TreyResearch\\.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Visual Studio tümleştirmesi](../msbuild/visual-studio-integration-msbuild.md)



