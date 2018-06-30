---
title: Visual C++ DLL UWP uygulamalar için Visual Studio'da test etme
ms.date: 02/15/2018
ms.prod: visual-studio-dev15
ms.technology: vs-ide-test
ms.topic: conceptual
ms.author: mblome
manager: douge
ms.workload:
- uwp
author: mikeblome
ms.openlocfilehash: d3b010998a56771cab1416c19a311f8bcbcf855b
ms.sourcegitcommit: d9e4ea95d0ea70827de281754067309a517205a1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/29/2018
ms.locfileid: "37117634"
---
# <a name="how-to-test-a-visual-c-dll"></a>Visual C++ DLL test etme

Bu konuda C++ için Microsoft Test Çerçevesi ile Evrensel Windows Platformu (UWP) uygulamaları için C++ DLL için birim testleri oluşturma yöntemlerinden biri açıklanmaktadır. RooterLib DLL belirsiz anılarınızı sınırı teorik olarak verilen bir sayının kare kökünü tahmini hesaplar işlevi uygulayarak hesaplama gösterir. Bir kullanıcı fun gösteren bir UWP uygulamasını DLL sonra dahil edilebilir math ile yapılabilir şey.

 Bu konuda birim geliştirme ilk adımı olarak testi kullanmayı gösterir. Bu yaklaşım önce test ettiğiniz sistemde belirli bir davranışı doğrular bir test yöntemi yazın ve ardından test başarılı kod yazın. Aşağıdaki yordamlar sırasına göre değişiklikler yaparak, bu strateji ilk yazma, test ve birim testleri yazma istediğiniz kod ters çevirebilirsiniz.

 Bu konu ayrıca tek bir Visual Studio çözümü ve birim testleri ve test etmek istediğiniz DLL için ayrı projeleri oluşturur. Birim testleri doğrudan DLL projesinde içerebilir veya birim testleri için ayrı çözümler oluşturabilirsiniz ve. DLL. Bkz: [mevcut C++ uygulamalarına birim testleri ekleme](../test/unit-testing-existing-cpp-applications-with-test-explorer.md) kullanmak için hangi yapısı ipuçları için.

##  <a name="Create_the_solution_and_the_unit_test_project"></a> Çözüm ve birim testi projesi oluşturma

1.  Üzerinde **dosya** menüsünde seçin **yeni** > **yeni proje**.

2.  Yeni Proje iletişim kutusuna genişletin **yüklü** > **Visual C++** ve **Windows Evrensel**. Ardından **birim testi uygulama (Evrensel Windows)** proje şablonları listesinden.

3.  Proje adı `RooterLibTests`; konumu belirtin; çözüm adı `RooterLib`; ve emin olun **çözüm için dizin oluştur** denetlenir.

     ![Çözüm ve proje adı ve konumu belirtin](../test/media/ute_cpp_windows_unittestlib_createspecs.png)

4.  Yeni projede açmak **unittest1.cpp**.

     ![UnitTest1.cpp](../test/media/ute_cpp_windows_unittest1_cpp.png)

     Aşağıdakilere dikkat edin:

    -   Her sınama kullanılarak tanımlanmış `TEST_METHOD(YourTestName){...}`.

         Geleneksel işlev imzası yazmak zorunda değildir. İmza TEST_METHOD makrosu tarafından oluşturulur. Makro void döndüren bir örnek işlev oluşturur. Ayrıca, test yöntemi hakkında bilgi döndüren statik bir işlev oluşturur. Bu bilgiler yöntemi bulmak test Gezgini sağlar.

    -   Test yöntemleri kullanarak sınıf halinde gruplandırılır `TEST_CLASS(YourClassName){...}`.

         Testler, her test sınıfının bir örneği oluşturulur. Test yöntemleri belirtilmeyen bir sırayı denir. Önce ve sonra her modül, sınıf veya yöntemin çağrılması özel yöntemler tanımlayabilirsiniz. Daha fazla bilgi için bkz: [Microsoft.VisualStudio.TestTools.CppUnitTestFramework kullanma](how-to-use-microsoft-test-framework-for-cpp.md) MSDN Kitaplığı'nda.

##  <a name="Verify_that_the_tests_run_in_Test_Explorer"></a> Testleri Test Explorer'da çalıştığını doğrulayın

1.  Bazı test kodu ekleyin:

    ```cpp
    TEST_METHOD(TestMethod1)
    {
        Assert::AreEqual(1,1);
    }
    ```

     Dikkat `Assert` sınıfı, test yöntemleri sonuçlarında doğrulamak için kullanabileceğiniz çeşitli statik yöntemler sağlar.

2.  Üzerinde **Test** menüsünde seçin **çalıştırmak** ve ardından **tümünü Çalıştır**.

     Test projesi oluşturur ve çalıştırır. Test Gezgini penceresi görünür ve test altında listelenen **testleri geçti**. Pencerenin altındaki Özet bölmesinde seçilen testi hakkında ek ayrıntılar sağlar.

     ![Test Gezgini](../test/media/ute_cpp_testexplorer_testmethod1.png)

