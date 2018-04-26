---
title: Visual Studio C++ çekirdek yönergeleri denetleyicisi başvurusu
ms.date: 03/22/2018
ms.prod: visual-studio-dev15
ms.technology: vs-ide-code-analysis
ms.topic: reference
helpviewer_keywords:
- code analysis, C++ core check
ms.assetid: f1429463-136e-41ed-8a75-a8dbf0b4fd89
author: mikeblome
ms.author: mblome
manager: wpickett
ms.workload:
- cplusplus
ms.openlocfilehash: 09abcf8b1ece1360056a479df568db3a4e569ff1
ms.sourcegitcommit: e13e61ddea6032a8282abe16131d9e136a927984
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/26/2018
---
# <a name="c-core-guidelines-checker-reference"></a>C++ çekirdek yönergeleri denetleyicisi başvurusu

Bu bölümde, C++ çekirdek yönergeleri denetleyicisi uyarıları listelenir. Kod çözümleme hakkında daha fazla bilgi için bkz: [/ analyze (kod çözümleme)](/cpp/build/reference/analyze-code-analysis) ve [hızlı başlangıç: C/C++ için Kod Analizi](../code-quality/quick-start-code-analysis-for-c-cpp.md).

> [!NOTE]
> Bazı uyarılar birden fazla gruba ait ve tüm uyarılar tam başvuru konusuna sahip.

## <a name="ownerpointer-group"></a>OWNER_POINTER grubu

