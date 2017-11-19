---
title: "TypeDef (hata ayıklama arabirimi Erişim SDK'sı) | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords: Typedef symbol [DIA SDK]
ms.assetid: 9ab441b9-cc72-47fa-83e2-87b3c2b891b4
caps.latest.revision: "15"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 4e7f1b3d7bcc7203755383201d24269e579919e5
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2017
---
# <a name="typedef-debug-interface-access-sdk"></a>Typedef (Arabirim Erişimi SDK'sında Hata Ayıklama)
İle simgeleri `SymTagTypedef` etiketleri tanıtmak diğer türleri için adları.  
  
## <a name="properties"></a>Özellikler  
 Aşağıdaki tabloda bu simge türü için geçerli ek özellikleri gösterir.  
  
|Özellik|Veri türü|Açıklama|  
|--------------|---------------|-----------------|  
|[Idiasymbol::get_basetype](../../debugger/debug-interface-access/idiasymbol-get-basetype.md)|`DWORD`|Aşağıdakilerden birini [BasicType numaralandırması](../../debugger/debug-interface-access/basictype.md) değerleri.|  
|[Idiasymbol::get_classparent](../../debugger/debug-interface-access/idiasymbol-get-classparent.md)|`IDiaSymbol*`|Varsa bu typedef sınıfı üst.|  
|[Idiasymbol::get_classparentıd](../../debugger/debug-interface-access/idiasymbol-get-classparentid.md)|`DWORD`|Sınıf üst simge kimliği.|  
|[Idiasymbol::get_constructor](../../debugger/debug-interface-access/idiasymbol-get-constructor.md)|`BOOL`|`TRUE`Bu typedef bir oluşturucu varsa.|  
|[Idiasymbol::get_consttype](../../debugger/debug-interface-access/idiasymbol-get-consttype.md)|`BOOL`|`TRUE`Eğer bu typedef sabit değer olarak işaretlenmiş.|  
|[Idiasymbol::get_hasassignmentoperator](../../debugger/debug-interface-access/idiasymbol-get-hasassignmentoperator.md)|`BOOL`|`TRUE`Bu typedef atama işleci varsa.|  
|[Idiasymbol::get_hascastoperator](../../debugger/debug-interface-access/idiasymbol-get-hascastoperator.md)|`BOOL`|`TRUE`Bu typedef atama işleci varsa.|  
|[Idiasymbol::get_hasnestedtypes](../../debugger/debug-interface-access/idiasymbol-get-hasnestedtypes.md)|`BOOL`|`TRUE`Bu typedef iç içe geçmiş türler varsa.|  
|[Idiasymbol::get_length](../../debugger/debug-interface-access/idiasymbol-get-length.md)|`ULONGLONG`|Bu typedef bayt cinsinden uzunluğu.|  
|[Idiasymbol::get_lexicalparent](../../debugger/debug-interface-access/idiasymbol-get-lexicalparent.md)|`IDiaSymbol*`|Kapsayan derlenecek dosya simgesi.|  
|[Idiasymbol::get_lexicalparentıd](../../debugger/debug-interface-access/idiasymbol-get-lexicalparentid.md)|`DWORD`|Sözcük üst simge kimliği.|  
|[Idiasymbol::get_name](../../debugger/debug-interface-access/idiasymbol-get-name.md)|`BSTR`|Typedef adı.|  
|[Idiasymbol::get_nested](../../debugger/debug-interface-access/idiasymbol-get-nested.md)|`BOOL`|`TRUE`Bu typedef sözcük kapsam içinde iç içe yerleştirilmiş ise.|  
|[Idiasymbol::get_overloadedoperator](../../debugger/debug-interface-access/idiasymbol-get-overloadedoperator.md)|`BOOL`|`TRUE`Bu typedef aşırı yüklenmiş bir işleç varsa.|  
|[Idiasymbol::get_packed](../../debugger/debug-interface-access/idiasymbol-get-packed.md)|`BOOL`|`TRUE`Bu typedef paketlenmiş durumunda.|  
|[Idiasymbol::get_reference](../../debugger/debug-interface-access/idiasymbol-get-reference.md)|`BOOL`|`TRUE`Bu typedef başvuru ise.|  
|[Idiasymbol::get_scoped](../../debugger/debug-interface-access/idiasymbol-get-scoped.md)|`BOOL`|`TRUE`Bu typedef Global olmayan bir sözcük kapsamları dahilinde olması durumunda.|  
|[Idiasymbol::get_symındexıd](../../debugger/debug-interface-access/idiasymbol-get-symindexid.md)|`DWORD`|Dizin kimliği simgesi.|  
|[Idiasymbol::get_symtag](../../debugger/debug-interface-access/idiasymbol-get-symtag.md)|`DWORD`|Döndürür `SymTagTypedef` (birini [SymTagEnum numaralandırması](../../debugger/debug-interface-access/symtagenum.md) değerleri).|  
|[Idiasymbol::get_type](../../debugger/debug-interface-access/idiasymbol-get-type.md)|`IDiaSymbol*`|Temel alınan tür simgesi.|  
|[Idiasymbol::get_typeıd](../../debugger/debug-interface-access/idiasymbol-get-typeid.md)|`DWORD`|Tür simgesi kimliği.|  
|[Idiasymbol::get_udtkind](../../debugger/debug-interface-access/idiasymbol-get-udtkind.md)|`DWORD`|Aşağıdakilerden birini [UdtKind numaralandırması](../../debugger/debug-interface-access/udtkind.md) değerleri.|  
|[Idiasymbol::get_unalignedtype](../../debugger/debug-interface-access/idiasymbol-get-unalignedtype.md)|`BOOL`|`TRUE`Bu typedef hizalı değil|  
|[Idiasymbol::get_virtualtableshape](../../debugger/debug-interface-access/idiasymbol-get-virtualtableshape.md)|`IDiaSymbol*`|Sanal tablo şekli açıklar simge.|  
|[Idiasymbol::get_virtualtableshapeıd](../../debugger/debug-interface-access/idiasymbol-get-virtualtableshapeid.md)|`DWORD`|Sanal tablo şekli simgenin kimliği.|  
|[Idiasymbol::get_volatiletype](../../debugger/debug-interface-access/idiasymbol-get-volatiletype.md)|`BOOL`|`TRUE`Eğer bu typedef geçici işaretlenmiş.|  
  
## <a name="remarks"></a>Açıklamalar  
 Bir typedef sınıfı, işaretçi veya kullanıcı tanımlı tür (UDT) temsil ettiği bir typedef simgesi simgelerin diğer bu türlerinden birini aynı özellikleri paylaşır.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Simge türlerinin sınıf hiyerarşisi](../../debugger/debug-interface-access/class-hierarchy-of-symbol-types.md)