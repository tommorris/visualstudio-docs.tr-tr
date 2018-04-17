---
title: Visual Studio 2017 Test Canlı birimi ile kodunuzu test öğrenin | Microsoft Docs | Microsoft Docs
ms.date: 08/31/2017
ms.technology: vs-ide-test
ms.topic: conceptual
helpviewer_keywords:
- Visual Studio ALM
- Live Unit Testing
author: rpetrusha
ms.author: ronpet
ms.workload:
- dotnet
ms.openlocfilehash: bd2bc43081418844f03b5cb58af46f6888d57652
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/16/2018
---
# <a name="get-started-with-live-unit-testing-in-visual-studio"></a>Visual Studio'da birim testi Canlı kullanmaya başlama

Visual Studio çözümünde Canlı birim testi'ı etkinleştirdiğinizde, birim testi Canlı görsel olarak test kapsamı ve testlerinizi durumunu gösterir. Kodunuzu değiştirmek olduğunda da dinamik testleri yürütür. Değişiklikleri kodunuzu kıran anında bildirim sağlar ve Ek testler gerekli olan alanları belirtir.

Dinamik birim testi .NET Framework veya .NET Core hedefleyen çözümler test etmek için kullanılabilir. Bu öğreticide, Canlı birim testi hedefleyen .NET standart bir basit sınıf kitaplığı oluşturarak kullanmayı öğreneceksiniz ve test etmek için .NET Core hedefleyen bir mstest'i projesi oluşturacaksınız.

