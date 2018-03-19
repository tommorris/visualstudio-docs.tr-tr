---
title: "Visual Studio'da C++ DLL'ler için birim testleri yazma | Microsoft Docs"
ms.date: 11/04/2017
ms.technology: vs-ide-test
ms.topic: article
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
author: mikeblome
ms.openlocfilehash: 519d1ae3c38e3366eb898ff1fe050533f1b5e221
ms.sourcegitcommit: 900ed1e299cd5bba56249cef8f5cf3981b10cb1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/19/2018
---
# <a name="write-unit-tests-for-c-dlls-in-visual-studio"></a>Visual Studio'da C++ DLL'ler için birim testleri yazma

 Olup olmadığını test etmek istediğiniz işlevleri dışa aktarır bağlı olarak, DLL kodu test etmek için birkaç yolu vardır. Aşağıdaki yöntemlerden birini seçin:

 **DLL'den dışarı yalnızca işlevlerine çağrı birim testleri:** açıklandığı gibi ayrı bir test projesi eklemek [C/C++ için birim testleri yazma](writing-unit-tests-for-c-cpp.md). Test projesinde DLL projesine bir başvuru ekleyin.

 Yordam gidin [dışarı aktarılan işlevler DLL projesinde başvurmak için](#projectRef).

 **DLL bir .exe dosyası olarak oluşturulmuştur:** ayrı bir test projesi ekleyin. Çıktı nesne dosyasına bağlayın.

 Yordam gidin [testleri için nesne veya kitaplık dosyalarını bağlamak için](#objectRef).

 **Hangi DLL ve DLL dışarı aktarılmaz birim testleri çağrısı olmayan üye işlevleri statik kitaplık olarak oluşturulabilir:** şekilde .lib dosyasına derlenmiş DLL projesi değiştirin. Test altındaki projeye başvuruda bulunan bir ayrı test projesi ekleyin.

 Bu yaklaşım testlerinizi dışarı olmayan üyeleri kullanır ancak ayrı bir projede testleri saklamak izin verme avantajına sahiptir.

 Yordam gidin [statik kitaplığa DLL değiştirmek için](#staticLink).

 **Birim testleri aktarılmaz üye olmayan işlevlerini çağırmanız gerekir ve kod dinamik bağlantı kitaplığı (DLL) oluşturulmalıdır:** ürün kodu aynı projede birim testleri ekleme.

 Yordam gidin [birim testleri aynı projede eklemek için](#sameProject).

## <a name="creating-the-tests"></a>Testleri oluşturma

###  <a name="staticLink"></a> Bir statik kitaplık DLL değiştirmek için

-   Testlerinizi DLL projesi tarafından verilmez üyeleri kullanmanız gerekir ve projeyi test altındaki dinamik kitaplık olarak oluşturulmuştur, bir statik kitaplık dönüştürme göz önünde bulundurun.

    1.  İçinde **Çözüm Gezgini**, test projesinin kısayol menüsünden seçin **özellikleri**. Proje Özellikleri penceresi açılır.

    2.  Seçin **yapılandırma özellikleri | Genel**.

    3.  Ayarlama **yapılandırma türü** için **statik kitaplık (.lib)**.

 Yordamla devam edin [testleri için nesne veya kitaplık dosyalarını bağlamak için](#objectRef).

###  <a name="projectRef"></a> Dışa aktarılan DLL işlevleri test projesinden başvurmak için

-   Test etmek istediğiniz işlevleri DLL projesi dışarı verirse, test projesinin kod projesine bir başvuru ekleyebilirsiniz.

    1.  Yerel birim testi projesi oluşturun.

        1.  Üzerinde **dosya** menüsünde seçin **yeni | Proje | Visual C++, Test | C++ birim testi projesi**.

    2.  İçinde **Çözüm Gezgini**, test projesinin kısayol menüsünden seçin **başvurular**. Proje Özellikleri penceresi açılır.

    3.  Seçin **ortak özellikleri | Framework ve başvuruları**ve ardından **Yeni Başvuru Ekle** düğmesi.

    4.  Seçin **projeleri**ve ardından sınanacak projesi.

         Seçin **Ekle** düğmesi.

    5.  Test projesi için Özellikler'de test projesinin konumunu içeren dizinler ekleyin.

         Seçin **yapılandırma özellikleri | VC ++ dizinleri | Yönergeleri dahil etme**.

         Seçin **Düzenle**ve ardından test altındaki projenin üstbilgi dizini ekleyin.

 Git [birim testleri yazma](#addTests).

###  <a name="objectRef"></a> Nesne veya kitaplık dosyalarını testleri bağlamak için

-   DLL test etmek istediğiniz işlevlerini dışarı aktarma değil, çıktı ekleyebilirsiniz **.obj** veya **.lib** test projesinin bağımlılıkları dosyasına.

    1.  Yerel birim testi projesi oluşturun.

        1.  Üzerinde **dosya** menüsünde seçin **yeni | Proje | Visual C++ | Test | Yerel birim testi projesi**.

    2.  İçinde **Çözüm Gezgini**, test projesinin kısayol menüsünden seçin **özellikleri**.

    3.  Seçin **yapılandırma özellikleri | Bağlayıcı | Giriş | Ek Bağımlılıklar**.

         Seçin **Düzenle**ve adlarını ekleyin **.obj** veya **.lib** dosyaları. Tam yol adları kullanmayın.

    4.  Seçin **yapılandırma özellikleri | Bağlayıcı | Genel | Ek Kitaplık dizinleri**.

         Seçin **Düzenle**ve dizin yolu Ekle **.obj** veya **.lib** dosyaları. Genellikle test projesinin yapı klasördeki yoludur.

    5.  Seçin **yapılandırma özellikleri | VC ++ dizinleri | Yönergeleri dahil etme**.

         Seçin **Düzenle**ve ardından test altındaki projenin üstbilgi dizini ekleyin.

 Git [birim testleri yazma](#addTests).

###  <a name="sameProject"></a> Birim testleri aynı projede eklemek için

1.  Üstbilgiler ve birim testi için gerekli olan kitaplık dosyaları dahil olmak üzere ürün kodu proje özelliklerini değiştirin.

    1.  İçinde **Çözüm Gezgini**, test projesinin kısayol menüsünden Özellikler'i seçin. Proje Özellikleri penceresi açılır.

    2.  Seçin **yapılandırma özellikleri | VC ++ dizinleri**.

    3.  Dahil et ve kitaplık dizinleri düzenleyin:

        |||
        |-|-|
        |**Yönergeleri dahil etme** | **$(VCInstallDir)UnitTest\include;$(IncludePath)**|
        |**Kitaplık dizinleri** | **$(VCInstallDir)UnitTest\lib;$(LibraryPath)**|

2.  C++ birim testi dosyasına ekleyin:

    -   İçinde **Çözüm Gezgini**, projesinin kısayol menüsünden seçin **Ekle | Yeni öğe | C++ birim testi**.

 Git [birim testleri yazma](#addTests).

##  <a name="addTests"></a> Birim testleri yazma

1.  Her birim testi kod dosyasında ekleyin bir `#include` test projesinin üstbilgilerinin deyimi.

2.  Test sınıflar ve yöntemler için birim testi kod dosyaları ekleyin. Örneğin:

    ```cpp
    #include "stdafx.h"
    #include "CppUnitTest.h"
    #include "MyProjectUnderTest.h"
    using namespace Microsoft::VisualStudio::CppUnitTestFramework;
    namespace MyTest
    {
      TEST_CLASS(MyTests)
      {
      public:
          TEST_METHOD(MyTestMethod)
          {
              Assert::AreEqual(MyProject::Multiply(2,3), 6);
          }
      };
    }
    ```

## <a name="run-the-tests"></a>Testleri çalıştırma

1.  Üzerinde **Test** menüsünde seçin **Windows | Test Gezgini**.

1. Tüm testleri penceresinde görünür değilse, kendi düğümünde sağ tıklayarak test projesi derleme **Çözüm Gezgini** ve seçme **yapı** veya **yeniden**.

1.  Test Gezgini seçin **tümünü Çalıştır**, veya çalıştırmak istediğiniz belirli testleri seçin. Bir test ile kesme noktaları etkin hata ayıklama modunda çalışan dahil olmak üzere diğer seçenekler için sağ tıklayın.

## <a name="see-also"></a>Ayrıca bkz.

- [C/C++ için birim testleri yazma](writing-unit-tests-for-c-cpp.md)
- [Microsoft.VisualStudio.TestTools.CppUnitTestFramework API Reference](../test/microsoft-visualstudio-testtools-cppunittestframework-api-reference.md)
- [Yerel kodda hata ayıklama](../debugger/debugging-native-code.md)
- [İzlenecek yol: Dinamik Bağlantı Kitaplığı Oluşturma ve Kullanma (C++)](/cpp/build/walkthrough-creating-and-using-a-dynamic-link-library-cpp)
- [İçeri ve Dışarı Aktarma](/cpp/build/importing-and-exporting)
- [Hızlı Başlangıç: Test Gezgini ile Test Güdümlü Geliştirme](../test/quick-start-test-driven-development-with-test-explorer.md)
