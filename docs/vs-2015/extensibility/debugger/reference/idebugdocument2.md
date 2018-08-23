---
title: IDebugDocument2 | Microsoft Docs
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
- IDebugDocument2
helpviewer_keywords:
- IDebugDocument2 interface
ms.assetid: 1bc58426-dbf5-4471-9aad-9d66cd80eef0
caps.latest.revision: 13
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: d840039f6ec9c4dce16e8efe9d6dbb2d91cad5d8
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/22/2018
ms.locfileid: "42692587"
---
# <a name="idebugdocument2"></a>IDebugDocument2
[!INCLUDE[vs2017banner](../../../includes/vs2017banner.md)]

Bu konuda en son sürümünü şu yolda bulunabilir: [IDebugDocument2](https://docs.microsoft.com/visualstudio/extensibility/debugger/reference/idebugdocument2).  
  
Bu arabirim, bir kaynak belge temsil eder.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
IDebugDocument2 : IUnknown  
```  
  
## <a name="notes-for-implementers"></a>Uygulayanlar için Notlar  
 [!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)] Genellikle bu arabirimi uygular. Bu kaynak kodu sağlaması gerekir ve kaynak disk üzerinde mevcut değil, hata ayıklama altyapısı (DE) Bu arabirim de uygulayabilirsiniz.  Böyle durumlarda da DE uygulamak [IDebugDocumentContext2](../../../extensibility/debugger/reference/idebugdocumentcontext2.md) ve [IDebugActivateDocumentEvent2](../../../extensibility/debugger/reference/idebugactivatedocumentevent2.md) arabirimleri yanı sıra bazı ek yöntemlerde [ IDebugDisassemblyStream2](../../../extensibility/debugger/reference/idebugdisassemblystream2.md) ve [IDebugDocumentPosition2](../../../extensibility/debugger/reference/idebugdocumentposition2.md) arabirimleri.  
  
## <a name="notes-for-callers"></a>Arayanlar İçin Notlar  
 Yöntemlerde `IDebugDocumentContext2`, `IDebugDisassemblyStream2`, `IDebugDocumentPosition2`, ve `IDebugActivateDocumentEvent2` arabirimi bu arabirim döndürür.  
  
## <a name="methods-in-vtable-order"></a>Vtable sırayla yöntemleri  
 Aşağıdaki tabloda yöntemlerini gösterilmektedir `IDebugDocument2`.  
  
|Yöntem|Açıklama|  
|------------|-----------------|  
|[GetName](../../../extensibility/debugger/reference/idebugdocument2-getname.md)|Belge adını çeşitli biçimlerden birinde alır.|  
|[GetDocumentClassID](../../../extensibility/debugger/reference/idebugdocument2-getdocumentclassid.md)|Belge sınıfı tanımlayıcısını alır.|  
  
## <a name="remarks"></a>Açıklamalar  
 Bu arabirim, yalnızca kaynak kodu DE sağladığı zaman uygulanır. Bir HTML sayfasında komut dosyası ayıklanırken kaynak indirilen veya dinamik olarak oluşturulan gibi DE kaynak kodu sağlar ve bir disk dosyası olarak mevcut değil. C++ gibi geleneksel dilleri hata ayıklama sırasında uygulanması bu arabirimi gerekmez.  
  
## <a name="requirements"></a>Gereksinimler  
 Üstbilgi: msdbg.h  
  
 Namespace: Microsoft.VisualStudio.Debugger.Interop  
  
 Derleme: Microsoft.VisualStudio.Debugger.Interop.dll  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [IsPositionInDocument](../../../extensibility/debugger/reference/idebugdocumentposition2-ispositionindocument.md)   
 [GetDocument](../../../extensibility/debugger/reference/idebugactivatedocumentevent2-getdocument.md)   
 [GetDocument](../../../extensibility/debugger/reference/idebugdocumentcontext2-getdocument.md)   
 [GetDocument](../../../extensibility/debugger/reference/idebugdocumentposition2-getdocument.md)   
 [GetDocument](../../../extensibility/debugger/reference/idebugdisassemblystream2-getdocument.md)

