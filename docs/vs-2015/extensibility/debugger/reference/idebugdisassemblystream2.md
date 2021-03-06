---
title: IDebugDisassemblyStream2 | Microsoft Docs
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
- IDebugDisassemblyStream2
helpviewer_keywords:
- IDebugDisassemblyStream2 interface
ms.assetid: b03cab0c-3f0b-4cc6-88dc-acb3b48c567a
caps.latest.revision: 13
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 8f72cea28e47bdd14681c1f843a2620a43162885
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/22/2018
ms.locfileid: "42686597"
---
# <a name="idebugdisassemblystream2"></a>IDebugDisassemblyStream2
[!INCLUDE[vs2017banner](../../../includes/vs2017banner.md)]

Bu konuda en son sürümünü şu yolda bulunabilir: [IDebugDisassemblyStream2](https://docs.microsoft.com/visualstudio/extensibility/debugger/reference/idebugdisassemblystream2).  
  
Bu arabirim, yönergelerin akışını temsil eder.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
IDebugDisassemblyStream2 : IUnknown  
```  
  
## <a name="notes-for-implementers"></a>Uygulayanlar için Notlar  
 Hata ayıklama altyapısı, bir programın kod ayrıştırılmış kodu desteklemek için bu arabirimi uygular.  
  
## <a name="notes-for-callers"></a>Arayanlar İçin Notlar  
 Bir çağrı [GetDisassemblyStream](../../../extensibility/debugger/reference/idebugprogram2-getdisassemblystream.md) yöntemi bu arabirimi döndürür.  
  
## <a name="methods-in-vtable-order"></a>Vtable sırayla yöntemleri  
 Aşağıdaki tabloda yöntemlerini gösterilmektedir `IDebugDisassemblyStream2`.  
  
|Yöntem|Açıklama|  
|------------|-----------------|  
|[Okuma](../../../extensibility/debugger/reference/idebugdisassemblystream2-read.md)|Ayrıştırılmış kodu stream'de geçerli konumundan başlayarak yönergeleri okur.|  
|[Arama](../../../extensibility/debugger/reference/idebugdisassemblystream2-seek.md)|Ayrıştırılmış kod akış yönergeler belirtilen konuma göre verilen sayıda okuma imleci taşır.|  
|[GetCodeLocationId](../../../extensibility/debugger/reference/idebugdisassemblystream2-getcodelocationid.md)|Belirli kod bağlamı için bir kod konum tanımlayıcısı döndürür.|  
|[GetCodeContext](../../../extensibility/debugger/reference/idebugdisassemblystream2-getcodecontext.md)|Belirtilen kod konumu tanımlayıcısına karşılık gelen bir kod bağlam nesnesi döndürür.|  
|[GetCurrentLocation](../../../extensibility/debugger/reference/idebugdisassemblystream2-getcurrentlocation.md)|Geçerli kod konumu temsil eden bir kod konum tanımlayıcısı döndürür.|  
|[GetDocument](../../../extensibility/debugger/reference/idebugdisassemblystream2-getdocument.md)|Bu çözümü stream ile ilişkili kaynak belge alır.|  
|[GetScope](../../../extensibility/debugger/reference/idebugdisassemblystream2-getscope.md)|Bu çözümü akış kapsamı alır.|  
|[GetSize](../../../extensibility/debugger/reference/idebugdisassemblystream2-getsize.md)|Bu çözümü akış boyutunu alır.|  
  
## <a name="remarks"></a>Açıklamalar  
 Ayrıştırılmış kod akışı, tüm adres veya yalnızca bir işlev veya modül alanı içinde temsil etmek için oluşturulabilir. Her yönerge tarafından temsil edilen bir [DisassemblyData](../../../extensibility/debugger/reference/disassemblydata.md) yapısı için bir çağrı tarafından döndürülen [okuma](../../../extensibility/debugger/reference/idebugdisassemblystream2-read.md) yöntemi.  
  
## <a name="requirements"></a>Gereksinimler  
 Üstbilgi: msdbg.h  
  
 Namespace: Microsoft.VisualStudio.Debugger.Interop  
  
 Derleme: Microsoft.VisualStudio.Debugger.Interop.dll  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Temel arabirimler](../../../extensibility/debugger/reference/core-interfaces.md)   
 [GetDisassemblyStream](../../../extensibility/debugger/reference/idebugprogram2-getdisassemblystream.md)   
 [DisassemblyData](../../../extensibility/debugger/reference/disassemblydata.md)

