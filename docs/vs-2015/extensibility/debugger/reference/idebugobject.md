---
title: IDebugObject | Microsoft Docs
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
- IDebugObject
helpviewer_keywords:
- IDebugObject interface
ms.assetid: 05cd8bf4-c9ee-4b49-b782-2263c33067d6
caps.latest.revision: 15
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: c6cf0197568a414e1387ba3fd72c814f9eeb77ab
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/22/2018
ms.locfileid: "42675199"
---
# <a name="idebugobject"></a>IDebugObject
[!INCLUDE[vs2017banner](../../../includes/vs2017banner.md)]

Bu konuda en son sürümünü şu yolda bulunabilir: [IDebugObject](https://docs.microsoft.com/visualstudio/extensibility/debugger/reference/idebugobject).  
  
> [!IMPORTANT]
>  Visual Studio 2015'te, bu şekilde ifade değerlendiricisi uygulama kullanım dışı bırakılmıştır. CLR ifade değerlendiricisi uygulama hakkında daha fazla bilgi için lütfen bkz [CLR ifade Değerlendiricilerini](https://github.com/Microsoft/ConcordExtensibilitySamples/wiki/CLR-Expression-Evaluators) ve [yönetilen ifade değerlendiricisi örnek](https://github.com/Microsoft/ConcordExtensibilitySamples/wiki/Managed-Expression-Evaluator-Sample).  
  
 Bu arabirim, semboller ve ifadeleri değerlerini yalıtılacak Bağlayıcısı oluşturur. bir nesneyi temsil eder.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
IDebugObject : IUnknown  
```  
  
## <a name="notes-for-implementers"></a>Uygulayanlar için Notlar  
 İfade değerlendiricisi, bir nesneyi göstermek için bu arabirimi uygular.  
  
## <a name="notes-for-callers"></a>Arayanlar İçin Notlar  
 İfade değerlendirici ayrıştırılmış ifadeler kullanan tüm nesneleri için taban sınıf arabirimidir. Bir çağrı tarafından döndürülen [bağlama](../../../extensibility/debugger/reference/idebugbinder-bind.md) yöntemi. [QueryInterface](http://msdn.microsoft.com/library/62fce95e-aafa-4187-b50b-e6611b74c3b3) daha özel arabirimler bu arabirimden alır.  
  
## <a name="methods-in-vtable-order"></a>Vtable sırayla yöntemleri  
 Aşağıdaki tabloda yöntemlerini gösterilmektedir `IDebugObject`.  
  
|Yöntem|Açıklama|  
|------------|-----------------|  
|[GetSize](../../../extensibility/debugger/reference/idebugobject-getsize.md)|Nesnenin boyutunu alır.|  
|[GetValue](../../../extensibility/debugger/reference/idebugobject-getvalue.md)|Nesnenin değerini ardışık bir bayt dizisi olarak alır.|  
|[SetValue](../../../extensibility/debugger/reference/idebugobject-setvalue.md)|Nesnenin değerini ardışık bir bayt serisinden ayarlar.|  
|[SetReferenceValue](../../../extensibility/debugger/reference/idebugobject-setreferencevalue.md)|Bu nesne başvuru değeri ayarlar.|  
|[GetMemoryContext](../../../extensibility/debugger/reference/idebugobject-getmemorycontext.md)|Nesne değeri adresini temsil eden bellek bağlamını alır.|  
|[GetManagedDebugObject](../../../extensibility/debugger/reference/idebugobject-getmanageddebugobject.md)|Hata ayıklama altyapısı adres alanında yönetilen nesnesinin bir kopyasını oluşturur.|  
|[IsNullReference](../../../extensibility/debugger/reference/idebugobject-isnullreference.md)|Bu nesne bir null başvuru olup olmadığını sınar.|  
|[Isequal](../../../extensibility/debugger/reference/idebugobject-isequal.md)|Bu bir nesneyi karşılaştırır.|  
|[IsReadOnly](../../../extensibility/debugger/reference/idebugobject-isreadonly.md)|Bu nesne, salt okunur olup olmadığını belirler.|  
|[IsProxy](../../../extensibility/debugger/reference/idebugobject-isproxy.md)|Nesnenin saydam bir ara sunucu olup olmadığını belirler.|  
  
## <a name="remarks"></a>Açıklamalar  
 İfade değerlendirici bu arabirim, ayrıştırma ağacı nesneleri temsil etmek için temel sınıf olarak kullanır.  
  
## <a name="requirements"></a>Gereksinimler  
 Üstbilgi: ee.h  
  
 Namespace: Microsoft.VisualStudio.Debugger.Interop  
  
 Derleme: Microsoft.VisualStudio.Debugger.Interop.dll  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [İfade değerlendirme arabirimleri](../../../extensibility/debugger/reference/expression-evaluation-interfaces.md)   
 [GetElement](../../../extensibility/debugger/reference/idebugarrayobject-getelement.md)   
 [bağlama](../../../extensibility/debugger/reference/idebugbinder-bind.md)

