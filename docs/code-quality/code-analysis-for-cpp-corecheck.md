---
title: "Visual Studio C++ çekirdek yönergeleri denetleyicisinin başvurusu | Microsoft Docs"
ms.custom: 
ms.date: 01/18/2017
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-code-analysis
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: code analysis, C++ core check
ms.assetid: f1429463-136e-41ed-8a75-a8dbf0b4fd89
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: d5db13aa350e33a297981066f36c3d1dfd1ecb67
ms.sourcegitcommit: bd16e764134c436d2d2f46490f51234d5246ee50
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/22/2018
---
# <a name="c-core-guidelines-checker-reference"></a>C++ çekirdek yönergeleri denetleyicisi başvurusu
Bu bölümde, C++ çekirdek yönergeleri denetleyicisi uyarıları listelenir. Kod çözümleme hakkında daha fazla bilgi için bkz: [/ analyze (kod çözümleme)](/cpp/build/reference/analyze-code-analysis) ve [hızlı başlangıç: C/C++ için Kod Analizi](../code-quality/quick-start-code-analysis-for-c-cpp.md).  
  
**Not**: bazı uyarılar birden fazla gruba ait ve tüm uyarılar başvuru konusu sahiptir.

## <a name="ownerpointer-group"></a>OWNER_POINTER grubu

