---
title: En İyi Yöntemler ve Örnekler (SAL)
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
ms.technology: vs-ide-code-analysis
ms.topic: conceptual
author: mikeblome
ms.author: mblome
manager: wpickett
ms.workload:
- multiple
ms.openlocfilehash: 5e1b86508b803844255458f3aa2c7f33d859af93
ms.sourcegitcommit: e13e61ddea6032a8282abe16131d9e136a927984
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/26/2018
ms.locfileid: "31901000"
---
# <a name="best-practices-and-examples-sal"></a>En İyi Yöntemler ve Örnekler (SAL)
Kaynak kodu ek açıklama dili (SAL) dışında en ve bazı yaygın sorunlar önlemek için bazı yollar şunlardır.

## <a name="in"></a>\_İçinde\_

Öğesine yazılacak işlev beklenen kullanırsanız `_Inout_` yerine `_In_`. Bu, özellikle eski makroları otomatik bir dönüştürme SAL için durumlarda ilgilidir. SAL önce birçok Programcı makroları yorum olarak kullanılan — adlandırılması makroları `IN`, `OUT`, `IN_OUT`, ya da bu adları çeşitlemelerini. SAL için bu makroları dönüştürmek öneririz, ancak biz de kodu özgün prototip yazılmıştır ve eski makrosu, artık kod yaptığı gösterebilir bu yana değişmiş olabilir çünkü dönüştürdüğünüz zaman dikkatli olmanız bağlantısını okumanızı tavsiye. Hakkında özellikle dikkat `OPTIONAL` , sık sık yanlış yerleştirildiğinden makrosu açıklama — Örneğin, tarafındaki yanlış virgül.

```cpp

// Incorrect
void Func1(_In_ int *p1)
{
    if (p1 == NULL)
        return;

    *p1 = 1;
}

// Correct
void Func2(_Inout_ PCHAR p1)
{
    if (p1 == NULL)
        return;

    *p1 = 1;
}
```

## <a name="opt"></a>\_İptal Et\_

Çağıran bir null işaretçi geçmesine izin verilmiyor kullanırsanız `_In_` veya `_Out_` yerine `_In_opt_` veya `_Out_opt_`. Bu parametrelerini denetler ve olmamalıdır zaman NULL ise, bir hata döndürür bile bir işlev için geçerlidir. Bir işlev parametresi için beklenmeyen NULL denetleyin ve düzgün bir şekilde dönmek olması iyi bir savunma kodlama uygulama olsa da, bu parametre ek açıklama isteğe bağlı bir türde olabilir gelmez (`_*Xxx*_opt_`).

```cpp

// Incorrect
void Func1(_Out_opt_ int *p1)
{
    *p = 1;
}

// Correct
void Func2(_Out_ int *p1)
{
    *p = 1;
}

```

## <a name="predefensive-and-postdefensive"></a>\_Öncesi\_savunma\_ ve \_Post\_savunma\_

Bir işlev bir güven sınırı varsa, kullanmanız önerilir `_Pre_defensive_` ek açıklama.  "Savunma" değiştiricisi, noktasında çağrı göstermek için bazı ek açıklamaları değiştirir, arabirimi tamamen denetlenmesi, ancak uygulama gövdesinde, yanlış parametreler geçebilir varsayın. Bu durumda, `_In_ _Pre_defensive_` NULL geçirmeye çalışırsa çağıran bir hata iletisiyle karşılaşırsınız rağmen sanki parametresi NULL ve işaretçiyi ilk olmadan XML'deki başvuru girişimleri olabilir işlev gövdesi analiz olduğunu belirtmek için bir güven sınırının adresindeki tercih edilir NULL denetimi işaretlenir.  A `_Post_defensive_` ek açıklama burada güvenilen taraf çağıran olduğu varsayılır ve güvenilmeyen kod çağrılan kod geri aramalar için kullanılabilir de.

## <a name="outwrites"></a>\_Out\_Yazar\_

Aşağıdaki örnek, bir ortak kötüye kullanımı gösterir `_Out_writes_`.

