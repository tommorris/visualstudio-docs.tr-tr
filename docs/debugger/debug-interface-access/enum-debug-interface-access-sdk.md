---
title: "Enum (hata ayıklama arabirimi Erişim SDK'sı) | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- enumerated types as symbols
- Enum symbol
ms.assetid: c777e2e6-88be-435b-b632-8d43f42b0b49
caps.latest.revision: "15"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 5b52a97fb549414c0f743c208f37530bc40c8a7c
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2017
---
# <a name="enum-debug-interface-access-sdk"></a>Enum (Arabirim Erişimi SDK'sında Hata Ayıklama)
Numaralandırmalar tanımlanır `SymTagEnum` simgeler. Her numaralandırma değeri ile bir sınıf alt olarak görünür bir `SymTagConstant` etiketi.  
  
## <a name="properties"></a>Özellikler  
 Aşağıdaki tabloda bu simge türü için geçerli ek özellikleri gösterir.  
  
|Özellik|Veri türü|Açıklama|  
|--------------|---------------|-----------------|  
|[Idiasymbol::get_basetype](../../debugger/debug-interface-access/idiasymbol-get-basetype.md)|`DWORD`|Aşağıdakilerden birini [BasicType numaralandırması](../../debugger/debug-interface-access/basictype.md) değerleri.|  
|[Idiasymbol::get_classparent](../../debugger/debug-interface-access/idiasymbol-get-classparent.md)|`IDiaSymbol*`|Bu numaralandırma, varsa üst sınıf.|  
|[Idiasymbol::get_classparentıd](../../debugger/debug-interface-access/idiasymbol-get-classparentid.md)|`DWORD`|Sınıf üst simge kimliği.|  
|[Idiasymbol::get_constructor](../../debugger/debug-interface-access/idiasymbol-get-constructor.md)|`BOOL`|`TRUE`Numaralandırma bir oluşturucu varsa.|  
|[Idiasymbol::get_consttype](../../debugger/debug-interface-access/idiasymbol-get-consttype.md)|`BOOL`|`TRUE`Numaralandırma olarak const olarak işaretlenmişse.|  
|[Idiasymbol::get_hasassignmentoperator](../../debugger/debug-interface-access/idiasymbol-get-hasassignmentoperator.md)|`BOOL`|`TRUE`Numaralandırma atama işleci varsa.|  
|[Idiasymbol::get_hascastoperator](../../debugger/debug-interface-access/idiasymbol-get-hascastoperator.md)|`BOOL`|`TRUE`Numaralandırma atama işleci varsa.|  
|[Idiasymbol::get_hasnestedtypes](../../debugger/debug-interface-access/idiasymbol-get-hasnestedtypes.md)|`BOOL`|`TRUE`Numaralandırma iç içe geçmiş türler varsa.|  
|[Idiasymbol::get_length](../../debugger/debug-interface-access/idiasymbol-get-length.md)|`DWORD`|Bu numaralandırma bayt cinsinden uzunluğu.|  
|[Idiasymbol::get_lexicalparent](../../debugger/debug-interface-access/idiasymbol-get-lexicalparent.md)|`IDiaSymbol*`|Kapsayan, simge [derlenecek](../../debugger/debug-interface-access/compiland.md).|  
|[Idiasymbol::get_lexicalparentıd](../../debugger/debug-interface-access/idiasymbol-get-lexicalparentid.md)|`DWORD`|Sözcük üst simge kimliği.|  
|[Idiasymbol::get_name](../../debugger/debug-interface-access/idiasymbol-get-name.md)|`BSTR`|Numaralandırılmış türünün adı.|  
|[Idiasymbol::get_nested](../../debugger/debug-interface-access/idiasymbol-get-nested.md)|`BOOL`|`TRUE`Numaralandırma iç içe yerleştirilmiş ise.|  
|[Idiasymbol::get_overloadedoperator](../../debugger/debug-interface-access/idiasymbol-get-overloadedoperator.md)|`BOOL`|`TRUE`Numaralandırma herhangi aşırı yüklenmiş işleçler varsa.|  
|[Idiasymbol::get_packed](../../debugger/debug-interface-access/idiasymbol-get-packed.md)|`BOOL`|`TRUE`Numaralandırma paketlenmiş durumunda.|  
|[Idiasymbol::get_scoped](../../debugger/debug-interface-access/idiasymbol-get-scoped.md)|`BOOL`|`TRUE`Numaralandırma Global olmayan bir sözcük kapsamda görünüyorsa.|  
|[Idiasymbol::get_symındexıd](../../debugger/debug-interface-access/idiasymbol-get-symindexid.md)|`DWORD`|Dizin kimliği simgesi.|  
|[Idiasymbol::get_symtag](../../debugger/debug-interface-access/idiasymbol-get-symtag.md)|`DWORD`|Döndürür `SymTagEnum` (birini [SymTagEnum numaralandırması](../../debugger/debug-interface-access/symtagenum.md) değerleri).|  
|[Idiasymbol::get_type](../../debugger/debug-interface-access/idiasymbol-get-type.md)|`IDiaSymbol*`|Temel alınan tür simgesi.|  
|[Idiasymbol::get_typeıd](../../debugger/debug-interface-access/idiasymbol-get-typeid.md)|`DWORD`|Tür simgesi kimliği.|  
|[Idiasymbol::get_unalignedtype](../../debugger/debug-interface-access/idiasymbol-get-unalignedtype.md)|`BOOL`|`TRUE`Numaralandırma hizalanmamış ise.|  
|[Idiasymbol::get_volatiletype](../../debugger/debug-interface-access/idiasymbol-get-volatiletype.md)|`BOOL`|`TRUE`Numaralandırma geçici işaretlenmişse.|  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Simge türlerinin sınıf hiyerarşisi](../../debugger/debug-interface-access/class-hierarchy-of-symbol-types.md)