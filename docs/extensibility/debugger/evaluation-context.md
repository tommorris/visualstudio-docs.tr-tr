---
title: "Değerlendirme bağlamı | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- debugging [Debugging SDK], expression evaluation
- expression evaluation, context
ms.assetid: 008a20c7-1b27-4013-bf96-d6a3f510da02
caps.latest.revision: "11"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload: vssdk
ms.openlocfilehash: 9a490ef7c4ea42fe85c291ee913d7ad5e1cda1bb
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/22/2017
---
# <a name="evaluation-context"></a>Değerlendirme bağlamı
> [!IMPORTANT]
>  Visual Studio 2015'te ifade değerlendiricisi uygulama bu şekilde kullanım dışıdır. CLR ifade değerlendiricisi uygulama hakkında daha fazla bilgi için lütfen bkz [CLR ifade Değerlendiricileri](https://github.com/Microsoft/ConcordExtensibilitySamples/wiki/CLR-Expression-Evaluators) ve [yönetilen ifade değerlendiricisi örnek](https://github.com/Microsoft/ConcordExtensibilitySamples/wiki/Managed-Expression-Evaluator-Sample).  
  
 Hata ayıklama altyapısı (DE) ifade değerlendiricisi (EE) çağırdığında için üç bağımsız değişken geçirildi [EvaluateSync](../../extensibility/debugger/reference/idebugparsedexpression-evaluatesync.md) aşağıdaki tabloda gösterildiği gibi bulma ve sembolleri değerlendirmek için bağlamı belirlemek.  
  
## <a name="arguments"></a>Arguments  
  
|Bağımsız Değişken|Açıklama|  
|--------------|-----------------|  
|`pSymbolProvider`|Bir [IDebugSymbolProvider](../../extensibility/debugger/reference/idebugsymbolprovider.md) simgenin tanımlamak için kullanılacak simge işleyici (SH) belirten arabirimi.|  
|`pAddress`|Bir [IDebugAddress](../../extensibility/debugger/reference/idebugaddress.md) geçerli yürütme noktası belirtir arabirimi. Yürütülen kod içeren yöntemi bulmak için kullanılabilir.|  
|`pBinder`|Bir [IDebugBinder](../../extensibility/debugger/reference/idebugbinder.md) adı verilen bir simge türü ve değeri bulmak için kullanılan arabirim.|  
  
 `IDebugParsedExpression::EvaluateSync`döndüren bir [IDebugProperty2](../../extensibility/debugger/reference/idebugproperty2.md) sonuç değeri ve türünü temsil eden arabirim.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Anahtar ifade değerlendiricisi arabirimleri](../../extensibility/debugger/key-expression-evaluator-interfaces.md)   
 [Yerel öğeler görüntüleme](../../extensibility/debugger/displaying-locals.md)   
 [EvaluateSync](../../extensibility/debugger/reference/idebugparsedexpression-evaluatesync.md)   
 [IDebugProperty2](../../extensibility/debugger/reference/idebugproperty2.md)   
 [IDebugSymbolProvider](../../extensibility/debugger/reference/idebugsymbolprovider.md)   
 [IDebugAddress](../../extensibility/debugger/reference/idebugaddress.md)   
 [IDebugBinder](../../extensibility/debugger/reference/idebugbinder.md)