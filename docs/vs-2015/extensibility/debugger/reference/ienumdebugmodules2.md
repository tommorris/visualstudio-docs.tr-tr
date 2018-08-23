---
title: IEnumDebugModules2 | Microsoft Docs
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
- IEnumDebugModules2
helpviewer_keywords:
- IEnumDebugModules2
ms.assetid: 4fe28074-a960-41ad-b74d-b57f04c0c0ad
caps.latest.revision: 12
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 26ce00fd82c9d11dbea2aa5bf02be6454558e302
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/22/2018
ms.locfileid: "42684480"
---
# <a name="ienumdebugmodules2"></a>IEnumDebugModules2
[!INCLUDE[vs2017banner](../../../includes/vs2017banner.md)]

Bu konuda en son sürümünü şu yolda bulunabilir: [IEnumDebugModules2](https://docs.microsoft.com/visualstudio/extensibility/debugger/reference/ienumdebugmodules2).  
  
Bu arabirim, modüllerin listesini numaralandırır.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
IEnumDebugModules2 : IUnknown  
```  
  
## <a name="notes-for-implementers"></a>Uygulayanlar için Notlar  
 Hata ayıklama altyapısı (DE) için bir program yüklü modüller listesini temsil etmek için bu arabirimi uygular.  
  
## <a name="notes-for-callers"></a>Arayanlar İçin Notlar  
 Visual Studio çağrıları [EnumModules](../../../extensibility/debugger/reference/idebugprogram2-enummodules.md) bu arabirimi elde edilir.  
  
## <a name="methods-in-vtable-order"></a>Vtable sırayla yöntemleri  
 Aşağıdaki tabloda yöntemlerini gösterilmektedir `IEnumDebugModules2`.  
  
|Yöntem|Açıklama|  
|------------|-----------------|  
|[Next](../../../extensibility/debugger/reference/ienumdebugmodules2-next.md)|Bir numaralandırma sıralı modüllerinin belirtilen bir sayı alır.|  
|[Atla](../../../extensibility/debugger/reference/ienumdebugmodules2-skip.md)|Bir numaralandırma sıralı modülleri belirtilen sayıda atlar.|  
|[Sıfırlama](../../../extensibility/debugger/reference/ienumdebugmodules2-reset.md)|Bir numaralandırma sıralı başlangıç durumuna sıfırlar.|  
|[Kopya](../../../extensibility/debugger/reference/ienumdebugmodules2-clone.md)|Geçerli Numaralandırıcı aynı numaralandırma duruma içeren bir numaralandırıcı oluşturur.|  
|[GetCount](../../../extensibility/debugger/reference/ienumdebugmodules2-getcount.md)|Modüller sayısını alır.|  
  
## <a name="remarks"></a>Açıklamalar  
 Visual Studio, öncelikli olarak güncelleştirmek için bu arabirimi kullanan **modülleri** penceresi.  
  
 Visual Studio'da hata ayıklama amacıyla, modül sınırları, bu nedenle çapraz kod yönergeleri mantıksal bir dizi programdır modülleri için tek bir listesi için gereken [IDebugProgram2](../../../extensibility/debugger/reference/idebugprogram2.md) arabirimi. Listedeki ilk modülü genellikle ilişkili programı için ilk giriş noktası içerir.  
  
## <a name="requirements"></a>Gereksinimler  
 Üstbilgi: msdbg.h  
  
 Namespace: Microsoft.VisualStudio.Debugger.Interop  
  
 Derleme: Microsoft.VisualStudio.Debugger.Interop.dll  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Temel arabirimler](../../../extensibility/debugger/reference/core-interfaces.md)   
 [IDebugProgram2](../../../extensibility/debugger/reference/idebugprogram2.md)   
 [EnumModules](../../../extensibility/debugger/reference/idebugprogram2-enummodules.md)

