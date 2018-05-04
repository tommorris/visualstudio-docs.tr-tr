---
title: Yönetilen kod için birim testleri oluşturma ve çalıştırma
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
ms.technology: vs-ide-test
ms.topic: conceptual
helpviewer_keywords:
- unit tests, walkthrough
- unit tests, creating
- unit tests, generating
- unit tests, running
- unit tests, authoring
ms.author: gewarren
manager: douge
ms.workload:
- dotnet
author: gewarren
ms.openlocfilehash: 29472e2590a767c98c5674bce14712171f16fdbf
ms.sourcegitcommit: a8e01952be5a539104e2c599e9b8945322118055
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/03/2018
---
# <a name="walkthrough-create-and-run-unit-tests-for-managed-code"></a>İzlenecek yol: Oluşturmak ve yönetilen kod için birim testleri çalıştırma

Bu kılavuz, oluşturmada size çalıştıran, adımları ve birim bir dizi özelleştirme testleri yönetilen kod ve Visual Studio için Microsoft birim test çerçevesi kullanarak **Test Gezgini**. Geliştirme aşamasındadır bir C# projesi ile başlayın, kendi kodu deneyen, testleri çalıştırmak ve sonuçları inceleyin testleri oluşturma. Sonra proje kodunu değiştirmek ve testleri yeniden çalıştırın.

> [!NOTE]
> Bu kılavuz, yönetilen kod için Microsoft birim test çerçevesi kullanır. **Test Gezgini** testleri üçüncü taraf biriminden bağdaştırıcılarınızın sahip test çerçevelerini çalıştırabilirsiniz **Test Gezgini**. Daha fazla bilgi için bkz: [üçüncü taraf birim test çerçevelerini yükleme](../test/install-third-party-unit-test-frameworks.md)

