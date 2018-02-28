---
title: IDebugCustomAttributeQuery | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- IDebugCustomAttributeQuery interface
ms.assetid: b804b619-70eb-4c38-80d9-c8b32b65ed3e
caps.latest.revision: 
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload:
- vssdk
ms.openlocfilehash: 0cb0bdb5277f71e5710a05b3c06b35318d8f173f
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/22/2017
---
# <a name="idebugcustomattributequery"></a>IDebugCustomAttributeQuery
Bir sorgu için bir yöntem veya türü özel öznitelikleri temsil eder.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
IDebugCustomAttributeQuery : IUnknown  
```  
  
## <a name="methods"></a>Yöntemler  
 Bu arabirim, aşağıdaki yöntemlerden uygular:  
  
|Yöntem|Açıklama|  
|------------|-----------------|  
|[GetCustomAttributeByName](../../../extensibility/debugger/reference/idebugcustomattributequery-getcustomattributebyname.md)|Özel bir öznitelik adı verilen alır.|  
|[IsCustomAttributeDefined](../../../extensibility/debugger/reference/idebugcustomattributequery-iscustomattributedefined.md)|Belirtilen belirler özel öznitelik tanımlandı.|  
  
## <a name="requirements"></a>Gereksinimler  
 Başlık: Sh.h  
  
 Namespace: Microsoft.VisualStudio.Debugger.Interop  
  
 Derleme: Microsoft.VisualStudio.Debugger.Interop.dll