[C26402 DONT_HEAP_ALLOCATE_MOVABLE_RESULT](C26402.md) Return a scoped object instead of a heap-allocated if it has a move constructor. Bkz: [C++ çekirdek yönergeleri R.3](https://github.com/isocpp/CppCoreGuidelines/blob/master/CppCoreGuidelines.md#Rr-ptr).

[C26403 RESET_OR_DELETE_OWNER](C26403.md) sıfırlama veya açıkça sahibi silme\<T > işaretçi '% değişken %'. Bkz: [C++ çekirdek yönergeleri R.3](https://github.com/isocpp/CppCoreGuidelines/blob/master/CppCoreGuidelines.md#Rr-ptr).

[C26404 DONT_DELETE_INVALID](C26404.md) sahibi silmeyin\<T > geçersiz bir durumda olabilir. Bkz: [C++ çekirdek yönergeleri R.3](https://github.com/isocpp/CppCoreGuidelines/blob/master/CppCoreGuidelines.md#Rr-ptr).

[C26405 DONT_ASSIGN_TO_VALID](C26405.md) sahip atamayın\<T > geçerli bir durumda olabilir. Bkz: [C++ çekirdek yönergeleri R.3](https://github.com/isocpp/CppCoreGuidelines/blob/master/CppCoreGuidelines.md#Rr-ptr).

[C26406 DONT_ASSIGN_RAW_TO_OWNER](C26406.md) ham bir işaretçi bir sahip atamayın\<T >. Bkz: [C++ çekirdek yönergeleri R.3](https://github.com/isocpp/CppCoreGuidelines/blob/master/CppCoreGuidelines.md#Rr-ptr).

[C26407 DONT_HEAP_ALLOCATE_UNNECESSARILY](C26407.md) Prefer scoped objects, don't heap-allocate unnecessarily. Bkz: [C++ çekirdek yönergeleri R.5](https://github.com/isocpp/CppCoreGuidelines/blob/master/CppCoreGuidelines.md#Rr-scoped).

[C26429 USE_NOTNULL](C26429.md) simge '% simgesi %' nullness için hiçbir zaman test, Nothing işaretlenebilir. Bkz: [C++ çekirdek yönergeleri F.23](https://github.com/isocpp/CppCoreGuidelines/blob/master/CppCoreGuidelines.md#f23-use-a-not_nullt-to-indicate-that-null-is-not-a-valid-value).

[C26430 TEST_ON_ALL_PATHS](C26430.md) simge '% simgesi %' nullness tüm yazmalar için test değil. Bkz: [C++ çekirdek yönergeleri F.23](https://github.com/isocpp/CppCoreGuidelines/blob/master/CppCoreGuidelines.md#f23-use-a-not_nullt-to-indicate-that-null-is-not-a-valid-value).

[C26431 DONT_TEST_NOTNULL](C26431.md) ifadesi '% expr %' zaten gsl::not_null türüdür. Nullness için sınamayın. Bkz: [C++ çekirdek yönergeleri F.23](https://github.com/isocpp/CppCoreGuidelines/blob/master/CppCoreGuidelines.md#f23-use-a-not_nullt-to-indicate-that-null-is-not-a-valid-value).

## <a name="rawpointer-group"></a>RAW_POINTER grubu

[C26400 NO_RAW_POINTER_ASSIGNMENT](c26400.md) bir ayırma veya işlev çağrısının sonucunu sahip atamayın\<T > dönüş değeri ham işaretçi; sahibi kullanın\<T > bunun yerine. Bkz: [C++ çekirdek yönergeleri I.11](https://github.com/isocpp/CppCoreGuidelines/blob/master/CppCoreGuidelines.md#Ri-raw).

[C26401 DONT_DELETE_NON_OWNER](c26401.md) sahibi değil raw bir işaretçi silmeyin\<T >. Bkz: [C++ çekirdek yönergeleri I.11](https://github.com/isocpp/CppCoreGuidelines/blob/master/CppCoreGuidelines.md#Ri-raw).

[C26402 DONT_HEAP_ALLOCATE_MOVABLE_RESULT](C26402.md)  Return a scoped object instead of a heap-allocated if it has a move constructor. Bkz: [C++ çekirdek yönergeleri R.3](https://github.com/isocpp/CppCoreGuidelines/blob/master/CppCoreGuidelines.md#Rr-ptr).

[C26408 NO_MALLOC_FREE](C26408.md) malloc() ve free() kaçınmak için tercih nothrow sürümüyle yeni Sil. Bkz: [C++ çekirdek yönergeleri R.10](https://github.com/isocpp/CppCoreGuidelines/blob/master/CppCoreGuidelines.md#Rr-mallocfree).

[C26409 NO_NEW_DELETE](C26409.md) kaçının yeni arama ve açıkça silebilir, std::make_unique\<T > bunun yerine. Bkz: [C++ çekirdek yönergeleri R.11](https://github.com/isocpp/CppCoreGuidelines/blob/master/CppCoreGuidelines.md#Rr-newdelete).

[C26429 USE_NOTNULL](C26429.md) simge '% simgesi %' nullness için hiçbir zaman test, Nothing işaretlenebilir. Bkz: [C++ çekirdek yönergeleri F.23](https://github.com/isocpp/CppCoreGuidelines/blob/master/CppCoreGuidelines.md#f23-use-a-not_nullt-to-indicate-that-null-is-not-a-valid-value).

[C26430 TEST_ON_ALL_PATHS](C26430.md) simge '% simgesi %' nullness tüm yazmalar için test değil. Bkz: [C++ çekirdek yönergeleri F.23](https://github.com/isocpp/CppCoreGuidelines/blob/master/CppCoreGuidelines.md#f23-use-a-not_nullt-to-indicate-that-null-is-not-a-valid-value).

[C26431 DONT_TEST_NOTNULL](C26431.md) ifadesi '% expr %' zaten gsl::not_null türüdür. Nullness için sınamayın. Bkz: [C++ çekirdek yönergeleri F.23](https://github.com/isocpp/CppCoreGuidelines/blob/master/CppCoreGuidelines.md#f23-use-a-not_nullt-to-indicate-that-null-is-not-a-valid-value).

[C26481 NO_POINTER_ARITHMETIC](C26481.md) işaretçi aritmetiği kullanmayın. Aralık kullanın. Bkz: [C++ çekirdek yönergeleri Bounds.1](https://github.com/isocpp/CppCoreGuidelines/blob/master/CppCoreGuidelines.md#SS-bounds).

[C26485 NO_ARRAY_TO_POINTER_DECAY](C26485.md).
'% Expr %' ifadesi: işaretçi decay için dizisi yok. Bkz: [C++ çekirdek yönergeleri Bounds.3](https://github.com/isocpp/CppCoreGuidelines/blob/master/CppCoreGuidelines.md#SS-bounds).

## <a name="uniquepointer-group"></a>UNIQUE_POINTER grubu

[C26410 NO_REF_TO_CONST_UNIQUE_PTR](C26410.md) '% parametre %' parametresi başvurusudur `const` benzersiz işaretçi const T * veya const T kullanın ve bunun yerine. Bkz: [C++ çekirdek yönergeleri R.32](https://github.com/isocpp/CppCoreGuidelines/blob/master/CppCoreGuidelines.md#Rr-uniqueptrparam).

[C26411 NO_REF_TO_UNIQUE_PTR](C26411.md) parametresi '% parametre %' benzersiz işaretçi başvuru, hiçbir zaman yeniden atandığında veya sıfırlamak için T * veya T kullanın ve bunun yerine. Bkz: [C++ çekirdek yönergeleri R.33](https://github.com/isocpp/CppCoreGuidelines/blob/master/CppCoreGuidelines.md#Rr-reseat).

[C26414 RESET_LOCAL_SMART_PTR](C26414.md) taşımak, kopyalama, yeniden atama veya yerel akıllı işaretçi '% simgesi %' Sıfırla. Bkz: [C++ çekirdek yönergeleri R.5](https://github.com/isocpp/CppCoreGuidelines/blob/master/CppCoreGuidelines.md#Rr-scoped).

[C26415 SMART_PTR_NOT_NEEDED](C26415.md) '% simgesi %' Akıllı işaretçi parametresi yalnızca kapsanan işaretçi erişmek için kullanılır. T * veya T kullanın ve bunun yerine. Bkz: [C++ çekirdek yönergeleri R.30](https://github.com/isocpp/CppCoreGuidelines/blob/master/CppCoreGuidelines.md#Rr-smartptrparam).

## <a name="sharedpointer-group"></a>SHARED_POINTER grubu

[C26414 RESET_LOCAL_SMART_PTR](C26414.md) taşımak, kopyalama, yeniden atama veya yerel akıllı işaretçi '% simgesi %' Sıfırla. Bkz: [C++ çekirdek yönergeleri R.5](https://github.com/isocpp/CppCoreGuidelines/blob/master/CppCoreGuidelines.md#Rr-scoped).

[C26415 SMART_PTR_NOT_NEEDED](C26415.md) '% simgesi %' Akıllı işaretçi parametresi yalnızca kapsanan işaretçi erişmek için kullanılır. T * veya T kullanın ve bunun yerine. Bkz: [C++ çekirdek yönergeleri R.30](https://github.com/isocpp/CppCoreGuidelines/blob/master/CppCoreGuidelines.md#Rr-smartptrparam).

[C26416 NO_RVALUE_REF_SHARED_PTR](C26416.md) paylaşılan işaretçi parametresi '% simgesi %' rvalue başvuru geçirilir. Değere göre bunun yerine geçer. Bkz: [C++ çekirdek yönergeleri R.34](https://github.com/isocpp/CppCoreGuidelines/blob/master/CppCoreGuidelines.md#Rr-sharedptrparam-owner).

[C26417 NO_LVALUE_REF_SHARED_PTR](C26417.md) paylaşılan işaretçi parametresi '% simgesi %' başvuruya göre geçirilen ve sıfırlama ya da yeniden atandı. T * veya T kullanın ve bunun yerine. Bkz: [C++ çekirdek yönergeleri R.35](https://github.com/isocpp/CppCoreGuidelines/blob/master/CppCoreGuidelines.md#Rr-sharedptrparam).

[C26418 NO_VALUE_OR_CONST_REF_SHARED_PTR](C26418.md) Shared pointer parameter '%symbol%' is not copied or moved. T * veya T kullanın ve bunun yerine. Bkz: [C++ çekirdek yönergeleri R.36](https://github.com/isocpp/CppCoreGuidelines/blob/master/CppCoreGuidelines.md#Rr-sharedptrparam-const).

## <a name="declaration-group"></a>BİLDİRİM grubu

[C26426 NO_GLOBAL_INIT_CALLS](C26426.md) genel Başlatıcı constexpr olmayan işlevi '% simgesi %' çağırır. Bkz: [C++ çekirdek yönergeleri I.22](https://github.com/isocpp/CppCoreGuidelines/blob/master/CppCoreGuidelines.md#i22-avoid-complex-initialization-of-global-objects).

[C26427 NO_GLOBAL_INIT_EXTERNS](C26427.md) genel Başlatıcı extern nesnesi '% simgesi %' erişir. Bkz: [C++ çekirdek yönergeleri I.22](https://github.com/isocpp/CppCoreGuidelines/blob/master/CppCoreGuidelines.md#i22-avoid-complex-initialization-of-global-objects).

[C26444 NO_UNNAMED_RAII_OBJECTS](c26444.md) özel oluşturma ve yok etme nesneleriyle adlandırılmamış kaçının. Bkz: [ES.84: (kurtarmayın) adı olmayan yerel bir değişken bildirme](https://github.com/isocpp/CppCoreGuidelines/blob/master/CppCoreGuidelines.md).

## <a name="class-group"></a>SINIF grubu

[C26432 DEFINE_OR_DELETE_SPECIAL_OPS](C26432.md) tanımlayın veya herhangi bir varsayılan işlemi '% simgesi %' türündeki silerseniz tanımlamak veya tümünü silin. Bkz: [C++ çekirdek yönergeleri C.21](https://github.com/isocpp/CppCoreGuidelines/blob/master/CppCoreGuidelines.md#c21-if-you-define-or-delete-any-default-operation-define-or-delete-them-all).

[C26433 OVERRIDE_EXPLICITLY](c26433.md) işlevi '% simgesi %' 'override' ile işaretlenmiş. Bkz: [C.128: sanal işlevleri tam olarak bir sanal, geçersiz kılma veya son belirtmelidir](https://github.com/isocpp/CppCoreGuidelines/blob/master/CppCoreGuidelines.md#c128-virtual-functions-should-specify-exactly-one-of-virtual-override-or-final).

[C26434 DONT_HIDE_METHODS](C26434.md) işlevi '% symbol_1% ', '% symbol_2% ' sanal olmayan bir işlev gizler. Bkz: [C++ çekirdek yönergeleri C.128](https://github.com/isocpp/CppCoreGuidelines/blob/master/CppCoreGuidelines.md#c128-virtual-functions-should-specify-exactly-one-of-virtual-override-or-final).

[C26435 SINGLE_VIRTUAL_SPECIFICATION](c26435.md) işlevi '% simgesi %' 'sanal', 'override' veya 'final' tam olarak birine belirtmeniz gerekir. Bkz: [C.128: sanal işlevleri tam olarak bir sanal, geçersiz kılma veya son belirtmelidir](https://github.com/isocpp/CppCoreGuidelines/blob/master/CppCoreGuidelines.md).


[C26436 NEED_VIRTUAL_DTOR](C26436.md) ortak ya da sanal ya da korumalı olmayan yıkıcı bir sanal işleve sahip ' % simgesi %' türü gerekiyor. Bkz: [C++ çekirdek yönergeleri C.35](https://github.com/isocpp/CppCoreGuidelines/blob/master/CppCoreGuidelines.md#c35-a-base-class-destructor-should-be-either-public-and-virtual-or-protected-and-nonvirtual).


[C26443 NO_EXPLICIT_DTOR_OVERRIDE](c26443.md) geçersiz kılınıyor yıkıcı açık 'override' veya 'sanal' tanımlayıcıları değil kullanmalıdır. Bkz: [C.128: sanal işlevleri tam olarak bir sanal, geçersiz kılma veya son belirtmelidir](https://github.com/isocpp/CppCoreGuidelines/blob/master/CppCoreGuidelines.md).


## <a name="type-group"></a>Tür grubu

[C26437 DONT_SLICE](C26437.md) olmayan dilim. Bkz: [C++ çekirdek yönergeleri ES.63](https://github.com/isocpp/CppCoreGuidelines/blob/master/CppCoreGuidelines.md#es63-dont-slice).

## <a name="style-group"></a>Stil grubu

[C26438 NO_GOTO](C26438.md) kaçının `goto`. Bkz: [C++ çekirdek yönergeleri ES.76](https://github.com/isocpp/CppCoreGuidelines/blob/master/CppCoreGuidelines.md#es76-avoid-goto).

## <a name="function-group"></a>İŞLEV grubu

[C26439 SPECIAL_NOEXCEPT](C26439.md) bu tür bir işlev değil atabilir. Bildirirken `noexcept`. Bkz: [C++ çekirdek yönergeleri F.6](https://github.com/isocpp/CppCoreGuidelines/blob/master/CppCoreGuidelines.md#f6-if-your-function-may-not-throw-declare-it-noexcept).

[C26440 DECLARE_NOEXCEPT](C26440.md) işlevi '% simgesi %' bildirilebilir `noexcept`. Bkz: [C++ çekirdek yönergeleri F.6](https://github.com/isocpp/CppCoreGuidelines/blob/master/CppCoreGuidelines.md#f6-if-your-function-may-not-throw-declare-it-noexcept).

[C26447 DONT_THROW_IN_NOEXCEPT](c26447.md) işlevi bildirilmiş **noexcept** ancak özel durumlar atabilir bir işlevi çağırır.
Bkz: [C++ çekirdek yönergeleri: F.6: işlevinizi atabilir değil, noexcept bildirme](https://github.com/isocpp/CppCoreGuidelines/blob/master/CppCoreGuidelines.md#f6-if-your-function-may-not-throw-declare-it-noexcept).

## <a name="concurrency-group"></a>EŞZAMANLILIK grubu

[C26441 NO_UNNAMED_GUARDS](C26441.md) koruma nesneler adlandırılmış. Bkz: [C++ çekirdek yönergeleri cp.44](https://github.com/isocpp/CppCoreGuidelines/blob/master/CppCoreGuidelines.md#cp44-remember-to-name-your-lock_guards-and-unique_locks).

## <a name="const-group"></a>CONST grubu

[C26460 USE_CONST_REFERENCE_ARGUMENTS](c26460.md) başvurusu bağımsız değişkeni '% değişken % ''işlevinin '% işlevi %' olarak işaretlenmiş `const`. Bkz: [C++ çekirdek yönergeleri con.3](https://github.com/isocpp/CppCoreGuidelines/blob/master/CppCoreGuidelines.md#Rconst-ref).

[C26461 USE_CONST_POINTER_ARGUMENTS](c26461.md): '% işlevi %' işlevi için işaretçi değişkeni '% değişken %' için bir işaretçi olarak işaretlenebilir `const`. Bkz: [C++ çekirdek yönergeleri con.3](https://github.com/isocpp/CppCoreGuidelines/blob/master/CppCoreGuidelines.md#Rconst-ref).

[C26462 USE_CONST_POINTER_FOR_VARIABLE](c26462.md) '% değişken % tarafından' işaret değeri yalnızca bir kez atanır, bir işaretçi olarak işaretle `const`. Bkz: [C++ çekirdek yönergeleri con.4](https://github.com/isocpp/CppCoreGuidelines/blob/master/CppCoreGuidelines.md#con4-use-const-to-define-objects-with-values-that-do-not-change-after-construction).

[C26463 USE_CONST_FOR_ELEMENTS](c26463.md) '% dizi %' dizinin öğeleri yalnızca bir kez işareti öğeleri atanan `const`. Bkz: [C++ çekirdek yönergeleri con.4](https://github.com/isocpp/CppCoreGuidelines/blob/master/CppCoreGuidelines.md#con4-use-const-to-define-objects-with-values-that-do-not-change-after-construction).

[C26464 USE_CONST_POINTER_FOR_ELEMENTS](c26464.md) '% dizi %' dizisi öğeleri tarafından işaret değerleri yalnızca bir kez işareti öğeleri işaretçi olarak atanan `const`. Bkz: [C++ çekirdek yönergeleri con.4](https://github.com/isocpp/CppCoreGuidelines/blob/master/CppCoreGuidelines.md#con4-use-const-to-define-objects-with-values-that-do-not-change-after-construction).

[C26496 USE_CONST_FOR_VARIABLE](c26496.md) değişkeni '% değişken %' yalnızca bir kez atanır, olarak işaretlemek `const`. Bkz: [C++ çekirdek yönergeleri con.4](https://github.com/isocpp/CppCoreGuidelines/blob/master/CppCoreGuidelines.md#con4-use-const-to-define-objects-with-values-that-do-not-change-after-construction).

[C26497 USE_CONSTEXPR_FOR_FUNCTION](c26497.md) bu işlevi işlevi % işaretlenebilir `constexpr` derleme zamanı değerlendirme isterseniz. Bkz: [C++ çekirdek yönergeleri F.4](https://github.com/isocpp/CppCoreGuidelines/blob/master/CppCoreGuidelines.md#Rf-constexpr).

[C26498 USE_CONSTEXPR_FOR_FUNCTIONCALL](c26498.md) bu işlev çağrısı işlevi % kullanabilirsiniz `constexpr` derleme zamanı değerlendirme isterseniz. Bkz: [C++ çekirdek yönergeleri con.5](https://github.com/isocpp/CppCoreGuidelines/blob/master/CppCoreGuidelines.md#Rconst-constexpr).

## <a name="type-group"></a>Tür grubu

[C26465 NO_CONST_CAST_UNNECESSARY](c26465.md) kullanmayan `const_cast` hemen yayınlanamıyor `const`. `const_cast` gerekli değildir; Bu dönüştürme kaldırılmıyor constness veya volatilite. Bkz: [C++ çekirdek yönergeleri Type.3](https://github.com/isocpp/CppCoreGuidelines/blob/master/CppCoreGuidelines.md#Pro-type-constcast).

[C26466 NO_STATIC_DOWNCAST_POLYMORPHIC](c26466.md) kullanmayan `static_cast` downcasts. Çok biçimli türünden bir cast dynamic_cast kullanmanız gerekir. Bkz: [C++ çekirdek yönergeleri Type.2](https://github.com/isocpp/CppCoreGuidelines/blob/master/CppCoreGuidelines.md#Pro-type-downcast).

[C26471 NO_REINTERPRET_CAST_FROM_VOID_PTR](c26471.md) Don't use `reinterpret_cast`. Bir dönüştürme void * kullanabilirsiniz `static_cast`. Bkz: [C++ çekirdek yönergeleri Type.1](https://github.com/isocpp/CppCoreGuidelines/blob/master/CppCoreGuidelines.md#Pro-type-reinterpretcast).

[C26472 NO_CASTS_FOR_ARITHMETIC_CONVERSION](C26472.md) kullanmayan bir `static_cast` aritmetik dönüşümler için. Küme parantezi başlatma, gsl::narrow_cast veya gsl::narow kullanın. Bkz: [C++ çekirdek yönergeleri Type.1](https://github.com/isocpp/CppCoreGuidelines/blob/master/CppCoreGuidelines.md#Pro-type-reinterpretcast).

[C26473 NO_IDENTITY_CAST](C26473.md) kaynak türü ve hedef türü nerede aynı işaretçi türleri arasında dönüştürme yok. Bkz: [C++ çekirdek yönergeleri Type.1](https://github.com/isocpp/CppCoreGuidelines/blob/master/CppCoreGuidelines.md#Pro-type-reinterpretcast).

[C26474 NO_IMPLICIT_CAST](C26474.md) dönüştürme örtük olabilir işaretçi türleri arasında dönüştürme yok. Bkz: [C++ çekirdek yönergeleri Type.1](https://github.com/isocpp/CppCoreGuidelines/blob/master/CppCoreGuidelines.md#Pro-type-reinterpretcast).

[C26475 NO_FUNCTION_STYLE_CASTS](C26475.md) işlevi stili C atamaları kullanmayın. Bkz: [C++ çekirdek yönergeleri ES.49](https://github.com/isocpp/CppCoreGuidelines/blob/master/CppCoreGuidelines.md#es49-if-you-must-use-a-cast-use-a-named-cast).

[C26490 NO_REINTERPRET_CAST](c26490.md) kullanmayan `reinterpret_cast`. Bkz: [C++ çekirdek yönergeleri Type.1](https://github.com/isocpp/CppCoreGuidelines/blob/master/CppCoreGuidelines.md#SS-type).

[C26491 NO_STATIC_DOWNCAST](c26490.md) kullanmayan `static_cast` downcasts. Bkz: [C++ çekirdek yönergeleri Type.2](https://github.com/isocpp/CppCoreGuidelines/blob/master/CppCoreGuidelines.md#SS-type).

[C26492 NO_CONST_CAST](c26492.md) kullanmayan `const_cast` hemen yayınlanamıyor `const`. Bkz: [C++ çekirdek yönergeleri Type.3](https://github.com/isocpp/CppCoreGuidelines/blob/master/CppCoreGuidelines.md#SS-type).

[C26493 NO_CSTYLE_CAST](c26493.md) C türü atamalar kullanmayın. Bkz: [C++ çekirdek yönergeleri Type.4](https://github.com/isocpp/CppCoreGuidelines/blob/master/CppCoreGuidelines.md#SS-type).

[C26494 VAR_USE_BEFORE_INIT](c26494.md) değişkeni '% değişken %', başlatılmamış. Her zaman bir nesneyi başlatın. Bkz: [C++ çekirdek yönergeleri Type.5](https://github.com/isocpp/CppCoreGuidelines/blob/master/CppCoreGuidelines.md#SS-type).

[C26495 MEMBER_UNINIT](c26495.md) değişkeni '% değişken %', başlatılmamış. Her zaman bir üye değişkenine başlatır. Bkz: [C++ çekirdek yönergeleri Type.6](https://github.com/isocpp/CppCoreGuidelines/blob/master/CppCoreGuidelines.md#SS-type).

## <a name="bounds-group"></a>SINIR grubu

[C26446 USE_GSL_AT](c26446.md) kullanmayı tercih `gsl::at()` yerine denetlenmeyen alt simge işleci. Bkz: [C++ çekirdek yönergeleri: Bounds.4: Standart Kitaplığı işlevleri ve sınırları işaretli olmayan türlerini kullanmayan](https://github.com/isocpp/CppCoreGuidelines/blob/master/CppCoreGuidelines.md#probounds-bounds-safety-profile).

[C26481 NO_POINTER_ARITHMETIC](C26481.md).
İşaretçi aritmetiği kullanmayın. Aralık kullanın. Bkz: [C++ çekirdek yönergeleri Bounds.1](https://github.com/isocpp/CppCoreGuidelines/blob/master/CppCoreGuidelines.md#SS-bounds)

[C26482 NO_DYNAMIC_ARRAY_INDEXING](c26482.md) yalnızca, sabit ifadeler kullanarak diziye dizin. Bkz: [C++ çekirdek yönergeleri Bounds.2](https://github.com/isocpp/CppCoreGuidelines/blob/master/CppCoreGuidelines.md#SS-bounds)

[C26483 STATIC_INDEX_OUT_OF_RANGE](c26483.md) değeri % değeri olan sınırları dışında (0, bağlı %) '% değişken %' değişkeninin. Yalnızca dizine dizi sınırları içinde sabit ifadeler kullanarak dizileri. Bkz: [C++ çekirdek yönergeleri Bounds.2](https://github.com/isocpp/CppCoreGuidelines/blob/master/CppCoreGuidelines.md#SS-bounds)

[C26485 NO_ARRAY_TO_POINTER_DECAY](C26485.md) ifadesi '% expr %': işaretçi decay için dizisi yok. Bkz: [C++ çekirdek yönergeleri Bounds.3](https://github.com/isocpp/CppCoreGuidelines/blob/master/CppCoreGuidelines.md#SS-bounds)

## <a name="gsl-group"></a>GSL grubu

[C26445 NO_SPAN_REF](c26445.md) başvuru `gsl::span` veya `std::string_view` ömrü sorun belirtisi olabilir.
Bkz: [C++ çekirdek yönergeleri GSL.view: görünümleri](https://github.com/isocpp/CppCoreGuidelines/blob/master/CppCoreGuidelines.md#gslview-views)

[C26446 USE_GSL_AT](c26446.md) kullanmayı tercih `gsl::at()` yerine denetlenmeyen alt simge işleci. Bkz: [C++ çekirdek yönergeleri: Bounds.4: Standart Kitaplığı işlevleri ve sınırları işaretli olmayan türlerini kullanmayan](https://github.com/isocpp/CppCoreGuidelines/blob/master/CppCoreGuidelines.md#probounds-bounds-safety-profile).

[C26448 USE_GSL_FINALLY ](c26448.md) düşünün kullanarak `gsl::finally` son eylem amaçlanıyorsa. Bkz: [C++ çekirdek yönergeleri: GSL.util: yardımcı programlar](https://github.com/isocpp/CppCoreGuidelines/blob/master/CppCoreGuidelines.md#SS-utilities).

[C26449 NO_SPAN_FROM_TEMPORARY](c26449.md) 
 `gsl::span` veya `std::string_view` geçici bir zaman geçersiz oluşturulacak geçici geçersiz kıldı. Bkz: [C++ çekirdek yönergeleri: GSL.view: görünümleri](https://github.com/isocpp/CppCoreGuidelines/blob/master/CppCoreGuidelines.md#gslview-views).


## <a name="deprecated-warnings"></a>Kullanım dışı uyarılar

Aşağıdaki uyarılarla bir erken Deneysel kural kümesindeki çekirdek yönergeleri denetleyicisi varsa, ancak artık kullanımdan kaldırıldı ve güvenle yoksayılabilir. Uyarılar, yukarıdaki listeden uyarıları tarafından kılınan.

- 26412 DEREF_INVALID_POINTER
- 26413 DEREF_NULLPTR
- 26420 ASSIGN_NONOWNER_TO_EXPLICIT_OWNER
- 26421 ASSIGN_VALID_OWNER
- 26422 VALID_OWNER_LEAVING_SCOPE
- 26423 ALLOCATION_NOT_ASSIGNED_TO_OWNER
- 26424 VALID_ALLOCATION_LEAVING_SCOPE
- 26425 ASSIGNING_TO_STATIC
- 26499 NO_LIFETIME_TRACKING

## <a name="see-also"></a>Ayrıca Bkz.
[C++ çekirdek yönergeleri denetleyicileri kullanma](using-the-cpp-core-guidelines-checkers.md)
