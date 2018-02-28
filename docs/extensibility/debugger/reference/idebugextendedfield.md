---
title: IDebugExtendedField | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- IDebugExtendedField interface
ms.assetid: b491499c-af57-47da-87d6-34b7398f6591
caps.latest.revision: 
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload:
- vssdk
ms.openlocfilehash: bc656814b355636e4bc4a9a362bd36b84c7d0786
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/22/2017
---
# <a name="idebugextendedfield"></a>IDebugExtendedField
Yönetilen kod genel türler desteklemek kullanılabilir alan türlerini genişletir.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
IDebugExtendedField : IDebugField  
```  
  
## <a name="methods"></a>Yöntemler  
 Yöntemlere ek olarak [IDebugField](../../../extensibility/debugger/reference/idebugfield.md) arabirimi, bu arabirimi uygulayan aşağıdaki yöntemleri:  
  
|Yöntem|Açıklama|  
|------------|-----------------|  
|[GetExtendedKind](../../../extensibility/debugger/reference/idebugextendedfield-getextendedkind.md)|Belirtilen genişletilmiş alan türü alır.|  
|[IsClosedType](../../../extensibility/debugger/reference/idebugextendedfield-isclosedtype.md)|Alan kapalı bir türü temsil edip etmediğini belirler.|  
  
## <a name="requirements"></a>Gereksinimler  
 Başlık: Sh.h  
  
 Namespace: Microsoft.VisualStudio.Debugger.Interop  
  
 Derleme: Microsoft.VisualStudio.Debugger.Interop.dll