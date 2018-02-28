---
title: IDebugGenericFieldDefinition | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- IDebugGenericFieldDefinition interface
ms.assetid: b5a853b7-221e-4d62-8948-07423089d75d
caps.latest.revision: 
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload:
- vssdk
ms.openlocfilehash: 5ad51914225ddb8e6a558cac419d20119b286ab6
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/22/2017
---
# <a name="idebuggenericfielddefinition"></a>IDebugGenericFieldDefinition
Yönetilen kod genel bir tür için bir alan tanımını temsil eder.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
IDebugGenericFieldDefinition : IUnknown  
```  
  
## <a name="methods"></a>Yöntemler  
 Bu arabirim, aşağıdaki yöntemlerden uygular:  
  
|Yöntem|Açıklama|  
|------------|-----------------|  
|[ConstructInstantiation](../../../extensibility/debugger/reference/idebuggenericfielddefinition-constructinstantiation.md)|Tür bağımsız değişkenleri dizisini verilen bir alan örneği oluşturur.|  
|[GetFormalTypeParams](../../../extensibility/debugger/reference/idebuggenericfielddefinition-getformaltypeparams.md)|Parametrelerin sayısı verilen tür parametreleri alır.|  
|[TypeParamCount](../../../extensibility/debugger/reference/idebuggenericfielddefinition-typeparamcount.md)|Tür parametreleri genel alanıyla ilişkili sayısını alır.|  
  
## <a name="requirements"></a>Gereksinimler  
 Başlık: Sh.h  
  
 Namespace: Microsoft.VisualStudio.Debugger.Interop  
  
 Derleme: Microsoft.VisualStudio.Debugger.Interop.dll