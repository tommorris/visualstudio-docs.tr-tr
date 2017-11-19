---
title: "Yapıları ve sınıfları yorumlama | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-code-analysis
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- _Field_size_bytes_part_
- _Field_size_bytes_full_opt_
- _Field_size_bytes_
- _Field_size_opt_
- _Field_size_part_
- _Field_size_bytes_part_opt_
- _Field_range_
- _Field_size_part_opt_
- _Field_size_
- _Field_size_bytes_opt_
- _Struct_size_bytes_
- _Field_size_bytes_full_
- _Field_size_full_
- _Field_size_full_opt_
ms.assetid: b8278a4a-c86e-4845-aa2a-70da21a1dd52
caps.latest.revision: "9"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 651108f2c917fb81857e3466384a9bfebada4a4b
ms.sourcegitcommit: fb751e41929f031d1a9247bc7c8727312539ad35
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/15/2017
---
# <a name="annotating-structs-and-classes"></a>Yapıları ve Sınıfları Yorumlama
Yapı ve sınıf üyeleri invariants gibi davranan ek açıklamaları kullanılarak açıklayabilirsiniz — herhangi bir işlev çağrısı veya bir parametre veya bir sonuç değeri kapsayan yapısı içerir işlevi giriş/çıkış en doğru olması için varsayılan.  
  
## <a name="struct-and-class-annotations"></a>Yapı ve sınıf ek açıklamaları  
  
-   `_Field_range_(low, high)`  
  
     Gelen (dahil) aralığında alandır `low` için `high`.  Eşdeğer `_Satisfies_(_Curr_ >= low && _Curr_ <= high)` uygun öncesi veya post koşullarını kullanarak açıklamalı nesnesine uygulanır.  
  
-   `_Field_size_(size)`, `_Field_size_opt_(size)`, `_Field_size_bytes_(size)`, `_Field_size_bytes_opt_(size)`  
  
     Öğeleri (veya bayt) tarafından belirtilen yazılabilir boyutuna sahip bir alan `size`.  
  
-   `_Field_size_part_(size, count)`, `_Field_size_part_opt_(size, count)`,         `_Field_size_bytes_part_(size, count)`, `_Field_size_bytes_part_opt_(size, count)`  
  
     Öğeleri (veya bayt) tarafından belirtilen yazılabilir boyutuna sahip bir alan `size`ve `count` okunabilir bu öğelerin (bayt).  
  
-   `_Field_size_full_(size)`, `_Field_size_full_opt_(size)`, `_Field_size_bytes_full_(size)`, `_Field_size_bytes_full_opt_(size)`  
  
     Öğeleri (veya bayt) tarafından belirtilen okunabilir ve yazılabilir boyutuna sahip bir alan `size`.  
  
-   `_Struct_size_bytes_(size)`  
  
     Öğeleri (veya bayt) tarafından belirtilen okunabilir ve yazılabilir boyutuna sahip bir alan `size`.  
  
     Yapı ya da sınıf bildirimi geçerlidir.  Bu tür geçerli bir nesne tarafından belirtilen bayt sayısı ile bildirilen türü büyük olabileceğini gösterir `size`.  Örneğin:  
  
    ```cpp  
  
    typedef _Struct_size_bytes_(nSize)  
    struct MyStruct {  
        size_t nSize;  
        ...  
    };  
  
    ```  
  
     Arabellek boyutunu bayt cinsinden parametresinin `pM` türü `MyStruct *` sonra olacak şekilde gerçekleştirilir:  
  
    ```cpp  
    min(pM->nSize, sizeof(MyStruct))  
    ```  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [C/C++ kod hatalarını azaltmak için SAL ek açıklamalarını kullanma](../code-quality/using-sal-annotations-to-reduce-c-cpp-code-defects.md)   
 [Sal'ı Anlama](../code-quality/understanding-sal.md)   
 [İşlev parametrelerini ve dönüş değerlerini açıklama](../code-quality/annotating-function-parameters-and-return-values.md)   
 [İşlev davranışını yorumlama](../code-quality/annotating-function-behavior.md)   
 [Kilitlenme davranışını yorumlama](../code-quality/annotating-locking-behavior.md)   
 [Açıklamanın ne zaman ve nereye uygulanacağını belirtme](../code-quality/specifying-when-and-where-an-annotation-applies.md)   
 [İç işlevler](../code-quality/intrinsic-functions.md)   
 [En iyi yöntemler ve örnekler](../code-quality/best-practices-and-examples-sal.md)