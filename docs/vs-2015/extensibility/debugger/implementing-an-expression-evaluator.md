---
title: İfade değerlendiricisi uygulama | Microsoft Docs
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
- expression evaluators
- debugging [Debugging SDK], expression evaluators
ms.assetid: e9ada7be-845e-4baa-bf8f-e4890e7ba490
caps.latest.revision: 13
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: d80688af9c574c522a1151c700d2ab117f4206d8
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/22/2018
ms.locfileid: "42628750"
---
# <a name="implementing-an-expression-evaluator"></a>ifade Değerlendiricisi Uygulama
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

Bu konuda en son sürümünü şu yolda bulunabilir: [ifade değerlendiricisi uygulama](https://docs.microsoft.com/visualstudio/extensibility/debugger/implementing-an-expression-evaluator).  
  
> [!IMPORTANT]
>  Visual Studio 2015'te, bu şekilde ifade değerlendiricisi uygulama kullanım dışı bırakılmıştır. CLR ifade değerlendiricisi uygulama hakkında daha fazla bilgi için lütfen bkz [CLR ifade Değerlendiricilerini](https://github.com/Microsoft/ConcordExtensibilitySamples/wiki/CLR-Expression-Evaluators) ve [yönetilen ifade değerlendiricisi örnek](https://github.com/Microsoft/ConcordExtensibilitySamples/wiki/Managed-Expression-Evaluator-Sample).  
  
 Bir ifadenin değerlendirilmesi, hata ayıklama altyapısı (DE), sembol sağlayıcısı (SP), bağlayıcı nesnesi ve ifade değerlendiricisi (EE) kendisi arasında karmaşık bir etkileşim özelliği olur. Şu dört bileşen bir başkası tarafından kullanılan ve bir bileşen tarafından uygulanan arabirimler bağlı.  
  
 EE ifade bir dize biçiminde DE tamamlanması ayrıştırır veya onu değerlendirir. EE DE tarafından kullanılan aşağıdaki arabirimlerinden uygular:  
  
-   [IDebugExpressionEvaluator](../../extensibility/debugger/reference/idebugexpressionevaluator.md)  
  
-   [IDebugParsedExpression](../../extensibility/debugger/reference/idebugparsedexpression.md)  
  
 Simgeler ve nesneler değerini almak için DE tarafından sağlanan bağlayıcı nesnesi, EE çağırır. EE DE tarafından uygulanan arabirimler kullanır:  
  
-   [IDebugObject](../../extensibility/debugger/reference/idebugobject.md)  
  
-   [IDebugArrayObject](../../extensibility/debugger/reference/idebugarrayobject.md)  
  
-   [IDebugFunctionObject](../../extensibility/debugger/reference/idebugfunctionobject.md)  
  
-   [IDebugPointerObject](../../extensibility/debugger/reference/idebugpointerobject.md)  
  
-   [IDebugManagedObject](../../extensibility/debugger/reference/idebugmanagedobject.md)  
  
-   [IEnumDebugObjects](../../extensibility/debugger/reference/ienumdebugobjects.md)  
  
-   [IDebugBinder](../../extensibility/debugger/reference/idebugbinder.md)  
  
 EE uygulayan [IDebugProperty2](../../extensibility/debugger/reference/idebugproperty2.md). `IDebugProperty2` yerel bir değişken, basit bir tür ya da bir nesneye, ardından ilgili bilgileri görüntüler. Visual Studio gibi bir ifade değerlendirme sonucu tanımlamak için bir mekanizma sağlar **Yereller**,  **İzleme**, veya **hemen** penceresi.  
  
 Bilgi için sorduğunda SP EE için DE tarafından verilir. SP adresleri ve aşağıdaki arabirimlerinden ve bunların türevleri gibi alanlar açıklayan arabirimlerini uygular:  
  
-   [IDebugSymbolProvider](../../extensibility/debugger/reference/idebugsymbolprovider.md)  
  
-   [IDebugAddress](../../extensibility/debugger/reference/idebugaddress.md)  
  
-   [IDebugField](../../extensibility/debugger/reference/idebugfield.md)  
  
 EE tüm bu arabirimleri kullanır.  
  
## <a name="in-this-section"></a>Bu Bölümde  
 [İfade Değerlendiricisi Uygulama Stratejisi](../../extensibility/debugger/expression-evaluator-implementation-strategy.md)  
 İfade değerlendirici (EE) uygulama stratejisi için üç adımlık bir işlemdir tanımlar.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Bir CLR ifade değerlendiricisi yazma](../../extensibility/debugger/writing-a-common-language-runtime-expression-evaluator.md)