##  <a name="Add_the_DLL_project_to_the_solution"></a> DLL projesi ekleyin

1.  Çözüm Gezgini'nde, çözüm adı seçin. Kısayol menüsünden **Ekle**ve ardından **Yeni Proje Ekle**.

     ![RooterLib projesi oluşturma](../test/media/ute_cpp_windows_rooterlib_create.png)

2.  İçinde **Yeni Proje Ekle** iletişim kutusunda, seçin **DLL (UWP uygulamaları)**.

3.  Aşağıdaki kodu ekleyin **RooterLib.h** dosyası:

    ```cpp
    // The following ifdef block is the standard way of creating macros which make exporting
    // from a DLL simpler. All files within this DLL are compiled with the ROOTERLIB_EXPORTS
    // symbol defined on the command line. This symbol should not be defined on any project
    // that uses this DLL. This way any other project whose source files include this file see
    // ROOTERLIB_API functions as being imported from a DLL, whereas this DLL sees symbols
    // defined with this macro as being exported.
    #ifdef ROOTERLIB_EXPORTS
    #define ROOTERLIB_API  __declspec(dllexport)
    #else
    #define ROOTERLIB_API __declspec(dllimport)
    #endif //ROOTERLIB_EXPORTS

    class ROOTERLIB_API CRooterLib {
    public:
        CRooterLib(void);
        double SquareRoot(double v);
    };
    ```

     Açıklamaları ıfdef blok yalnızca dll geliştirici, ancak bunların proje DLL'de başvuran herkes açıklanmaktadır. DLL proje özelliklerini kullanarak komut satırına ROOTERLIB_EXPORTS simge ekleyebilirsiniz.

     `CRooterLib` Sınıfı bir oluşturucu bildirir ve `SqareRoot` tahmin yöntemi.

4.  ROOTERLIB_EXPORTS simgesi için komut satırını ekleyin.

    1.  Çözüm Gezgini'nde seçin **RooterLib** proje ve ardından **özellikleri** kısayol menüsünden.

         ![Önişlemci sembolü tanımını ekleyin](../test/media/ute_cpp_windows_addpreprocessorsymbol.png)

    2.  RooterLib özellik sayfası iletişim kutusunda genişletin **yapılandırma özellikleri**, genişletin **C++** ve **önişlemci**.

    3.  Seçin  **\<Düzenle … >** gelen **önişlemci tanımları** listeleyin ve ardından ekleyin `ROOTERLIB_EXPORTS` önişlemci tanımları iletişim kutusunda.

5.  Bildirilen işlevlerin en az uygulamaları ekleyin. Açık **RooterLib.cpp** ve aşağıdaki kodu ekleyin:

    ```cpp
    // constructor
    CRooterLib::CRooterLib()
    {
    }

    // Find the square root of a number.
    double CRooterLib::SquareRoot(double v)
    {
        return 0.0;
    }

    ```

##  <a name="make_the_dll_functions_visible_to_the_test_code"></a> Dll işlevleri test kodu tarafından görülebilir kılma

1.  RooterLib RooterLibTests projeye ekleyin.

    1.  Çözüm Gezgini'nde seçin **RooterLibTests** proje ve ardından **başvuruları** kısayol menüsünde.

    2.  RooterLib Proje Özellikleri iletişim kutusunda genişletin **ortak özellikleri** ve **Framework ve başvurular**.

    3.  Seçin **Yeni Başvuru Ekle**

    4.  İçinde **Başvuru Ekle** iletişim kutusunda, genişletin **çözüm** ve ardından **projeleri**. Ardından **RouterLib** öğesi.

2.  İçinde RooterLib üst bilgi dosyasını dahil **unittest1.cpp**.

    1.  Açık **unittest1.cpp**.

    2.  Bu kod eklemek için aşağıdaki `#include "CppUnitTest.h"` satırı:

        ```cpp
        #include "..\RooterLib\RooterLib.h"
        ```

3.  İçeri aktarılan işlevini kullanan bir test ekleyin. Aşağıdaki kodu ekleyin **unittest1.cpp**:

    ```cpp
    TEST_METHOD(BasicTest)
    {
        CRooterLib rooter;
        Assert::AreEqual(
            // Expected value:
            0.0,
            // Actual value:
            rooter.SquareRoot(0.0),
            // Tolerance:
            0.01,
            // Message:
            L"Basic test failed",
            // Line number - used if there is no PDB file:
            LINE_INFO());
    }

    ```

4.  Çözümü oluşturun.

     Yeni test Test Gezgininde görünür **testleri değil Çalıştır** düğümü.

5.  Test Gezgini seçin **tümünü Çalıştır**.

     ![Temel sınaması başarılı oldu](../test/media/ute_cpp_testexplorer_basictest.png)

 Test ve kod projeleri ayarlayabilir ve kod projesinde işlevlerini Çalıştırma testleri çalıştırabilirsiniz doğrulandı. Şimdi, gerçek testleri ve kod yazmaya başlayabilirsiniz.

##  <a name="Iteratively_augment_the_tests_and_make_them_pass"></a> Tekrarlayarak testleri büyütmek ve onları geçirin

