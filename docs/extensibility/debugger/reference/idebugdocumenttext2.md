---
title: IDebugDocumentText2 | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: IDebugDocumentText2
helpviewer_keywords: IDebugDocumentText2 interface
ms.assetid: e85f50a3-211c-4220-a9f4-789950ba2782
caps.latest.revision: "12"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: ebcb90f570ad29f38eabe8712928b484fd6961c0
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2017
---
# <a name="idebugdocumenttext2"></a>IDebugDocumentText2
Bu arabirim, bir metin belgesi temsil eder.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
IDebugDocumentText2 : IDebugDocument2  
```  
  
## <a name="notes-for-implementers"></a>Uygulayanlar için Notlar  
 Hata ayıklama altyapısı (DE) sağlamak için gereken kaynak kodunu metin biçiminde olduğunda bu arabirimi uygular. SE kullanılıyorsa, bu en tipik durumda olduğundan [IDebugDocument2](../../../extensibility/debugger/reference/idebugdocument2.md) arabirimi, bu da uygulamanız gerekir `IDebugDocumentText2` arabirimi.  
  
## <a name="notes-for-callers"></a>Arayanlar İçin Notlar  
 Kullanım `QueryInterface` bu arabirimden elde etmek için yöntemi bir `IDebugDocument2` arabirimi.  
  
## <a name="methods-in-vtable-order"></a>Vtable sırayla yöntemleri  
 Yöntemlere ek olarak `IDebugDocument2` arabirimi, bu arabirimi uygulayan aşağıdaki yöntemleri:  
  
|Yöntem|Açıklama|  
|------------|-----------------|  
|[GetSize](../../../extensibility/debugger/reference/idebugdocumenttext2-getsize.md)|Belgenin bu konumda metin boyutunu alır.|  
|[GetText](../../../extensibility/debugger/reference/idebugdocumenttext2-gettext.md)|Belgedeki belirtilen konumdan metni alır.|  
  
## <a name="remarks"></a>Açıklamalar  
 Bu arabirimi uygulayan bir nesne de uygulamalıdır <xref:System.Runtime.InteropServices.ComTypes.IConnectionPointContainer> arabirim, hangi kaynakları <xref:System.Runtime.InteropServices.ComTypes.IConnectionPoint> için arabirim bir [IDebugDocumentTextEvents2](../../../extensibility/debugger/reference/idebugdocumenttextevents2.md) nesnesi.  
  
## <a name="requirements"></a>Gereksinimler  
 Başlık: msdbg.h  
  
 Namespace: Microsoft.VisualStudio.Debugger.Interop  
  
 Derleme: Microsoft.VisualStudio.Debugger.Interop.dll  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [IDebugDocument2](../../../extensibility/debugger/reference/idebugdocument2.md)   
 [IDebugDocumentTextEvents2](../../../extensibility/debugger/reference/idebugdocumenttextevents2.md)