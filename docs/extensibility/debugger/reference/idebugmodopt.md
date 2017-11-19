---
title: IDebugModOpt | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: IDebugModOpt interface
ms.assetid: ebd525e3-d140-4071-9d8c-41871de4125e
caps.latest.revision: "6"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: fa4416bbb2a4b37ba986bb0d57b32dfa5aa319cf
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2017
---
# <a name="idebugmodopt"></a>IDebugModOpt
Hata ayıklama isteğe bağlı değiştiricisi temsil eder.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
IDebugModOpt : IUnknown  
```  
  
## <a name="notes-for-callers"></a>Arayanlar İçin Notlar  
 Alınan bir [IDebugField](../../../extensibility/debugger/reference/idebugfield.md) bir sınıf veya yöntemini temsil eden nesne.  
  
## <a name="methods"></a>Yöntemler  
 Aşağıdaki yöntem bu arabirimi uygular:  
  
|Yöntem|Açıklama|  
|------------|-----------------|  
|[GetModOpts](../../../extensibility/debugger/reference/idebugmodopt-getmodopts.md)|İsteğe bağlı değiştiricileri listesini alır.|  
  
## <a name="requirements"></a>Gereksinimler  
 Başlık: Sh.h  
  
 Namespace: Microsoft.VisualStudio.Debugger.Interop  
  
 Derleme: Microsoft.VisualStudio.Debugger.Interop.dll