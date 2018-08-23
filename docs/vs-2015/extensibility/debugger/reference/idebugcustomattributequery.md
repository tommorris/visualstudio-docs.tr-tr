---
title: IDebugCustomAttributeQuery | Microsoft Docs
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- IDebugCustomAttributeQuery interface
ms.assetid: b804b619-70eb-4c38-80d9-c8b32b65ed3e
caps.latest.revision: 8
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: d53bbc353093bd2a28732b488ce05879063f798d
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/22/2018
ms.locfileid: "42627921"
---
# <a name="idebugcustomattributequery"></a>IDebugCustomAttributeQuery
[!INCLUDE[vs2017banner](../../../includes/vs2017banner.md)]

Bu konuda en son sürümünü şu yolda bulunabilir: [IDebugCustomAttributeQuery](https://docs.microsoft.com/visualstudio/extensibility/debugger/reference/idebugcustomattributequery).  
  
Bir sorgu için bir yöntem veya türü özel öznitelikleri temsil eder.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
IDebugCustomAttributeQuery : IUnknown  
```  
  
## <a name="methods"></a>Yöntemler  
 Bu arabirim, aşağıdaki yöntemleri uygular:  
  
|Yöntem|Açıklama|  
|------------|-----------------|  
|[GetCustomAttributeByName](../../../extensibility/debugger/reference/idebugcustomattributequery-getcustomattributebyname.md)|Özel bir öznitelik adı verilen alır.|  
|[IsCustomAttributeDefined](../../../extensibility/debugger/reference/idebugcustomattributequery-iscustomattributedefined.md)|Belirler belirtilen özel özniteliğin tanımlandığından.|  
  
## <a name="requirements"></a>Gereksinimler  
 Üstbilgi: Sh.h  
  
 Namespace: Microsoft.VisualStudio.Debugger.Interop  
  
 Derleme: Microsoft.VisualStudio.Debugger.Interop.dll

