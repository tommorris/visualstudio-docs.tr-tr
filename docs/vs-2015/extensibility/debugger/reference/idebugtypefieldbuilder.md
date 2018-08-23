---
title: IDebugTypeFieldBuilder | Microsoft Docs
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
- IDebugTypeFieldBuilder interface
ms.assetid: 2dfed0be-6972-4bec-baec-f0b78df9ef97
caps.latest.revision: 7
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: e88ab51bd6af9b2b1741d00d7097a9b07baa5c15
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/22/2018
ms.locfileid: "42630921"
---
# <a name="idebugtypefieldbuilder"></a>IDebugTypeFieldBuilder
[!INCLUDE[vs2017banner](../../../includes/vs2017banner.md)]

Bu konuda en son sürümünü şu yolda bulunabilir: [IDebugTypeFieldBuilder](https://docs.microsoft.com/visualstudio/extensibility/debugger/reference/idebugtypefieldbuilder).  
  
Türünü temsil eden bir alan oluşturma özelliği temsil eder.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
IDebugTypeFieldBuilder : IUnknown  
```  
  
## <a name="notes-for-callers"></a>Arayanlar İçin Notlar  
 Bu arabirim, sembol Sağlayıcısı'ndan elde edilir.  
  
## <a name="methods"></a>Yöntemler  
 Bu arabirim, aşağıdaki yöntemleri uygular:  
  
|Yöntem|Açıklama|  
|------------|-----------------|  
|[CreatePrimitive](../../../extensibility/debugger/reference/idebugtypefieldbuilder-createprimitive.md)|Temel türünü temsil eden bir nesne oluşturur.|  
|[CreatePointerToType](../../../extensibility/debugger/reference/idebugtypefieldbuilder-createpointertotype.md)|Belirtilen tür işaretçisi oluşturur.|  
  
## <a name="requirements"></a>Gereksinimler  
 Üstbilgi: Sh.h  
  
 Namespace: Microsoft.VisualStudio.Debugger.Interop  
  
 Derleme: Microsoft.VisualStudio.Debugger.Interop.dll

