---
title: IDebugExtendedField | Microsoft Docs
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
- IDebugExtendedField interface
ms.assetid: b491499c-af57-47da-87d6-34b7398f6591
caps.latest.revision: 7
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: ace5f36ccebc5861c7fe31bba9be41b35a8fdcf5
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/22/2018
ms.locfileid: "42630540"
---
# <a name="idebugextendedfield"></a>IDebugExtendedField
[!INCLUDE[vs2017banner](../../../includes/vs2017banner.md)]

Bu konuda en son sürümünü şu yolda bulunabilir: [IDebugExtendedField](https://docs.microsoft.com/visualstudio/extensibility/debugger/reference/idebugextendedfield).  
  
Yönetilen kod genel türleri desteklemek kullanılabilir alan türlerini genişletir.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
IDebugExtendedField : IDebugField  
```  
  
## <a name="methods"></a>Yöntemler  
 Yöntemlere ek olarak [IDebugField](../../../extensibility/debugger/reference/idebugfield.md) arabirimi bu arabirim, aşağıdaki yöntemleri uygular:  
  
|Yöntem|Açıklama|  
|------------|-----------------|  
|[GetExtendedKind](../../../extensibility/debugger/reference/idebugextendedfield-getextendedkind.md)|Belirtilen genişletilmiş alan türünü alır.|  
|[IsClosedType](../../../extensibility/debugger/reference/idebugextendedfield-isclosedtype.md)|Alan kapalı bir tür temsil edip etmediğini belirler.|  
  
## <a name="requirements"></a>Gereksinimler  
 Üstbilgi: Sh.h  
  
 Namespace: Microsoft.VisualStudio.Debugger.Interop  
  
 Derleme: Microsoft.VisualStudio.Debugger.Interop.dll

