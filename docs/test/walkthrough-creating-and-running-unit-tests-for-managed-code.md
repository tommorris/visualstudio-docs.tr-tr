---
title: "İzlenecek yol: Oluşturmak ve çalıştırmak için birim testleri yönetilen kod | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-devops-test
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- unit tests, walkthrough
- unit tests, creating
- unit tests, generating
- unit tests, running
- unit tests, authoring
ms.assetid: 2b018b18-b412-4e0e-b0ee-b580a2f3ba9c
caps.latest.revision: "83"
ms.author: douge
manager: douge
ms.openlocfilehash: 825adc757b9ae984bb39b308bab37a0d98b63ab5
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2017
---
# <a name="walkthrough-creating-and-running-unit-tests-for-managed-code"></a>İzlenecek yol: Yönetilen Kod için Birim Testleri Oluşturma ve Çalıştırma
Bu kılavuzda oluşturma, çalıştıran ve yönetilen kod ve Visual Studio Test Gezgini için Microsoft birim test çerçevesi kullanarak birim testlerini bir dizi özelleştirme adım. Geliştirme aşamasındadır bir C# projesi ile başlayın, kendi kodu deneyen, testleri çalıştırmak ve sonuçları inceleyin testleri oluşturma. Sonra proje kodunu değiştirmek ve testleri yeniden çalıştırın.  
  
 Bu konu aşağıdaki bölümleri içermektedir:  
  
 [İzlenecek yol hazırlama](../test/walkthrough-creating-and-running-unit-tests-for-managed-code.md#BKMK_Prepare_the_walkthrough)  
  
 [Birim testi projesi oluşturma](../test/walkthrough-creating-and-running-unit-tests-for-managed-code.md#BKMK_Create_a_unit_test_project)  
  
 [Test sınıfı oluşturma](../test/walkthrough-creating-and-running-unit-tests-for-managed-code.md#BKMK_Create_the_test_class)  
  
-   [Test sınıfı gereksinimleri](../test/walkthrough-creating-and-running-unit-tests-for-managed-code.md#BKMK_Test_class_requirements)  
  
 [Create ilk test yöntemi](../test/walkthrough-creating-and-running-unit-tests-for-managed-code.md#BKMK_Create_the_first_test_method)  
  
-   [Test yöntemi gereksinimleri](../test/walkthrough-creating-and-running-unit-tests-for-managed-code.md#BKMK_Test_method_requirements)  
  
 [Derleme ve test çalıştırma](../test/walkthrough-creating-and-running-unit-tests-for-managed-code.md#BKMK_Build_and_run_the_test)  
  
 [Kodunuzu düzeltin ve testleri yeniden çalıştırın](../test/walkthrough-creating-and-running-unit-tests-for-managed-code.md#BKMK_Fix_your_code_and_rerun_your_tests)  
  
 [Kodunuzu geliştirmek için kullanım birim testleri](../test/walkthrough-creating-and-running-unit-tests-for-managed-code.md#BKMK_Use_unit_tests_to_improve_your_code)  
  
> [!NOTE]
>  Bu kılavuz, yönetilen kod için Microsoft birim test çerçevesi kullanır. Test Gezgini testleri için Test Gezgini bağdaştırıcılara sahip test çerçevelerini üçüncü taraf biriminden çalıştırabilirsiniz. Daha fazla bilgi için bkz: [üçüncü taraf birim test çerçevelerini yükleme](../test/install-third-party-unit-test-frameworks.md)  
  
> [!NOTE]
>  Bir komut satırından testleri çalıştırma hakkında daha fazla bilgi için bkz: [izlenecek yol: komut satırı test yardımcı programını kullanarak](http://msdn.microsoft.com/Library/52c11992-9e94-4067-a4b7-59f19d69d867).  
  
## <a name="prerequisites"></a>Önkoşullar  
  
-   Banka projesi. Bkz: [örnek proje birim testleri oluşturmak için](../test/sample-project-for-creating-unit-tests.md).  
  
##  <a name="BKMK_Prepare_the_walkthrough"></a>İzlenecek yol hazırlama  
  
1.  Visual Studio'yu açın.  
  
2.  Üzerinde **dosya** menüsündeki **yeni** ve ardından **proje**.  
  
     **Yeni proje** iletişim kutusu görüntülenir.  
  
3.  Altında **yüklü şablonlar**, tıklatın **Visual C#**.  
  
4.  Uygulama türleri listesinde tıklatın **sınıf kitaplığı**.  
  
5.  İçinde **adı** kutusuna `Bank` ve ardından **Tamam**.  
  
    > [!NOTE]
    >  "Banka" adı zaten kullanılıyorsa, proje için başka bir ad seçin.  
  
     Yeni Banka projesi oluşturulur ve Kod Düzenleyicisi'nde açık Class1.cs dosyası ile Çözüm Gezgini'nde görüntülenir.  
  
    > [!NOTE]
    >  Class1.cs dosyası kod düzenleyicide açık değilse, açmak için Çözüm Gezgini'nde Class1.cs dosyasını çift tıklatın.  
  
6.  Kaynak kodunu kopyalayın [birim testleri oluşturmak için örnek proje](../test/sample-project-for-creating-unit-tests.md).  
  
7.  Özgün Class1.cs kodla değiştir [birim testleri oluşturmak için örnek proje](../test/sample-project-for-creating-unit-tests.md).  
  
8.  Dosyayı BankAccount.cs kaydedin  
  
9. Üzerinde **yapı** menüsünde tıklatın **yapı çözümü**.  
  
 Artık banka adlı projesi var. Test etmek için kaynak kodu ve ile test etmek için Araçlar içerir. Banka için ad alanı **BankAccountNS**, ortak sınıfı içeren **BankAccount**, aşağıdaki yordamlarda test olan yöntemleri.  
  
 Bu Hızlı Başlangıç, biz odaklanmak `Debit` yöntemi. Para geri alınmış zaman borç yöntemi çağrılır bir hesap ve aşağıdaki kodu içerir:  
  
```csharp  
// method under test  
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
  
##  <a name="BKMK_Create_a_unit_test_project"></a>Birim testi projesi oluşturma  
 **Önkoşul**: yordamdaki adımları [Yönergeyi Hazırla](../test/walkthrough-creating-and-running-unit-tests-for-managed-code.md#BKMK_Prepare_the_walkthrough).  
  
#### <a name="to-create-a-unit-test-project"></a>Birim testi projesi oluşturmak için  
  
1.  Üzerinde **dosya** menüsünde seçin **Ekle**ve ardından **yeni proje...** .  
  
2.  Yeni Proje iletişim kutusuna genişletin **yüklü**, genişletin **Visual C#**ve ardından **Test**.  
  
3.  Şablonları listesinden seçin **birim testi projesi**.  
  
4.  İçinde **adı** kutusuna BankTest girin ve ardından **Tamam**.  
  
     **BankTests** projesi eklenir **banka** çözümü.  
  
5.  İçinde **BankTests** proje, bir başvuru ekleyin **banka** çözümü.  
  
     Çözüm Gezgini'nde seçin **başvuruları** içinde **BankTests** proje ve ardından **Başvuru Ekle...**  ve bağlam menüsünden.  
  
6.  Başvuru Yöneticisi iletişim kutusunda genişletin **çözüm** ve denetleyin **banka** öğesi.  
  
##  <a name="BKMK_Create_the_test_class"></a>Test sınıfı oluşturma  
 Doğrulama için bir test sınıf ihtiyacımız `BankAccount` sınıfı. Proje şablonu tarafından oluşturulan UnitTest1.cs kullanıyoruz, ancak biz dosyaya verin ve daha açıklayıcı adlar sınıfının gerekir. Tek bir adımda Çözüm Gezgini'nde dosyayı yeniden adlandırmadan bunu.  
  
 **Bir sınıf dosyasını yeniden adlandırma**  
  
 Çözüm Gezgini'nde BankTests projesindeki UnitTest1.cs dosyasını seçin. Bağlam menüsünden **yeniden adlandırma**ve BankAccountTests.cs için dosyayı yeniden adlandırın. Seçin **Evet** projedeki tüm başvuruları 'UnitTest1' kod öğesini yeniden adlandırma isteyip istemediğinizi soran iletişim kutusunda. Bu adım için sınıf adını değiştirir `BankAccountTest`.  
  
 BankAccountTests.cs dosyası artık aşağıdaki kod içerir:  
  
```csharp  
// unit test code  
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
  
 **Using Ekle test altındaki projeye deyimi**  
  
 Ayrıca kullanarak bir ekleyebiliriz test altındaki projesine tam olarak kullanarak adları yetkili olmadan çağırmak için bize sınıfına deyimi. Sınıf dosyasının üstüne ekleyin:  
  
```csharp  
using BankAccountNS;  
```  
  
###  <a name="BKMK_Test_class_requirements"></a>Test sınıfı gereksinimleri  
 Test sınıfı için en düşük gereksinimler aşağıda verilmiştir:  
  
-   `[TestClass]` Özniteliği gerekli framework yönetilen için test Microsoft biriminde kodunu herhangi bir sınıf için Test Explorer'da çalıştırmak istediğiniz birim test yöntemleri içerir.  
  
-   Explorer çalıştırmak için test etmek istediğiniz her test yöntemi olmalıdır `[TestMethod]`özniteliği.  
  
 Olmadığı diğer birim testi projesi sınıflarda olabilir `[TestClass]` özniteliği ve olabilir diğer yöntemleri olmadığı test sınıflarda `[TestMethod]` özniteliği. Test yöntemlerinizi bu diğer sınıflar ve yöntemler kullanabilirsiniz.  
  
##  <a name="BKMK_Create_the_first_test_method"></a>Create ilk test yöntemi  
 Bu yordamda, biz birim testi davranışını doğrulamak için yöntem yazacak `Debit` yöntemi `BankAccount` sınıfı. Yöntemi, yukarıda listelenen.  
  
 Test yöntemi çözümleyerek denetlenmesi gereken en az üç davranış olduğunu belirleriz:  
  
1.  Yöntem oluşturulur bir <xref:System.ArgumentOutOfRangeException> borç tutarını Bakiye büyükse.  
  
2.  Ayrıca oluşturur `ArgumentOutOfRangeException` borç tutarını küçükse sıfır.  
  
3.  Eğer 1 denetimlerinde.) ve 2.) memnun, hesap bakiyesini tutarından yöntemi çıkarır.  
  
 İlk testimizde geçerli tutar (bir hesap bakiyesini değerinden küçük ve sıfırdan büyük) hesabından doğru miktarı çeker doğrulayın.  
  
#### <a name="to-create-a-test-method"></a>Test yöntemi oluşturmak için  
  
1.  Using Ekle `BankAccountNS;` BankAccountTests.cs dosyasına deyimi.  
  
2.  İçin aşağıdaki yöntemi ekleyin `BankAccountTests` sınıfı:  
  
    ```csharp  
    // unit test code  
    [TestMethod]  
    public void Debit_WithValidAmount_UpdatesBalance()  
    {  
        // arrange  
        double beginningBalance = 11.99;  
        double debitAmount = 4.55;  
        double expected = 7.44;  
        BankAccount account = new BankAccount("Mr. Bryan Walton", beginningBalance);  
  
        // act  
        account.Debit(debitAmount);  
  
        // assert  
        double actual = account.Balance;  
        Assert.AreEqual(expected, actual, 0.001, "Account not debited correctly");  
    }  
    ```  
  
 Yöntemi, bunun yerine basit bir işlemdir. Yeni bir ayarlarız `BankAccount` nesne başına bakiyesi olan ve geçerli bir miktar programdan çıkın. Yönetilen kod için Microsoft birim test çerçevesi kullanırız <xref:Microsoft.VisualStudio.TestTools.UnitTesting.Assert.AreEqual%2A> Bitiş bakiye beklenen olduğunu doğrulamak için yöntem.  
  
###  <a name="BKMK_Test_method_requirements"></a>Test yöntemi gereksinimleri  
 Test yöntemi aşağıdaki gereksinimleri karşılamalıdır:  
  
-   Yöntem ile tasarlanmalıdır `[TestMethod]` özniteliği.  
  
-   Yöntem döndürmelidir `void`.  
  
-   Yöntem parametreleri olamaz.  
  
##  <a name="BKMK_Build_and_run_the_test"></a>Derleme ve test çalıştırma  
  
#### <a name="to-build-and-run-the-test"></a>Yapı ve test çalıştırmak için  
  
1.  Üzerinde **yapı** menüsünde seçin **yapı çözümü**.  
  
     Herhangi bir hata varsa, UnitTestExplorer penceresi görüntülenir **Debit_WithValidAmount_UpdatesBalance** listelenen **testleri değil Çalıştır** grubu. Test Gezgini başarılı derleme sonrası görünmüyorsa seçin **Test** menüsünde ardından **Windows**ve ardından **Test Gezgini**.  
  
2.  Seçin **tümünü Çalıştır** testi çalıştırmak için. Test durum çubuğu penceresinin en üstünde çalışır durumda olduğundan animasyon eklenir. Herhangi bir test başarısız olursa test çalıştırması sonunda, tüm test yöntemlerini geçirirseniz yeşil veya kırmızı çubuğu etkinleştirir.  
  
3.  Bu durumda, test başarısız olmaz. Test yöntemi taşınır **başarısız testler**. Grup. Pencerenin altındaki ayrıntılarını görüntülemek için Test Explorer'da yöntemi seçin.  
  
##  <a name="BKMK_Fix_your_code_and_rerun_your_tests"></a>Kodunuzu düzeltin ve testleri yeniden çalıştırın  
 **Test sonuçlarını analiz etme**  
  
 Test sonucu hatayı açıklayan bir ileti içerir. İçin `AreEquals` yöntemi, ileti görüntüler, ne bekleniyordu ((**beklenen\<*XXX*>**parametresi) ve ne gerçekte alındı (  **Gerçek\<*YYY* >**  parametresi). Başlangıç bakiyenin dışında reddetmek için Bakiye şuydu, ancak bunun yerine mevzuatı tutarına göre artırılmıştır.  
  
 ATM kod reexamination birim test hata bulma başarılı olduğunu gösterir. Mevzuatı miktarını çıkarılsın mı hesap bakiyesini eklenir.  
  
 **Hatayı düzeltin**  
  
 Hatayı düzeltmek için yalnızca satır değiştirin  
  
```csharp  
m_balance += amount;  
```  
  
 örneklerini şununla değiştirin:  
  
```csharp  
m_balance -= amount;  
```  
  
 **Test yeniden çalıştırın**  
  
 Test Gezgini seçin **tümünü Çalıştır** test yeniden çalıştırmak için. Kırmızı/yeşil çubuk yeşil kapatır ve test taşınır **testleri geçti** grubu.  
  
##  <a name="BKMK_Use_unit_tests_to_improve_your_code"></a>Kodunuzu geliştirmek için kullanım birim testleri  
 Bu bölümde, analiz, birim testi geliştirme ve yeniden düzenleme yinelemeli süreç üretim kodunuzu daha sağlam ve etkin hale getirmek nasıl yardımcı olabileceğini açıklanmaktadır.  
  
 **Sorunlarını çözümleme**  
  
 Onaylamak için bir test yöntemi oluşturduktan sonra geçerli bir miktar doğru olduğunu, kesinti `Debit` yöntemi, biz kapatma kalan çalışmalarını bizim özgün çözümlemede:  
  
1.  Yöntem oluşturulur bir `ArgumentOutOfRangeException` borç tutarını Bakiye büyükse.  
  
2.  Ayrıca oluşturur `ArgumentOutOfRangeException` borç tutarını küçükse sıfır.  
  
 **Test yöntemleri oluşturma**  
  
 Bu sorunları gidermek için bir test yöntemi oluşturma sırasında bir ilk girişimi taahhüdü gibi görünüyor:  
  
```csharp  
//unit test method  
[TestMethod]  
[ExpectedException(typeof(ArgumentOutOfRangeException))]  
public void Debit_WhenAmountIsLessThanZero_ShouldThrowArgumentOutOfRange()  
{  
    // arrange  
    double beginningBalance = 11.99;  
    double debitAmount = -100.00;  
    BankAccount account = new BankAccount("Mr. Bryan Walton", beginningBalance);  
  
    // act  
    account.Debit(debitAmount);  
  
    // assert is handled by ExpectedException  
}  
  
```  
  
 Kullanırız <xref:Microsoft.VisualStudio.TestTools.UnitTesting.ExpectedExceptionAttribute> sağ özel durum oluşturdu onaylanacak özniteliği. Öznitelik testin sürece başarısız olmasına neden olan bir `ArgumentOutOfRangeException` oluşturulur. Her iki pozitif ve negatif testi çalıştırma `debitAmount` değerleri ve test genel throw altındaki yöntemi geçici olarak değiştirme <xref:System.ApplicationException> test davranır doğru olduğunda tutarı sıfırdan küçük gösterir. Durum geri miktar Bakiye'den büyük olduğunda sınamak için yapmamız gereken tek şey:  
  
1.  Adlı yeni bir test yöntemi oluşturma `Debit_WhenAmountIsMoreThanBalance_ShouldThrowArgumentOutOfRange`.  
  
2.  Yöntem gövdesinden kopyalama `Debit_WhenAmountIsLessThanZero_ShouldThrowArgumentOutOfRange` yeni yöntemi.  
  
3.  Ayarlama `debitAmount` Bakiye büyük bir sayı.  
  
 **Testleri çalıştırma**  
  
 İki yöntem için farklı değerler çalışan `debitAmount` testleri yeterli bizim kalan durumlarında olduğunu gösterir. Çalışan tüm üç testi onaylayın bizim özgün analiz tüm durumlarda doğru ele alınmıştır.  
  
 **Analiz devam**  
  
 Ancak, son iki test yöntemleri de biraz kaygı değildir. Biz ya da test çalışmasını olduğunda hangi koşul altında test kodda oluşturur belirli olamaz. İki koşul ayrım bazı şekilde yararlı olacaktır. Biz daha fazla sorun düşünün, hangi koşulun ihlal edildiğini bilerek bizim güvenirlik testlerinde artacaktır belirgin olur. Bu bilgiler ayrıca büyük olasılıkla test altındaki yöntemi tarafından oluşturulan özel durumu işler üretim mekanizması için yararlı olacaktır. Daha fazla bilgi yöntemi atar tüm ilgilenen yardımcı olacağı zaman oluşturma ancak `ExpectedException` özniteliği olamaz bu bilgileri sağlayın...  
  
 Test yöntemi yeniden bakarak, biz kullanmak hem koşullu deyimler bkz bir `ArgumentOutOfRangeException` bağımsız değişkeni bir parametre olarak adını alan oluşturucu:  
  
```csharp  
throw new ArgumentOutOfRangeException("amount");  
```  
  
 MSDN Kitaplığı aramadan çok daha zengin bilgi raporları bir oluşturucu var keşfedin. <xref:System.ArgumentOutOfRangeException.%23ctor%2A>`(String, Object, String)`bağımsız değişkeni, bağımsız değişken değeri ve bir kullanıcı tarafından tanımlanan ileti adını içerir. Biz bu oluşturucu kullanmak için test altındaki yöntemi yeniden. Hatta daha iyi biz hataları belirtmek için genel kullanıma açık tür üyeleri kullanabilirsiniz.  
  
 **Test altındaki kodun yeniden Düzenle**  
  
 Biz öncelikle sınıfı kapsamda hata iletileri için iki sabitleri tanımlayın:  
  
```csharp  
// class under test  
public const string DebitAmountExceedsBalanceMessage = "Debit amount exceeds balance";  
public const string DebitAmountLessThanZeroMessage = "Debit amount less than zero";  
```  
  
 Biz sonra iki koşullu ifadeler değiştirme `Debit` yöntemi:  
  
```csharp  
// method under test  
// ...  
    if (amount > m_balance)  
    {  
        throw new ArgumentOutOfRangeException("amount", amount, DebitAmountExceedsBalanceMessage);  
    }  
  
    if (amount < 0)  
    {  
        throw new ArgumentOutOfRangeException("amount", amount, DebitAmountLessThanZeroMessage);  
    }  
// ...  
```  
  
 **Test yöntemleri yeniden Düzenle**  
  
 Bizim test yönteminde biz kaldırın `ExpectedException` özniteliği. Onun yerine oluşturulan özel durum yakalamak ve doğru koşul deyiminde oluşturuldu doğrulayın. Ancak, biz şimdi bizim kalan koşullar doğrulamak için iki seçenekten karar vermeniz gerekir. Örneğin `Debit_WhenAmountIsMoreThanBalance_ShouldThrowArgumentOutOfRange` yöntemi, biz alabilir aşağıdaki eylemlerden birini:  
  
-   Bu onay `ActualValue` özel durum özelliği (öğesinin ikinci parametresi, `ArgumentOutOfRangeException` Oluşturucusu) Başlangıç bakiyesi büyük. Bu seçenek, biz test gerektirir `ActualValue` karşı özel durum özelliği `beginningBalance` test yönteminin değişken ve ayrıca gerektirir. ardından doğrulayın `ActualValue` sıfırdan büyük.  
  
-   İletinin (Oluşturucusu üçüncü parametre) içerdiğini assert `DebitAmountExceedsBalanceMessage` tanımlanan `BankAccount` sınıfı.  
  
 <xref:Microsoft.VisualStudio.TestTools.UnitTesting.StringAssert.Contains%2A?displayProperty=fullName> Microsoft birim test çerçevesi yönteminde doğrulamamızı ilk seçenek gerekli olan hesaplamalar olmadan ikinci seçeneği sağlar.  
  
 Düzeltilmesi, ikinci deneme `Debit_WhenAmountIsMoreThanBalance_ShouldThrowArgumentOutOfRange` aşağıdaki gibi görünmelidir:  
  
```csharp  
[TestMethod]  
public void Debit_WhenAmountIsMoreThanBalance_ShouldThrowArgumentOutOfRange()  
{  
    // arrange  
    double beginningBalance = 11.99;  
    double debitAmount = 20.0;  
    BankAccount account = new BankAccount("Mr. Bryan Walton", beginningBalance);  
  
    // act  
    try  
    {  
        account.Debit(debitAmount);  
    }  
    catch (ArgumentOutOfRangeException e)  
    {  
        // assert  
        StringAssert.Contains(e.Message, BankAccount. DebitAmountExceedsBalanceMessage);  
    }  
}  
```  
  
 **Sürücüyle, yeniden yazma ve yeniden Çözümle**  
  
 Biz farklı değerleri olan test yöntemlerini yeniden sınayın, biz aşağıdaki gerçekleri karşılaşırsınız:  
  
1.  Assert kullanarak kimliğinizi doğru hata catch varsa burada `debitAmount` Bakiye büyük `Contains` assert geçirir, özel durum göz ardı edilir ve bu nedenle test yöntemi geçirir. İstediğimiz davranış budur.  
  
2.  Biz kullanırsanız, bir `debitAmount` 0'dan az olan, yanlış hata iletisini döndürdüğünden assert başarısız olur. Biz geçici bir belirtiyorsa assert de başarısız `ArgumentOutOfRange` test kod yolunda yönteminde başka bir noktada özel durum. Bu çok iyi olur.  
  
3.  Varsa `debitAmount` değeri (yani, Bakiye, sıfırdan büyük ancak sayısından az hiçbir özel durum yakalandı, assert hiçbir zaman yakalanan şekilde. geçerli Test yöntemi geçirir. Hiçbir özel durum, başarısız olması için test yöntemi istiyoruz olduğundan bu iyi değil.  
  
 Üçüncü olgu bizim test yönteminde bir hatadır. Bu sorunu çözmek denemek için eklediğimiz bir <xref:Microsoft.VisualStudio.TestTools.UnitTesting.Assert.Fail%2A> nerede hiçbir özel durum durumu işlemek için test yöntemi sonunda assert.  
  
 Ancak retesting doğru özel durumu yakalandı varsa test şimdi başarısız olduğunu gösterir. Özel durum catch deyimi sıfırlar ve yöntemi yeni assert başarısız yürütmek devam eder. Yeni sorunu gidermek için eklediğimiz bir `return` sonra deyimi `StringAssert`. Retesting bizim sorunları çözümledik onaylar. Bizim son sürümünü `Debit_WhenAmountIsMoreThanBalance_ShouldThrowArgumentOutOfRange` aşağıdaki gibi görünür:  
  
```csharp  
[TestMethod]  
public void Debit_WhenAmountIsMoreThanBalance_ShouldThrowArgumentOutOfRange()  
{  
    // arrange  
    double beginningBalance = 11.99;  
    double debitAmount = 20.0;  
    BankAccount account = new BankAccount("Mr. Bryan Walton", beginningBalance);  
  
    // act  
    try  
    {  
        account.Debit(debitAmount);  
    }  
    catch (ArgumentOutOfRangeException e)  
    {  
        // assert  
        StringAssert.Contains(e.Message, BankAccount. DebitAmountExceedsBalanceMessage);  
        return;  
    }  
    Assert.Fail("No exception was thrown.");  
}  
  
```  
  
 Son Bu bölümde, daha sağlam ve bilgilendirici test yöntemleri bizim test kodu geliştirme yaptığımız iş gerektiriyordu. Ancak daha da önemlisi, ek çözümleme de daha iyi kodda Projemizin test etmeleri.
