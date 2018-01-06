---
title: IDebugObject2 | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: IDebugObject2
helpviewer_keywords: IDebugObject2 interface
ms.assetid: ef640967-8adb-4793-994d-ae1736510891
caps.latest.revision: "15"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload: vssdk
ms.openlocfilehash: 40b52cf5c36db3bf4fa07004df9a171e77c2520e
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/22/2017
---
# <a name="idebugobject2"></a>IDebugObject2
> [!IMPORTANT]
>  Visual Studio 2015'te ifade değerlendiricisi uygulama bu şekilde kullanım dışıdır. CLR ifade değerlendiricisi uygulama hakkında daha fazla bilgi için lütfen bkz [CLR ifade Değerlendiricileri](https://github.com/Microsoft/ConcordExtensibilitySamples/wiki/CLR-Expression-Evaluators) ve [yönetilen ifade değerlendiricisi örnek](https://github.com/Microsoft/ConcordExtensibilitySamples/wiki/Managed-Expression-Evaluator-Sample).  
  
 Bu arabirim, bir nesne hakkında ek bilgi sağlar.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
IDebugObject2 : IDebugObject  
```  
  
## <a name="notes-for-implementers"></a>Uygulayanlar için Notlar  
 İfade değerlendirici destek diğer adlar ve erişim nesne hakkında bilgi için bu arabirimi uygular.  
  
## <a name="notes-for-callers"></a>Arayanlar İçin Notlar  
 Bir [IDebugObject](../../../extensibility/debugger/reference/idebugobject.md) arabirimi elde edebilirsiniz bu arabirimi kullanarak [QueryInterface](/cpp/atl/queryinterface). Ayrıca, [GetObject](../../../extensibility/debugger/reference/idebugalias-getobject.md) bu arabirimini döndürür.  
  
## <a name="methods-in-vtable-order"></a>Vtable sırayla yöntemleri  
 Yöntemlere ek olarak [IDebugObject](../../../extensibility/debugger/reference/idebugobject.md) arabirimi, `IDebugObject2` arabirimini uygulayan aşağıdaki:  
  
|Yöntem|Açıklama|  
|------------|-----------------|  
|[GetBackingFieldForProperty](../../../extensibility/debugger/reference/idebugobject2-getbackingfieldforproperty.md)|Alan veya değişken (varsa) alır, yedekleme bu nesne tarafından temsil edilen özelliği.|  
|[GetICorDebugValue](../../../extensibility/debugger/reference/idebugobject2-geticordebugvalue.md)|Bu nesnenin değerini temsil eden yönetilen kod nesnesini alır.|  
|[CreateAlias](../../../extensibility/debugger/reference/idebugobject2-createalias.md)|Bu nesne için benzersiz bir kimliği oluşturur veya mevcut bir diğer adı döndürür.|  
|[GetAlias](../../../extensibility/debugger/reference/idebugobject2-getalias.md)|Bu nesneyle ilişkili diğer adı varsa alır.|  
|[GetField](../../../extensibility/debugger/reference/idebugobject2-getfield.md)|Bu nesne türünü alır.|  
|[IsUserData](../../../extensibility/debugger/reference/idebugobject2-isuserdata.md)|Bu nesne kullanıcı verilerini temsil edip etmediğini belirler.|  
|[IsEncOutdated](../../../extensibility/debugger/reference/idebugobject2-isencoutdated.md)|Düzenle ve devam et durumu artık geçerli olup olmadığını belirler.<br /><br /> Bu yöntem bir özel ifade değerlendiricisi uygulamaz (her zaman döndürmelidir `E_NOTIMPL`).|  
  
## <a name="remarks"></a>Açıklamalar  
 Bkz: [IDebugAlias](../../../extensibility/debugger/reference/idebugalias.md) diğer adlar hakkında bir tartışma için.  
  
## <a name="requirements"></a>Gereksinimler  
 Başlık: ee.h  
  
 Namespace: Microsoft.VisualStudio.Debugger.Interop  
  
 Derleme: Microsoft.VisualStudio.Debugger.Interop.dll  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [İfade değerlendirme arabirimleri](../../../extensibility/debugger/reference/expression-evaluation-interfaces.md)   
 [IDebugObject](../../../extensibility/debugger/reference/idebugobject.md)   
 [IDebugAlias](../../../extensibility/debugger/reference/idebugalias.md)   
 [GetObject](../../../extensibility/debugger/reference/idebugalias-getobject.md)