1.  Yeni bir test ekleyin:

    ```cpp
    TEST_METHOD(RangeTest)
    {
        CRooterLib rooter;
        for (double v = 1e-6; v < 1e6; v = v * 3.2)
        {
            double expected = v;
            double actual = rooter.SquareRoot(v*v);
            double tolerance = expected/1000;
            Assert::AreEqual(expected, actual, tolerance);
        }
    };
    ```

    > [!TIP]
    > Başarılı olan testler değiştirmemenizi öneririz. Bunun yerine, yeni bir test ekleyin, kod test başarılı şekilde güncelleştirin ve sonra başka bir test ekleyin ve benzeri.
    >
    > Kullanıcılarınızın kendi gereksinimleri değiştiğinde, artık doğru testleri devre dışı bırakın. Yeni testleri yazmak ve bunları bir seferde bir artımlı aynı şekilde çalışır duruma getirin.

2.  Test Gezgini seçin **tümünü Çalıştır**.

3.  Sınama başarısız olur.

     ![RangeTest başarısız](../test/media/ute_cpp_testexplorer_rangetest_fail.png)

    > [!TIP]
    > Hemen yazdıktan sonra her bir test başarısız olduğunu doğrulayın. Bu, hiçbir zaman başarısız bir test yazma kolay hata önlemenize yardımcı olur.

4.  Yeni test sağlayacak şekilde test altındaki kodun geliştirin. Aşağıdakileri ekleyin **RooterLib.cpp**:

    ```cpp
    #include <math.h>
    ...
    // Find the square root of a number.
    double CRooterLib::SquareRoot(double v)
    {
        double result = v;
        double diff = v;
        while (diff > result/1000)
        {
            double oldResult = result;
            result = result - (result*result - v)/(2*result);
            diff = abs (oldResult - result);
        }
        return result;
    }

    ```

5.  Çözümü derlemek ve Test Explorer'da seçin **tümünü Çalıştır**.

     Her iki testleri geçirin.

> [!TIP]
> Kod, aynı anda testleri bir ekleyerek geliştirin. Tüm testler her yinelemeden sonra başarılı olduğundan emin olun.


##  <a name="Debug_a_failing_test"></a> Başarısız test hata ayıklama

1.  Başka bir testine ekleme **unittest1.cpp**:

    ```cpp
    // Verify that negative inputs throw an exception.
     TEST_METHOD(NegativeRangeTest)
     {
       wchar_t message[200];
       CRooterLib rooter;
       for (double v = -0.1; v > -3.0; v = v - 0.5)
       {
         try
         {
           // Should raise an exception:
           double result = rooter.SquareRoot(v);

           swprintf_s(message, L"No exception for input %g", v);
           Assert::Fail(message, LINE_INFO());
         }
         catch (std::out_of_range ex)
         {
           continue; // Correct exception.
         }
         catch (...)
         {
           swprintf_s(message, L"Incorrect exception for %g", v);
           Assert::Fail(message, LINE_INFO());
         }
       }
    };

    ```

2.  Test Gezgini seçin **tümünü Çalıştır**.

     Sınama başarısız olur. Test adı Test Explorer'da seçin. Başarısız onaylama vurgulanır. Hata iletisi Test Gezgini ayrıntı bölmesinde görünür olur.

     ![NegativeRangeTests başarısız oldu](../test/media/ute_cpp_testexplorer_negativerangetest_fail.png)

3.  Neden sınama başarısız görmek için işleviyle adım:

    1.  Başlangıcında bir kesme noktası belirleyerek `SquareRoot` işlevi.

    2.  Başarısız test kısayol menüsünden seçin **seçili Testlerde Hata Ayıkla**.

         Çalıştır kesme noktasında durduğunda kod boyunca adım.

    3.  Kodu ekleyin **RooterLib.cpp** özel durumu yakalamak için:

        ```cpp
        #include <stdexcept>
        ...
        double CRooterLib::SquareRoot(double v)
        {
            //Validate the input parameter:
            if (v < 0.0)
            {
              throw std::out_of_range("Can't do square roots of negatives");
            }
        ...

        ```

    1.  Test Gezgini seçin **tümünü Çalıştır** test düzeltilmiş yöntemi ve bir gerileme sunulan henüz emin olun.

 Tüm testler şimdi geçirin.

 ![Tüm sınamaları geçmesi](../test/media/ute_ult_alltestspass.png)

##  <a name="Refactor_the_code_without_changing_tests"></a> Testleri değiştirmeden kodu yeniden düzenleyin

1.  Merkezi hesaplamadaki basitleştirmek `SquareRoot` işlevi:

    ```csharp
    // old code
    //result = result - (result*result - v)/(2*result);
    // new code
    result = (result + v/result) / 2.0;
    ```

2.  Seçin **tümünü Çalıştır** test işlenmiş yöntemi ve bir gerileme sunulan henüz emin olun.

    > [!TIP]
    > İyi birim testleri kararlı bir dizi kodu değiştirdiğinizde, hatalar sunulmuştur değil, güven verir.
    >
    > Diğer değişiklikler ayrı yeniden düzenleme tutun.
