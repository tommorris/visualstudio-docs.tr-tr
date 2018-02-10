---
title: ".NET Framework uzantılarını kaydetme | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: msbuild
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Add References dialog box, registering extensions of the .NET Framework
- MSBuild, registering extensions of the .NET Framework
- .NET Framework extensions, registering
ms.assetid: deee6f53-ea87-4b88-a120-bea589822e03
caps.latest.revision: 
author: Mikejo5000
ms.author: mikejo
manager: ghogen
ms.workload:
- dotnet
ms.openlocfilehash: 495a6bb1d72e521b3f44ea989974446def555c15
ms.sourcegitcommit: 205d15f4558315e585c67f33d5335d5b41d0fcea
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/09/2018
---
# <a name="registering-extensions-of-the-net-framework"></a>.NET Framework Uzantılarını Kaydetme
Belirli bir .NET Framework sürümünü genişleten bir derlemeyi geliştirebilirsiniz. Visual Studio'da görünmesi derleme etkinleştirmek için **Başvuru Ekle** iletişim kutusu, sistem kayıt defterine içeren klasörü eklemeniz gerekir.  
  
 Örneğin, Trey Research şirket .NET Framework 4 genişleten ve görünmesi kitaplık derlemeleri istediği bir kitaplık geliştirmiştir varsayın **Başvuru Ekle** bir proje .NET Framework 4 hedeflediğinde iletişim kutusu. Ayrıca derlemeler 32 bit bir bilgisayar veya bir 64-bit bilgisayarda 64-bit derlemeleri üzerinde çalışan 32 bit derlemeleri olduğunu ve bunlar C:\TreyResearch\Extensions4\ klasöründe yüklenecek varsayalım.  
  
 Bu klasör, bu anahtarı kullanarak kaydedin: HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\\. NETFramework\v4.0.21006\AssemblyFoldersEx\TreyResearch\\. Bu varsayılan değeri anahtar verin: C:\TreyResearch\Extensions4.  
  
> [!NOTE]
>  .NET Framework sürümünün derleme numarası farklı olabilir.  
  
 Bir 64-bit bilgisayarda 32 bit derleme kaydetmek için Wow6432 düğümü, örneğin kullanın: HKEY_LOCAL_MACHINE\SOFTWARE\Wow6432Node\Microsoft\\. NETFramework\v4.0.21006\AssemblyFoldersEx\TreyResearch\\.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Visual Studio Integration](../msbuild/visual-studio-integration-msbuild.md)