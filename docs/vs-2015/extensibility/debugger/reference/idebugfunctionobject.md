---
title: IDebugFunctionObject | Microsoft Docs
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- IDebugFunctionObject
helpviewer_keywords:
- IDebugFunctionObject interface
ms.assetid: 8d94e97c-a9d1-400c-8a98-a44b5385b33a
caps.latest.revision: 14
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 74289719713f03912a45d7980419ad13fe56425a
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/22/2018
ms.locfileid: "42692764"
---
# <a name="idebugfunctionobject"></a>IDebugFunctionObject
[!INCLUDE[vs2017banner](../../../includes/vs2017banner.md)]

Bu konuda en son sürümünü şu yolda bulunabilir: [IDebugFunctionObject](https://docs.microsoft.com/visualstudio/extensibility/debugger/reference/idebugfunctionobject).  
  
> [!IMPORTANT]
>  Visual Studio 2015'te, bu şekilde ifade değerlendiricisi uygulama kullanım dışı bırakılmıştır. CLR ifade değerlendiricisi uygulama hakkında daha fazla bilgi için lütfen bkz [CLR ifade Değerlendiricilerini](https://github.com/Microsoft/ConcordExtensibilitySamples/wiki/CLR-Expression-Evaluators) ve [yönetilen ifade değerlendiricisi örnek](https://github.com/Microsoft/ConcordExtensibilitySamples/wiki/Managed-Expression-Evaluator-Sample).  
  
 Bu arabirim, bir işlevi temsil eder.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
IDebugFunctionObject : IDebugObject  
```  
  
## <a name="notes-for-implementers"></a>Uygulayanlar için Notlar  
 İfade değerlendiricisi, bir işlevi temsil etmek için bu arabirimi uygular.  
  
## <a name="notes-for-callers"></a>Arayanlar İçin Notlar  
 Bu bir arabirimdir özelleştirmesi [IDebugObject](../../../extensibility/debugger/reference/idebugobject.md) arabirim ve kullanılarak elde edilen [QueryInterface](http://msdn.microsoft.com/library/62fce95e-aafa-4187-b50b-e6611b74c3b3) üzerinde `IDebugObject` arabirimi.  
  
## <a name="methods-in-vtable-order"></a>Vtable sırayla yöntemleri  
 Devralınan yöntemleri yanı sıra [IDebugObject](../../../extensibility/debugger/reference/idebugobject.md), `IDebugFunctionObject` arabirimi aşağıdaki yöntemleri sunar.  
  
|Yöntem|Açıklama|  
|------------|-----------------|  
|[CreatePrimitiveObject](../../../extensibility/debugger/reference/idebugfunctionobject-createprimitiveobject.md)|Temel veri nesnesi oluşturur.|  
|[CreateObject](../../../extensibility/debugger/reference/idebugfunctionobject-createobject.md)|Bir oluşturucu kullanılarak bir nesne oluşturur.|  
|[CreateObjectNoConstructor](../../../extensibility/debugger/reference/idebugfunctionobject-createobjectnoconstructor.md)|Bir nesne ile hiçbir oluşturucu oluşturur.|  
|[CreateArrayObject](../../../extensibility/debugger/reference/idebugfunctionobject-createarrayobject.md)|Bir dizi nesnesi oluşturur.|  
|[CreateStringObject](../../../extensibility/debugger/reference/idebugfunctionobject-createstringobject.md)|Bir dize nesnesi oluşturur.|  
|[Değerlendir](../../../extensibility/debugger/reference/idebugfunctionobject-evaluate.md)|İşlevini çağırır ve bir nesne olarak elde edilen değeri döndürür.|  
  
## <a name="remarks"></a>Açıklamalar  
 Bu arabirim, ayrıştırma ağacı işlevlerini temsil etmek ifade değerlendirici sağlar. `Create` Bu arabirimdeki yöntemleri yönteme giriş parametrelerini temsil eden nesneler oluşturmak için kullanılır. İşlev çağrı yaparak sonra yürütülebilen [değerlendir](../../../extensibility/debugger/reference/idebugfunctionobject-evaluate.md) yöntemi işlevinin dönüş değerini temsil eden bir nesne döndürür.  
  
## <a name="requirements"></a>Gereksinimler  
 Üstbilgi: ee.h  
  
 Namespace: Microsoft.VisualStudio.Debugger.Interop  
  
 Derleme: Microsoft.VisualStudio.Debugger.Interop.dll  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [İfade değerlendirme arabirimleri](../../../extensibility/debugger/reference/expression-evaluation-interfaces.md)   
 [IDebugObject](../../../extensibility/debugger/reference/idebugobject.md)

