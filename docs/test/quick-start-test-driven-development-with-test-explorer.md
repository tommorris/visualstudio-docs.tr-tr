---
title: Visual Studio'da Test Gezgini ile test güdümlü geliştirme
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
ms.technology: vs-ide-test
ms.topic: conceptual
ms.author: gewarren
manager: douge
ms.workload:
- multiple
author: gewarren
ms.openlocfilehash: 83dfee8bc028ff92e01b18d6cb50933b46907354
ms.sourcegitcommit: 58052c29fc61c9a1ca55a64a63a7fdcde34668a4
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/04/2018
ms.locfileid: "34751429"
---
# <a name="quickstart-test-driven-development-with-test-explorer"></a>Hızlı Başlangıç: Test Gezgini ile Test Güdümlü Geliştirme

Birçok artımlı geliştirme adımlarını düzgün çalışmasını kodunuzu tutmaya yardımcı olmak için birim testleri oluşturmanızı öneririz. Bazı üçüncü taraflar tarafından geliştirilen dahil olmak üzere, birim testleri yazmak için kullanabileceğiniz birkaç çerçeveleri vardır. Bazı test çerçevelerini farklı dil ya da platformlar testi için özelleştirilmiş. Test Gezgini birim testlerinde bu çerçeveleri için tek bir arabirim sağlar. Bağdaştırıcılar için en yaygın olarak kullanılan çerçeveleri tarafından kullanılabilir ve diğer çerçeveler için kendi bağdaştırıcıları yazabilirsiniz.

 Test Gezgini Visual Studio'nun önceki sürümleri bulunan birim testi windows yerini alır. Kendi yararlar şunlardır:

-   .NET, yönetilmeyen, veritabanı ve diğer tür tek bir arabirim kullanarak testleri çalıştırın.

-   Kullanım birim test çerçevesi NUnit gibi tercih ettiğiniz veya mstest'i çerçeveleri.

-   Bir pencerede gerek duyduğunuz tüm bilgileri görebilirsiniz.

## <a name="using-test-explorer"></a>Test Gezgini kullanma
 ![Birim Test Gezgini gösterme tümünü Çalıştır düğmesi](../test/media/unittestexplorer-beta-.png)

### <a name="to-run-unit-tests-by-using-test-explorer"></a>Birim testi Gezgini'ni kullanarak Testleri Çalıştır için

1.  Tercih ettiğiniz test çerçeveleri kullanmak birim testleri oluşturun.

     Örneğin, bir test oluşturmak için mstest'i çerçevesi kullanır:

    1.  Bir test projesi oluşturun.

         İçinde **yeni proje** iletişim kutusunda, genişletin **Visual Basic**, **Visual C#**, veya **Visual C++** ve ardından **Test**.

         Seçin **birim testi projesi**.

    2.  Her birim testi bir yöntem olarak yazma. Her test yöntemi ile önek `[TestMethod]` özniteliği.

