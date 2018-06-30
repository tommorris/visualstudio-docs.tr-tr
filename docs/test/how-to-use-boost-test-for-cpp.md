---
title: Visual Studio'da c++ Boost.Test kullanma
ms.date: 01/29/2018
ms.prod: visual-studio-dev15
ms.technology: vs-ide-test
ms.topic: conceptual
author: mikeblome
ms.author: mblome
manager: douge
ms.workload:
- cplusplus
ms.openlocfilehash: 739368b8611d4755138466b8de37c16e5552fe11
ms.sourcegitcommit: d9e4ea95d0ea70827de281754067309a517205a1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/29/2018
ms.locfileid: "37120427"
---
# <a name="how-to-use-boosttest-for-c-in-visual-studio"></a>Visual Studio'da c++ Boost.Test kullanma

İçinde **Visual Studio 2017 sürüm 15,5** ve daha sonra Visual Studio IDE içinde bir bileşeni olarak Boost.Test test bağdaştırıcısı tümleşiktir **C++ ile masaüstü geliştirme** iş yükü.

![Test bağdaştırıcısı Boost.Test için](media/cpp-boost-component.png)

Sahip değilseniz **C++ ile masaüstü geliştirme** yüklü, iş yükü açık **Visual Studio yükleyicisi** seçip **Değiştir**. Seçin **C++ ile masaüstü geliştirme** iş yükü, ardından **Değiştir** düğmesi.

## <a name="install-boost"></a>Artırma yükleyin

