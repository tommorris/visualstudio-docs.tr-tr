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
ms.workload:
- cplusplus
author: mikeblome
ms.openlocfilehash: 8ae88a819dca24af504c954a00c4f25a9d61d38c
ms.sourcegitcommit: c0a2385a16cc4f47d2e1ff23d35c4da40f5605e0
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/23/2018
---
# <a name="how-to-use-ctest-for-c-in-visual-studio"></a>Visual Studio'da c++ CTest kullanma

(CTest içeren) CMake tümleşik Visual Studio IDE içinde varsayılan olarak bir bileşeni olarak **C++ ile masaüstü Develoment** iş yükü. Makinenizde yüklemeniz gerekiyorsa, Visual Studio yükleyicisi programını açın, **Değiştir** düğmesini tıklatıp denetleyin [CMake araçları Visual C++ için](/cpp/ide/cmake-tools-for-visual-cpp) iş yükü bileşenlerin listesi altında.

## <a name="to-write-tests"></a>Testleri yazmak için

Visual Studio'da CMake desteği Visual Studio Proje sistemi kullanılmaz. Bu nedenle, yazma ve hiçbir CMake ortamında gibi CTest testleri yapılandırın. Visual Studio'da CMake kullanma hakkında daha fazla bilgi için bkz: [CMake araçları Visual C++ için](/cpp/ide/cmake-tools-for-visual-cpp). 

## <a name="to-run-tests-visual-studio-2017-version-156"></a>(Visual Studio 2017 sürüm 15,6) testleri çalıştırmak için

Visual Studio 2017 içinde sürüm 15,6, CTest tam olarak tümleşiktir **Test Gezgini** ve Google ve artırma birim testi çerçevelerini de destekler. Bu çerçeveleri bileşen olarak varsayılan olarak dahil **C++ ile masaüstü Develoment** iş yükü. Ancak, daha eski bir sürümü Visual Studio Proje yükseltiyorsanız, Visual Studio yükleyicisi programını kullanarak bu çerçeveleri yüklemeniz gerekebilir.

Aşağıdaki çizimde Google Test Çerçevesi kullanarak çalışacak bir CTest sonuçlarını gösterir:

![Google Test çerçevesinde VS2017 ile CTest 15,6](media/ctest-test-explorer.png "CTest ve Google testinde Test Gezgini")

CTest ancak değil Google veya artırma bağdaştırıcıları kullanıyorsanız, tek tek yerine CTest düzeyinde yöntemi düzeyi test sonuçları görürsünüz. Hata ayıklama ve Adımla yalnızca CTest yürütülebilir dosyaları, ancak Yığın izlemeleri tek tek testlerin üzerinde desteklenmez.

## <a name="to-run-tests-visual-studio-2017-version-155"></a>(Visual Studio 2017 sürüm 15,5) testleri çalıştırmak için

İçinde **Visual Studio 2017 sürüm 15,5**, CTest ile tümleşik değildir **Test Gezgini**. Testlerinizi CMake ana menüden veya bağlam menüsünden çalıştırabilirsiniz bir **CMakeLists.txt** dosyasını **Çözüm Gezgini**. Visual Studio test sonuçlarını yönergelerine uygun **çıktı penceresi**.

![VS2017 15,5 CTest testler](media/cpp-cmake-run-tests.png "çalıştırmak CTest içinde 15,5 testleri")

## <a name="see-also"></a>Ayrıca Bkz.

[C/C++ için birim testleri yazma](writing-unit-tests-for-c-cpp.md)