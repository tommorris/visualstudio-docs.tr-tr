---
title: Visual C# kodu Visual Studio'da Test birim
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
ms.technology: vs-ide-test
ms.topic: conceptual
ms.author: gewarren
manager: douge
ms.workload:
- uwp
author: gewarren
ms.openlocfilehash: b409e3faa44b19cf0018e770915c8a3868f9ead4
ms.sourcegitcommit: e13e61ddea6032a8282abe16131d9e136a927984
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/26/2018
---
# <a name="unit-testing-visual-c-code"></a>Birim testi Visual C# kodu

Bu konuda, bir UWP uygulamasında bir Visual C# sınıfı için birim testleri oluşturma yöntemlerinden biri açıklanmaktadır. Rooter sınıfı belirsiz anılarınızı sınırı teorik olarak verilen bir sayının kare kökünü tahmini hesaplar işlevi uygulayarak hesaplama gösterir. Matematik uygulama sonra bir kullanıcı fun göstermek için bu işlevi kullanabilirsiniz math ile yapılabilir şey.

Bu konu, birim geliştirme ilk adımı olarak testi kullanımı gösterilmiştir. Bu yaklaşım önce test ettiğiniz sistemde belirli bir davranışı doğrular bir test yöntemi yazın ve ardından test başarılı kod yazın. Aşağıdaki yordamlar sırasına göre değişiklikler yaparak, bu strateji ilk yazma, test ve birim testleri yazma istediğiniz kod ters çevirebilirsiniz.

Bu konu ayrıca tek bir Visual Studio çözümü ve birim testleri ve test etmek istediğiniz DLL için ayrı projeleri oluşturur. Birim testleri doğrudan DLL projesinde içerebilir veya birim testleri ve DLL için ayrı çözümler oluşturabilirsiniz.

## <a name="create-the-solution-and-the-unit-test-project"></a>Çözüm ve birim testi projesi oluşturma

1. Üzerinde **dosya** menüsünde seçin **yeni** > **proje...** .

2. İçinde **yeni proje** iletişim kutusunda, genişletin **yüklü** > **Visual C#** ve **Windows Evrensel**. Ardından **boş uygulama** proje şablonları listesinden.

3. Proje adı `Maths` ve emin olun **çözüm için dizin oluştur** seçilir.

4. Çözüm Gezgini'nde, çözüm adı seçin, seçin **Ekle** kısayol menüsünden ve ardından **yeni proje**.

5. İçinde **yeni proje** iletişim kutusunda, genişletin **yüklü**, ardından **Visual C#** ve seçin **Windows Evrensel**. Ardından **birim testi uygulama (Evrensel Windows)** proje şablonları listesinden.

