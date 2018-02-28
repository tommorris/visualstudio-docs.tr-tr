---
title: "Simge türlerinin sözcük hiyerarşisi | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- symbols [DIA SDK], type hierarchies
ms.assetid: 912da653-ddfe-45a4-84aa-64281283739a
caps.latest.revision: 
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.workload:
- multiple
ms.openlocfilehash: d6f9fe7b24a1e2bdd68d92f6dd22952df0d2a057
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/22/2017
---
# <a name="lexical-hierarchy-of-symbol-types"></a>Simge Türlerinin Sözcük Hiyerarşisi
Aşağıdaki tabloda Simge türlerinin sözcük hiyerarşi içinde gösterir.  
  
## <a name="symbol-types"></a>Sembol türleri  
  
|Simge türü|Açıklama|  
|-----------------|-----------------|  
|[Ek Açıklama](../../debugger/debug-interface-access/annotation.md)|Program kodunda açıklamalı bir konum belirtir.|  
|[Block](../../debugger/debug-interface-access/block.md)|İç içe geçmiş kapsamlar işlevlerde belirtir.|  
|`Compiland`|Belirten bir `compiland` .exe dosyasına bağlı.|  
|[CompilandDetails](../../debugger/debug-interface-access/compilanddetails.md)|Ek derlenecek ayrıntıları yükleniyor gerektirir ve bu nedenle almak için çalışma zamanında yük doğurur derlenecek dosya verilerini belirtir.|  
|[CompilandEnv](../../debugger/debug-interface-access/compilandenv.md)|Derlenecek derlenmesini önemli herhangi bir ek ortam değişkenlerini belirtir.|  
|[Özel (Arabirim Erişimi SDK'sında Hata Ayıklama)](../../debugger/debug-interface-access/custom-debug-interface-access-sdk.md)|Kullanıcı tanımlı bir sembol belirtir.|  
|[Veriler (Arabirim Erişimi SDK'sında Hata Ayıklama)](../../debugger/debug-interface-access/data-debug-interface-access-sdk.md)|Bu değişkenleri parametreler, yerel değişkenleri, genel değişkenler ve sınıf üyeleri belirtir.|  
|[Exe](../../debugger/debug-interface-access/exe.md)|Genel kapsamdaki verileri belirtir; Tüm bir .exe veya .dll dosyasına karşılık gelir.|  
|[FuncDebugEnd](../../debugger/debug-interface-access/funcdebugend.md)|Tanımlanan bir nokta olan bir işlev belirtir sona erdirmek için hangi hata ayıklama sırasında değildir.|  
|[FuncDebugStart](../../debugger/debug-interface-access/funcdebugstart.md)|Tanımlanan bir nokta olan bir işlev belirtir başlamak için hangi hata ayıklama sırasında değildir.|  
|[İşlev (Arabirim Erişimi SDK'sında Hata Ayıklama)](../../debugger/debug-interface-access/function-debug-interface-access-sdk.md)|Bir işlev belirtir.|  
|[Etiket (Arabirim Erişimi SDK'sında Hata Ayıklama)](../../debugger/debug-interface-access/label-debug-interface-access-sdk.md)|Program kodunda bir konum belirtir.|  
|[PublicSymbol](../../debugger/debug-interface-access/publicsymbol.md)|Bir yürütülebilir programı oluştururken görünür dış bir sembol belirtir.|  
|[Dönüştürücü](../../debugger/debug-interface-access/thunk.md)|Belirten bir `thunk`.|  
|[UsingNameSpace](../../debugger/debug-interface-access/usingnamespace.md)|Belirten bir `namespace`tanımlayıcısı.|  
  
> [!NOTE]
>  Sembol türüne bağlı olarak ek sembol özellikleri kullanılabilir. Bu özellikleri tek tek sembol konuları listelenmiştir.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Simge türlerinin sınıf hiyerarşisi](../../debugger/debug-interface-access/class-hierarchy-of-symbol-types.md)   
 [Idiasymbol::get_symtag](../../debugger/debug-interface-access/idiasymbol-get-symtag.md)   
 [Simgeler ve simge etiketleri](../../debugger/debug-interface-access/symbols-and-symbol-tags.md)   
 [SymTagEnum numaralandırması](../../debugger/debug-interface-access/symtagenum.md)