[C26402 DONT_HEAP_ALLOCATE_MOVABLE_RESULT](C26402.md)  
  Bir taşıma oluşturucusuna varsa yığında ayrılmış yerine kapsamlı bir nesne döndürür. Bkz: [C++ çekirdek yönergeleri R.3](https://github.com/isocpp/CppCoreGuidelines/blob/master/CppCoreGuidelines.md#Rr-ptr). 
     
[C26403 RESET_OR_DELETE_OWNER](C26403.md)  
  Sıfırlamak veya açıkça sahibi silmek\<T > işaretçi '% değişken %'. Bkz: [C++ çekirdek yönergeleri R.3](https://github.com/isocpp/CppCoreGuidelines/blob/master/CppCoreGuidelines.md#Rr-ptr).  
     
[C26404 DONT_DELETE_INVALID](C26404.md)  
  Bir sahip silmeyin\<T > geçersiz bir durumda olabilir. Bkz: [C++ çekirdek yönergeleri R.3](https://github.com/isocpp/CppCoreGuidelines/blob/master/CppCoreGuidelines.md#Rr-ptr).  

[C26405 DONT_ASSIGN_TO_VALID](C26405.md)  
  Bir sahip atamayın\<T > geçerli bir durumda olabilir. Bkz: [C++ çekirdek yönergeleri R.3](https://github.com/isocpp/CppCoreGuidelines/blob/master/CppCoreGuidelines.md#Rr-ptr).  

[C26406 DONT_ASSIGN_RAW_TO_OWNER](C26406.md)  
  Ham bir işaretçi bir sahip atamayın\<T >. Bkz: [C++ çekirdek yönergeleri R.3](https://github.com/isocpp/CppCoreGuidelines/blob/master/CppCoreGuidelines.md#Rr-ptr).  
  
[C26407 DONT_HEAP_ALLOCATE_UNNECESSARILY](C26407.md)  
  Kapsanan nesneler tercih, yığın-gereksiz yere Ayır yok. Bkz: [C++ çekirdek yönergeleri R.5](https://github.com/isocpp/CppCoreGuidelines/blob/master/CppCoreGuidelines.md#Rr-scoped).  

[C26429 USE_NOTNULL](C26429.md)  
  Sembol '% simgesi %' nullness için hiç test etmediniz, Nothing işaretlenebilir. Bkz: [C++ çekirdek yönergeleri F.23](https://github.com/isocpp/CppCoreGuidelines/blob/master/CppCoreGuidelines.md#f23-use-a-not_nullt-to-indicate-that-null-is-not-a-valid-value).  

[C26430 TEST_ON_ALL_PATHS](C26430.md)  
  '% Simgesi %' simgesi nullness tüm yazmalar için test edilmemiştir. Bkz: [C++ çekirdek yönergeleri F.23](https://github.com/isocpp/CppCoreGuidelines/blob/master/CppCoreGuidelines.md#f23-use-a-not_nullt-to-indicate-that-null-is-not-a-valid-value).  
  
[C26431 DONT_TEST_NOTNULL](C26431.md)  
  '% Expr %' ifadesinin zaten gsl::not_null türüdür. Nullness için sınamayın. Bkz: [C++ çekirdek yönergeleri F.23](https://github.com/isocpp/CppCoreGuidelines/blob/master/CppCoreGuidelines.md#f23-use-a-not_nullt-to-indicate-that-null-is-not-a-valid-value).  

## <a name="rawpointer-group"></a>RAW_POINTER Group
 
[C26400 NO_RAW_POINTER_ASSIGNMENT](c26400.md)  
Bir ayırma veya işlev çağrısının sonucunu sahip atamayın\<T > dönüş değeri ham işaretçi; sahibi kullanın\<T > bunun yerine. Bkz: [C++ çekirdek yönergeleri I.11](https://github.com/isocpp/CppCoreGuidelines/blob/master/CppCoreGuidelines.md#Ri-raw). 

[C26401 DONT_DELETE_NON_OWNER](c26401.md)  
Sahibi değil raw bir işaretçi silmeyin\<T >. Bkz: [C++ çekirdek yönergeleri I.11](https://github.com/isocpp/CppCoreGuidelines/blob/master/CppCoreGuidelines.md#Ri-raw). 

[C26402 DONT_HEAP_ALLOCATE_MOVABLE_RESULT](C26402.md)  Return a scoped object instead of a heap-allocated if it has a move constructor. Bkz: [C++ çekirdek yönergeleri R.3](https://github.com/isocpp/CppCoreGuidelines/blob/master/CppCoreGuidelines.md#Rr-ptr). 
 
[C26408 NO_MALLOC_FREE](C26408.md)  
  Malloc() ve free() kaçınmak için nothrow sürümüyle yeni delete tercih eder. Bkz: [C++ çekirdek yönergeleri R.10](https://github.com/isocpp/CppCoreGuidelines/blob/master/CppCoreGuidelines.md#Rr-mallocfree).  
  
[C26409 NO_NEW_DELETE](C26409.md)  
  Yeni arama önlemek ve açıkça silebilir, std::make_unique\<T > bunun yerine. Bkz: [C++ çekirdek yönergeleri R.11](https://github.com/isocpp/CppCoreGuidelines/blob/master/CppCoreGuidelines.md#Rr-newdelete).  

[C26429 USE_NOTNULL](C26429.md)  
  Sembol '% simgesi %' nullness için hiç test etmediniz, Nothing işaretlenebilir. Bkz: [C++ çekirdek yönergeleri F.23](https://github.com/isocpp/CppCoreGuidelines/blob/master/CppCoreGuidelines.md#f23-use-a-not_nullt-to-indicate-that-null-is-not-a-valid-value).  
  
[C26430 TEST_ON_ALL_PATHS](C26430.md)  
  '% Simgesi %' simgesi nullness tüm yazmalar için test edilmemiştir. Bkz: [C++ çekirdek yönergeleri F.23](https://github.com/isocpp/CppCoreGuidelines/blob/master/CppCoreGuidelines.md#f23-use-a-not_nullt-to-indicate-that-null-is-not-a-valid-value).  
  
[C26431 DONT_TEST_NOTNULL](C26431.md)  
  '% Expr %' ifadesinin zaten gsl::not_null türüdür. Nullness için sınamayın. Bkz: [C++ çekirdek yönergeleri F.23](https://github.com/isocpp/CppCoreGuidelines/blob/master/CppCoreGuidelines.md#f23-use-a-not_nullt-to-indicate-that-null-is-not-a-valid-value).  
  
[C26481 NO_POINTER_ARITHMETIC](C26481.md)  
  İşaretçi aritmetiği kullanmayın. Aralık kullanın. Bkz: [C++ çekirdek yönergeleri Bounds.1](https://github.com/isocpp/CppCoreGuidelines/blob/master/CppCoreGuidelines.md#SS-bounds).  

[C26485 NO_ARRAY_TO_POINTER_DECAY](C26485.md)   
  '% Expr %' ifadesi: işaretçi decay için dizisi yok. Bkz: [C++ çekirdek yönergeleri Bounds.3](https://github.com/isocpp/CppCoreGuidelines/blob/master/CppCoreGuidelines.md#SS-bounds).  

## <a name="uniquepointer-group"></a>UNIQUE_POINTER grubu
  
[C26410 NO_REF_TO_CONST_UNIQUE_PTR](C26410.md)  
  '% Parametre %' parametresi başvurusudur `const` benzersiz işaretçi const T * veya const T kullanın ve bunun yerine. Bkz: [C++ çekirdek yönergeleri R.32](https://github.com/isocpp/CppCoreGuidelines/blob/master/CppCoreGuidelines.md#Rr-uniqueptrparam).  
     
[C26411 NO_REF_TO_UNIQUE_PTR](C26411.md)  
  '% Parametre %' benzersiz işaretçi başvuru parametredir ve hiçbir zaman yeniden atandığında veya sıfırlama, T * veya T kullanın ve bunun yerine. Bkz: [C++ çekirdek yönergeleri R.33](https://github.com/isocpp/CppCoreGuidelines/blob/master/CppCoreGuidelines.md#Rr-reseat).  
     
[C26414 RESET_LOCAL_SMART_PTR](C26414.md)  
  Taşıma, kopyalayın, yeniden atama veya yerel akıllı işaretçi '% simgesi %' Sıfırla. Bkz: [C++ çekirdek yönergeleri R.5](https://github.com/isocpp/CppCoreGuidelines/blob/master/CppCoreGuidelines.md#Rr-scoped).  
    
[C26415 SMART_PTR_NOT_NEEDED](C26415.md)  
  Akıllı işaretçi parametresi '% simgesi %' yalnızca içerdiği erişim işaretçisine kullanılır. T * veya T kullanın ve bunun yerine. Bkz: [C++ çekirdek yönergeleri R.30](https://github.com/isocpp/CppCoreGuidelines/blob/master/CppCoreGuidelines.md#Rr-smartptrparam).  

## <a name="sharedpointer-group"></a>SHARED_POINTER Group

[C26414 RESET_LOCAL_SMART_PTR](C26414.md)  
  Taşıma, kopyalayın, yeniden atama veya yerel akıllı işaretçi '% simgesi %' Sıfırla. Bkz: [C++ çekirdek yönergeleri R.5](https://github.com/isocpp/CppCoreGuidelines/blob/master/CppCoreGuidelines.md#Rr-scoped).  
    
[C26415 SMART_PTR_NOT_NEEDED](C26415.md)  
  Akıllı işaretçi parametresi '% simgesi %' yalnızca içerdiği erişim işaretçisine kullanılır. T * veya T kullanın ve bunun yerine. Bkz: [C++ çekirdek yönergeleri R.30](https://github.com/isocpp/CppCoreGuidelines/blob/master/CppCoreGuidelines.md#Rr-smartptrparam).  
    
[C26416 NO_RVALUE_REF_SHARED_PTR](C26416.md)  
  Paylaşılan işaretçi parametresi '% simgesi %' rvalue başvuru geçirilir. Değere göre bunun yerine geçer. Bkz: [C++ çekirdek yönergeleri R.34](https://github.com/isocpp/CppCoreGuidelines/blob/master/CppCoreGuidelines.md#Rr-sharedptrparam-owner).  
  
[C26417 NO_LVALUE_REF_SHARED_PTR](C26417.md)  
  Paylaşılan işaretçi parametresi '% simgesi %' başvuruya göre geçirilen ve sıfırlama veya yeniden atandı. T * veya T kullanın ve bunun yerine. Bkz: [C++ çekirdek yönergeleri R.35](https://github.com/isocpp/CppCoreGuidelines/blob/master/CppCoreGuidelines.md#Rr-sharedptrparam).  
  
[C26418 NO_VALUE_OR_CONST_REF_SHARED_PTR](C26418.md)  
  Paylaşılan işaretçi parametresi '% simgesi %' kopyalanamaz veya taşınamaz değil. T * veya T kullanın ve bunun yerine. Bkz: [C++ çekirdek yönergeleri R.36](https://github.com/isocpp/CppCoreGuidelines/blob/master/CppCoreGuidelines.md#Rr-sharedptrparam-const).  

## <a name="declaration-group"></a>BİLDİRİM grubu
    
[C26426 NO_GLOBAL_INIT_CALLS](C26426.md)  
  Genel Başlatıcı constexpr olmayan işlevi '% simgesi %' çağırır. Bkz: [C++ çekirdek yönergeleri I.22](https://github.com/isocpp/CppCoreGuidelines/blob/master/CppCoreGuidelines.md#i22-avoid-complex-initialization-of-global-objects).  
  
[C26427 NO_GLOBAL_INIT_EXTERNS](C26427.md)  
  Genel Başlatıcı extern nesnesi '% simgesi %' erişir. Bkz: [C++ çekirdek yönergeleri I.22](https://github.com/isocpp/CppCoreGuidelines/blob/master/CppCoreGuidelines.md#i22-avoid-complex-initialization-of-global-objects).  
  
[C26444 NO_UNNAMED_RAII_OBJECTS](c26444.md) özel oluşturma ve yok etme nesneleriyle adlandırılmamış kaçının. [es.84: (kurtarmayın) adı olmayan yerel bir değişken bildirme](https://github.com/isocpp/CppCoreGuidelines/blob/master/CppCoreGuidelines.md).

## <a name="class-group"></a>SINIF grubu
    
[C26432 DEFINE_OR_DELETE_SPECIAL_OPS](C26432.md)  
  Tanımlayın veya herhangi bir varsayılan işlemi '% simgesi %' türündeki silerseniz tanımlayın veya tüm silin. Bkz: [C++ çekirdek yönergeleri C.21](https://github.com/isocpp/CppCoreGuidelines/blob/master/CppCoreGuidelines.md#c21-if-you-define-or-delete-any-default-operation-define-or-delete-them-all).  


[C26433 OVERRIDE_EXPLICITLY](c26433.md) işlevi '% simgesi %' 'override' ile işaretlenmiş. Bkz: [ C.128: sanal işlevleri tam olarak bir sanal, geçersiz kılma veya son belirtmelidir](https://github.com/isocpp/CppCoreGuidelines/blob/master/CppCoreGuidelines.md#c128-virtual-functions-should-specify-exactly-one-of-virtual-override-or-final). 

  
[C26434 DONT_HIDE_METHODS](C26434.md)  
  Sanal olmayan işlevi '% symbol_2% ' işlevi '% symbol_1% ' gizler. Bkz: [C++ çekirdek yönergeleri C.128](https://github.com/isocpp/CppCoreGuidelines/blob/master/CppCoreGuidelines.md#c128-virtual-functions-should-specify-exactly-one-of-virtual-override-or-final).  
  

[C26435 SINGLE_VIRTUAL_SPECIFICATION](c26435.md) işlevi '% simgesi %' 'sanal', 'override' veya 'final' tam olarak birine belirtmeniz gerekir. Bkz: [ C.128: sanal işlevleri tam olarak bir sanal, geçersiz kılma veya son belirtmelidir](https://github.com/isocpp/CppCoreGuidelines/blob/master/CppCoreGuidelines.md). 


[C26436 NEED_VIRTUAL_DTOR](C26436.md)  
  Bir sanal işleve sahip ' % simgesi %' türü ortak ya da sanal ya da korumalı olmayan yıkıcı gerekir. Bkz: [C++ çekirdek yönergeleri C.35](https://github.com/isocpp/CppCoreGuidelines/blob/master/CppCoreGuidelines.md#c35-a-base-class-destructor-should-be-either-public-and-virtual-or-protected-and-nonvirtual).  


[C26443 NO_EXPLICIT_DTOR_OVERRIDE](c26443.md) geçersiz kılınıyor yıkıcı açık 'override' veya 'sanal' tanımlayıcıları değil kullanmalıdır. Bkz: [C.128: sanal işlevleri tam olarak bir sanal, geçersiz kılma veya son belirtmelidir](https://github.com/isocpp/CppCoreGuidelines/blob/master/CppCoreGuidelines.md).


## <a name="type-group"></a>Tür grubu
    
[C26437 DONT_SLICE](C26437.md)  
  Dilim değil. Bkz: [C++ çekirdek yönergeleri ES.63](https://github.com/isocpp/CppCoreGuidelines/blob/master/CppCoreGuidelines.md#es63-dont-slice).  

## <a name="style-group"></a>Stil grubu  
[C26438 NO_GOTO](C26438.md)  
  Kaçının `goto`. Bkz: [C++ çekirdek yönergeleri ES.76](https://github.com/isocpp/CppCoreGuidelines/blob/master/CppCoreGuidelines.md#es76-avoid-goto).  
  
## <a name="function-group"></a>İŞLEV grubu
    
[C26439 SPECIAL_NOEXCEPT](C26439.md)  
  Bu tür bir işlev atabilir değil. Bildirirken `noexcept`. Bkz: [C++ çekirdek yönergeleri F.6](https://github.com/isocpp/CppCoreGuidelines/blob/master/CppCoreGuidelines.md#f6-if-your-function-may-not-throw-declare-it-noexcept).  
  
[C26440 DECLARE_NOEXCEPT](C26440.md)  
  İşlevi '% simgesi %' bildirilebilir `noexcept`. Bkz: [C++ çekirdek yönergeleri F.6](https://github.com/isocpp/CppCoreGuidelines/blob/master/CppCoreGuidelines.md#f6-if-your-function-may-not-throw-declare-it-noexcept).  

## <a name="concurrency-group"></a>EŞZAMANLILIK grubu
    
[C26441 NO_UNNAMED_GUARDS](C26441.md)  
 Koruma nesneleri adlandırılmalıdır. Bkz: [C++ çekirdek yönergeleri cp.44](https://github.com/isocpp/CppCoreGuidelines/blob/master/CppCoreGuidelines.md#cp44-remember-to-name-your-lock_guards-and-unique_locks).  

## <a name="const-group"></a>CONST grubu
    
C26460 USE_CONST_REFERENCE_ARGUMENTS  
  '% İşlevi %' işlevi için başvuru bağımsız değişkeni '% değişken %' olarak işaretlenmiş `const`. Bkz: [C++ çekirdek yönergeleri con.3](https://github.com/isocpp/CppCoreGuidelines/blob/master/CppCoreGuidelines.md#Rconst-ref).  
  
C26461 USE_CONST_POINTER_ARGUMENTS: '% işlevi %' işlevi için işaretçi değişkeni '% değişken %' için bir işaretçi olarak işaretlenebilir `const`. Bkz: [C++ çekirdek yönergeleri con.3](https://github.com/isocpp/CppCoreGuidelines/blob/master/CppCoreGuidelines.md#Rconst-ref).  
  
C26462 USE_CONST_POINTER_FOR_VARIABLE  
  '% Değişken % tarafından' işaret değeri yalnızca bir kez atanır, bir işaretçi olarak işaretle `const`. Bkz: [C++ çekirdek yönergeleri con.4](https://github.com/isocpp/CppCoreGuidelines/blob/master/CppCoreGuidelines.md#con4-use-const-to-define-objects-with-values-that-do-not-change-after-construction).  
  
C26463 USE_CONST_FOR_ELEMENTS  
  '% Dizi %' dizinin öğeleri yalnızca bir kez işareti öğeleri atanan `const`. Bkz: [C++ çekirdek yönergeleri con.4](https://github.com/isocpp/CppCoreGuidelines/blob/master/CppCoreGuidelines.md#con4-use-const-to-define-objects-with-values-that-do-not-change-after-construction).  
  
C26464 USE_CONST_POINTER_FOR_ELEMENTS  
  '% Dizi %' dizisi öğeleri tarafından işaret değerleri yalnızca bir kez işareti öğeleri işaretçi olarak atanan `const`. Bkz: [C++ çekirdek yönergeleri con.4](https://github.com/isocpp/CppCoreGuidelines/blob/master/CppCoreGuidelines.md#con4-use-const-to-define-objects-with-values-that-do-not-change-after-construction).  

C26496 USE_CONST_FOR_VARIABLE  
  '% Değişken %' değişken yalnızca bir kez atanır, olarak işaretlemek `const`. Bkz: [C++ çekirdek yönergeleri con.4](https://github.com/isocpp/CppCoreGuidelines/blob/master/CppCoreGuidelines.md#con4-use-const-to-define-objects-with-values-that-do-not-change-after-construction).  
  
C26497 USE_CONSTEXPR_FOR_FUNCTION  
  Bu işlev işlevi % işaretlenebilir `constexpr` derleme zamanı değerlendirme isterseniz. Bkz: [C++ çekirdek yönergeleri F.4](https://github.com/isocpp/CppCoreGuidelines/blob/master/CppCoreGuidelines.md#Rf-constexpr).  
  
C26498 USE_CONSTEXPR_FOR_FUNCTIONCALL  
  Bu işlev çağrısı işlevi % kullanabilirsiniz `constexpr` derleme zamanı değerlendirme isterseniz. Bkz: [C++ çekirdek yönergeleri con.5](https://github.com/isocpp/CppCoreGuidelines/blob/master/CppCoreGuidelines.md#Rconst-constexpr).  

## <a name="type-group"></a>Tür grubu
C26465 NO_CONST_CAST_UNNECESSARY  
  Kullanmayan `const_cast` hemen yayınlanamıyor `const`. `const_cast`gerekli değildir; Bu dönüştürme kaldırılmıyor constness veya volatilite. Bkz: [C++ çekirdek yönergeleri Type.3](https://github.com/isocpp/CppCoreGuidelines/blob/master/CppCoreGuidelines.md#Pro-type-constcast).  
  
C26466 NO_STATIC_DOWNCAST_POLYMORPHIC  
  Kullanmayan `static_cast` downcasts. Çok biçimli türünden bir cast dynamic_cast kullanmanız gerekir. Bkz: [C++ çekirdek yönergeleri Type.2](https://github.com/isocpp/CppCoreGuidelines/blob/master/CppCoreGuidelines.md#Pro-type-downcast).  
  
C26471 NO_REINTERPRET_CAST_FROM_VOID_PTR  
  Kullanmayan `reinterpret_cast`. Bir dönüştürme void * kullanabilirsiniz `static_cast`. Bkz: [C++ çekirdek yönergeleri Type.1](https://github.com/isocpp/CppCoreGuidelines/blob/master/CppCoreGuidelines.md#Pro-type-reinterpretcast).  
  
[C26472 NO_CASTS_FOR_ARITHMETIC_CONVERSION](C26472.md)  
  Kullanmayan bir `static_cast` aritmetik dönüşümler için. Küme parantezi başlatma, gsl::narrow_cast veya gsl::narow kullanın. Bkz: [C++ çekirdek yönergeleri Type.1](https://github.com/isocpp/CppCoreGuidelines/blob/master/CppCoreGuidelines.md#Pro-type-reinterpretcast).  
  
[C26473 NO_IDENTITY_CAST](C26473.md)  
  Kaynak türü ve hedef türü aynı nerede işaretçi türleri arasında dönüştürme yok. Bkz: [C++ çekirdek yönergeleri Type.1](https://github.com/isocpp/CppCoreGuidelines/blob/master/CppCoreGuidelines.md#Pro-type-reinterpretcast).  
  
[C26474 NO_IMPLICIT_CAST](C26474.md)  
  Dönüştürme örtük olabilir işaretçi türleri arasında dönüştürme yok. Bkz: [C++ çekirdek yönergeleri Type.1](https://github.com/isocpp/CppCoreGuidelines/blob/master/CppCoreGuidelines.md#Pro-type-reinterpretcast).  
  
[C26475 NO_FUNCTION_STYLE_CASTS](C26475.md)  
  İşlev stili C atamaları kullanmayın. Bkz: [C++ çekirdek yönergeleri ES.49](https://github.com/isocpp/CppCoreGuidelines/blob/master/CppCoreGuidelines.md#es49-if-you-must-use-a-cast-use-a-named-cast).  
     
C26490 NO_REINTERPRET_CAST  
  Kullanmayan `reinterpret_cast`. Bkz: [C++ çekirdek yönergeleri Type.1](https://github.com/isocpp/CppCoreGuidelines/blob/master/CppCoreGuidelines.md#SS-type).  
  
C26491 NO_STATIC_DOWNCAST  
  Kullanmayan `static_cast` downcasts. Bkz: [C++ çekirdek yönergeleri Type.2](https://github.com/isocpp/CppCoreGuidelines/blob/master/CppCoreGuidelines.md#SS-type).  
  
C26492 NO_CONST_CAST  
  Kullanmayan `const_cast` hemen yayınlanamıyor `const`. Bkz: [C++ çekirdek yönergeleri Type.3](https://github.com/isocpp/CppCoreGuidelines/blob/master/CppCoreGuidelines.md#SS-type).  
    
C26493 NO_CSTYLE_CAST  
  C türü atamalar kullanmayın. Bkz: [C++ çekirdek yönergeleri Type.4](https://github.com/isocpp/CppCoreGuidelines/blob/master/CppCoreGuidelines.md#SS-type). 
     
C26494 VAR_USE_BEFORE_INIT  
  Değişkeni '% değişken %' başlatılmadı. Her zaman bir nesneyi başlatın. Bkz: [C++ çekirdek yönergeleri Type.5](https://github.com/isocpp/CppCoreGuidelines/blob/master/CppCoreGuidelines.md#SS-type).  
  
C26495 MEMBER_UNINIT  
  Değişkeni '% değişken %' başlatılmadı. Her zaman bir üye değişkenine başlatır. Bkz: [C++ çekirdek yönergeleri Type.6](https://github.com/isocpp/CppCoreGuidelines/blob/master/CppCoreGuidelines.md#SS-type).  
  
## <a name="bounds-group"></a>SINIR grubu

[C26481 NO_POINTER_ARITHMETIC](C26481.md)   
  İşaretçi aritmetiği kullanmayın. Aralık kullanın. Bkz: [C++ çekirdek yönergeleri Bounds.1](https://github.com/isocpp/CppCoreGuidelines/blob/master/CppCoreGuidelines.md#SS-bounds).  
  
C26482 NO_DYNAMIC_ARRAY_INDEXING  
  Yalnızca dizine sabit ifadeler kullanarak dizileri. Bkz: [C++ çekirdek yönergeleri Bounds.2](https://github.com/isocpp/CppCoreGuidelines/blob/master/CppCoreGuidelines.md#SS-bounds).  
  
C26483 STATIC_INDEX_OUT_OF_RANGE  
  Değer % değeri olan sınırları dışında (0, bağlı %) '% değişken %' değişkeninin. Yalnızca dizine dizi sınırları içinde sabit ifadeler kullanarak dizileri. Bkz: [C++ çekirdek yönergeleri Bounds.2](https://github.com/isocpp/CppCoreGuidelines/blob/master/CppCoreGuidelines.md#SS-bounds).  

[C26485 NO_ARRAY_TO_POINTER_DECAY](C26485.md)   
  '% Expr %' ifadesi: işaretçi decay için dizisi yok. Bkz: [C++ çekirdek yönergeleri Bounds.3](https://github.com/isocpp/CppCoreGuidelines/blob/master/CppCoreGuidelines.md#SS-bounds).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
[C++ çekirdek yönergeleri denetleyicileri kullanma](using-the-cpp-core-guidelines-checkers.md)
