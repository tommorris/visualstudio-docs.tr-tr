---
title: "Bir ifade değerlendiricisi uygulama | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- expression evaluators
- debugging [Debugging SDK], expression evaluators
ms.assetid: e9ada7be-845e-4baa-bf8f-e4890e7ba490
caps.latest.revision: "12"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload: vssdk
ms.openlocfilehash: 9f18e2e131b6baa325bd7e0b65babee4c3679ed8
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/22/2017
---
# <a name="implementing-an-expression-evaluator"></a>Bir ifade değerlendiricisi uygulama
> [!IMPORTANT]
>  Visual Studio 2015'te ifade değerlendiricisi uygulama bu şekilde kullanım dışıdır. CLR ifade değerlendiricisi uygulama hakkında daha fazla bilgi için lütfen bkz [CLR ifade Değerlendiricileri](https://github.com/Microsoft/ConcordExtensibilitySamples/wiki/CLR-Expression-Evaluators) ve [yönetilen ifade değerlendiricisi örnek](https://github.com/Microsoft/ConcordExtensibilitySamples/wiki/Managed-Expression-Evaluator-Sample).  
  
 Bir ifade değerlendirme hata ayıklama altyapısı (DE), simge sağlayıcısı (SP), bağlayıcı nesnesi ve ifade değerlendiricisi (EE) kendisi arasında karmaşık Interplay olur. Bu dört bileşenlerin bir bileşen tarafından uygulanan ve bir başkası tarafından tüketilen arabirimleri tarafından bağlanır.  
  
 EE DE biçiminde bir dize öğesinden bir ifade alır ve ayrıştırır veya onu değerlendirir. EE DE tarafından tüketilen aşağıdaki arabirimlerini uygular:  
  
-   [IDebugExpressionEvaluator](../../extensibility/debugger/reference/idebugexpressionevaluator.md)  
  
-   [IDebugParsedExpression](../../extensibility/debugger/reference/idebugparsedexpression.md)  
  
 EE sembolleri ve nesnelerine değerini almak için DE tarafından sağlanan bağlayıcı nesnesi çağırır. EE DE tarafından uygulanan aşağıdaki arayüzleri kullanır:  
  
-   [IDebugObject](../../extensibility/debugger/reference/idebugobject.md)  
  
-   [IDebugArrayObject](../../extensibility/debugger/reference/idebugarrayobject.md)  
  
-   [IDebugFunctionObject](../../extensibility/debugger/reference/idebugfunctionobject.md)  
  
-   [IDebugPointerObject](../../extensibility/debugger/reference/idebugpointerobject.md)  
  
-   [IDebugManagedObject](../../extensibility/debugger/reference/idebugmanagedobject.md)  
  
-   [IEnumDebugObjects](../../extensibility/debugger/reference/ienumdebugobjects.md)  
  
-   [IDebugBinder](../../extensibility/debugger/reference/idebugbinder.md)  
  
 EE uygulayan [IDebugProperty2](../../extensibility/debugger/reference/idebugproperty2.md). `IDebugProperty2`yerel bir değişken, ilkel veya ilgili bilgileri görüntüler Visual Studio, bir nesne gibi bir ifade değerlendirme sonucu açıklamak için bir mekanizma sağlar **Yereller**,  **Gözcü**, veya **hemen** penceresi.  
  
 Bilgi için sorduğunda SP tarafından DE EE verilir. SP adresleri ve aşağıdaki arabirimleri ve bunların türevleri gibi alanlarını açıklayan arabirimlerini uygular:  
  
-   [IDebugSymbolProvider](../../extensibility/debugger/reference/idebugsymbolprovider.md)  
  
-   [IDebugAddress](../../extensibility/debugger/reference/idebugaddress.md)  
  
-   [IDebugField](../../extensibility/debugger/reference/idebugfield.md)  
  
 EE tüm bu arabirimleri tüketir.  
  
## <a name="in-this-section"></a>Bu Bölümde  
 [İfade Değerlendiricisi Uygulama Stratejisi](../../extensibility/debugger/expression-evaluator-implementation-strategy.md)  
 İfade değerlendirici (EE) uygulama stratejisi için üç adımlık bir işlemdir tanımlar.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Bir CLR ifade değerlendiricisi yazma](../../extensibility/debugger/writing-a-common-language-runtime-expression-evaluator.md)