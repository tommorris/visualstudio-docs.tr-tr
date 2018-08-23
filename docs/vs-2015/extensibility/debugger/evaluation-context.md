---
title: Değerlendirme bağlamı | Microsoft Docs
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
- debugging [Debugging SDK], expression evaluation
- expression evaluation, context
ms.assetid: 008a20c7-1b27-4013-bf96-d6a3f510da02
caps.latest.revision: 12
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 97869b59b657ab4f035e573e87808ca4e86246c1
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/22/2018
ms.locfileid: "42692651"
---
# <a name="evaluation-context"></a>Değerlendirme Bağlamı
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

Bu konuda en son sürümünü şu yolda bulunabilir: [değerlendirme bağlamı](https://docs.microsoft.com/visualstudio/extensibility/debugger/evaluation-context).  
  
> [!IMPORTANT]
>  Visual Studio 2015'te, bu şekilde ifade değerlendiricisi uygulama kullanım dışı bırakılmıştır. CLR ifade değerlendiricisi uygulama hakkında daha fazla bilgi için lütfen bkz [CLR ifade Değerlendiricilerini](https://github.com/Microsoft/ConcordExtensibilitySamples/wiki/CLR-Expression-Evaluators) ve [yönetilen ifade değerlendiricisi örnek](https://github.com/Microsoft/ConcordExtensibilitySamples/wiki/Managed-Expression-Evaluator-Sample).  
  
 Hata ayıklama altyapısı (DE) ifade değerlendiricisi (EE) çağırdığında, üç bağımsız değişken geçirilen [EvaluateSync](../../extensibility/debugger/reference/idebugparsedexpression-evaluatesync.md) bulma ve değerlendirme sembolleri bağlam aşağıdaki tabloda gösterildiği gibi belirleyin.  
  
## <a name="arguments"></a>Arguments  
  
|Bağımsız Değişken|Açıklama|  
|--------------|-----------------|  
|`pSymbolProvider`|Bir [IDebugSymbolProvider](../../extensibility/debugger/reference/idebugsymbolprovider.md) sembolü tanımlamak için kullanılacak sembol işleyici (SH) belirten arabirimi.|  
|`pAddress`|Bir [IDebugAddress](../../extensibility/debugger/reference/idebugaddress.md) arabirimi geçerli yürütme noktasını belirtir. Yürütülen kod içeren yöntemi bulmak için kullanılabilir.|  
|`pBinder`|Bir [IDebugBinder](../../extensibility/debugger/reference/idebugbinder.md) adı verilen bir simgenin türünü ve değerini bulmak için kullanılan arabirim.|  
  
 `IDebugParsedExpression::EvaluateSync` döndürür bir [IDebugProperty2](../../extensibility/debugger/reference/idebugproperty2.md) sonuç değerini ve türünü temsil eden arabirim.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Anahtar ifade değerlendiricisi arabirimleri](../../extensibility/debugger/key-expression-evaluator-interfaces.md)   
 [Yerel öğeleri görüntüleme](../../extensibility/debugger/displaying-locals.md)   
 [EvaluateSync](../../extensibility/debugger/reference/idebugparsedexpression-evaluatesync.md)   
 [IDebugProperty2](../../extensibility/debugger/reference/idebugproperty2.md)   
 [IDebugSymbolProvider](../../extensibility/debugger/reference/idebugsymbolprovider.md)   
 [IDebugAddress](../../extensibility/debugger/reference/idebugaddress.md)   
 [IDebugBinder](../../extensibility/debugger/reference/idebugbinder.md)

