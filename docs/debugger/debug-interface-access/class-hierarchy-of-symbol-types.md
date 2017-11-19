---
title: "Sınıf hiyerarşisi Simge türlerinin | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords: symbols [DIA SDK], class hierarchies
ms.assetid: 0ccd6990-4654-44cd-a6f3-bdd82fe90f6c
caps.latest.revision: "10"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: a89cc0342ed5b9d4e1fcb85cbc84e124588d9c9b
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2017
---
# <a name="class-hierarchy-of-symbol-types"></a>Simge Türlerinin Sınıf Hiyerarşisi
Aşağıdaki tabloda sınıf hiyerarşisi simgesi türlerini tanımlar.  
  
## <a name="symbol-types"></a>Sembol türleri  
  
|Simge türü|Açıklama|  
|-----------------|-----------------|  
|[UDT](../../debugger/debug-interface-access/udt.md)|Her sınıf, yapı ve birleşim temsil etmek için kullanılan simge.|  
|[Enum (hata ayıklama arabirimi Erişim SDK'sı)](../../debugger/debug-interface-access/enum-debug-interface-access-sdk.md)|Numaralandırılmış türler simgesi.|  
|[PointerType](../../debugger/debug-interface-access/pointertype.md)|İşaretçi türleri simgesi.|  
|[ArrayType](../../debugger/debug-interface-access/arraytype.md)|Dizi türleri simgesi.|  
|[BaseType](../../debugger/debug-interface-access/basetype.md)|Taban türleri simgesi|  
|[TypeDef (hata ayıklama arabirimi Erişim SDK'sı)](../../debugger/debug-interface-access/typedef-debug-interface-access-sdk.md)|Diğer türleri için adları tanıtır simge.|  
|[BaseClass](../../debugger/debug-interface-access/baseclass.md)|Her bir kullanıcı tanımlı tür (UDT) taban sınıfı için kullanılan simge.|  
|[Arkadaş (hata ayıklama arabirimi Erişim SDK'sı)](../../debugger/debug-interface-access/friend-debug-interface-access-sdk.md)|Arkadaş sınıfları ve arkadaş işlevleri simgesi.|  
|[FunctionType](../../debugger/debug-interface-access/functiontype.md)|Her benzersiz işlev imzası simgesi.|  
|[FunctionArgType](../../debugger/debug-interface-access/functionargtype.md)|Bir işlev için her bir parametreyi simgesi.|  
|[VTableShape](../../debugger/debug-interface-access/vtableshape.md)|Sanal tablo boyutunu simgesi.|  
|[VTable](../../debugger/debug-interface-access/vtable.md)|Sanal bir tablo simgesi.|  
|[CustomType](../../debugger/debug-interface-access/customtype.md)|Satıcı tanımlı tür simgesi.|  
|[ManagedType](../../debugger/debug-interface-access/managedtype.md)|Meta verilerde tanımlanan bir tür simgesi.|  
|[Boyut](../../debugger/debug-interface-access/dimension.md)|Dizi boyutları simgesi.|  
  
> [!NOTE]
>  Her simge diğer simgelerini başvurular yanı sıra simgesi hakkındaki bilgileri tutmak özelliklere sahip olabilir. Bu özellikleri tek tek sembol konuları listelenmiştir.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [CV_access_e numaralandırması](../../debugger/debug-interface-access/cv-access-e.md)   
 [Simge türlerinin sözcük hiyerarşisi](../../debugger/debug-interface-access/lexical-hierarchy-of-symbol-types.md)   
 [Simgeler ve simge etiketleri](../../debugger/debug-interface-access/symbols-and-symbol-tags.md)