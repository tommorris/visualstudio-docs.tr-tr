---
title: Arkadaş (hata ayıklama arabirimi Erişim SDK'sı) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-debug
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- friend functions [DIA SDK]
- friend classes [DIA SDK]
- Friend symbol
ms.assetid: 5147a170-41ce-4727-8ace-c318e8d11647
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: c496b2b653bc1243a122f2025aa9d08b47fef7b1
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/16/2018
---
# <a name="friend-debug-interface-access-sdk"></a>Arkadaş (Arabirim Erişimi SDK'sında Hata Ayıklama)
Arkadaş sınıfları ve arkadaş işlevleri tanımlanır `SymTagFriend` simgeler. Kullanıcı tanımlı türler (atama) üst öğenin alt öğeleri olan ve sahip bir [Idiasymbol::get_classparent](../../debugger/debug-interface-access/idiasymbol-get-classparent.md) özelliği.  
  
## <a name="properties"></a>Özellikler  
 Aşağıdaki tabloda bu simge türü için geçerli ek özellikleri gösterir.  
  
|Özellik|Veri türü|Açıklama|  
|--------------|---------------|-----------------|  
|[IDiaSymbol::get_classParent](../../debugger/debug-interface-access/idiasymbol-get-classparent.md)|`IDiaSymbol*`|UDT üst simgesi.|  
|[IDiaSymbol::get_classParentId](../../debugger/debug-interface-access/idiasymbol-get-classparentid.md)|`DWORD`|Sınıf üst simge kimliği.|  
|[IDiaSymbol::get_name](../../debugger/debug-interface-access/idiasymbol-get-name.md)|`BSTR`|Sınıf veya işlev adı.|  
|[IDiaSymbol::get_symIndexId](../../debugger/debug-interface-access/idiasymbol-get-symindexid.md)|`DWORD`|Dizin kimliği simgesi.|  
|[IDiaSymbol::get_symTag](../../debugger/debug-interface-access/idiasymbol-get-symtag.md)|`DWORD`|Döndürür `SymTagFriend` (birini [SymTagEnum numaralandırması](../../debugger/debug-interface-access/symtagenum.md) değerleri).|  
|[IDiaSymbol::get_type](../../debugger/debug-interface-access/idiasymbol-get-type.md)|`IDiaSymbol*`|Sınıf veya işlevi için simge.|  
|[IDiaSymbol::get_typeId](../../debugger/debug-interface-access/idiasymbol-get-typeid.md)|`DWORD`|Tür simgesi kimliği.|  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Simge Türlerinin Sınıf Hiyerarşisi](../../debugger/debug-interface-access/class-hierarchy-of-symbol-types.md)