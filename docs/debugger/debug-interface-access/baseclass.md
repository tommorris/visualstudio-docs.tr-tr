---
title: BaseClass | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- user-defined types, base classes
- BaseClass symbol
- base classes, user-defined types
ms.assetid: 9375ca35-cb91-45f5-8903-7344ee4528e8
caps.latest.revision: "16"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: a19dee7c2b31df52a379f6ef2044a862baed7972
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2017
---
# <a name="baseclass"></a>BaseClass
Her bir kullanıcı tanımlı tür (UDT) simgesi için temel sınıfı bir alt tarafından tanımlanan bir `SymTagBaseClass` etiketi. [Idiasymbol::get_type](../../debugger/debug-interface-access/idiasymbol-get-type.md) özelliği için temel alınan UDT simgesi içerir ve temel UDT tüm özelliklerini kullanılabilir bu BaseClass simgesi bir parçası olarak.  
  
## <a name="properties"></a>Özellikler  
 Aşağıdaki tabloda bu simge türü için geçerli ek özellikleri gösterir.  
  
|Özellik|Veri türü|Açıklama|  
|--------------|---------------|-----------------|  
|[Idiasymbol::get_access](../../debugger/debug-interface-access/idiasymbol-get-access.md)|`DWORD`|Bu temel sınıfına uygulanan erişim değiştiricisi. Aşağıdakilerden birini [CV_access_e numaralandırması](../../debugger/debug-interface-access/cv-access-e.md) değerleri.|  
|[Idiasymbol::get_classparent](../../debugger/debug-interface-access/idiasymbol-get-classparent.md)|`IDiaSymbol*`|Simge kapsayan bir sınıfın (varsa).|  
|[Idiasymbol::get_classparentıd](../../debugger/debug-interface-access/idiasymbol-get-classparentid.md)|`DWORD`|Sınıf üst simge kimliği.|  
|[Idiasymbol::get_constructor](../../debugger/debug-interface-access/idiasymbol-get-constructor.md)|`BOOL`|`TRUE`taban sınıf oluşturucu varsa.|  
|[Idiasymbol::get_consttype](../../debugger/debug-interface-access/idiasymbol-get-consttype.md)|`BOOL`|`TRUE`temel sınıf olarak const olarak işaretlenmişse.|  
|[Idiasymbol::get_hasassignmentoperator](../../debugger/debug-interface-access/idiasymbol-get-hasassignmentoperator.md)|`BOOL`|`TRUE`taban sınıfı bir atama işleci varsa.|  
|[Idiasymbol::get_hascastoperator](../../debugger/debug-interface-access/idiasymbol-get-hascastoperator.md)|`BOOL`|`TRUE`taban sınıfı atama işleci varsa.|  
|[Idiasymbol::get_hasnestedtypes](../../debugger/debug-interface-access/idiasymbol-get-hasnestedtypes.md)|`BOOL`|`TRUE`taban sınıfı iç içe geçmiş türler varsa.|  
|[Idiasymbol::get_indirectvirtualbaseclass](../../debugger/debug-interface-access/idiasymbol-get-indirectvirtualbaseclass.md)|`BOOL`|`TRUE`taban sınıf dolaylı ise.|  
|[Idiasymbol::get_length](../../debugger/debug-interface-access/idiasymbol-get-length.md)|`DWORD`|Taban sınıfı bayt cinsinden uzunluğu.|  
|[Idiasymbol::get_lexicalparent](../../debugger/debug-interface-access/idiasymbol-get-lexicalparent.md)|`IDiaSymbol*`|Kapsayan derlenecek dosya simgesi.|  
|[Idiasymbol::get_lexicalparentıd](../../debugger/debug-interface-access/idiasymbol-get-lexicalparentid.md)|`DWORD`|Sözcük üst simge kimliği.|  
|[Idiasymbol::get_name](../../debugger/debug-interface-access/idiasymbol-get-name.md)|`BSTR`|Temel sınıfın adı.|  
|[Idiasymbol::get_nested](../../debugger/debug-interface-access/idiasymbol-get-nested.md)|`BOOL`|`TRUE`taban sınıfı iç içe yerleştirilmiş ise.|  
|[Idiasymbol::get_offset](../../debugger/debug-interface-access/idiasymbol-get-offset.md)|`LONG`|Yapısı içinde temel sınıfı temsil eder alt nesne, uzaklık.|  
|[Idiasymbol::get_overloadedoperator](../../debugger/debug-interface-access/idiasymbol-get-overloadedoperator.md)|`BOOL`|`TRUE`temel sınıfın tüm aşırı yüklenmiş işleçler varsa.|  
|[Idiasymbol::get_packed](../../debugger/debug-interface-access/idiasymbol-get-packed.md)|`BOOL`|`TRUE`taban sınıfı paketlenmiş varsa.|  
|[Idiasymbol::get_scoped](../../debugger/debug-interface-access/idiasymbol-get-scoped.md)|`BOOL`|`TRUE`taban sınıfı Global olmayan bir kapsam içinde görünüyorsa.|  
|[Idiasymbol::get_symındexıd](../../debugger/debug-interface-access/idiasymbol-get-symindexid.md)|`DWORD`|Dizin kimliği simgesi.|  
|[Idiasymbol::get_symtag](../../debugger/debug-interface-access/idiasymbol-get-symtag.md)|`DWORD`|Döndürür `SymTagBaseClass` (birini [SymTagEnum numaralandırması](../../debugger/debug-interface-access/symtagenum.md) değerleri).|  
|[Idiasymbol::get_type](../../debugger/debug-interface-access/idiasymbol-get-type.md)|`IDiaSymbol*`|Taban sınıfı için simge [UDT](../../debugger/debug-interface-access/udt.md).|  
|[Idiasymbol::get_typeıd](../../debugger/debug-interface-access/idiasymbol-get-typeid.md)|`DWORD`|Tür simgesi kimliği.|  
|[Idiasymbol::get_udtkind](../../debugger/debug-interface-access/idiasymbol-get-udtkind.md)|`DWORD`|Arasında bir değer [UdtKind numaralandırması](../../debugger/debug-interface-access/udtkind.md).|  
|[Idiasymbol::get_unalignedtype](../../debugger/debug-interface-access/idiasymbol-get-unalignedtype.md)|`BOOL`|`TRUE`taban sınıf hizalanmamış ise.|  
|[Idiasymbol::get_virtualbaseclass](../../debugger/debug-interface-access/idiasymbol-get-virtualbaseclass.md)|`BOOL`|`TRUE`taban sınıf sanal ise.|  
|[Idiasymbol::get_virtualbasedispındex](../../debugger/debug-interface-access/idiasymbol-get-virtualbasedispindex.md)|`DWORD`|Sanal Taban öteleme tabloya dizin.|  
|[Idiasymbol::get_virtualbasepointeroffset](../../debugger/debug-interface-access/idiasymbol-get-virtualbasepointeroffset.md)|`LONG`|Sanal Taban işaretçisinin uzaklığı.|  
|[Idiasymbol::get_virtualbasetabletype](../../debugger/debug-interface-access/idiasymbol-get-virtualbasetabletype.md)|`IDiaSymbol*`|Sanal temel tablo işaretçi türü.|  
|[Idiasymbol::get_virtualtableshape](../../debugger/debug-interface-access/idiasymbol-get-virtualtableshape.md)|`IDiaSymbol*`|Taban sınıfı için sanal tablo türünü tanımlayan simge.|  
|[Idiasymbol::get_virtualtableshapeıd](../../debugger/debug-interface-access/idiasymbol-get-virtualtableshapeid.md)|`DWORD`|Sanal tablo şekli simgenin kimliği.|  
|[Idiasymbol::get_volatiletype](../../debugger/debug-interface-access/idiasymbol-get-volatiletype.md)|`BOOL`|`TRUE`taban sınıfı geçici işaretlenmişse.|  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Simge türlerinin sınıf hiyerarşisi](../../debugger/debug-interface-access/class-hierarchy-of-symbol-types.md)   
 [UDT](../../debugger/debug-interface-access/udt.md)