2.  Tek tek testlerin herhangi bir sırayla çalıştırmak engelleyen bağımlılık varsa, paralel test yürütmesi ile Aç ![UTE&#95;parallelicon&#45;küçük](../test/media/ute_parallelicon-small.png) iki durumlu düğme araç çubuğunda. Bu, tüm testleri çalıştırmak için geçen süre önemli ölçüde azaltabilir.

3.  Menü çubuğunda seçin **Test**, **Birim Testleri Çalıştır**, **tüm testleri**.

     Çözüm oluşturur ve testleri çalıştırın.

     Test Gezgini açılır ve sonuçları özetini görüntüler.

 **Testleri tam listesini görmek için:** Seç **Tümünü Göster** herhangi kategorisinde.

 **Test sonucu ayrıntılarını görmek için:** test Gezgini'nde Test Ayrıntılar bölmesinde özel durum iletileri gibi ayrıntılarını görüntülemek için seçin.

 **Bir test kodu gidin:** test Test Gezgini'nde çift tıklatın veya seçin **açık Test** kısayol menüsünde.

 **Bir test hata ayıklamak için:** bir veya daha fazla testleri için kısayol menüsünü açın ve ardından **seçili Testlerde Hata Ayıkla**.

> [!IMPORTANT]
> Görüntülenen sonuçları için en son çalışır. Renkli sonuçları çubuğu yalnızca çalıştırdığınız testlerin sonuçlarını gösterir. Örneğin, birkaç testleri çalıştırmak ve bunların bazıları başarısız ve yalnızca başarılı testleri çalıştırın, ardından sonuçları çubuğu tüm yeşil gösterir.


> [!NOTE]
> Hiçbir test görünürse, kullanmakta olduğunuz test çerçevesi Test Gezgini bağlanmak için bir bağdaştırıcı yüklediğinizden emin olun. Daha fazla bilgi için bkz: [Test Gezgini ile farklı Test çerçevelerini kullanarak](#frameworks).


##  <a name="walkthrough"></a> İzlenecek yol: Bir yöntem geliştirmek için birim testleri kullanma
 Bu kılavuz, C# Microsoft birim testi çerçevesini kullanarak test edilmiş bir yöntem geliştirmek gösterilmiştir. Bu diğer diller için ve diğer test çerçevelerini NUnit gibi kullanmak için kolayca uyarlayabilirsiniz. Daha fazla bilgi için bkz: [farklı Test çerçevelerini kullanarak](#frameworks).

#### <a name="creating-the-test-and-method"></a>Test ve yöntemi oluşturma

1.  Visual C# sınıf kitaplığı projesi oluşturun. Bu proje teslim etmek istiyoruz kodu içerir. Bu örnekte adlı `MyMath`.

2.  Bir Test projesi oluşturun.

    -   İçinde **yeni proje** iletişim kutusunda, seçin **Visual C#**, **Test** ve ardından **birim testi projesi**.

         ![Yeni koduna ve test projeleri](../test/media/unittestexplorerwalk1.png)

3.  Temel test yöntemi yazın. Belirli bir giriş için elde edilen sonucu doğrulayın:

    ```csharp

    [TestMethod]
    public void BasicRooterTest()
    {
      // Create an instance to test:
      Rooter rooter = new Rooter();
      // Define a test input and output value:
      double expectedResult = 2.0;
      double input = expectedResult * expectedResult;
      // Run the method under test:
      double actualResult = rooter.SquareRoot(input);
      // Verify the result:
      Assert.AreEqual(expectedResult, actualResult,
          delta: expectedResult / 100);
    }
    ```

4.  Yöntem testi oluşturun.

    1.  İmleç Yerleştir `Rooter`ve ardından kısayol menüsünden seçin **Generate**, **yeni türü**.

    2.  İçinde **oluştur yeni türü** iletişim kutusu, kümesi **proje** sınıf kitaplığı projesine. Bu örnek, `MyMath`.

    3.  İmleç Yerleştir `SquareRoot`ve ardından kısayol menüsünden seçin **Generate**, **yöntemi saplama**.

5.  Birim testi çalıştırma.

    1.  Üzerinde **Test** menüsünde seçin **Birim Testleri Çalıştır**, **tüm testleri**.

         Çözüm oluşturur ve çalıştırır.

         Test Gezgini açılır ve sonuçları görüntüler.

         Test altında görünür **başarısız testler**.

6.  Test adını seçin.

     Test ayrıntılarını Test Gezgini alt kısmında görüntülenir.

7.  Altında öğeleri seçin **yığın izleme** test başarısız olduğu görmek için.

 ![Birim testi başarısız gösteren Explorer'ı sınayın.](../test/media/unittestexplorerwalkthrough2.png)

 Bu noktada, test ve değiştirecek ve böylece test başarılı bir saplama oluşturdunuz.

#### <a name="after-every-change-make-all-the-tests-pass"></a>Her bir değişiklikten sonra geçirmek tüm testleri olun

1.  İçinde `MyMath\Rooter.cs`, kodu geliştirmek `SquareRoot`:

    ```csharp
    public double SquareRoot(double input)
     {
       return input / 2;
     }
    ```

2.  Test Gezgini seçin **tümünü Çalıştır**.

     Kod oluşturur ve test çalıştırır.

     Test başarılı olur.

     ![Birim Test Gezgini geçirme test gösteriliyor.](../test/media/unittestexplorerwalkthrough3.png)

#### <a name="add-tests-to-extend-the-range-of-inputs"></a>Girdi aralığı genişletmek için testleri ekleme

1.  Her durumda, kodunuzun çalıştığı, güvenini artırmak için geniş bir giriş değerleri deneyin testleri ekleyin.

    > [!TIP]
    > Geçen varolan testler değiştirilmesine kaçının. Bunun yerine, yeni testler ekleyin. Yalnızca kullanıcı gereksinimleri değiştiğinde mevcut testleri değiştirin. Bu ilke kodu genişletmeye çalışırken mevcut işlevselliğini kaybetmeyin emin olmanıza yardımcı olur.

     Test sınıfınızda giriş değerleri aralığı çalıştığında aşağıdaki sınama ekleyin:

    ```csharp
    [TestMethod]
    public void RooterValueRange()
    {
      // Create an instance to test:
      Rooter rooter = new Rooter();
      // Try a range of values:
      for (double expectedResult = 1e-8;
          expectedResult < 1e+8;
          expectedResult = expectedResult * 3.2)
      {
        RooterOneValue(rooter, expectedResult);
      }
    }

    private void RooterOneValue(Rooter rooter, double expectedResult)
    {
      double input = expectedResult * expectedResult;
      double actualResult = rooter.SquareRoot(input);
      Assert.AreEqual(expectedResult, actualResult,
          delta: expectedResult / 1000);
    }
    ```

2.  Test Gezgini seçin **tümünü Çalıştır**.

     İlk testi yine geçirir karşın yeni sınama başarısız olur.

     Hata noktası bulmak için başarısız olan test seçin ve Test Gezgini alt kısmında üst öğesi'nin ardından **yığın izleme**.

3.  Ne sorun olabilir görmek için test altındaki yöntemi inceleyin. İçinde `MyMath.Rooter` sınıfı, kodu yeniden yazma:

    ```
    public double SquareRoot(double input)
    {
      double result = input;
      double previousResult = -input;
      while (Math.Abs(previousResult - result) > result / 1000)
      {
        previousResult = result;
        result = result - (result * result - input) / (2 * result);
      }
      return result;
    }
    ```

4.  Test Gezgini seçin **tümünü Çalıştır**.

     Her iki testleri şimdi geçirin.

#### <a name="add-tests-for-exceptional-cases"></a>Olağanüstü durumlar için testleri ekleme

1.  Negatif girişleri için bir sınama ekleyin:

    ```csharp
    [TestMethod]
     public void RooterTestNegativeInputx()
     {
         Rooter rooter = new Rooter();
         try
         {
             rooter.SquareRoot(-10);
         }
         catch (ArgumentOutOfRangeException e)
         {
             return;
         }
         Assert.Fail();
     }
    ```

2.  Test Gezgini seçin **tümünü Çalıştır**.

     Yöntemin altında döngüler test edin ve el ile iptal edilmesi gerekir.

3.  Seçin **iptal**.

     Test 10 saniye sonra durdurur.

4.  Yöntemi kodu düzeltin:

    ```csharp

    public double SquareRoot(double input)
    {
      if (input <= 0.0)
      {
        throw new ArgumentOutOfRangeException();
      }
    ...
    ```

5.  Test Gezgini seçin **tümünü Çalıştır**.

     Tüm testler geçirin.

#### <a name="refactor-without-changing-tests"></a>Testleri değiştirmeden yeniden Düzenle

1.  Kodu basitleştirmek ancak testleri değiştirmeyin.

    > [!TIP]
    > A *yeniden düzenleme* daha iyi performans Kodu'nu veya kod anlamak daha kolay hale getirmek için amaçlanan bir değişikliktir. Kod davranışını değiştirmek için amaçlanmamıştır ve bu nedenle testleri değiştirilmez.
    >
    > Yeniden düzenleme adımları ayrı ayrı işlevselliğini genişleten adımları gerçekleştirdiğinizden emin öneririz. Değişmeden testleri tutma, yanlışlıkla hatalar yeniden düzenleme sırasında sunulan değil, güven verir.

    ```csharp
    public class Rooter
    {
      public double SquareRoot(double input)
      {
        if (input <= 0.0)
        {
          throw new ArgumentOutOfRangeException();
        }
        double result = input;
        double previousResult = -input;
        while (Math.Abs(previousResult - result) > result / 1000)
        {
          previousResult = result;
          result = (result + input / result) / 2;
          //was: result = result - (result * result - input) / (2*result);
        }
        return result;
      }
    }
    ```

2.  Seçin **çalıştırması**.

     Tüm testler hala geçirin.

     ![Birim testi 3 geçirilen testleri gösteren Gezgini.](../test/media/unittestexplorerwalkthrough4.png)
