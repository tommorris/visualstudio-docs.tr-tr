---
title: IDebugExpressionEvaluator3 | Microsoft Docs
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
- IDebugExpressionEvaluator3 interface
ms.assetid: c27c2a14-300b-4535-be22-767c83602f69
caps.latest.revision: 12
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 4e8dc830ddca5726ab10d5ba2311c48bace411ac
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/22/2018
ms.locfileid: "42629554"
---
# <a name="idebugexpressionevaluator3"></a>IDebugExpressionEvaluator3
[!INCLUDE[vs2017banner](../../../includes/vs2017banner.md)]

Bu konuda en son sürümünü şu yolda bulunabilir: [IDebugExpressionEvaluator3](https://docs.microsoft.com/visualstudio/extensibility/debugger/reference/idebugexpressionevaluator3).  
  
> [!IMPORTANT]
>  Visual Studio 2015'te, bu şekilde ifade değerlendiricisi uygulama kullanım dışı bırakılmıştır. CLR ifade değerlendiricisi uygulama hakkında daha fazla bilgi için lütfen bkz [CLR ifade Değerlendiricilerini](https://github.com/Microsoft/ConcordExtensibilitySamples/wiki/CLR-Expression-Evaluators) ve [yönetilen ifade değerlendiricisi örnek](https://github.com/Microsoft/ConcordExtensibilitySamples/wiki/Managed-Expression-Evaluator-Sample).  
  
 İfade değerlendiricisi (EE) ile bir Gelişmiş ayrıştırıcı ağacı temsil eder.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
IDebugExpressionEvaluator3 : IDebugExpressionEvaluator2  
```  
  
## <a name="notes-for-callers"></a>Arayanlar İçin Notlar  
 Ayrıştırıcının'ın bu sürümü sembol sağlayıcısı ve değerlendirme çerçevesinin adresi geçirir.  
  
## <a name="methods"></a>Yöntemler  
 Yöntemlere ek olarak [IDebugExpressionEvaluator2](../../../extensibility/debugger/reference/idebugexpressionevaluator2.md) arabirimi bu arabirim, aşağıdaki yöntemi uygular:  
  
|Yöntem|Açıklama|  
|------------|-----------------|  
|[Parse2](../../../extensibility/debugger/reference/idebugexpressionevaluator3-parse2.md)|Bir ifade dizesini verilen sembol sağlayıcısı ve değerlendirme çerçevesinin adres ayrıştırılmış bir ifade dönüştürür.|  
  
## <a name="requirements"></a>Gereksinimler  
 Üstbilgi: Ee.h  
  
 Namespace: Microsoft.VisualStudio.Debugger.Interop  
  
 Derleme: Microsoft.VisualStudio.Debugger.Interop.dll