# <a name="ctabcsharp"></a>[C#](#tab/csharp)
C# geçerli çözümü yüklenebilir [MicrosoftDocs/Visual Studio-belgeleri](https://github.com/MicrosoftDocs/visualstudio-docs/tree/master/docs/test/samples/csharp/UtilityLibraries/) bağlantıların github'da.
# <a name="visual-basictabvisual-basic"></a>[Visual Basic](#tab/visual-basic)
Visual Basic geçerli çözümü yüklenebilir [MicrosoftDocs/Visual Studio-belgeleri](https://github.com/MicrosoftDocs/visualstudio-docs/tree/master/docs/test/samples/visual-basic/UtilityLibraries/) bağlantıların github'da.

---

## <a name="prerequisites"></a>Önkoşullar

Bu öğreticide, Visual Studio 2017 Enterprise Edition sürümü 15.3 .NET Core 2.0 yüküyle yüklediğiniz gerektirir.

## <a name="create-the-solution-and-the-class-library-project"></a>Çözüm ve sınıf kitaplığı proje oluşturma

Begin adlı bir Visual Studio çözümü oluşturarak `UtilityLibraries` tek bir .NET standart sınıf kitaplığı proje, oluşur `StringLibrary`. Yazabileceğiniz `StringLibrary` C# veya Visual Basic.

Yalnızca bir veya daha fazla projeleri için bir kapsayıcı çözümüdür. Çözüm oluşturmak için Visual Studio 2017 açın ve aşağıdakileri yapın:

1. Seçin **dosya**, **yeni**, **proje** en üst düzey Visual Studio menüsünde.

1. İçinde **yeni proje** iletişim kutusunda, genişletin **diğer proje türleri** düğümü ve select **Visual Studio çözümleri**. Seçin **boş çözüm** sağ bölmede şablon ve girin `UtilityLibraries` içinde **adı** metin kutusunda, aşağıdaki şekilde gösterildiği gibi:

   ![** Yeni Proje ** iletişim](./media/lut-start/new-solution.png)

1. Seçin **Tamam** çözümü oluşturmak için.

Çözüm oluşturduğunuza göre adlı bir sınıf kitaplığı oluşturacaksınız `StringLibrary` Dizelerle çalışmaya yönelik genişletme yöntemleri sayısını içerir.

# <a name="ctabcsharp"></a>[C#](#tab/csharp)
1. İçinde **Çözüm Gezgini**, sağ tıklayın `UtilityLibraries` çözümü ve select **Ekle**, **yeni proje**.

1. İçinde **Yeni Proje Ekle** iletişim kutusunda, seçin C# düğümünü, ardından **.NET standart**.

   > [!NOTE]
   > Bizim kitaplığı .NET standart yerine belirli bir .NET uygulama hedeflediğinden, bu sürümünü .NET standardını destekleyen herhangi bir .NET uygulamasından çağrılabilir. Daha fazla bilgi için bkz: [.NET standart](/dotnet/standard/net-standard).

1. Seçin **sınıf kitaplığı (.NET standart)** sağ bölmede, şablon ve girin `StringLibrary` içinde **adı** metin kutusunda, aşağıdaki şekilde gösterildiği gibi:

   ![** Ekleme yeni proje ** iletişim](./media/lut-start/add-project-cs.png)

1. Seçin **Tamam** projesi oluşturmak için.

1. Tüm kod penceresinde var olan kodu aşağıdaki kodla değiştirin:

   [!code-csharp[StringLibrary source code](samples/csharp/utilitylibraries/stringlibrary/class1.cs)]

   `StringLibrary` üç statik yöntemler vardır:

      - `StartsWithUpper` döndürür `true` Aksi halde, bir dizeyi bir büyük harf karakter ile; başlıyorsa döndürür `false`.

      - `StartsWithLower`döndürür `true` Aksi halde, bir dizeyi bir küçük harf ile; başlıyorsa döndürür `false`.

      - `HasEmbeddedSpaces` döndürür `true` bir katıştırılmış boşluk karakteri; bir dize içeriyorsa, aksi takdirde, döndürür `false`.

1.  Seçin **yapı**, **yapı çözümü** en üst düzey Visual Studio menüsünde. Visual Studio başarıyla kitaplığınızın oluşturması gerekir.

# <a name="visual-basictabvisual-basic"></a>[Visual Basic](#tab/visual-basic)
1. İçinde **Çözüm Gezgini**, sağ tıklayın `UtilityLibraries` çözümü ve select **Ekle**, **yeni proje**.

1. İçinde **Yeni Proje Ekle** iletişim kutusunda, Visual Basic düğümünü seçin ve ardından **.NET standart**.

   > [!NOTE]
   > Bizim kitaplığı .NET standart yerine belirli bir .NET uygulama hedeflediğinden, bu sürümünü .NET standardını destekleyen herhangi bir .NET uygulamasından çağrılabilir. Daha fazla bilgi için bkz: [.NET standart](/dotnet/standard/net-standard).

1. Seçin **sınıf kitaplığı (.NET standart)** sağ bölmede, şablon ve girin `StringLibrary` içinde **adı** metin kutusunda, aşağıdaki şekilde gösterildiği gibi:

   ![** Ekleme yeni proje ** iletişim](./media/lut-start/add-project-vb.png)

1. Seçin **Tamam** projesi oluşturmak için.

1. Tüm kod penceresinde var olan kodu aşağıdaki kodla değiştirin:

   [!code-vb[StringLibrary source code](samples/visual-basic/utilitylibraries/stringlibrary/class1.vb)]

   `StringLibrary` üç statik yöntemler vardır:

      - `StartsWithUpper` döndürür `true` Aksi halde, bir dizeyi bir büyük harf karakter ile; başlıyorsa döndürür `false`.

      - `StartsWithLower`döndürür `true` Aksi halde, bir dizeyi bir küçük harf ile; başlıyorsa döndürür `false`.

      - `HasEmbeddedSpaces` döndürür `true` bir katıştırılmış boşluk karakteri; bir dize içeriyorsa, aksi takdirde, döndürür `false`.

1. StringLibrary projeye sağ tıklayın **Çözüm Gezgini** seçip **özellikleri**. İçinde **uygulama** sekmesinde, metinde silme **kök ad alanı** metin kutusunda, aşağıdaki şekilde gösterildiği gibi. Kök ad tarafından tanımlanan [Namespace deyimi](/dotnet/visual-basic/language-reference/statements/namespace-statement) kaynak kodundaki.

   ![Visual Basic projesinde için Proje Özellikleri iletişim kutusu](./media/lut-start/vb-properties.png)

1.  Seçin **yapı**, **yapı çözümü** en üst düzey Visual Studio menüsünde. Visual Studio başarıyla kitaplığınızın oluşturması gerekir.

---

## <a name="create-the-test-project"></a>Testi projesi oluşturma

Test etmek için birim testi projesi oluşturmak için sonraki adımdır `StringLibrary` kitaplığı. Birim testleri, aşağıdaki adımları gerçekleştirerek oluşturun:

# <a name="ctabcsharp"></a>[C#](#tab/csharp)
1. İçinde **Çözüm Gezgini**, sağ tıklayın `UtilityLibraries` çözümü ve select **Ekle**, **yeni proje**.

1. İçinde **Yeni Proje Ekle** iletişim kutusunda, seçin C# düğümünü, ardından **.NET Core**.

   > [!NOTE]
   > Sınıf kitaplığı olarak aynı dilde birim testleri yazmak zorunda değildir.

1. Seçin **birim testi projesi (.NET Core)** sağ bölmede, şablon ve girin `StringLibraryTests` içinde **adı** metin kutusunda, aşağıdaki şekilde gösterildiği gibi:

   ![** Birim testi projesi için ekleme yeni proje ** iletişim kutusu](./media/lut-start/add-unit-test-cs.png)

1. Seçin **Tamam** projesi oluşturmak için.

   > [!NOTE]
   > Bu başlangıç öğreticisinde Canlı birim testi mstest'i testi çerçevesi ile kullanır. Ayrıca, xUnit ve NUnit test çerçevelerini kullanabilirsiniz.

1. Birim testi projesi otomatik olarak test ediyor sınıf kitaplığı erişemez. Sınıf kitaplığı projesine bir başvuru ekleyerek test kitaplığı erişimi verin. Bunu yapmak için sağ `StringLibraryTests` proje ve seçin **Ekle**, **başvuru**. İçinde **başvuru Yöneticisi** iletişim kutusunda, emin olun **çözüm** sekmesi seçili ve select `StringLibrary` , aşağıdaki çizimde gösterildiği gibi proje.

   ![** Başvuru Yöneticisi ** iletişim](./media/lut-start/add-reference.png)

1. Aşağıdaki kod ile şablon tarafından sağlanan Demirbaş birim test kodu değiştirin:

   [!code-csharp[StringLibraryTest source code](samples/snippets/csharp/lut-start/unittest1.cs)]

1. Projenizi seçerek kaydetmek **kaydetmek** araç çubuğunda simge.

1. Birim testi için kodu bazı ASCII olmayan karakterler içeriyor, Visual Studio bize biz dosyayı kendi varsayılan ASCII biçiminde kaydederseniz bazı karakterler kaybolacak uyarmak için aşağıdaki iletişim kutusunu görüntüler. Seçin **diğer kodlamayla kaydetme** düğmesi.

   ![Dosya kodlama seçin](media/lut-start/ascii-encoding.png)

1. İçinde **kodlama** aşağı açılan listesi **öncelikli kaydetme seçenekleri** iletişim kutusunda, seçin **Unicode (UTF-8 imza olmadan) - Codepage 65001**, aşağıdaki şekilde gösterildiği gibi:

   ![UTF-8 kodlaması seçme](media/lut-start/utf8-encoding.png)

1. Birim testi projesi tarafından derleme **yapı**, **çözümü yeniden derle** en üst düzey Visual Studio menüsünde.

# <a name="visual-basictabvisual-basic"></a>[Visual Basic](#tab/visual-basic)

1. İçinde **Çözüm Gezgini**, sağ tıklayın `UtilityLibraries` çözümü ve select **Ekle**, **yeni proje**.

1. İçinde **Yeni Proje Ekle** iletişim kutusunda, Visual Basic düğümünü seçin ve ardından **.NET Core**.

   > [!NOTE]
   > Sınıf kitaplığı olarak aynı dilde birim testleri yazmak zorunda değildir.

1. Seçin **birim testi projesi (.NET Core)** sağ bölmede, şablon ve girin `StringLibraryTests` içinde **adı** metin kutusunda, aşağıdaki şekilde gösterildiği gibi:

   ![** Birim testi için ekleme yeni proje ** iletişim kutusu](./media/lut-start/add-unit-test-vb.png)

1. Seçin **Tamam** projesi oluşturmak için.

   > [!NOTE]
   > Bu başlangıç öğreticisinde Canlı birim testi mstest'i testi çerçevesi ile kullanır. Ayrıca, xUnit ve NUnit test çerçevelerini kullanabilirsiniz.

1. Birim testi projesi otomatik olarak test ediyor sınıf kitaplığı erişemez. Sınıf kitaplığı projesine bir başvuru ekleyerek test kitaplığı erişimi verin. Bunu yapmak için sağ `StringLibraryTests` proje ve seçin **Ekle**, **başvuru**. İçinde **başvuru Yöneticisi** iletişim kutusunda, emin olun **çözüm** sekmesi seçili ve select `StringLibrary` , aşağıdaki çizimde gösterildiği gibi proje.

   ![** Başvuru Yöneticisi ** iletişim](./media/lut-start/add-reference.png)

1. Aşağıdaki kod ile şablon tarafından sağlanan Demirbaş birim test kodu değiştirin:

   [!code-vb[StringLibraryTest source code](samples/snippets/visual-basic/lut-start/unittest1.vb)]

1. Projenizi seçerek kaydetmek **kaydetmek** araç çubuğunda simge.

1. Birim testi için kodu bazı ASCII olmayan karakterler içeriyor, Visual Studio bize biz dosyayı kendi varsayılan ASCII biçiminde kaydederseniz bazı karakterler kaybolacak uyarmak için aşağıdaki iletişim kutusunu görüntüler. Seçin **diğer kodlamayla kaydetme** düğmesi.

   ![Dosya kodlama seçin](media/lut-start/ascii-encoding.png)

1. İçinde **kodlama** aşağı açılan listesi **öncelikli kaydetme seçenekleri** iletişim kutusunda, seçin **Unicode (UTF-8 imza olmadan) - Codepage 65001**, aşağıdaki şekilde gösterildiği gibi:

   ![UTF-8 kodlaması seçme](media/lut-start/utf8-encoding.png)

1. Birim testi projesi tarafından derleme **yapı**, **çözümü yeniden derle** en üst düzey Visual Studio menüsünde.

---

Bir sınıf kitaplığı gibi bazı Birim testleri için oluşturduğunuz. Birim testi Canlı kullanmak için gerekli başlangıç kuralları şimdi tamamladınız.

## <a name="enable-live-unit-testing"></a>Dinamik birim testi etkinleştir

Böylece şimdiye kadar testler için yazdığınız rağmen `StringLibrary` sınıf kitaplığı, henüz yürüttüğünüz bunları. Etkinleştirdikten sonra canlı birim testi bunları otomatik olarak yürütür. Bunu yapmak için aşağıdakileri yapın:

1. İsteğe bağlı olarak, kodu içeren kod penceresi seçin `StringLibrary`. Bir C# projesi için class1.cs ya da bir Visual Basic proje Class1.vb'ye budur. (Bu adım, Canlı birim testi etkinleştirdikten sonra testlerinizi sonucu ve kod kapsamı kapsamını görsel olarak inceleyin olanak tanır.)

1. Seçin **Test**, **Canlı birim testi**, **Başlat** en üst düzey Visual Studio menüsünde.

1. Visual Studio Canlı birim, otomatik olarak tüm testleri çalıştırır testi başlatır.

Testlerinizi çalıştıran tamamlandığında **Test Gezgini** genel sonuçları ve tek tek testlerin sonuçlarını görüntüler. Ayrıca, kod penceresi grafik test kod kapsamı ve testleri için sonucu görüntüler. Aşağıdaki şekilde gösterildiği gibi tüm üç testi başarıyla yürütüldü. Ayrıca bizim testleri içindeki tüm kod yollarının ele aldıktan gösterir `StartsWithUpper` yöntemi ve başarıyla yürütüldü bu testler tüm ("✓" Yeşil onay işaretiyle belirtilir). Son olarak, bu diğer yöntemlerle hiçbiri gösterir `StringLibrary` (hangi mavi bir satırda, "➖" belirtilir) kod kapsamı vardır.

# <a name="ctabcsharp"></a>[C#](#tab/csharp)
![Canlı birim testi başlattıktan Test Gezgini ve kod penceresi](media/lut-start/lut-results-cs.png)

# <a name="visual-basictabvisual-basic"></a>[Visual Basic](#tab/visual-basic)
![Canlı birim testi başlattıktan Test Gezgini ve kod penceresi](media/lut-start/lut-results-vb.png)

---

Kod penceresinde belirli kod kapsamı simgesini seçerek kapsamı ve test sonuçları da test hakkında daha ayrıntılı bilgi elde edebilirsiniz. Bu ayrıntılı incelemek için aşağıdakileri yapın:

# <a name="ctabcsharp"></a>[C#](#tab/csharp)
1. Yeşil onay işareti okur satırında tıklayın `if (String.IsNullOrWhiteSpace(s))` içinde `StartsWithUpper` yöntemi. Aşağıdaki şekilde gösterildiği gibi canlı birim testi üç sınama kod satırını kapsar ve tüm başarıyla yürütüldü olduğunu gösterir.

   !['If' koşullu deyim için kod kapsamı](media/lut-start/code-coverage-cs1.png)

1. Yeşil onay işareti okur satırında tıklayın `return Char.IsUpper(s[0])` içinde `StartsWithUpper` yöntemi. Aşağıdaki şekilde gösterildiği gibi canlı birim testi yalnızca iki testleri kod satırını kapsar ve tüm başarıyla yürütüldü olduğunu gösterir.

   ![Return deyimi için kod kapsamı](media/lut-start/code-coverage-cs2.png)

# <a name="visual-basictabvisual-basic"></a>[Visual Basic](#tab/visual-basic)
1. Yeşil onay işareti okur satırında tıklayın `If (String.IsNullOrWhiteSpace(s)) Then` içinde `StartsWithUpper` yöntemi. Aşağıdaki şekilde gösterildiği gibi canlı birim testi üç sınama kod satırını kapsar ve tüm başarıyla yürütüldü olduğunu gösterir.

   !['If' koşullu deyim için kod kapsamı](media/lut-start/code-coverage-vb1.png)

1. Yeşil onay işareti okur satırında tıklayın `Return Char.IsUpper(s(0))` içinde `StartsWithUpper` yöntemi. Aşağıdaki şekilde gösterildiği gibi canlı birim testi yalnızca iki testleri kod satırını kapsar ve tüm başarıyla yürütüldü olduğunu gösterir.

   ![Return deyimi için kod kapsamı](media/lut-start/code-coverage-vb2.png)

---

Birim testi Canlı tanımlayan ana tamamlanmamış kod kapsamı sorunudur. Bu sonraki bölümde adresi.

## <a name="expand-test-coverage"></a>Test kapsamı genişletin

Birim testleri için genişletme Bu bölümde, `StartsWithLower` yöntemi. Bunu karşın, dinamik birim testi dinamik olarak kodunuzu test etmek devam eder.

Kod Kapsamı genişletmek için `StartsWithLower` yöntemi, aşağıdakileri yapın:

# <a name="ctabcsharp"></a>[C#](#tab/csharp)
1. Aşağıdakileri ekleyin `TestStartsWithLower` ve `TestDoesNotStartWithLower` projenizin test kaynak kodu dosyasının yöntemleri:

    [!code-csharp[StringLibraryTest source code](samples/snippets/csharp/lut-start/unittest2.cs#1)]

1. Değiştirme `DirectCallWithNullOrEmpty` yöntemini çağırdıktan hemen sonra aşağıdaki kodu ekleyerek [ `Microsoft.VisualStudio.TestTools.UnitTesting.Assert.IsFalse` ](/dotnet/api/microsoft.visualstudio.testtools.unittesting.assert.isfalse) yöntemi.

    [!code-csharp[StringLibraryTest source code](samples/snippets/csharp/lut-start/unittest2.cs#2)]

1. Kaynak kodunuz değiştirdiğinizde dinamik birim testi yeni ve değiştirilen testleri otomatik olarak yürütür. Aşağıdaki şekil olarak **Test Gezgini** gösterir, tüm eklediğiniz iki ve değiştirdiğiniz, biri de dahil olmak üzere testin başarılı.

   ![Genişletme sonra Test Gezgini kapsamı sınayın.](media/lut-start/test-dynamic.png)

1. Geçiş için kaynak kodunu içeren bir pencere için `StringLibrary` sınıfı. Canlı bizim kod kapsamı için genişletilmiş birim testi şimdi gösterir `StartsWithLower` yöntemi.

    ![StartsWithLower yöntemi için kod kapsamı](media/lut-start/lut-extended-cs.png)

# <a name="visual-basictabvisual-basic"></a>[Visual Basic](#tab/visual-basic)
1. Aşağıdakileri ekleyin `TestStartsWithLower` ve `TestDoesNotStartWithLower` projenizin test kaynak kodu dosyasının yöntemleri:

    [!code-vb[StringLibraryTest source code](samples/snippets/visual-basic/lut-start/unittest2.vb#1)]

1. Değiştirme `DirectCallWithNullOrEmpty` yöntemini çağırdıktan hemen sonra aşağıdaki kodu ekleyerek [ `Microsoft.VisualStudio.TestTools.UnitTesting.Assert.IsFalse` ](/dotnet/api/microsoft.visualstudio.testtools.unittesting.assert.isfalse) yöntemi.

    [!code-vb[StringLibraryTest source code](samples/snippets/visual-basic/lut-start/unittest2.vb#2)]

1. Kaynak kodunuz değiştirdiğinizde dinamik birim testi yeni ve değiştirilen testleri otomatik olarak yürütür. Aşağıdaki şekil olarak **Test Gezgini** gösterir, tüm eklediğiniz iki ve değiştirdiğiniz, biri de dahil olmak üzere testin başarılı.

   ![Genişletme sonra Test Gezgini kapsamı sınayın.](media/lut-start/test-dynamic.png)

1. Geçiş için kaynak kodunu içeren bir pencere için `StringLibrary` sınıfı. Canlı bizim kod kapsamı için genişletilmiş birim testi şimdi gösterir `StartsWithLower` yöntemi.

    ![StartsWithLower için kod kapsamı](media/lut-start/lut-extended-vb.png)

---

Bazı durumlarda, başarılı testlerinde **Test Gezgini** grileştirilmiş olabilir. Bir test yürütülmekte veya test olduğundan kod değişiklikleri yeniden çalıştırılmadı son yürütüldüğü beri test etkileyebilecek gösterir.

Şu ana kadar tüm bizim testleri sahip başarılı. Sonraki bölümde, test hatası nasıl işleneceğini inceleyeceğiz.

## <a name="handling-a-test-failure"></a>Bir test hata işleme

Bu bölümde, nasıl dinamik birim testi tanımlamak, sorun giderme ve test hataları gidermek için kullanabileceğiniz ele alacağız. Bu test kapsamı genişleterek gerçekleştirirsiniz `HasEmbeddedSpaces` yöntemi.

# <a name="ctabcsharp"></a>[C#](#tab/csharp)
1. Test dosyanız aşağıdaki yöntemi ekleyin:

    [!code-csharp[The TestHasEmbeddedSpaces test method](samples/snippets/csharp/lut-start/unittest2.cs#3)]

1. Test yürütüldüğünde, Canlı birim testi belirten `TestHasEmbeddedSpaces` yöntemi başarısız oldu, aşağıdaki şekilde gösterildiği gibi: ![Test başarısız bir test bildirimi Gezgin.](media/lut-start/test-failure.png)

1. Kitaplık kodu görüntüler penceresi seçin. Canlı birim testi için kod kapsamı genişletilmiştir Not `HasEmbeddedSpaces` yöntemi. Kırmızı ekleyerek de test hata raporları "🞩" testler başarısız tarafından kapsanan satırlar için.

1. Satırıyla üzerine gelerek `HasEmbeddedSpaces` yöntem imzası. Dinamik birim testi yöntemini aşağıdaki şekilde gösterildiği gibi bir test tarafından kapsanan raporları bir araç ipucu görüntüler:

   ![Canlı başarısız bir test hakkında bilgiler birim testi.](media/lut-start/test-failure-info-cs.png)

1. Başarısız seçin **TestHasEmbeddedSpaces** sınayın. Birim testi Canlı verir tüm testleri çalıştırmak, select testleri çalıştırma, tüm testler hata ayıklama ve hata ayıklama gibi birkaç seçenek, testleri, aşağıdaki şekilde seçtiğiniz gösterir Not:

   ![Dinamik birim testi seçenekleri başarısız bir test.](media/lut-start/test-failure-options.png)

1. Seçin **hata ayıklama seçili** başarısız test hata ayıklamak için.

1. Visual Studio test hata ayıklama modunda yürütür. Bizim test her bir dizi dizesinde adlı bir değişkene atar `phrase` ve buna ileten `HasEmbeddedSpaces` yöntemi. Program yürütme duraklatır ve assert ifade edilen hata ayıklayıcı ilk zaman çağırır `false`. Beklenmeyen değerden sonuçları özel durum iletişim [ `Microsoft.VisualStudio.TestTools.UnitTesting.Assert.IsTrue` ](/dotnet/api/microsoft.visualstudio.testtools.unittesting.assert.istrue) yöntem çağrısı aşağıdaki çizimde gösterilmiştir.

   ![Dinamik birim testi özel durumu iletişim kutusu.](media/lut-start/exception-dialog-cs.png)

   Ayrıca, tüm Visual Studio sağlar hata ayıklama araçları bizim başarısız test aşağıdaki şekilde gösterildiği gibi sorun giderme yardımcı olmak kullanılabilir:

   ![Visual Studio hata ayıklama araçları.](media/lut-start/debugging-tools-cs.png)

   İçinde Not **otomobiller** penceresi, değeri `phrase` değişkeni olan "Name\tDescription" dizisinin ikinci öğesi olduğu. Test yöntemi bekliyor `HasEmbeddedSpaces` döndürülecek `true` bunun yerine, bu dize; geçirildiğinde döndürür `false`. Evidently, bunu "\t", sekme karakteri katıştırılmış bir alan olarak tanımıyor.

1. Seçin **hata ayıklama**, **devam**F5 tuşuna basın veya tıklatın **devam** test program yürütme devam etmek için araç çubuğunda. İşlenmeyen bir özel durum oluştuğundan test sonlandırır.

# <a name="visual-basictabvisual-basic"></a>[Visual Basic](#tab/visual-basic)
1. Test dosyanız aşağıdaki yöntemi ekleyin:

    [!code-vb[The TestHasEmbeddedSpaces test method](samples/snippets/visual-basic/lut-start/unittest2.vb#3)]

1. Test yürütüldüğünde, Canlı birim testi belirten `TestHasEmbeddedSpaces` yöntemi başarısız oldu, aşağıdaki şekilde gösterildiği gibi:

   ![Başarısız bir test bildirimi Test Gezgini.](media/lut-start/test-failure.png)

1. Kitaplık kodu görüntüler penceresi seçin. Canlı birim testi için kod kapsamı genişletilmiştir Not `HasEmbeddedSpaces` yöntemi. Kırmızı ekleyerek de test hata raporları "🞩" testler başarısız tarafından kapsanan satırlar için.

1. Satırıyla üzerine gelerek `HasEmbeddedSpaces` yöntem imzası. Dinamik birim testi yöntemini aşağıdaki şekilde gösterildiği gibi bir test tarafından kapsanan raporları bir araç ipucu görüntüler:

   ![Canlı başarısız bir test hakkında bilgiler birim testi.](media/lut-start/test-failure-info-vb.png)

1. Başarısız seçin **TestHasEmbeddedSpaces** sınayın. Birim testi Canlı verir tüm testleri çalıştırmak, select testleri çalıştırma, tüm testler hata ayıklama ve hata ayıklama gibi birkaç seçenek, testleri, aşağıdaki şekilde seçtiğiniz gösterir Not:

   ![Dinamik birim testi seçenekleri başarısız bir test.](media/lut-start/test-failure-options.png)

1. Seçin **hata ayıklama seçili** başarısız test hata ayıklamak için.

1. Visual Studio test hata ayıklama modunda yürütür. Bizim test her bir dizi dizesinde adlı bir değişkene atar `phrase` ve buna ileten `HasEmbeddedSpaces` yöntemi. Program yürütme duraklatır ve assert ifade edilen hata ayıklayıcı ilk zaman çağırır `false`. Beklenmeyen değerden sonuçları özel durum iletişim [ `Microsoft.VisualStudio.TestTools.UnitTesting.Assert.IsTrue` ](/dotnet/api/microsoft.visualstudio.testtools.unittesting.assert.istrue) yöntem çağrısı aşağıdaki çizimde gösterilmiştir.

   ![Dinamik birim testi özel durumu iletişim kutusu.](media/lut-start/exception-dialog-vb.png)

   Ayrıca, tüm Visual Studio sağlar hata ayıklama araçları bizim başarısız test aşağıdaki şekilde gösterildiği gibi sorun giderme yardımcı olmak kullanılabilir:

   ![Visual Studio hata ayıklama araçları.](media/lut-start/debugging-tools-vb.png)

   İçinde Not **otomobiller** penceresi, değeri `phrase` değişkeni olan "Name" + vbTab dizisinin ikinci öğedir "Açıklama". Test yöntemi bekliyor `HasEmbeddedSpaces` döndürülecek `true` bunun yerine, bu dize; geçirildiğinde döndürür `false`. Evidently, bu sekme karakteri katıştırılmış bir alan olarak tanımıyor.

1. Seçin **hata ayıklama**, **devam**F5 tuşuna basın veya tıklatın **devam** test program yürütme devam etmek için araç çubuğunda. İşlenmeyen bir özel durum oluştuğundan test sonlandırır.

---

Bu hatanın Ön araştırma için yeterli bilgi sağlar. Her iki `TestHasEmbeddedSpaces`, yanlış bir varsayım yaptığınız test yordamı veya `HasEmbeddedSpaces` doğru tüm katıştırılmış boşluklar tanımıyor. Tanılamak ve sorunu düzeltmek için başlayın `StringLibrary.HasEmbeddedSpaces` yöntemi:

# <a name="ctabcsharp"></a>[C#](#tab/csharp)
1. Buna karşılık bakabilir `HasEmbeddedSpaces` yöntemi. U + 0020 olması için katıştırılmış bir alanı değerlendirir. Ancak, Unicode standart diğer alanı karakter sayısını içerir. Bu kitaplık kodu, boşluk karakteri hatalı test önerir.

1. Çağrı eşitlik karşılaştırması yerine <xref:System.Char.IsWhiteSpace%2A?displayProperty=fullName> yöntemi:

    [!code-csharp[The TestHasEmbeddedSpaces test method](samples/snippets/csharp/lut-start/program2.cs#1)]

1. Otomatik olarak başarısız test yöntemi yeniden çalıştırır dinamik birim testi ve güncelleştirmeleri kod penceresinde hem de sonuçları **Test Gezgini**, aşağıdaki şekilde gösterildiği gibi:

    ![Başarılı HasEmbeddedSpaces test.](media/lut-start/test-success-cs.png)

# <a name="visual-basictabvisual-basic"></a>[Visual Basic](#tab/visual-basic)
1. Buna karşılık bakabilir `HasEmbeddedSpaces` yöntemi. U + 0020 olması için katıştırılmış bir alanı değerlendirir. Ancak, Unicode standart diğer alanı karakter sayısını içerir. Bu kitaplık kodu, boşluk karakteri hatalı test önerir.

1. Çağrı eşitlik karşılaştırması yerine <xref:System.Char.IsWhiteSpace%2A?displayProperty=fullName> yöntemi:

    [!code-vb[The TestHasEmbeddedSpaces test method](samples/snippets/visual-basic/lut-start/class2.vb#1)]

1. Otomatik olarak yeniden başarısız test yöntemi çalışır dinamik birim testi ve güncelleştirmeleri kod penceresi ve sonuçları **Test Gezgini**, aşağıdaki şekilde gösterildiği gibi:

    ![Başarılı HasEmbeddedSpaces test.](media/lut-start/test-success-vb.png)

---

## <a name="see-also"></a>Ayrıca bkz.
[Birim testi Visual Studio'da canlı](live-unit-testing.md)
[Canlı birim testi sık sorulan sorular](live-unit-testing-faq.md)
