---
title: IDebugModOpt | Microsoft Docs
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
- IDebugModOpt interface
ms.assetid: ebd525e3-d140-4071-9d8c-41871de4125e
caps.latest.revision: 7
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: e280e0b74d4cba3a988bccb5811a409c86c058b8
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/22/2018
ms.locfileid: "42692802"
---
# <a name="idebugmodopt"></a>IDebugModOpt
[!INCLUDE[vs2017banner](../../../includes/vs2017banner.md)]

Bu konuda en son sürümünü şu yolda bulunabilir: [IDebugModOpt](https://docs.microsoft.com/visualstudio/extensibility/debugger/reference/idebugmodopt).  
  
Hata ayıklama isteğe bağlı bir değiştirici temsil eder.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
IDebugModOpt : IUnknown  
```  
  
## <a name="notes-for-callers"></a>Arayanlar İçin Notlar  
 Alınan bir [IDebugField](../../../extensibility/debugger/reference/idebugfield.md) bir sınıf veya yöntemi temsil eden nesne.  
  
## <a name="methods"></a>Yöntemler  
 Bu arabirim, aşağıdaki yöntemi uygular:  
  
|Yöntem|Açıklama|  
|------------|-----------------|  
|[GetModOpts](../../../extensibility/debugger/reference/idebugmodopt-getmodopts.md)|İsteğe bağlı değiştiricilere listesini alır.|  
  
## <a name="requirements"></a>Gereksinimler  
 Üstbilgi: Sh.h  
  
 Namespace: Microsoft.VisualStudio.Debugger.Interop  
  
 Derleme: Microsoft.VisualStudio.Debugger.Interop.dll

