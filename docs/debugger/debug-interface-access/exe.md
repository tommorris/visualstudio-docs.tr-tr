---
title: Exe | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- .dll files
- Exe symbol
- .exe files
- executable files, Exe symbol
ms.assetid: a781d2cf-55fe-4373-9cf1-b732864244e0
caps.latest.revision: "17"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: ab02eacffe01c267a2f3d4ff463b729591bb8b19
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2017
---
# <a name="exe"></a>Exe
.Exe veya .dll dosyasının genel kapsamı temsil eden Exe yalnızca ya da bir sözcük simge veya üst sınıf aynıdır. Yalnızca bir simgeyle yoktur `SymTagExe` dosya başına etiketi. [Idiasession::get_globalscope](../../debugger/debug-interface-access/idiasession-get-globalscope.md) yöntemi simgenin döndürür.  
  
## <a name="properties"></a>Özellikler  
 Aşağıdaki tabloda bu simge türü için geçerli olan özellikleri gösterir.  
  
|Özellik|Veri türü|Açıklama|  
|--------------|---------------|-----------------|  
|[Idiasymbol::get_age](../../debugger/debug-interface-access/idiasymbol-get-age.md)|`DWORD`|Bu yürütülebilir dosya yaşı.|  
|[Idiasymbol::get_guid](../../debugger/debug-interface-access/idiasymbol-get-guid.md)|`GUID`|`GUID`Bu, yürütülebilir.|  
|[IDiaSymbol::get_isCTypes](../../debugger/debug-interface-access/idiasymbol-get-isctypes.md)|`BOOL`|`TRUE`Sembol dosyası ile ilişkili ise bu yürütülebilir dosya C türleri (yalnızca DIA SDK v8.0 veya sonrası) içerir.|  
|[Idiasymbol::get_isstripped](../../debugger/debug-interface-access/idiasymbol-get-isstripped.md)|`BOOL`|`TRUE`özel sembolleri bu çalıştırılabilir (yalnızca DIA SDK v8.0 veya sonrası) ilişkili simge dosyasından atılmış durumunda.|  
|[Idiasymbol::get_machinetype](../../debugger/debug-interface-access/idiasymbol-get-machinetype.md)|`DWORD`|Değer hedef CPU belirten (birini [CV_CPU_TYPE_e numaralandırması](../../debugger/debug-interface-access/cv-cpu-type-e.md) değerleri).|  
|[Idiasymbol::get_name](../../debugger/debug-interface-access/idiasymbol-get-name.md)|`BSTR`|.Exe dosya adı.|  
|[Idiasymbol::get_signature](../../debugger/debug-interface-access/idiasymbol-get-signature.md)|`DWORD`|İmza yürütülebilir.|  
|[Idiasymbol::get_symbolsfilename](../../debugger/debug-interface-access/idiasymbol-get-symbolsfilename.md)|`BSTR`|.Exe dosyasının .pdb veya .dbg dosyasının tam yolu.|  
|[Idiasymbol::get_symındexıd](../../debugger/debug-interface-access/idiasymbol-get-symindexid.md)|`DWORD`|Dizin kimliği simgesi.|  
|[Idiasymbol::get_symtag](../../debugger/debug-interface-access/idiasymbol-get-symtag.md)|`DWORD`|Döndürür `SymTagExe` (birini [SymTagEnum numaralandırması](../../debugger/debug-interface-access/symtagenum.md) değerleri).|  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Idiasession::get_globalscope](../../debugger/debug-interface-access/idiasession-get-globalscope.md)   
 [Simge türlerinin sözcük hiyerarşisi](../../debugger/debug-interface-access/lexical-hierarchy-of-symbol-types.md)