Boost.Test gerektirir [artırma](http://www.boost.org/)! Yüklü artırma yoksa Vcpkg Paket Yöneticisi'ni kullanmanızı öneririz.

1. Bölümündeki yönergeleri izleyin [Vcpkg: Windows için bir C++ Paket Yöneticisi](/cpp/vcpkg) vcpkg (, zaten yoksa) yüklemek için.

1. Boost.Test dinamik veya statik kitaplık yükleyin:

    - Çalıştırma **vcpkg yükleme artırma test** Boost.Test dinamik kitaplığı yüklemek için.

       -VEYA-

    - Çalıştırma **vcpkg yükleme artırma-test: x 86 windows statik** Boost.Test statik kitaplık yüklemek için.

1. Çalıştırma **vcpkg tümleştirmek yükleme** kitaplığı ile Visual Studio'yu yapılandırma ve ikili dosyaları ve artırma üstbilgiler yollara eklemek için.

## <a name="add-the-item-template-visual-studio-2017-version-156-and-later"></a>Öğe şablonu (Visual Studio 2017 sürüm 15.6 ve sonrası) Ekle

1. Testleriniz için .cpp dosyası oluşturmak için proje düğümüne sağ tıklayın **Çözüm Gezgini** ve **Yeni Öğe Ekle**.

   ![Boost.Test öğe şablonu](media/boost_test_item_template.png)

1. Yeni bir dosya bir örnek test yöntemi içerir. Etkinleştirmek için projenizi derleme **Test Gezgini** yöntemi bulmak için.

Öğe şablonu Boost.Test tek üstbilgi türevi kullanır, ancak değiştirebileceğiniz # tek başına kitaplığı değişken kullanılacak yol include. Daha fazla bilgi için bkz: [Ekle içerme yönergeleri](#add-include-directives).

## <a name="create-a-test-project-visual-studio-2017-version-155"></a>Bir test projesi (Visual Studio 2017 sürüm 15,5) oluşturma

Visual Studio 2017 içinde sürüm 15,5, önceden yapılandırılmış test proje veya öğe şablonları Boost.Test için kullanılabilir. Bu nedenle, oluşturabilir ve testleri tutmak için bir konsol uygulama projesi yapılandırmanız gerekir.

1. İçinde **Çözüm Gezgini**çözüm düğümüne sağ tıklayın ve seçin **Ekle** > **yeni proje**.

1. Sol bölmede seçin **Visual C++** > **Windows Masaüstü**ve ardından **Windows konsol uygulaması** şablonu.

1. Proje bir ad verin ve seçin **Tamam**.
1. Silme `main` .cpp dosyasına işlevi.

1. Boost.Test tek üstbilgi veya dinamik kitaplık sürümünü kullanıyorsanız, Git [Ekle içerme yönergeleri](#add-include-directives). Statik kitaplık sürümünü kullanıyorsanız, bazı ek yapılandırma gerçekleştirmeniz gerekir:

   a. Proje dosyası düzenlemek için önce onu kaldırın. İçinde **Çözüm Gezgini**, proje düğümüne sağ tıklayın ve seçin **projeyi**. Sonra proje düğümüne sağ tıklayın ve seçin **Düzenle < adı\>.vcxproj**.

   b. İçin iki satırı ekleyin **Globals** aşağıda gösterildiği gibi özellik grubu:

    ```xml
    <PropertyGroup Label="Globals">
    ....
        <VcpkgTriplet>x86-windows-static</VcpkgTriplet>
        <VcpkgEnabled>true</VcpkgEnabled>
    </PropertyGroup>
    ```
   c. Kaydet ve Kapat \*.vcxproj dosya ve projeyi yeniden yükle.

   d. Açmak için **özellik sayfaları**, proje düğümüne sağ tıklayın ve seçin **özellikleri**.

   d. Genişletme **C/C++** > **kod oluşturma**ve ardından **çalışma zamanı kitaplığı**. Seçin **/MTd** hata ayıklama statik çalışma zamanı kitaplığı veya **/MT** yayın statik çalışma zamanı kitaplığı.

   f. Genişletme **bağlayıcı > Sistem**. Doğrulayın **alt sistemi** ayarlanır **konsol**.

   g. Seçin **Tamam** özellik sayfalarını kapatmak için.

## <a name="add-include-directives"></a>Ekleme yönergeleri içerir

1. Test .cpp dosyanızda herhangi gerekli ekleyin `#include` programınızın türler ve İşlevler, test kodu görülebilmesi yönergeleri. Tipik olarak bir düzey klasör hiyerarşisindeki programdır. Yazarsanız, `#include "../"`, bir IntelliSense penceresi görüntülenir ve üstbilgi dosyası tam yolunu seçmenize olanak sağlar.

   ![Ekleme # yönergeleri include](media/cpp-gtest-includes.png)

   Tek başına kitaplıkla kullanabilirsiniz:

   ```cpp
   #include <boost/test/unit_test.hpp>
   ```

   Veya tek üstbilgi sürümüyle kullanın:

   ```cpp
   #include <boost/test/included/unit_test.hpp>
   ```

   Daha sonra tanımlamak `BOOST_TEST_MODULE`.

Aşağıdaki örnek olarak bulunabilir olması test için yeterli **Test Gezgini**:

```cpp
#define BOOST_TEST_MODULE MyTest
#include <boost/test/included/unit_test.hpp\> //single-header
#include "../MyProgram/MyClass.h" // project being tested
#include <string>

BOOST_AUTO_TEST_CASE(my\_boost_test)
{
    std::string expected_value = "Bill";

    // assume MyClass is defined in MyClass.h
    // and get_value() has public accessibility
    MyClass mc;
    BOOST_CHECK(expected_value == mc.get_value());
}
```

## <a name="write-and-run-tests"></a>Yazma ve testleri çalıştırma
Şimdi yazmak ve artırma testleri çalıştırmak hazırsınız. Bkz: [artırma Test kitaplığı belgeleri](http://www.boost.org/doc/libs/release/libs/test/doc/html/index.html) test makroları hakkında bilgi için. Bkz: [Test Gezgini ile birim testleri çalıştırma](run-unit-tests-with-test-explorer.md) bulmaya çalışan ve kullanarak için testlerinizin gruplandırılması hakkında bilgi için **Test Gezgini**.

## <a name="see-also"></a>Ayrıca bkz.
[C/C++ için birim testleri yazma](writing-unit-tests-for-c-cpp.md)
