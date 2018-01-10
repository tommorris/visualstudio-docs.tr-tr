---
title: "Nasıl yapılır: C++ DLL'ler için birim testleri yazma | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2017
ms.reviewer: 
ms.suite: 
ms.technology: vs-devops-test
ms.tgt_pltfrm: 
ms.topic: article
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
author: mikeblome
ms.openlocfilehash: 0e3852687b837c99bf92b73a65be9a5d139bc0cc
ms.sourcegitcommit: 7ae502c5767a34dc35e760ff02032f4902c7c02b
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/09/2018
---
# <a name="how-to-write-unit-tests-for-c-dlls"></a>Nasıl yapılır: C++ DLL'ler için birim testleri yazma
Bu kılavuz, yerel C++ önce test yöntemi kullanarak DLL'den geliştirmek açıklar. Temel adımlar aşağıdaki gibidir:  
  
1.  [Yerel Test projesi oluşturma](#create_test_project). Oluşturduğunuz test projesinin DLL projesi olarak aynı çözüme bulunur.  
  
2.  [DLL projesi oluşturma](#create_dll_project). Bu kılavuzda yeni bir DLL oluşturur ama varolan bir DLL sınama yordamını benzer.  
  
3.  [DLL işlevleri testleri görünür kılma](#make_functions_visible).  
  
4.  [Testleri tekrarlayarak büyütmek](#iterate). Kod geliştirme testleri tarafından neden bir "kırmızı yeşil düzenleme" döngüsü öneririz.  
  
5.  [Başarısız olan testleri hata ayıklama](#debug). Hata ayıklama modunda testleri çalıştırabilirsiniz.  
  
6.  [Testleri değişmeden tutarken yeniden düzenlemeniz](#refactor). Yeniden düzenleme kod yapısını dış davranışını değiştirmeden geliştirme anlamına gelir. Performans, genişletilebilirlik veya kod okunabilirliğini artırmak için bunu yapabilirsiniz. Amacınız davranışını değiştirmek için değil olduğundan, kodu yeniden düzenleme değişiklik yapma çalışırken testleri değiştirmeyin. Testleri yeniden düzenleme sırada, hatalar tanıtmak değil, sağlanmasına yardımcı olur.
  
7.  [Kapsamı denetleme](using-code-coverage-to-determine-how-much-code-is-being-tested.md). Birim testleri daha kodunuzun çalışma sırasında daha faydalıdır. Kodunuzu hangi kısımlarının testleri tarafından kullanılmış bulabilir.  
  
8.  [Dış kaynaklara birimlerinden yalıtmak](using-stubs-to-isolate-parts-of-your-application-from-each-other-for-unit-testing.md). Genellikle, DLL diğer DLL'leri, veritabanları veya uzak alt sistemleri gibi geliştirdiğiniz sisteminin diğer bileşenleri bağımlıdır. Haklarında bağımlılıklarını ayrı her birim test etmek kullanışlıdır. Dış bileşenler yavaş çalışmasına test yapabilirsiniz. Geliştirme sırasında diğer bileşenleri tamamlanmamış olabilir.  
  
##  <a name="create_test_project"></a>Yerel birim testi projesi oluşturma  
  
1.  Üzerinde **dosya** menüsünde seçin **yeni | Proje**.  
  
     İletişim kutusunda genişletin **yüklü | Şablonları | Visual C++ | Test**.  
  
     Seçin **yerel birim testi projesi** şablon veya ne olursa olsun yüklü tercih ettiğiniz framework. Google Test veya Boost.Test gibi başka bir şablonu seçerseniz, bazı ayrıntılar farklılık gösterir ancak temel ilkeleri aynıdır.
  
     Bu kılavuzda, test projesinin adlı `NativeRooterTest`.  
  
     ![C++ birim testi projesi oluşturma](../test/media/utecpp01.png "UteCpp01")  
  
2.  Yeni projede incelemek **unittest1.cpp**  
  
     ![Projeyi TEST &#95;test; SINIF ve TEST &#95; YÖNTEM](../test/media/utecpp2.png "UteCpp2")  
  
     Şunlara dikkat edin:  
  
    -   Her sınama kullanılarak tanımlanmış `TEST_METHOD(YourTestName){...}`.  
  
         Geleneksel işlev imzası yazmak zorunda değildir. İmza TEST_METHOD makrosu tarafından oluşturulur. Makro void döndüren bir örnek işlev oluşturur. Ayrıca, test yöntemi hakkında bilgi döndüren statik bir işlev oluşturur. Bu bilgiler yöntemi bulmak test Gezgini sağlar.  
  
    -   Test yöntemleri kullanarak sınıf halinde gruplandırılır `TEST_CLASS(YourClassName){...}`.  
  
         Testler, her test sınıfının bir örneği oluşturulur. Test yöntemleri belirtilmeyen bir sırayı denir. Önce ve sonra her modül, sınıf veya yöntemin çağrılması özel yöntemler tanımlayabilirsiniz.  
  
3.  Testleri Test Explorer'da çalıştığını doğrulayın:  
  
    1.  Bazı test kodu ekleyin:  
  
        ```cpp  
        TEST_METHOD(TestMethod1)  
        {  
            Assert::AreEqual(1,1);  
        }  
        ```  
  
         Dikkat `Assert` sınıfı, test yöntemleri sonuçlarında doğrulamak için kullanabileceğiniz çeşitli statik yöntemler sağlar.  
  
    2.  Üzerinde **Test** menüsünde seçin **çalıştırma | Tüm testler**.  
  
         Test oluşturur ve çalıştırır.  
  
         Test Gezgini görüntülenir.  
  
         Test altında görünür **testleri geçti**.  
  
         ![Birim Test Gezgini ile geçirilen test](../test/media/utecpp04.png "UteCpp04")  
  
##  <a name="create_dll_project"></a>DLL projesi oluşturma  
  
1.  Oluşturma bir **Visual C++** kullanarak proje **Win32 Proje** şablonu.  
  
     Bu kılavuzda, proje adı `RootFinder`.  
  
     ![C++ Win32 Proje oluşturma](../test/media/utecpp05.png "UteCpp05")  
  
2.  Seçin **DLL** ve **verme simgeleri** Win32 Uygulama Sihirbazı'nda.  
  
     **Sembolleri dışa aktar** seçeneği, dışa aktarılan yöntemleri bildirmek için kullanabileceğiniz uygun bir makrosu üretir.  
  
     ![C++ projesi Sihirbazı DLL ve sembolleri dışa aktar için ayarlama](../test/media/utecpp06.png "UteCpp06")  
  
3.  Dışarı aktarılan bir işlevin asıl .h dosyasında bildirin:  
  
     ![Yeni DLL kodunu projeyi ve .h dosya API makroları ile](../test/media/utecpp07.png "UteCpp07")  
  
     Bildirimcisi `__declspec(dllexport)` dışında DLL görünür olması ortak ve korumalı üyeleri sınıfın neden olur. Daha fazla bilgi için bkz: [C++ sınıflarında dllimport ve dllexport kullanma](/cpp/cpp/using-dllimport-and-dllexport-in-cpp-classes).  
  
4.  Asıl .cpp dosyasında işlev için en az bir gövde ekleyin:  
  
    ```cpp  
        // Find the square root of a number.  
        double CRootFinder::SquareRoot(double v)  
        {  
            return 0.0;  
        }  
    ```  
  
##  <a name="make_functions_visible"></a>Birkaç DLL projesi için test projesi  
  
1.  DLL projesi test projesinin proje başvuruları ekleyin:  
  
    1.  Oluşturduğunuz test projesinin özelliklerini açın ve seçin **ortak özellikleri**, **Framework ve başvurular**.  
  
         ![C++ proje özellikleri | Framework ve başvuruları](../test/media/utecpp08.png "UteCpp08")  
  
    2.  Seçin **Yeni Başvuru Ekle**.  
  
         İçinde **Başvuru Ekle** iletişim kutusunda, DLL projesi seçin ve Seç **Ekle**.  
  
         ![C++ proje özellikleri | Yeni Başvuru Ekle](../test/media/utecpp09.png "UteCpp09")  
  
2.  Asıl birim test .cpp dosyasında DLL kodunun .h dosyası şunları içerir:  
  
    ```cpp  
    #include "..\RootFinder\RootFinder.h"  
    ```  
  
3.  Dışarı aktarılan işlevini kullanan basit bir sınama ekleyin:  
  
    ```cpp  
    TEST_METHOD(BasicTest)  
    {  
       CRootFinder rooter;  
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
  
     Yeni test Test Gezgini'nde görünür.  
  
5.  Test Gezgini seçin **tümünü Çalıştır**.  
  
     ![Birim Test Gezgini &#45; Geçirilen temel Test](../test/media/utecpp10.png "UteCpp10")  
  
 Test ve kod projeleri ayarlayabilir ve kod projesinde işlevlerini Çalıştırma testleri çalıştırabilirsiniz doğrulandı. Şimdi, gerçek testleri ve kod yazmaya başlayabilirsiniz.  
  
##  <a name="iterate"></a>Tekrarlayarak testleri büyütmek ve onları geçirin  
  
1.  Yeni bir test ekleyin:  
  
    ```cpp  
    TEST_METHOD(RangeTest)  
    {  
      CRootFinder rooter;  
      for (double v = 1e-6; v < 1e6; v = v * 3.2)  
      {  
        double actual = rooter.SquareRoot(v*v);  
        Assert::AreEqual(v, actual, v/1000);  
      }  
    }  
    ```  
  
    > [!TIP]
    >  Başarılı olan testler değiştirmemenizi öneririz. Bunun yerine, yeni bir test ekleyin, kod test başarılı şekilde güncelleştirin ve sonra başka bir test ekleyin ve benzeri.  
    >   
    >  Kullanıcılarınızın kendi gereksinimleri değiştiğinde, artık doğru testleri devre dışı bırakın. Yeni testleri yazmak ve bunları bir seferde bir artımlı aynı şekilde çalışır duruma getirin.  
  
2.  Çözümü derlemek ve Test Explorer'da seçin **tümünü Çalıştır**.  
  
     Yeni test başarısız olur.  
  
     ![RangeTest başarısız](../test/media/ute_cpp_testexplorer_rangetest_fail.png "UTE_Cpp_TestExplorer_RangeTest_Fail")  
  
    > [!TIP]
    >  Hemen yazdıktan sonra her bir test başarısız olduğunu doğrulayın. Bu, hiçbir zaman başarısız bir test yazma kolay hata önlemenize yardımcı olur.  
  
3.  Böylece yeni test geçirir DLL kodunuzu geliştirir:  
  
    ```cpp  
    #include <math.h>  
    ...  
    double CRootFinder::SquareRoot(double v)  
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
  
4.  Çözümü derlemek ve Test Explorer'da seçin **tümünü Çalıştır**.  
  
     Her iki testleri geçirin.  
  
     ![Birim Test Gezgini &#45; Geçirilen aralığı Test](../test/media/utecpp12.png "UteCpp12")  
  
    > [!TIP]
    >  Kod, aynı anda testleri bir ekleyerek geliştirin. Tüm testler her yinelemeden sonra başarılı olduğundan emin olun.  
  
##  <a name="debug"></a>Başarısız test hata ayıklama  
  
1.  Başka bir test ekleyin:  
  
    ```cpp    
    #include <stdexcept>  
    ...  
    // Verify that negative inputs throw an exception.  
    TEST_METHOD(NegativeRangeTest)  
    {  
      wchar_t message[200];  
      CRootFinder rooter;  
      for (double v = -0.1; v > -3.0; v = v - 0.5)  
      {  
        try   
        {  
          // Should raise an exception:  
          double result = rooter.SquareRoot(v);  
  
          _swprintf(message, L"No exception for input %g", v);  
          Assert::Fail(message, LINE_INFO());  
        }  
        catch (std::out_of_range ex)  
        {  
          continue; // Correct exception.  
        }  
        catch (...)  
        {  
          _swprintf(message, L"Incorrect exception for %g", v);  
          Assert::Fail(message, LINE_INFO());  
        }  
      }  
    }  
    ```  
  
2.  Çözümü derlemek ve seçin **tümünü Çalıştır**.  
  
3.  Başarısız test açın (veya çift tıklatın).  
  
     Başarısız onaylama vurgulanır. Hata iletisi Test Gezgini ayrıntı bölmesinde görünür olur.  
  
     ![Başarısız NegativeRangeTests](../test/media/ute_cpp_testexplorer_negativerangetest_fail.png "UTE_Cpp_TestExplorer_NegativeRangeTest_Fail")  
  
4.  Neden sınama başarısız görmek için işleviyle adım:  
  
    1.  SquareRoot işlevi başlangıcında bir kesme noktası ayarlayın.  
  
    2.  Başarısız test kısayol menüsünden seçin **seçili Testlerde Hata Ayıkla**.  
  
         Çalıştır kesme noktasında durduğunda kod boyunca adım.  
  
5.  Kodu geliştirdiğiniz işlevi ekleyin:  
  
    ```cpp  
  
    #include <stdexcept>  
    ...  
    double CRootFinder::SquareRoot(double v)  
    {  
        // Validate parameter:  
        if (v < 0.0)   
        {  
          throw std::out_of_range("Can't do square roots of negatives");  
        }  
  
    ```  
  
6.  Tüm testler şimdi geçirin.  
  
     ![Tüm sınamaları geçmesi](../test/media/ute_ult_alltestspass.png "UTE_ULT_AllTestsPass")  
  
> [!TIP]
>  Tek tek testlerin herhangi bir sırayla çalıştırmak engelleyen bağımlılık varsa, paralel test yürütmesi ile Aç ![UTE &#95;parallelicon &#45; küçük](../test/media/ute_parallelicon-small.png "UTE_parallelicon küçük") iki durumlu düğme araç çubuğunda. Bu, tüm testleri çalıştırmak için geçen süre önemli ölçüde azaltabilir.  
  
##  <a name="refactor"></a>Testleri değiştirmeden kodu yeniden düzenleyin  
  
1.  SquareRoot işlevi merkezi hesaplamadaki basitleştirmek:  
  
    ```  
    // old code:  
    //   result = result - (result*result - v)/(2*result);  
    // new code:  
         result = (result + v/result)/2.0;  
  
    ```  
  
2.  Çözümü derlemek ve seçin **tümünü Çalıştır**, bir hata sunulmuştur değil olduğunu doğrulayın.  
  
    > [!TIP]
    >  Birim testleri iyi bir dizi kodu değiştirdiğinizde, hatalar sunulmuştur değil, güven verir.  
    >   
    >  Diğer değişiklikler ayrı yeniden düzenleme tutun.  
  
## <a name="next-steps"></a>Sonraki adımlar  
  
-   **Yalıtım.** Çoğu DLL'leri, veritabanları ve diğer DLL'ler gibi diğer alt sistemleri bağlıdır. Bu diğer bileşenleri genellikle paralel olarak geliştirilir. Birim testi diğer bileşenleri henüz kullanılabilir değildir; ancak gerçekleştirilecek izin vermek için sahte yerine olması veya  
  
-   **Yapı doğrulama testleri.** Belirlenen aralıklarda ekibinizin derleme sunucusundaki gerçekleştirilen testleri olabilir. Bu, birkaç takım üyeleri iş tümleştirildiğinde hatalar sunulan değil, sağlar.  
  
-   **İade etme sınar.** Her ekip üyesi kod kaynak denetimine iade etmeden önce bazı testleri gerçekleştirilir zorunlu kılabilir. Genellikle bu yapı doğrulama testlerini eksiksiz bir alt kümesidir.  
  
     Kod kapsamı en düşük düzeyde zorunlu kılabilir.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Mevcut C++ uygulamalarına birim testleri ekleme](../test/unit-testing-existing-cpp-applications-with-test-explorer.md)   
 [Microsoft.VisualStudio.TestTools.CppUnitTestFramework kullanma](../test/using-microsoft-visualstudio-testtools-cppunittestframework.md)   
 [Yerel kodda hata ayıklama](../debugger/debugging-native-code.md)   
 [İzlenecek yol: Oluşturma ve dinamik bağlantı kitaplığı (C++) kullanma](/cpp/build/walkthrough-creating-and-using-a-dynamic-link-library-cpp)   
 [İçeri ve Dışarı Aktarma](/cpp/build/importing-and-exporting)