```cpp

// Incorrect
void Func1(_Out_writes_(size) CHAR *pb,
    DWORD size
);

```

Ek açıklamanın `_Out_writes_` arabellek sahip olduğunu belirtir. Bunun `cb` Çıkışta başlatılan ilk bayta kalan ayrılan bayt sayısı. Bu ek açıklama kesinlikle yanlış değil ve ayrılmış boyutu express yararlıdır. Ancak, kaç tane öğeleri işlevi tarafından başlatılmış söylemez.

Sonraki örnek tamamen başlatılmış bölümü arabellek tam boyutunu belirtmek için üç doğru şekilde gösterir.

```cpp

// Correct
void Func1(_Out_writes_to_(size, *pCount) CHAR *pb,
    DWORD size,
    PDWORD pCount
);

void Func2(_Out_writes_all_(size) CHAR *pb,
    DWORD size
);

void Func3(_Out_writes_(size) PSTR pb,
    DWORD size
);

```

## <a name="out-pstr"></a>\_Out\_ PSTR

Kullanımını `_Out_ PSTR` neredeyse her zaman yanlış. Bu bir karakteri arabelleğe işaret eden bir output parametresi sahip olarak yorumlanır ve onu NULL ile sonlandırılmış.

```cpp

// Incorrect
void Func1(_Out_ PSTR pFileName, size_t n);

// Correct
void Func2(_Out_writes_(n) PSTR wszFileName, size_t n);

```

Ek açıklamanın ister `_In_ PCSTR` ortak ve kullanışlıdır. NULL sonlandırma sahip olduğundan bir giriş dizesi işaret önkoşulu `_In_` NULL sonlandırılmış bir dize tanınmasını sağlar.

## <a name="in-wchar-p"></a>\_İçinde\_ WCHAR * p

`_In_ WCHAR* p` bir giriş işaretçisi olduğunu söylüyor `p` işaret eden bir karakter. Bununla birlikte, çoğu durumda bu kullanılmaya belirtimi değil büyük olasılıkla. Bunun yerine, büyük olasılıkla kullanılmaya NULL ile sonlandırılmış bir dizi belirtimidir; Bunu yapmak için kullanmak `_In_ PWSTR`.

```cpp

// Incorrect
void Func1(_In_ WCHAR* wszFileName);

// Correct
void Func2(_In_ PWSTR wszFileName);

```

NULL sonlandırma uygun belirtimi eksik yaygındır. Uygun kullanın `STR` sürüm türü, aşağıdaki örnekte gösterildiği gibi değiştirin.

```cpp

// Incorrect
BOOL StrEquals1(_In_ PCHAR p1, _In_ PCHAR p2)
{
    return strcmp(p1, p2) == 0;
}

// Correct
BOOL StrEquals2(_In_ PSTR p1, _In_ PSTR p2)
{
    return strcmp(p1, p2) == 0;
}

```

## <a name="outrange"></a>\_Out_range\_

Parametre gösteren bir işaretçidir ve işaretçiyi tarafından kullanılacak işaret öğenin değerini aralığını express istiyorsanız `_Deref_out_range_` yerine `_Out_range_`. Aşağıdaki örnekte, aralığı * pcbFilled ifade edilir, pcbFilled değil.

```cpp

// Incorrect
void Func1(
    _Out_writes_bytes_to_(cbSize, *pcbFilled) BYTE *pb,
    DWORD cbSize,
    _Out_range_(0, cbSize) DWORD *pcbFilled
);

// Correct
void Func2(
    _Out_writes_bytes_to_(cbSize, *pcbFilled) BYTE *pb,
    DWORD cbSize,
    _Deref_out_range_(0, cbSize) _Out_ DWORD *pcbFilled
);

```

 `_Deref_out_range_(0, cbSize)` gelen çıkarsanabileceği için bazı araçlar kesinlikle gerekli olmadığından `_Out_writes_to_(cbSize,*pcbFilled)`, ancak bütünlük açısından buraya gösterilir.

