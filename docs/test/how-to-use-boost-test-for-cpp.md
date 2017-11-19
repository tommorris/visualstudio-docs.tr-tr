---
title: Visual Studio'da c++ Boost.Test kullanma | Microsoft Docs
ms.custom: 
ms.date: 11/07/2017
ms.reviewer: 
ms.suite: 
ms.technology: vs-devops-test
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 2e0710a8-8e8a-4f6e-8415-5ab3eb830079
caps.latest.revision: "14"
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 6bfce4aa4153d8f01fa9ef6cd6dc0d4b08eedbc4
ms.sourcegitcommit: fb751e41929f031d1a9247bc7c8727312539ad35
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/15/2017
---
# <a name="how-to-use-boosttest-for-c-in-visual-studio"></a>Visual Studio'da c++ Boost.Test kullanma
İçinde **Visual Studio 2017 sürüm 15,5** ve daha sonra Visual Studio IDE içinde bir bileşeni olarak Boost.Test tümleşiktir **C++ ile masaüstü Develoment** iş yükü. Makinenize yüklemek için Visual Studio Yükleyicisi'ni açın ve Bul **Boost.Test bağdaştırıcısı** iş yükü bileşenlerin listesi altında:

![Artırma Test yüklemek](media/cpp-boost-component.png "Boost.Test C++ için yükleyin")

## <a name="install-boost"></a>Artırma yükleyin

 Boost.Test gerektirir [artırma](http://www.boost.org/)! Yüklü artırma yoksa Vcpkg Paket Yöneticisi'ni kullanmanızı öneririz. 

1. Bölümündeki yönergeleri izleyin [Vcpkg: Windows için bir C++ Paket Yöneticisi](/cpp/vcpkg) vcpkg (, zaten yoksa) yüklemek için.
2. Çalıştırma `vcpkg install boost` artırma kitaplıkları yüklemek için.
3. Çalıştırma `vcpkg integrate install` kitaplığı ile Visual Studio'yu yapılandırma ve ikili dosyaları ve artırma üstbilgiler yollara eklemek için komutu. 

## <a name="create-a-project-for-your-tests"></a>Testleriniz için bir proje oluşturun
Visual Studio 2017 içinde sürüm 15,5, önceden yapılandırılmış test proje veya öğe şablonları Boost.Test için kullanılabilir. Bu nedenle, testlerinizi tutmak için bir konsol uygulama projesi oluşturmanız gerekir. Test şablonları Boost.Test için Visual Studio gelecek bir sürümünde eklenmek üzere planlanmıştır. 

1. İçinde **Çözüm Gezgini**çözüm düğümüne sağ tıklayın ve seçin **Ekle | Yeni proje**. 
2. Sol bölmede seçin **Windows Masaüstü** ve ardından **Windows konsol uygulaması** Orta bölmede. 
3. Proje bir ad verin ve tıklatın **Tamam**. 

## <a name="add-include-directives"></a>Ekleme yönergeleri içerir
Test .cpp dosyanızda herhangi gerekli ekleyin `#include` programınızın türler ve İşlevler, test kodu görülebilmesi yönergeleri. Tipik olarak bir düzey klasör hiyerarşisindeki programdır. Yazarsanız `#include "../"` IntelliSense penceresi görünür ve üstbilgi dosyası tam yolunu seçmenizi sağlar.

![Ekle # yönergeleri include](media/cpp-gtest-includes.png "Ekle içerme test .cpp dosyasına yönergeleri")

En azından dahil etmenize gerek [Boost.Test tek üstbilgi türevi](http://www.boost.org/doc/libs/1_48_0/libs/test/doc/html/utf/user-guide/usage-variants/single-header-variant.html) ile `#include <path>/unit_test.hpp` ve tanımlayın `BOOST_TEST_MODULE`. Aşağıdaki örnek olarak bulunabilir olması test için yeterli **Test Gezgini**:

```cpp
#include "stdafx.h"
#define BOOST_TEST_MODULE MyTest
#include <boost/test/included/unit_test.hpp>
#include "../MyProgram/MyClass.h" // project being tested
#include <string>

BOOST_AUTO_TEST_CASE(my_boost_test)
{
    std::string name = "Bill";
    MyClass mc(name);
    Assert::AreEqual();
    BOOST_CHECK(name == mc.GetName());
}
```

## <a name="write-and-run-tests"></a>Yazma ve testleri çalıştırma
Şimdi yazmak ve artırma testleri çalıştırmak hazırsınız. Bkz: [artırma Test kitaplığı belgeleri](http://www.boost.org/doc/libs/1_38_0/libs/test/doc/html/index.html) test makroları hakkında bilgi için. Bkz: [Test Gezgini ile birim testleri çalıştırma](run-unit-tests-with-test-explorer.md) bulmaya çalışan ve kullanarak için testlerinizin gruplandırılması hakkında bilgi için **Test Gezgini**.

## <a name="see-also"></a>Ayrıca Bkz.
[C/C++ için birim testleri yazma](writing-unit-tests-for-c-cpp.md)


  







