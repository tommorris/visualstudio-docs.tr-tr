---
title: IDebugProgramEx2 | Microsoft Docs
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
- IDebugProgramEx2
helpviewer_keywords:
- IDebugProgramEx2 interface
ms.assetid: 663359ed-635a-4539-addb-0cc52f19d1bd
caps.latest.revision: 19
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: b04a592bfb2d2a341ce2431461b4c23fd7088b3b
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/22/2018
ms.locfileid: "42690660"
---
# <a name="idebugprogramex2"></a>IDebugProgramEx2
[!INCLUDE[vs2017banner](../../../includes/vs2017banner.md)]

Bu konuda en son sürümünü şu yolda bulunabilir: [IDebugProgramEx2](https://docs.microsoft.com/visualstudio/extensibility/debugger/reference/idebugprogramex2).  
  
Bu arabirim, hata ayıklama Yöneticisi (SDM), bir programa ekledikten ve programla ilişkili program düğümünü Al oturum sağlar.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
IDebugProgramEx2 : IUnknown  
```  
  
## <a name="notes-for-implementers"></a>Uygulayanlar için Notlar  
 Özel bağlantı noktası sağlayıcısı aynı nesne üzerinde bu arabirimi uygulayan [IDebugProgram2](../../../extensibility/debugger/reference/idebugprogram2.md) aynı anda tüm oturumları izlemek bağlantı noktası sağlayıcısı izin vererek bağlı durumdayken, bir programa ekledikten SDM izin vermek için arabirimi Program. Seçerse bu özel bağlantı noktası sağlayıcısı bu arabirim uygulayabilir.  
  
## <a name="notes-for-callers"></a>Arayanlar İçin Notlar  
 SDM çağrıları [QueryInterface](http://msdn.microsoft.com/library/62fce95e-aafa-4187-b50b-e6611b74c3b3) üzerinde bir `IDebugProgram2` programlar ekli oturumları izlemek için bu arabirimi almak için arabirim.  
  
## <a name="methods-in-vtable-order"></a>Vtable sırayla yöntemleri  
 Aşağıdaki tabloda yöntemlerini gösterilmektedir `IDebugProgramEx2`.  
  
|Yöntem|Açıklama|  
|------------|-----------------|  
|[Attach](../../../extensibility/debugger/reference/idebugprogramex2-attach.md)|Bir program bir oturumuna ekler.|  
|[GetProgramNode](../../../extensibility/debugger/reference/idebugprogramex2-getprogramnode.md)|Bir programla ilişkili program düğümünü alır.|  
  
## <a name="remarks"></a>Açıklamalar  
 Bu arabirim, SDM ve program özeldir.  
  
## <a name="requirements"></a>Gereksinimler  
 Üstbilgi: Portpriv.h  
  
 Namespace: Microsoft.VisualStudio.Debugger.Interop  
  
 Derleme: Microsoft.VisualStudio.Debugger.Interop.dll  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Temel arabirimler](../../../extensibility/debugger/reference/core-interfaces.md)   
 [IDebugProgram2](../../../extensibility/debugger/reference/idebugprogram2.md)