## <a name="wrong-context-in-when"></a>Yanlış bağlamda \_zaman\_

Başka bir ortak hata sonrası durum değerlendirme önkoşulları kullanmaktır. Aşağıdaki örnekte, `_Requires_lock_held_` önkoşuluna değil.

```cpp

// Incorrect
_When_(return == 0, _Requires_lock_held_(p->cs))
int Func1(_In_ MyData *p, int flag);

// Correct
_When_(flag == 0, _Requires_lock_held_(p->cs))
int Func2(_In_ MyData *p, int flag);

```

 İfade `result` öncesi kullanılabilir durumda olmayan bir sonrası durum değeri ifade eder.

## <a name="true-in-success"></a>TRUE olarak \_başarılı\_

Dönüş değeri sıfır olduğunda işlevi başarılı olursa kullanmak `return != 0` yerine başarı koşulu olarak `return == TRUE`. NonZero derleyici sağlayan gerçek değer eşdeğerliğine mutlaka gelmez `TRUE`. Parametre `_Success_` ifade olan ve aşağıdaki ifadeler eşdeğer olarak değerlendirilir: `return != 0`, `return != false`, `return != FALSE`, ve `return` parametreleri veya karşılaştırmaları.

```cpp

// Incorrect
_Success_(return == TRUE, _Acquires_lock_(*lpCriticalSection))
BOOL WINAPI TryEnterCriticalSection(
  _Inout_ LPCRITICAL_SECTION lpCriticalSection
);

// Correct
_Success_(return != 0, _Acquires_lock_(*lpCriticalSection))
BOOL WINAPI TryEnterCriticalSection(
  _Inout_ LPCRITICAL_SECTION lpCriticalSection
);

```

## <a name="reference-variable"></a>Başvuru değişkeni

Bir başvuru değişkenin SAL'ın önceki sürümünü zımni işaretçi ek açıklama hedef olarak kullanılan ve eklenmesi gereken bir `__deref` başvuru değişkenine bağlı ek açıklamalara. Bu sürüm nesnenin kendisini kullanır ve ek gerektirmez `_Deref_`.

```cpp

// Incorrect
void Func1(
    _Out_writes_bytes_all_(cbSize) BYTE *pb,
    _Deref_ _Out_range_(0, 2) _Out_ DWORD &cbSize
);

// Correct
void Func2(
    _Out_writes_bytes_all_(cbSize) BYTE *pb,
    _Out_range_(0, 2) _Out_ DWORD &cbSize
);

```

## <a name="annotations-on-return-values"></a>Dönüş değerleri hakkında ek açıklamalar

Aşağıdaki örnek, dönüş değeri ek açıklamalar ortak bir sorunu gösterir.

```cpp

// Incorrect
_Out_opt_ void *MightReturnNullPtr1();

// Correct
_Ret_maybenull_ void *MightReturnNullPtr2();

```

Bu örnekte, `_Out_opt_` işaretçinin önkoşulu bir parçası olarak NULL olabilir söyler. Ancak, önkoşulları dönüş değerini uygulanamaz. Bu durumda, doğru ek açıklama olup `_Ret_maybenull_`.

## <a name="see-also"></a>Ayrıca bkz.

[C/C++ kod hatalarını azaltmak için SAL ek açıklamalarını kullanma](../code-quality/using-sal-annotations-to-reduce-c-cpp-code-defects.md)
[SAL anlama](../code-quality/understanding-sal.md)
[işlev parametrelerini ve dönüş değerlerini açıklama](../code-quality/annotating-function-parameters-and-return-values.md) 
 [İşlev davranışını yorumlama](../code-quality/annotating-function-behavior.md)
[yapıları ve sınıfları yorumlama](../code-quality/annotating-structs-and-classes.md)
[kilitlenme davranışını yorumlama](../code-quality/annotating-locking-behavior.md) 
 [Açıklamanın ne zaman ve nereye uygulanacağını belirtme](../code-quality/specifying-when-and-where-an-annotation-applies.md)
[iç işlevler](../code-quality/intrinsic-functions.md)