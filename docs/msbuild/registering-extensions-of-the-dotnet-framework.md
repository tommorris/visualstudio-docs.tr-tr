---
title: .NET Framework uzantılarını kaydetme | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology: msbuild
ms.topic: conceptual
helpviewer_keywords:
- Add References dialog box, registering extensions of the .NET Framework
- MSBuild, registering extensions of the .NET Framework
- .NET Framework extensions, registering
ms.assetid: deee6f53-ea87-4b88-a120-bea589822e03
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- dotnet
ms.openlocfilehash: cad3d2d02ed27ab46410be6edc024b137bbca7bd
ms.sourcegitcommit: 42ea834b446ac65c679fa1043f853bea5f1c9c95
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/19/2018
ms.locfileid: "31579049"
---
# <a name="registering-extensions-of-the-net-framework"></a>.NET Framework Uzantılarını Kaydetme
Belirli bir .NET Framework sürümünü genişleten bir derlemeyi geliştirebilirsiniz. Visual Studio'da görünmesi derleme etkinleştirmek için **Başvuru Ekle** iletişim kutusu, sistem kayıt defterine içeren klasörü eklemeniz gerekir.  
  
 Örneğin, Trey Research şirket .NET Framework 4 genişleten ve görünmesi kitaplık derlemeleri istediği bir kitaplık geliştirmiştir varsayın **Başvuru Ekle** bir proje .NET Framework 4 hedeflediğinde iletişim kutusu. Ayrıca derlemeler 32 bit bir bilgisayar veya bir 64-bit bilgisayarda 64-bit derlemeleri üzerinde çalışan 32 bit derlemeleri olduğunu ve bunlar C:\TreyResearch\Extensions4\ klasöründe yüklenecek varsayalım.  
  
 Bu klasör, bu anahtarı kullanarak kaydedin: HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\\. NETFramework\v4.0.21006\AssemblyFoldersEx\TreyResearch\\. Bu varsayılan değeri anahtar verin: C:\TreyResearch\Extensions4.  
  
> [!NOTE]
>  .NET Framework sürümünün derleme numarası farklı olabilir.  
  
 Bir 64-bit bilgisayarda 32 bit derleme kaydetmek için Wow6432 düğümü, örneğin kullanın: HKEY_LOCAL_MACHINE\SOFTWARE\Wow6432Node\Microsoft\\. NETFramework\v4.0.21006\AssemblyFoldersEx\TreyResearch\\.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Visual Studio tümleştirmesi](../msbuild/visual-studio-integration-msbuild.md)