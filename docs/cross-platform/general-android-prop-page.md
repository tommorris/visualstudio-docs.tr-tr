---
title: "Genel proje özellikleri (Android C++) | Microsoft Docs"
ms.custom: 
ms.date: 10/23/2017
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-mobile
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 65f4868b-b864-4989-a275-1e51869ef599
author: corob
ms.author: mblome
manager: ghogen
f1_keywords:
- VC.Project.VCConfiguration.OutputDirectory
- VC.Project.VCConfiguration.IntermediateDirectory
- VC.Project.VCConfiguration.TargetName
- VC.Project.VCConfiguration.TargetExt
- VC.Project.VCConfiguration.DeleteExtensionsOnClean
- VC.Project.VCConfiguration.BuildLogFile
- VC.Project.VCConfiguration.PlatformToolset
- VC.Project.VCConfiguration.ConfigurationType
- VC.Project.VCConfiguration.DeleteExtensionsOnClean
- VC.Project.VCConfiguration.UseOfSTL
- VC.Project.VCConfiguration.ThumbMode
ms.workload:
- xplat-cplusplus
ms.openlocfilehash: 6ec191d4f5deefd959c4647ae98a1626a0bd1d36
ms.sourcegitcommit: 205d15f4558315e585c67f33d5335d5b41d0fcea
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/09/2018
---
# <a name="general-project-properties-android-c"></a>Genel proje özellikleri (Android C++)

Özellik | Açıklama | Seçenekler
--- | ---| ---
Çıktı dizini | Çıktı dosyası dizini için göreli bir yol belirtir; ortam değişkenleri içerebilir.
Ara dizini | Ara dosyası dizine göreli bir yol belirtir; ortam değişkenleri içerebilir.
Hedef Adı | Bu proje oluşturacak olan bir dosya adını belirtir.
Hedef uzantısı | Bu proje oluşturacak olan bir dosya uzantısı belirtir. (Örnek: .exe veya .dll)
Temiz üzerinde silme uzantıları | Joker karakter belirtimi üzerinde temiz silmek veya yeniden ara dizinde hangi dosyalarını noktalı virgülle ayrılmış.
Günlük dosyası oluşturma | Günlük ne zaman oluşturulacağını etkin yazmak için yapılandırma günlük dosyasını belirtir.
Platform araç takımı | Geçerli yapılandırma oluşturmak için kullanılan araç takımı belirtir; Aksi halde kümesi, varsayılan araç takımı kullanılır.
Yapılandırma türü | Bu yapılandırma oluşturur çıktı türünü belirtir. | **Dinamik kitaplığı (.so)** -dinamik kitaplığı (.so)<br>**Statik kitaplık (bir)** -statik kitaplık (bir)<br>**Yardımcı programı** - yardımcı programı<br>**Derleme görevleri dosyası** -derleme görevleri dosyası<br>
Hedef API düzeyi | Android NDK API bu yapılandırma tarafından hedeflenen düzeyi.
STL kullanımı | Bu yapılandırma için kullanmak üzere hangi C++ Standart Kitaplığı belirtir. | **En az C++ çalışma zamanı kitaplığı (Sistem)**<br>**C++ çalışma zamanı statik kitaplık (gabi ++ _statik)**<br>**C++ çalışma zamanı paylaşılan kitaplığı (gabi ++ _shared)**<br>**STLport çalışma zamanı statik kitaplık (stlport_static)**<br>**STLport çalışma zamanı paylaşılan kitaplığı (stlport_shared)**<br>**GNU STL statik kitaplık (gnustl_static)**<br>**GNU STL paylaşılan kitaplık (gnustl_shared)**<br>**LLVM libc ++ statik kitaplık (c ++ _statik)**<br>**LLVM libc ++ paylaşılan kitaplık (c ++ _shared)**<br>
Flash modu | Flash mikro mimarisi için yürütülen kodu oluşturur. Bu, yalnızca arm mimarisi için geçerlidir. | **Flash**<br>**ARM**<br>**Devre dışı**<br>