> [!NOTE]
> Bir komut satırından testleri çalıştırma hakkında daha fazla bilgi için bkz: [izlenecek yol: komut satırı test yardımcı programını kullanarak](http://msdn.microsoft.com/Library/52c11992-9e94-4067-a4b7-59f19d69d867).

## <a name="prerequisites"></a>Önkoşullar

- Banka projesi. Bkz: [örnek proje birim testleri oluşturmak için](../test/sample-project-for-creating-unit-tests.md).

## <a name="create-a-project-to-test"></a>Test etmek için bir proje oluşturun

1. Visual Studio'yu açın.

2. Üzerinde **dosya** menüsünde, select **yeni** > **proje**.

     **Yeni proje** iletişim kutusu görüntülenir.

3. Altında **yüklü şablonlar**, tıklatın **Visual C#**.

4. Uygulama türleri listesinde tıklatın **sınıf kitaplığı**.

5. İçinde **adı** kutusuna `Bank` ve ardından **Tamam**.

    > [!NOTE]
    > "Banka" adı zaten kullanılıyorsa, proje için başka bir ad seçin.

     Yeni Banka projesi oluşturulur ve görüntülenen **Çözüm Gezgini** ile *Class1.cs* dosya Kod düzenleyicisinde açın.

    > [!NOTE]
    > Varsa *Class1.cs* dosyası Kod Düzenleyicisi'nde açık değil, dosyayı çift tıklatın *Class1.cs* açmak için Çözüm Gezgini'nde.

6. Kaynak kodunu kopyalayın [birim testleri oluşturmak için örnek proje](../test/sample-project-for-creating-unit-tests.md)ve özgün Değiştir *Class1.cs* kopyalanan koduna sahip.

7. Dosyayı Farklı Kaydet *BankAccount.cs*.

8. Üzerinde **yapı** menüsünde tıklatın **yapı çözümü**.

Artık banka adlı projesi var. Test etmek için kaynak kodu ve ile test etmek için Araçlar içerir. Ad alanı için banka, BankAccountNS, ortak sınıf BankAccount, aşağıdaki yordamlarda test edeceksiniz, yöntemleri içerir.

Bu makalede, testleri borç yöntemine odaklanır. Para bir hesaptan geri alınmış zaman borç yöntemi çağrılır. Yöntem tanımı aşağıda verilmiştir:

```csharp
// Method to be tested.
public void Debit(double amount)
{
    if(amount > m_balance)
    {
        throw new ArgumentOutOfRangeException("amount");
    }
    if (amount < 0)
    {
        throw new ArgumentOutOfRangeException("amount");
    }
    m_balance += amount;
}
```

## <a name="create-a-unit-test-project"></a>Birim testi projesi oluşturma

1. Üzerinde **dosya** menüsünde, select **Ekle** > **yeni proje**.

2. Yeni Proje iletişim kutusuna genişletin **yüklü**, genişletin **Visual C#** ve ardından **Test**.

3. Şablonları listesinden seçin **birim testi projesi**.

4. İçinde **adı** kutusuna `BankTests`ve ardından **Tamam**.

     **BankTests** projesi eklenir **banka** çözümü.

5. İçinde **BankTests** proje, bir başvuru ekleyin **banka** projesi.

     Çözüm Gezgini'nde seçin **başvuruları** içinde **BankTests** proje ve ardından **Başvuru Ekle** ve bağlam menüsünden.

6. Başvuru Yöneticisi iletişim kutusunda genişletin **çözüm** ve denetleyin **banka** öğesi.

## <a name="create-the-test-class"></a>Test sınıfı oluşturma

Doğrulamak için bir test sınıfı oluşturma `BankAccount` sınıfı. Kullanabileceğiniz *UnitTest1.cs* proje şablonu tarafından oluşturulan dosya ancak dosyaya verin ve sınıf adları daha açıklayıcı. Dosyayı yeniden adlandırmadan, tek bir adımda yapabilirsiniz **Çözüm Gezgini**.

### <a name="rename-a-class-file"></a>Bir sınıf dosyayı yeniden adlandırın

İçinde **Çözüm Gezgini**seçin *UnitTest1.cs* BankTests proje dosyasında. Bağlam menüsünden **yeniden adlandırma**ve dosyayı yeniden adlandırın *BankAccountTests.cs*. Seçin **Evet** tüm başvurularını kod öğesini yeniden adlandırma isteyip istemediğinizi soran iletişim kutusunda `UnitTest1` projesinde.

Bu adım için sınıf adını değiştirir `BankAccountTests`. *BankAccountTests.cs* dosyası artık aşağıdaki kod içerir:

```csharp
using System;
using Microsoft.VisualStudio.TestTools.UnitTesting;

namespace BankTests
{
    [TestClass]
    public class BankAccountTests
    {
        [TestMethod]
        public void TestMethod1()
        {
        }
    }
}
```

### <a name="add-a-using-statement-to-the-project-under-test"></a>Using Ekle test altındaki projeye deyimi

Ayrıca ekleyebileceğiniz bir `using` test altındaki projesine tam olarak kullanarak adları yetkili olmadan arayabilmesi için için sınıfa ifade. Sınıf dosyasının üstüne ekleyin:

```csharp
using BankAccountNS;
```

### <a name="test-class-requirements"></a>Test sınıfı gereksinimleri

Test sınıfı için minimum gereksinimleri şunlardır:

- `[TestClass]` Özniteliği gerekli framework yönetilen için test Microsoft biriminde kodunu herhangi bir sınıf için Test Explorer'da çalıştırmak istediğiniz birim test yöntemleri içerir.

- Explorer çalıştırmak için test etmek istediğiniz her test yöntemi olmalıdır `[TestMethod]`özniteliği.

Olmadığı diğer birim testi projesi sınıflarda olabilir `[TestClass]` özniteliği ve olabilir diğer yöntemleri olmadığı test sınıflarda `[TestMethod]` özniteliği. Test yöntemlerinizi bu diğer sınıflar ve yöntemler kullanabilirsiniz.

## <a name="create-the-first-test-method"></a>Create ilk test yöntemi

Bu yordamda, birim testi davranışını doğrulamak için yöntem yazacaksınız `Debit` yöntemi `BankAccount` sınıfı. `Debit` Yöntemi bu makalede daha önce gösterilir.

Denetlenmesi gereken en az üç davranış vardır:

- Yöntem oluşturulur bir <xref:System.ArgumentOutOfRangeException> borç tutarını Bakiye büyükse.

- Yöntem oluşturulur <xref:System.ArgumentOutOfRangeException> borç tutarını küçükse sıfır.

- Borç tutarını geçerli ise, yöntem hesap bakiyesini borç tutarından çıkarır.

> [!TIP]
> Varsayılan silebilirsiniz `TestMethod1` yöntemi, bu kılavuzda kullandığından olmaz.

### <a name="to-create-a-test-method"></a>Test yöntemi oluşturmak için

İlk testi geçerli tutar (diğer bir deyişle, bir hesap bakiyesini ve sıfır büyüktür daha az) hesabından doğru miktarı çeker doğrular. İçin aşağıdaki yöntemi ekleyin `BankAccountTests` sınıfı:

```csharp
[TestMethod]
public void Debit_WithValidAmount_UpdatesBalance()
{
    // Arrange
    double beginningBalance = 11.99;
    double debitAmount = 4.55;
    double expected = 7.44;
    BankAccount account = new BankAccount("Mr. Bryan Walton", beginningBalance);

    // Act
    account.Debit(debitAmount);

    // Assert
    double actual = account.Balance;
    Assert.AreEqual(expected, actual, 0.001, "Account not debited correctly");
}
```

Basit bir yöntemdir: yeni ayarlar `BankAccount` nesne başına bakiyesi olan ve geçerli bir miktar çeker. Kullandığı <xref:Microsoft.VisualStudio.TestTools.UnitTesting.Assert.AreEqual%2A> yöntemi Bitiş bakiye beklendiği gibi olduğunu doğrulayın.

### <a name="test-method-requirements"></a>Test yöntemi gereksinimleri

Test yöntemi aşağıdaki gereksinimleri karşılamalıdır:

- İle donatılmış `[TestMethod]` özniteliği.

- Döndürdüğü `void`.

- Parametrelere sahip olamaz.

## <a name="build-and-run-the-test"></a>Derleme ve test çalıştırma

1. Üzerinde **yapı** menüsünde seçin **yapı çözümü**.

   Hiçbir hatalar varsa **Test Gezgini** görünür **Debit_WithValidAmount_UpdatesBalance** listelenen **testleri değil Çalıştır** grubu.

   > [!TIP]
   > Varsa **Test Gezgini** başarılı derleme sonrası görüntülenmiyorsa, seçin **Test** menüsünde ardından **Windows**ve ardından **Test Gezgini**.

2. Seçin **tümünü Çalıştır** testi çalıştırmak için. Test çalışırken, pencerenin üstündeki durum çubuğu animasyon eklenir. Herhangi bir test başarısız olursa test çalıştırması sonunda, tüm test yöntemlerini geçirirseniz yeşil veya kırmızı çubuğu etkinleştirir.

3. Bu durumda, sınama başarısız olur. Test yöntemi taşınır **başarısız testler** grubu. Yöntemini seçin **Test Gezgini** pencerenin altındaki ayrıntılarını görüntülemek için.

## <a name="fix-your-code-and-rerun-your-tests"></a>Kodunuzu düzeltin ve testleri yeniden çalıştırın

**Test sonuçlarını analiz etme**

Test sonucu hatayı açıklayan bir ileti içerir. İçin `AreEquals` yöntemi, ileti görüntüler beklenen ( **beklenen\<*değeri* >**  parametresi) ve ne gerçekte alındı ( **Gerçek\<*değeri* >** parametresi). Azaltmak için Bakiye bekleniyordu ancak bunun yerine mevzuatı miktarı gerçekte artar.

Birim testi hata sınamayla: mevzuatı miktarı *eklenen* olmalıdır, hesap bakiyesini için *çıkarılır*.

**Hatayı düzeltin**

Hatayı düzeltmek için satırı değiştirin:

```csharp
m_balance += amount;
```

İle:

```csharp
m_balance -= amount;
```

**Test yeniden çalıştırın**

Test Gezgini seçin **tümünü Çalıştır** test yeniden çalıştırmak için. Kırmızı/yeşil çubuğu test geçirilen ve test taşınır gösteren yeşil kapatır **testleri geçti** grubu.

## <a name="use-unit-tests-to-improve-your-code"></a>Kodunuzu geliştirmek için kullanım birim testleri

Bu bölümde, analiz, birim testi geliştirme ve yeniden düzenleme yinelemeli süreç üretim kodunuzu daha sağlam ve etkin hale getirmek nasıl yardımcı olabileceğini açıklanmaktadır.

**Sorunlarını çözümleme**

Geçerli bir süre içinde doğru çıkarılır onaylamak için bir test yöntemi oluşturduğunuz `Debit` yöntemi. Şimdi, yöntem oluşturulur doğrula bir <xref:System.ArgumentOutOfRangeException> borç tutarını ya da ise:

- Bakiye büyüktür veya
- sıfırdan.

**Test yöntemleri oluşturma**

Borç tutarını doğru davranış sıfırdan doğrulamak için bir test yöntemi oluşturun:

```csharp
[TestMethod]
[ExpectedException(typeof(ArgumentOutOfRangeException))]
public void Debit_WhenAmountIsLessThanZero_ShouldThrowArgumentOutOfRange()
{
    // Arrange
    double beginningBalance = 11.99;
    double debitAmount = -100.00;
    BankAccount account = new BankAccount("Mr. Bryan Walton", beginningBalance);

    // Act
    account.Debit(debitAmount);

    // Assert is handled by the ExpectedException attribute on the test method.
}
```

Kullanım <xref:Microsoft.VisualStudio.TestTools.UnitTesting.ExpectedExceptionAttribute> doğru özel durum oluşturdu onaylanacak özniteliği. Öznitelik testin sürece başarısız olmasına neden olan bir <xref:System.ArgumentOutOfRangeException> oluşturulur. Daha fazla genel throw test altındaki yöntemi geçici olarak değiştirirseniz, <xref:System.ApplicationException> borç tutarını küçük olduğunda sıfır, test düzgün şekilde davranan&mdash;diğer bir deyişle, başarısız olur.

Durum geri miktar Bakiye'den büyük olduğunda sınamak için aşağıdaki adımları uygulayın:

1. Adlı yeni bir test yöntemi oluşturma `Debit_WhenAmountIsMoreThanBalance_ShouldThrowArgumentOutOfRange`.

2. Yöntem gövdesinden kopyalama `Debit_WhenAmountIsLessThanZero_ShouldThrowArgumentOutOfRange` yeni yöntemi.

3. Ayarlama `debitAmount` Bakiye büyük bir sayı.

**Testleri çalıştırma**

İki test yöntemleri çalışan testleri doğru bir şekilde çalıştığını gösterir.

**Analiz devam**

Ancak, son iki test yöntemleri de kaygı değildir. Her iki testi çalıştırdığınızda, hangi koşul altında test yöntemi özel durum oluşturur olamazsınız. Negatif borç tutarı veya bakiye büyük bir miktarını, iki koşul ayrım yapma, bazı şekilde testlerinde, güvenirlik artırır.

Looki yeniden test ve her iki koşullu deyimler kullanmak bildirimi altında yöntemi, bir `ArgumentOutOfRangeException` yalnızca oluşturucu bağımsız değişkeni bir parametre olarak adını alır:

```csharp
throw new ArgumentOutOfRangeException("amount");
```

Çok daha zengin bilgi raporları kullanabileceğiniz bir oluşturucu yok: <xref:System.ArgumentOutOfRangeException.%23ctor%2A> `(String, Object, String)` adı bağımsız değişkeni, bağımsız değişken değeri ve kullanıcı tanımlı bir ileti içerir. Bu oluşturucu kullanmak için test altındaki yöntemi yeniden düzenleyin. Hatta daha iyi ve genel kullanıma açık tür üyeleri hataları belirtmek için kullanabilirsiniz.

**Test altındaki kodun yeniden Düzenle**

İlk olarak, iki sabitler sınıfı kapsamda hata iletileri için tanımlayın. Bu test altındaki sınıfında put (`Bank`):

```csharp
public const string DebitAmountExceedsBalanceMessage = "Debit amount exceeds balance";
public const string DebitAmountLessThanZeroMessage = "Debit amount is less than zero";
```

Ardından, iki koşullu ifadeler değiştirin `Debit` yöntemi:

```csharp
    if (amount > m_balance)
    {
        throw new ArgumentOutOfRangeException("amount", amount, DebitAmountExceedsBalanceMessage);
    }

    if (amount < 0)
    {
        throw new ArgumentOutOfRangeException("amount", amount, DebitAmountLessThanZeroMessage);
    }
```

**Test yöntemleri yeniden Düzenle**

Kaldırma `ExpectedException` test yöntemi özniteliği ve bunun yerine, oluşturulan özel durum yakalamak ve onun ilişkili ileti doğrulayın. <xref:Microsoft.VisualStudio.TestTools.UnitTesting.StringAssert.Contains%2A?displayProperty=fullName> Yöntemi iki dizeleri karşılaştırmak olanağı sağlar.

Şimdi, `Debit_WhenAmountIsMoreThanBalance_ShouldThrowArgumentOutOfRange` şuna benzeyebilir:

```csharp
[TestMethod]
public void Debit_WhenAmountIsMoreThanBalance_ShouldThrowArgumentOutOfRange()
{
    // Arrange
    double beginningBalance = 11.99;
    double debitAmount = 20.0;
    BankAccount account = new BankAccount("Mr. Bryan Walton", beginningBalance);

    // Act
    try
    {
        account.Debit(debitAmount);
    }
    catch (ArgumentOutOfRangeException e)
    {
        // Assert
        StringAssert.Contains(e.Message, BankAccount.DebitAmountExceedsBalanceMessage);
    }
}
```

**Sürücüyle, yeniden yazma ve yeniden Çözümle**

Test yönteminde bir hata varsa varsayar ve `Debit` yöntemi olmayan bile *throw* bir <xref:System.ArgumentOutOfRangeException>, nevermind doğru iletinin özel durumu ile çıktı. Şu anda, test yöntemi bu durumda işleyemez. Varsa `debitAmount` değeri geçerli (diğer bir deyişle, değerinden sıfırdan büyük ancak Bakiye), assert hiçbir zaman harekete için hiçbir özel durum yakalandı. Henüz, test yöntemi geçirir. Hiçbir özel durum, başarısız olması için test yöntemi istediğiniz olduğundan bu iyi değil.

Bu test yönteminde hatasıdır. Sorunu çözmek için ekleme bir <xref:Microsoft.VisualStudio.TestTools.UnitTesting.Assert.Fail%2A> nerede hiçbir özel durum durumu işlemek için test yöntemi sonunda assert.

Ancak sınamasını yeniden çalıştırma gösterir, test şimdi *başarısız* doğru özel durumu yakalandı durumunda. `catch` Blok yakalar özel durum ancak yöntemi yürütmeye devam eder ve yeni başarısız <xref:Microsoft.VisualStudio.TestTools.UnitTesting.Assert.Fail%2A> assert. Bu sorunu gidermek için ekleme bir `return` sonra deyimi `StringAssert` içinde `catch` bloğu. Test yeniden, bu sorunu düzelttik onaylar. Son sürümü `Debit_WhenAmountIsMoreThanBalance_ShouldThrowArgumentOutOfRange` şöyle görünür:

```csharp
[TestMethod]
public void Debit_WhenAmountIsMoreThanBalance_ShouldThrowArgumentOutOfRange()
{
    // Arrange
    double beginningBalance = 11.99;
    double debitAmount = 20.0;
    BankAccount account = new BankAccount("Mr. Bryan Walton", beginningBalance);

    // Act
    try
    {
        account.Debit(debitAmount);
    }
    catch (ArgumentOutOfRangeException e)
    {
        // Assert
        StringAssert.Contains(e.Message, BankAccount.DebitAmountExceedsBalanceMessage);
        return;
    }

    Assert.Fail("The expected exception was not thrown.");
}
```

Test kodu geliştirmeleri için daha sağlam ve bilgilendirici test yöntemleri gerektiriyordu. Ancak daha da önemlisi, test altındaki kodun'bunlar da geliştirildi.
