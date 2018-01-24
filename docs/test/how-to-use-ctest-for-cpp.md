---
title: Visual Studio'da c++ CTest kullanma | Microsoft Docs
ms.custom: 
ms.date: 11/07/2017
ms.reviewer: 
ms.suite: 
ms.technology: vs-devops-test
ms.tgt_pltfrm: 
ms.topic: article
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
author: mikeblome
ms.openlocfilehash: 529e070a3db1e6587989f8d0c55dc04e6db0388c
ms.sourcegitcommit: 49aa031cbebdd9c7ec070c713afb1a97d1ecb701
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/23/2018
---
# <a name="how-to-use-ctest-for-c-in-visual-studio"></a>Visual Studio'da c++ CTest kullanma
(CTest içeren) CMake bir bileşeni olarak Visual Studio IDE içinde tümleşik **C++ ile masaüstü Develoment** iş yükü. Makinenize yüklemek için Visual Studio Yükleyicisi'ni açın ve Bul [CMake araçları Visual C++ için](/cpp/ide/cmake-tools-for-visual-cpp) iş yükü bileşenlerin listesi altında.

Visual Studio'da CMake desteği Visual Studio Proje sistemi gerektirmez. Bu nedenle, yazma ve hiçbir CMake ortamında gibi CTest testleri yapılandırın. Bkz: [CMake araçları Visual C++ için](/cpp/ide/cmake-tools-for-visual-cpp) CMake Visual Studio'da kullanma hakkında daha fazla bilgi için.

**Visual Studio 2017 sürüm 15,5** CTest şu anda tümleşik değildir ile **Test Gezgini**. Testlerinizi CMake ana menüden veya bağlam menüsünden çalıştırabilirsiniz bir **CMakeLists.txt** dosyasını **Çözüm Gezgini**. Visual Studio test sonuçlarını yönergelerine uygun **çıktı penceresi**.

![CTest testler](media/cpp-cmake-run-tests.png "çalıştırmak CTest testleri")

## <a name="see-also"></a>Ayrıca Bkz.
[C/C++ için birim testleri yazma](writing-unit-tests-for-c-cpp.md)