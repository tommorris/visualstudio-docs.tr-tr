---
title: IDebugField | Microsoft Docs
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
- IDebugField
helpviewer_keywords:
- IDebugField interface
ms.assetid: adecdd1c-b1b9-4027-92da-74cbe910636f
caps.latest.revision: 13
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 26bcd1d2a85e547aa733c6a8e7d906a822d0fdc0
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/22/2018
ms.locfileid: "42694643"
---
# <a name="idebugfield"></a>IDebugField
[!INCLUDE[vs2017banner](../../../includes/vs2017banner.md)]

Bu konuda en son sürümünü şu yolda bulunabilir: [IDebugField](https://docs.microsoft.com/visualstudio/extensibility/debugger/reference/idebugfield).  
  
Bu arabirim, bir alan, diğer bir deyişle, bir simge veya türü bir açıklamasını temsil eder.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
IDebugField : IUnknown  
```  
  
## <a name="notes-for-implementers"></a>Uygulayanlar için Notlar  
 Sembol sağlayıcısı, tüm alanlar için temel sınıf olarak bu arabirimi uygular.  
  
## <a name="notes-for-callers"></a>Arayanlar İçin Notlar  
 Bu arabirim, tüm alanlar için temel sınıftır. Dönüş değerini temel alarak [GetKind](../../../extensibility/debugger/reference/idebugfield-getkind.md), bu arabirim daha özel arabirimler kullanarak döndürebilir [QueryInterface](http://msdn.microsoft.com/library/62fce95e-aafa-4187-b50b-e6611b74c3b3). Ayrıca, pek çok arabirimi dönüş `IDebugField` çeşitli yöntemler nesneleri.  
  
## <a name="methods-in-vtable-order"></a>Vtable sırayla yöntemleri  
 Aşağıdaki tabloda yöntemlerini gösterilmektedir `IDebugField`.  
  
|Yöntem|Açıklama|  
|------------|-----------------|  
|[GetInfo](../../../extensibility/debugger/reference/idebugfield-getinfo.md)|Simge veya türü görüntülenebilir bilgilerini alır.|  
|[GetKind](../../../extensibility/debugger/reference/idebugfield-getkind.md)|Alan türünü alır.|  
|[GetType](../../../extensibility/debugger/reference/idebugfield-gettype.md)|Alan türünü alır.|  
|[GetContainer](../../../extensibility/debugger/reference/idebugfield-getcontainer.md)|Alan kapsayıcısını alır.|  
|[GetAddress](../../../extensibility/debugger/reference/idebugfield-getaddress.md)|Adres alanının alır.|  
|[GetSize](../../../extensibility/debugger/reference/idebugfield-getsize.md)|Bir alanın bayt cinsinden boyutunu alır.|  
|[GetExtendedInfo](../../../extensibility/debugger/reference/idebugfield-getextendedinfo.md)|Genişletilmiş bir alanla ilgili bilgiler.|  
|[eşittir](../../../extensibility/debugger/reference/idebugfield-equal.md)|İki alan karşılaştırır.|  
|[GetTypeInfo](../../../extensibility/debugger/reference/idebugfield-gettypeinfo.md)|Tür bağımsız türü ve sembol bilgilerini alır.|  
  
## <a name="remarks"></a>Açıklamalar  
 Bir tür için bir C dili eşdeğerdir `typedef`.  
  
 Aşağıdaki örnekte C++ dili, `weather` bir sınıf türüdür ve `sunny` ve `stormy` simgeler şunlardır:  
  
```cpp#  
class weather;  
weather sunny;  
weather stormy;  
```  
  
 Bir alan temsil eden bir simge ya da türü çağırarak belirlenebilir [GetKind](../../../extensibility/debugger/reference/idebugfield-getkind.md) inceleyerek [FIELD_KIND](../../../extensibility/debugger/reference/field-kind.md) sonucu. Varsa `FIELD_KIND_TYPE` bitinin ayarlanmasıdır, alanın bir tür olduğunda ve `FIELD_KIND_SYMBOL` bit ayarlandığında, bir semboldür.  
  
## <a name="requirements"></a>Gereksinimler  
 Üstbilgi: sh.h  
  
 Namespace: Microsoft.VisualStudio.Debugger.Interop  
  
 Derleme: Microsoft.VisualStudio.Debugger.Interop.dll  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Sembol Sağlayıcısı Arabirimleri](../../../extensibility/debugger/reference/symbol-provider-interfaces.md)

