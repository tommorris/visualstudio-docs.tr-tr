---
title: Visual Studio'da C++ için Google Test kullanma
ms.date: 11/04/2017
ms.prod: visual-studio-dev15
ms.technology: vs-ide-test
ms.topic: conceptual
ms.author: mblome
manager: douge
ms.workload:
- cplusplus
author: mikeblome
ms.openlocfilehash: c5e86884f017aa2fc490eb926485c567742b8647
ms.sourcegitcommit: e13e61ddea6032a8282abe16131d9e136a927984
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/26/2018
---
# <a name="how-to-use-google-test-for-c-in-visual-studio"></a>Visual Studio'da C++ için Google Test kullanma
İçinde **Visual Studio 2017 sürüm 15,5** ve daha sonra Visual Studio IDE içinde varsayılan bileşeni olarak Google Test tümleşiktir **C++ ile masaüstü Develoment** iş yükü. Makinenize yüklü olduğunu doğrulamak için Visual Studio Yükleyicisi'ni açın ve Google Test iş yükü bileşenlerin listesi altında bulabilirsiniz:

![Google Test yüklemek](media/cpp-google-component.png "Google Test c++ yükleyin")

## <a name="add-a-google-test-project-to-the-solution"></a>Bir Google Test projesi ekleyin
1. İçinde **Çözüm Gezgini**çözüm düğümüne sağ tıklayın ve seçin **Ekle | Yeni proje**.
2. Sol bölmede seçin **Visual C++ | Test** ve ardından **Google Test projesi** Orta bölmede.
3. Oluşturduğunuz test projesinin bir ad verin ve tıklatın **Tamam**.

![Yeni Google Test projesi](media/cpp-gtest-new-project.png "yeni bir Google Test projesi ekleme")

## <a name="configure-the-test-project"></a>Test projesi yapılandırın
İçinde **Test projesi yapılandırma** görüntülenen iletişim kutusunda, test etmek istediğiniz projeyi seçebilirsiniz. Bir proje seçtiğinizde, Visual Studio seçili projesine bir başvuru ekler. Proje seçerseniz, test etmek istediğiniz proje başvuruları el ile eklemeniz gerekir. Statik ve dinamik Google Test ikili dosyalar için bağlama arasında seçerken, konuları herhangi bir C++ programı ile aynıdır. Daha fazla bilgi için bkz: [DLL'leri Visual C++'ta](/cpp/build/dlls-in-visual-cpp).

 ![Google Test projesi yapılandırmak](media/cpp-gtest-config.png "Google Test projesi yapılandırın")

## <a name="set-additional-options"></a>Ek seçeneklerini ayarlama
Ana menüden **Araçlar | Seçenekleri | Bağdaştırıcı Google testi için test** ek seçenekleri ayarlamak için. Bu ayarlar hakkında daha fazla bilgi için Google Test belgelerine bakın.

 ![Google Test proje ayarları](media/cpp-gtest-settings.png "Google Test proje ayarları")

## <a name="add-include-directives"></a>Ekleme yönergeleri içerir
Test .cpp dosyanızda herhangi gerekli ekleyin `#include` programınızın türler ve İşlevler, test kodu görülebilmesi yönergeleri. Tipik olarak bir düzey klasör hiyerarşisindeki programdır. Yazarsanız `#include "../"` IntelliSense penceresi görünür ve üstbilgi dosyası tam yolunu seçmenizi sağlar.

![Ekle # yönergeleri include](media/cpp-gtest-includes.png "Ekle içerme test .cpp dosyasına yönergeleri")

## <a name="write-and-run-tests"></a>Yazma ve testleri çalıştırma
Şimdi yazmak ve Google testleri çalıştırmak hazırsınız. Bkz: [Google Test Primer](https://github.com/google/googletest/blob/master/googletest/docs/Primer.md) test makroları hakkında bilgi için. Bkz: [Test Gezgini ile birim testleri çalıştırma](run-unit-tests-with-test-explorer.md) bulmaya çalışan ve kullanarak için testlerinizin gruplandırılması hakkında bilgi için **Test Gezgini**.

## <a name="see-also"></a>Ayrıca bkz.
[C/C++ için birim testleri yazma](writing-unit-tests-for-c-cpp.md)










