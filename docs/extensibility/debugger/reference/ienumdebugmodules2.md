---
title: IEnumDebugModules2 | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: IEnumDebugModules2
helpviewer_keywords: IEnumDebugModules2
ms.assetid: 4fe28074-a960-41ad-b74d-b57f04c0c0ad
caps.latest.revision: "11"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 481a9c04b56ad330731b1c5a06863eb7b3f0f8e2
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2017
---
# <a name="ienumdebugmodules2"></a>IEnumDebugModules2
Bu arabirim modüllerin listesini numaralandırır.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
IEnumDebugModules2 : IUnknown  
```  
  
## <a name="notes-for-implementers"></a>Uygulayanlar için Notlar  
 Hata ayıklama altyapısı (DE) için bir program yüklü modülleri listesini temsil etmek için bu arabirimi uygular.  
  
## <a name="notes-for-callers"></a>Arayanlar İçin Notlar  
 Visual Studio çağrıları [EnumModules](../../../extensibility/debugger/reference/idebugprogram2-enummodules.md) bu arabirimi elde edilir.  
  
## <a name="methods-in-vtable-order"></a>Vtable sırayla yöntemleri  
 Aşağıdaki tabloda yöntemlerini gösterilmektedir `IEnumDebugModules2`.  
  
|Yöntem|Açıklama|  
|------------|-----------------|  
|[Sonraki](../../../extensibility/debugger/reference/ienumdebugmodules2-next.md)|Bir numaralandırma sırasını modülleri belirtilen sayısını alır.|  
|[Atla](../../../extensibility/debugger/reference/ienumdebugmodules2-skip.md)|Bir numaralandırma sırasını modülleri belirtilen sayıda atlar.|  
|[Sıfırla](../../../extensibility/debugger/reference/ienumdebugmodules2-reset.md)|Bir numaralandırma sırasını başlangıç durumuna sıfırlar.|  
|[Kopya](../../../extensibility/debugger/reference/ienumdebugmodules2-clone.md)|Geçerli Numaralandırıcı aynı numaralandırma duruma içeren bir numaralandırıcı oluşturur.|  
|[GetCount](../../../extensibility/debugger/reference/ienumdebugmodules2-getcount.md)|Modülleri sayısını alır.|  
  
## <a name="remarks"></a>Açıklamalar  
 Visual Studio öncelikle güncelleştirmek için bu arabirimi kullanan **modülleri** penceresi.  
  
 Visual Studio'da hata ayıklama amacıyla, mantıksal bir sıra modülü sınırlar, bu nedenle arası kod yönerge programdır tek bir modüllerin listesini gereksinimini [IDebugProgram2](../../../extensibility/debugger/reference/idebugprogram2.md) arabirimi. Listedeki ilk modülü genellikle ilişkili programı için ilk giriş noktası içerir.  
  
## <a name="requirements"></a>Gereksinimler  
 Başlık: msdbg.h  
  
 Namespace: Microsoft.VisualStudio.Debugger.Interop  
  
 Derleme: Microsoft.VisualStudio.Debugger.Interop.dll  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Çekirdek arabirimleri](../../../extensibility/debugger/reference/core-interfaces.md)   
 [IDebugProgram2](../../../extensibility/debugger/reference/idebugprogram2.md)   
 [EnumModules](../../../extensibility/debugger/reference/idebugprogram2-enummodules.md)