6. Açık *UnitTest1.cs* Visual Studio düzenleyicisinde.

   ```csharp
   using System;
   using System.Collections.Generic;
   using System.Linq;
   using System.Text;
   using Microsoft.VisualStudio.TestTools.UnitTesting;
   using Maths;

   namespace RooterTests
   {
       [TestClass]
       public class UnitTest1

           [TestMethod]
           public void TestMethod1()
           {

           }
   ```

   Aşağıdakilere dikkat edin:

   - Her sınama kullanılarak tanımlanmış <xref:Microsoft.VisualStudio.TestTools.UnitTesting.TestMethodAttribute> özniteliği. Test yöntemi boş döndürmeleri gerektiği ve herhangi bir parametresi olamaz.

   - Test yöntemleri ile donatılmış bir sınıf olmalıdır <xref:Microsoft.VisualStudio.TestTools.UnitTesting.TestClassAttribute> özniteliği.

        Testler, her test sınıfının bir örneği oluşturulur. Test yöntemleri belirtilmeyen bir sırayı denir.

   - Önce ve sonra her modül, sınıf veya yöntemin çağrılması özel yöntemler tanımlayabilirsiniz. Daha fazla bilgi için bkz: [mstest'i framework birim testlerinde kullanma](../test/using-microsoft-visualstudio-testtools-unittesting-members-in-unit-tests.md).

## <a name="verify-that-the-tests-run-in-test-explorer"></a>Testleri Test Explorer'da çalıştığını doğrulayın

1. Bazı test kodu TestMethod1 içinde eklemek **UnitTest1.cs** dosyası:

   ```csharp
   [TestMethod]
   public void TestMethod1()
   {
       Assert.AreEqual(0, 0);
   }
   ```

   Dikkat <xref:Microsoft.VisualStudio.TestTools.UnitTesting.Assert> sınıfı, test yöntemleri sonuçlarında doğrulamak için kullanabileceğiniz çeşitli statik yöntemler sağlar.

2. Üzerinde **Test** menüsünde seçin **çalıştırmak** ve ardından **tümünü Çalıştır**.

   Test projesi oluşturur ve çalıştırır. Test Gezgini penceresi görünür ve test altında listelenen **testleri geçti**. Pencerenin altındaki Özet bölmesinde seçilen testi hakkında ek ayrıntılar sağlar.

   ![Test Gezgini](../test/media/ute_cpp_testexplorer_testmethod1.png)

## <a name="add-the-rooter-class-to-the-maths-project"></a>Matematik projeye Rooter sınıfı ekleme

1. Çözüm Gezgini'nde seçin **matematik** proje adı. Kısayol menüsünden **Ekle**ve ardından **sınıfı**.

2. Sınıf dosya adı *Rooter.cs*.

3. Rooter sınıfa aşağıdaki kodu ekleyin *Rooter.cs* dosyası:

   ```csharp
   public Rooter()
   {
   }

   // estimate the square root of a number
   public double SquareRoot(double x)
   {
       return 0.0;
   }
   ```

   `Rooter` Sınıfı bir oluşturucu bildirir ve `SquareRoot` tahmin yöntemi.

4. `SquareRoot` Yöntemdir en az bir uygulama yalnızca, test Kurulum temel yapısını test etmek yeterli.

## <a name="couple-the-test-project-to-the-app-project"></a>Birkaç uygulama projesi için test projesi

1. Matematik uygulama referansı RooterTests projeye ekleyin.

    1. Çözüm Gezgini'nde seçin **RooterTests** proje ve ardından **Başvuru Ekle...**  kısayol menüsünde.

    2. İçinde **Başvuru Ekle - RooterTests** iletişim kutusunda, genişletin **çözüm** ve **projeleri**. Ardından **matematik** öğesi.

        ![Matematik projesine bir başvuru ekleyin](../test/media/ute_cs_windows_addreference.png)

2. Kullanarak bir ekleme deyimi *UnitTest1.cs* dosyası:

    1. Açık *UnitTest1.cs*.

    2. Bu kodu ekleyin `using Microsoft.VisualStudio.TestTools.UnitTesting;` satır:

       ```csharp
       using Maths;
       ```

3. Rooter işlevini kullanan bir test ekleyin. Aşağıdaki kodu ekleyin *UnitTest1.cs*:

   ```csharp
   [TestMethod]
   public void BasicTest()
   {
       Maths.Rooter rooter = new Rooter();
       double expected = 0.0;
       double actual = rooter.SquareRoot(expected * expected);
       double tolerance = .001;
       Assert.AreEqual(expected, actual, tolerance);
   }
   ```

4. Çözümü oluşturun.

   Yeni test Test Gezgininde görünür **testleri değil Çalıştır** düğümü.

5. Test Gezgini seçin **tümünü Çalıştır**.

   ![Temel sınaması başarılı oldu](../test/media/ute_cpp_testexplorer_basictest.png)

Test ve kod projeleri ayarlayabilir ve kod projesinde işlevlerini Çalıştırma testleri çalıştırabilirsiniz doğrulandı. Şimdi, gerçek testleri ve kod yazmaya başlayabilirsiniz.

## <a name="iteratively-augment-the-tests-and-make-them-pass"></a>Tekrarlayarak testleri büyütmek ve onları geçirin

1. Yeni bir test ekleyin:

   ```csharp
   [TestMethod]
   public void RangeTest()
   {
       Rooter rooter = new Rooter();
       for (double v = 1e-6; v < 1e6; v = v * 3.2)
       {
           double expected = v;
           double actual = rooter.SquareRoot(v*v);
           double tolerance = ToleranceHelper(expected);
           Assert.AreEqual(expected, actual, tolerance);
       }
   }
   ```

   > [!TIP]
   > Başarılı olan testler değiştirmemenizi öneririz. Bunun yerine, yeni bir test ekleyin, kod test başarılı şekilde güncelleştirin ve sonra başka bir test ekleyin ve benzeri.
   >
   > Kullanıcılarınızın kendi gereksinimleri değiştiğinde, artık doğru testleri devre dışı bırakın. Yeni testleri yazmak ve bunları bir seferde bir artımlı aynı şekilde çalışır duruma getirin.

2. Test Gezgini seçin **tümünü Çalıştır**.

3. Sınama başarısız olur.

   ![RangeTest başarısız](../test/media/ute_cpp_testexplorer_rangetest_fail.png)

   > [!TIP]
   > Hemen yazdıktan sonra her bir test başarısız olduğunu doğrulayın. Bu, hiçbir zaman başarısız bir test yazma kolay hata önlemenize yardımcı olur.

4. Yeni test sağlayacak şekilde test altındaki kodun geliştirin. Değişiklik `SquareRoot` işlevi *Rooter.cs* bu:

   ```csharp
   public double SquareRoot(double x)
   {
       double estimate = x;
       double diff = x;
       while (diff > estimate / 1000)
       {
           double previousEstimate = estimate;
           estimate = estimate - (estimate * estimate - x) / (2 * estimate);
           diff = Math.Abs(previousEstimate - estimate);
       }
       return estimate;
   }
   ```

5. Çözümü derlemek ve ardından **Test Gezgini**, seçin **tümünü Çalıştır**.

   Tüm üç testleri şimdi geçirin.

> [!TIP]
> Kod, aynı anda testleri bir ekleyerek geliştirin. Tüm testler her yinelemeden sonra başarılı olduğundan emin olun.

## <a name="debug-a-failing-test"></a>Başarısız test hata ayıklama

1. Başka bir testine ekleme *UnitTest1.cs*:

    ```csharp
    // Verify that negative inputs throw an exception.
    [TestMethod]
    public void NegativeRangeTest()
    {
        string message;
        Rooter rooter = new Rooter();
        for (double v = -0.1; v > -3.0; v = v - 0.5)
        {
            try
            {
                // Should raise an exception:
                double actual = rooter.SquareRoot(v);

                message = String.Format("No exception for input {0}", v);
                Assert.Fail(message);
            }
            catch (ArgumentOutOfRangeException ex)
            {
                continue; // Correct exception.
            }
            catch (Exception e)
            {
                message = String.Format("Incorrect exception for {0}", v);
                Assert.Fail(message);
            }
        }
    }
    ```

2. İçinde **Test Gezgini**, seçin **tümünü Çalıştır**.

   Sınama başarısız olur. Test adı seçin **Test Gezgini**. Başarısız onaylama vurgulanır. Hata iletisi ayrıntı bölmesinde görünür **Test Gezgini**.

   ![NegativeRangeTests başarısız oldu](../test/media/ute_cpp_testexplorer_negativerangetest_fail.png)

3. Neden sınama başarısız görmek için işleviyle adım:

    1. Başlangıcında bir kesme noktası belirleyerek `SquareRoot` işlevi.

    2. Başarısız test kısayol menüsünden seçin **seçili Testlerde Hata Ayıkla**.

        Çalıştır kesme noktasında durduğunda kod boyunca adım.

    3. Kodu özel durumu yakalamak için Rooter yöntemine ekleyin:

        ```csharp
        public double SquareRoot(double x)
        {
            if (x < 0.0)
            {
                throw new ArgumentOutOfRangeException();
        }
        ```

4. Test Gezgini seçin **tümünü Çalıştır** test düzeltilmiş yöntemi ve bir gerileme sunulan henüz emin olun.

Tüm testler şimdi geçirin.

![Tüm sınamaları geçmesi](../test/media/ute_ult_alltestspass.png)

## <a name="refactor-the-code"></a>Kodu yeniden düzenleyin

**SquareRoot işlevi merkezi hesaplamadaki basitleştirin.**

1. Sonuç uygulamasını değiştirin

    ```csharp
    // old code
    //result = result - (result*result - v)/(2*result);
    // new code
    result = (result + v/result) / 2.0;
    ```

2. Seçin **tümünü Çalıştır** test işlenmiş yöntemi ve bir gerileme sunulan henüz emin olun.

> [!TIP]
> İyi birim testleri kararlı bir dizi kodu değiştirdiğinizde, hatalar sunulmuştur değil, güven verir.

**Yinelenen kod ortadan kaldırmak için test kodu yeniden düzenleyin.**

Unutmayın `RangeTest` yöntemi sabit kodları, payda `tolerance` geçirilir değişkeni <xref:Microsoft.VisualStudio.TestTools.UnitTesting.Assert> yöntemi. Aynı dayanıklılık hesaplama kullanmak Ek testler eklemeyi planlıyorsanız, sabit kodlanmış bir değer birden fazla konumda kullanımını hatalarına neden.

1. Özel bir yöntem tolerans değerini hesaplamak için Unit1Test sınıfına ekleyin ve bu yöntem yerine çağırın.

    ```csharp
    private double ToleranceHelper(double expected)
    {
        return expected / 1000;
    }

    ...

    [TestMethod]
    public void RangeTest()
    {
        ...
        // old code
        // double tolerance = expected/1000;
        // new code
        double tolerance = ToleranceHelper(expected);
        Assert.AreEqual(expected, actual, tolerance);
    }
    ...
    ```

2. Seçin **tümünü Çalıştır** işlenmiş yöntemi test ve hata sunulan henüz emin olun.

> [!NOTE]
> Görüntülenmesini istemediğiniz bir test sınıfına bir yardımcı yöntem eklerseniz **Test Gezgini**, eklemeyin <xref:Microsoft.VisualStudio.TestTools.UnitTesting.TestMethodAttribute> özniteliği yöntemi.