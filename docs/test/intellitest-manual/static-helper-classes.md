---
title: "Statik yardımcı sınıfları | Microsoft Intellitest Geliştirici Test aracı | Microsoft Docs"
ms.custom: 
ms.date: 05/02/2017
ms.reviewer: 
ms.suite: 
ms.technology: vs-devops-test
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- IntelliTest, Static helper classes
ms.author: gewarren
manager: ghogen
ms.workload:
- multiple
author: gewarren
ms.openlocfilehash: fe4c855f9fad611dd1131997a86143523f51a80e
ms.sourcegitcommit: 7ae502c5767a34dc35e760ff02032f4902c7c02b
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/09/2018
---
# <a name="static-helper-classes"></a>Statik yardımcı sınıfları

Intellitest yazılırken kullanılan statik yardımcı sınıfını kümesi sağlar [parametreli birim testleri](test-generation.md#parameterized-unit-testing):

* [PexAssume](#pexassume): girişler için varsayımlar tanımlamak için kullanılır ve istenmeyen girişlerini filtreleme için faydalıdır
* [PexAssert](#pexassert): test çerçevesi bir sağlamıyorsa kullanmak için basit onaylama sınıfı
* [PexChoose](#pexchoose): Intellitest yöneten ek sınama Giriş akışı
* [PexObserve](#pexobserve): somut değerleri ve optionaly günlükleri, oluşturulan kodda doğrular

Bazı sınıflar, bir alt düzey adresindeki Intellitest mantığı altyapısı ile etkileşim kurmasına izin ver:

* [PexSymbolicValue](#pexsymbolicvalue): inceleme veya değiştirme değişkenleri simgesel kısıtlamalar için yardımcı programlar

<a name="pexassume"></a>
## <a name="pexassume"></a>PexAssume

Varsayımları gibi ifade etmek için kullanılan bir statik sınıf [önkoşulları](test-generation.md#precondition), [parametreli birim testleri](test-generation.md#parameterized-unit-testing).
Bu sınıf yöntemlerini istenmeyen test girişleri filtrelemek için kullanılabilir.

Varsayılan koşul giriş, bazı test için barındırmıyorsa bir **PexAssumeFailedException** atılır. Bu, sessizce yok sayılacak test neden olur.

**Örnek**

Aşağıdaki parametreli test değil değerlendirir **j = 0**:

```
public void TestSomething(int i, int j) {
     PexAssume.AreNotEqual(j, 0);
     int k = i/j;
     ...
}
```

**Açıklamalar**

Yukarıdaki kod neredeyse eşdeğerdir:

```
     if (j==0)
          return;
```

dışında başarısız **PexAssume** hiçbir test çalışmaları neden olur. Durumunda bir **varsa** deyimi, Intellitest oluşturur karşılamak için ayrı bir test çalışması **sonra** dalı **varsa** deyimi.

**PexAssume** de varsayımlar dize, dizileri ve koleksiyonlar için specialzed iç içe geçmiş sınıflar içerir.

<a name="pexassert"></a>
## <a name="pexassert"></a>PexAssert

Onaylar, gibi ifade etmek için kullanılan bir statik sınıf [Sonkoşullar](test-generation.md#postcondition), [parametreli birim testleri](test-generation.md#parameterized-unit-testing).

Onaylanan koşul giriş, bazı test için barındırmıyorsa bir **PexAssertFailedException** oluşturulur, testin başarısız olmasına neden olur.

**Örnek**

Tamsayı mutlak değeri pozitif olduğunu onaylar:

```
public void TestSomething(int i) {
     int j = Maths.Abs(i);
     PexAssert.IsTrue(j >= 0);
     ...
}
```

<a name="pexchoose"></a>
## <a name="pexchoose"></a>PexChoose

Uygulamak için kullanılan bir teste yardımcı giriş değerlerini sağlayan bir statik sınıf [parametreli Mocks](input-generation.md#parameterized-mocks).

**PexChoose** sınıfı yardımcı bir testi geçtiğini veya belirli giriş değerleri için başarısız olduğunu belirlemede. **PexChoose** de denir giriş değerleri yalnızca sağlar *seçimleri*. Bunu hala kadar giriş değerleri kısıtlamak için ve bir test başarılı veya başarısız olduğunda tanımlayan onaylar yazmak için kullanıcıdır.

**İşlem modları**

**PexChoose** sınıfı, iki modda çalışabilir:

* Test sırasında test edilen kodu ve simgesel analiz Intellitest gerçekleştirirken [giriş nesil](input-generation.md), rastgele değerler Seçici döndürür ve Intellitest izleyen her değer test ve test edilen kodu nasıl kullanılır. Intellitest test ve test edilen kodu farklı bir yürütme yollarında tetiklemek için ilgili değerleri oluşturur.

* Belirli test durumları için oluşturulan kodu seçim Sağlayıcısı'nı belirli bir şekilde ayarlar, böylece bu tür bir test çalışmasının yeniden yürütme belirli yürütme yolu tetiklemek için belirli seçenekleri hale getirir.

**Kullanım**

* Basit Arama **PexChoose.Value** yeni bir değer üretmek için:

```
public int Foo() {
    return PexChoose.Value<int>("foo");
}
```

<a name="pexobserve"></a>
## <a name="pexobserve"></a>PexObserve

Adlandırılmış değerler oturum için statik bir sınıf.

Kod Intellitest araştırır zaman **PexObserve** kendi biçimlendirilmiş dize Beyanları kullanılarak hesaplanan değerler kaydetmek için kullanılır. Değerlerin benzersiz adı ile ilişkilendirilir.

```
PexObserve.Value<string>("result", result);
```

**Örnek**

```
// product code
public static class MathEx {
     public static int Square(int value) { return value * value; }
}


// fixture
[TestClass]
public partial class MathExTests {
     [PexMethod]
     public int SquareTest(int a) {
        int result = MathEx.Square(a); 
        // storing result
        return result;
     }
}
```

<a name="pexsymbolicvalue"></a>
## <a name="pexsymbolicvalue"></a>PexSymbolicValue

Statik sınıf parametrelerindeki kısıtlamalar yoksay ve değerleri ile ilişkili simgesel bilgilerini yazdırmak için kullanılır.

**Kullanım**

Normalde, yürütme sırasında tüm yürütme yolları kodunun kapsayacak şekilde Intellitest çalışır. Ancak, özellikle varsayılır ve onaylama koşullar hesaplanırken, tüm olası durumların araştırmanız gereken değil.

**Örnek**

Bu örnek uygulaması gösterir **PexAssume.Arrays.ElementsAreNotNull** yöntemi. Yönteminde dizinin farklı boyutlarda oluşturmaya çalışırken Intellitest önlemek için dize değeri lengh kısıtlamalar yoksay. Kısıtlamalar yalnızca burada göz ardı edilir. Test edilen kodu için farklı dizisi uzunluklarının farklı şekilde davranan, Intellitest test edilmiş kod kısıtlamaları farklı boyutlu diziler oluşturulamıyor.

```
public static void AreElementsNotNull<T>(T[] value)
    where T : class
{
    PexAssume.NotNull(value);
    // the followings prevents the exploration of all array lengths
    int len = PexSymbolicValue.Ignore<int>(value.Length);

    // building up a boolean value as follows prevents exploration
    // of all combinations of non-null (instead, there are just two cases)
    bool anyNull = false;
    for (int i = 0; i < len; ++i)
        anyNull |= value[i] == null;

    // was any element null?
    if (anyNull)
        PexAssume.Fail("some element of array is a null reference");
}
```

## <a name="got-feedback"></a>Geri bildirim var mı?

Fikirlerinizi sonrası ve özellik istekleri  **[UserVoice](https://visualstudio.uservoice.com/forums/121579-visual-studio-2015/category/157869-test-tools?query=IntelliTest)**.
