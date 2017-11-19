---
title: "Profıler_heap_object_optıonal_ınfo yapısı | Microsoft Docs"
ms.custom: 
ms.date: 01/18/2017
ms.prod: windows-script-interfaces
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: reference
ms.assetid: 77e638bd-ae36-4292-a170-90a0c500e610
caps.latest.revision: "5"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 52e231484b48bf2741281644c746b448fd6f657b
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2017
---
# <a name="profilerheapobjectoptionalinfo-structure"></a>PROFILER_HEAP_OBJECT_OPTIONAL_INFO Yapısı
Yığın nesneler hakkında isteğe bağlı bilgileri temsil eder.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
typedef struct _PROFILER_HEAP_OBJECT_OPTIONAL_INFO{    PROFILER_HEAP_OBJECT_OPTIONAL_INFO_TYPE infoType;    [switch_type(PROFILER_HEAP_OBJECT_OPTIONAL_INFO_TYPE), switch_is(infoType)] union    {        [case(PROFILER_HEAP_OBJECT_OPTIONAL_INFO_PROTOTYPE)] PROFILER_HEAP_OBJECT_ID prototype;        [case(PROFILER_HEAP_OBJECT_OPTIONAL_INFO_FUNCTION_NAME)] LPCWSTR functionName;        [case(PROFILER_HEAP_OBJECT_OPTIONAL_INFO_ELEMENT_ATTRIBUTES_SIZE)] UINT elementAttributesSize;        [case(PROFILER_HEAP_OBJECT_OPTIONAL_INFO_ELEMENT_TEXT_CHILDREN_SIZE)] UINT elementTextChildrenSize;        [case(PROFILER_HEAP_OBJECT_OPTIONAL_INFO_SCOPE_LIST)] PROFILER_HEAP_OBJECT_SCOPE_LIST* scopeList;        [case(PROFILER_HEAP_OBJECT_OPTIONAL_INFO_INTERNAL_PROPERTY)] PROFILER_HEAP_OBJECT_RELATIONSHIP* internalProperty;        [case(PROFILER_HEAP_OBJECT_OPTIONAL_INFO_NAME_PROPERTIES)] PROFILER_HEAP_OBJECT_RELATIONSHIP_LIST* namePropertyList;        [case(PROFILER_HEAP_OBJECT_OPTIONAL_INFO_INDEX_PROPERTIES)] PROFILER_HEAP_OBJECT_RELATIONSHIP_LIST* indexPropertyList;        [case(PROFILER_HEAP_OBJECT_OPTIONAL_INFO_RELATIONSHIPS)] PROFILER_HEAP_OBJECT_RELATIONSHIP_LIST* relationshipList;        [case(PROFILER_HEAP_OBJECT_OPTIONAL_INFO_WINRTEVENTS)] PROFILER_HEAP_OBJECT_RELATIONSHIP_LIST* eventList;    };} PROFILER_HEAP_OBJECT_OPTIONAL_INFO;  
```  
  
## <a name="members"></a>Üyeler  
  
|Üye|Tür|Açıklama|  
|------------|----------|-----------------|  
|bilgi türü|[Profıler_heap_object_optıonal_ınfo_type numaralandırması](../../winscript/reference/profiler-heap-object-optional-info-type-enumeration.md)|İsteğe bağlı bilgileri türü.|  
|prototip|[Profıler_heap_object_ıd türü](../../winscript/reference/profiler-heap-object-id-type.md)|Yığın nesnenin prototip nesnesi kimliği.|  
|functionName|LPCWSTR|Yığın nesnenin işlev adı.|  
|elementAttributesSize|UINT|Yığın nesnenin öğesi özniteliklerini boyutu.|  
|elementTextChildrenSize|UINT|Yığın nesnenin metin alt boyutu.|  
|KapsamListesi|[Profıler_heap_object_scope_lıst yapısı](../../winscript/reference/profiler-heap-object-scope-list-structure.md)|Yığın nesnenin kapsam listesi.|  
|internalProperty|[Profıler_heap_object_relatıonshıp yapısı](../../winscript/reference/profiler-heap-object-relationship-structure.md)|Yığın nesnenin iç özelliği.|  
|namePropertyList|[Profıler_heap_object_relatıonshıp_lıst yapısı](../../winscript/reference/profiler-heap-object-relationship-list-structure.md)|Yığın nesnenin adı özelliklerin listesi.|  
|indexPropertyList|[Profıler_heap_object_relatıonshıp_lıst yapısı](../../winscript/reference/profiler-heap-object-relationship-list-structure.md)|Yığın nesnenin dizin özelliklerin listesi.|  
|relationshipList|[Profıler_heap_object_relatıonshıp_lıst yapısı](../../winscript/reference/profiler-heap-object-relationship-list-structure.md)|Yığın nesnenin ilişkileri listesi.|  
|eventList|[Profıler_heap_object_relatıonshıp_lıst yapısı](../../winscript/reference/profiler-heap-object-relationship-list-structure.md)|Yığın nesnenin olayların listesi.|