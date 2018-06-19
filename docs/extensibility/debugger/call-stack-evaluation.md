---
title: Çağrı yığını değerlendirme | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- debugging [Debugging SDK], call stack evaluation
- call stacks, evaluation
ms.assetid: 373d6b49-0459-4cce-816e-05745a44fe49
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: bcfc2f2afa622534772390df59597f6972463de8
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/16/2018
ms.locfileid: "31101309"
---
# <a name="call-stack-evaluation"></a>Çağrı yığını değerlendirme
Kesme modunda çağrı yığınının yığın çerçeveleri görüntüleyebilmek için uygulamanız gereken [EnumFrameInfo](../../extensibility/debugger/reference/idebugthread2-enumframeinfo.md) yöntemi.  
  
## <a name="methods-for-evaluation"></a>Değerlendirme için yöntemleri  
 Basit hata ayıklama motoru (DE), tek bir yığın çerçevesi olabilir. Kesme modunda yığın çerçevesi incelemek için aşağıdaki yöntemleri uygulamak [IDebugStackFrame2](../../extensibility/debugger/reference/idebugstackframe2.md).  
  
|Yöntem|Açıklama|  
|------------|-----------------|  
|[GetCodeContext](../../extensibility/debugger/reference/idebugstackframe2-getcodecontext.md)|Yığın çerçevesi için kod bağlamını alır. Kod bağlamı geçerli yönerge işaretçisi yığın çerçevesinde temsil eder.|  
|[GetDocumentContext](../../extensibility/debugger/reference/idebugstackframe2-getdocumentcontext.md)|Yığın çerçevesi için belge bağlamını alır. Belge bağlam yığın çerçevesi için kaynak kodundaki geçerli konumunu temsil eder. Bir programı durdurulduğunda kaynak kodunu görüntülemek için gereklidir.|  
  
 Bu yöntemler birkaç bağlamı ile ilgili arabirimler ve yöntemler uygulaması gerektirir. Bu nedenle, uygulamanız gereken [GetDocumentContext](../../extensibility/debugger/reference/idebugcodecontext2-getdocumentcontext.md) yöntemi ve aşağıdaki yöntemlerden birini [IDebugDocumentContext2](../../extensibility/debugger/reference/idebugdocumentcontext2.md).  
  
|Yöntem|Açıklama|  
|------------|-----------------|  
|[GetStatementRange](../../extensibility/debugger/reference/idebugdocumentcontext2-getstatementrange.md)|Bir belge bağlamı dosya deyimi aralığını alır.|  
  
 Kod bağlamları numaralandırmak için tüm yöntemleri uygulamak [IEnumDebugCodeContexts2](../../extensibility/debugger/reference/ienumdebugcodecontexts2.md).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Yürütme Denetimi ve Durum Değerlendirmesi](../../extensibility/debugger/execution-control-and-state-evaluation.md)