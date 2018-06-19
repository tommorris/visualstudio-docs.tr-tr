---
title: Sonlandırma ve ayırma | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- programs, termination events
- debug engines, detaching from programs
ms.assetid: 268c1e51-6363-45d1-964c-1ab99bdfa4f9
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: e5af218098f6d79cf6208c66b314c35d2471af15
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/16/2018
ms.locfileid: "31127387"
---
# <a name="termination-and-detaching"></a>Sonlandırma ve ayırma
Aşağıdaki normal sonlandırma açıklar.  
  
## <a name="discussion"></a>Tartışma  
 Sonra [IDebugLoadCompleteEvent2](../../extensibility/debugger/reference/idebugloadcompleteevent2.md) veya [IDebugEntryPointEvent2](../../extensibility/debugger/reference/idebugentrypointevent2.md) arabirimi devam eder, yoksa hiçbir kesme noktaları, özel durumlar, çalışma zamanı hataları veya ayıklanacak, uygulamada sonsuz döngüler Ayıklanacak program tamamlanıncaya kadar çalışır. Normal sonlandırma budur.  
  
 Göndermesi gerekir bir [IDebugProgramDestroyEvent2](../../extensibility/debugger/reference/idebugprogramdestroyevent2.md) normal sonlandırma uygulamak için. Bu uygulama gerektirir [IDebugProgramDestroyEvent2::GetExitCode](../../extensibility/debugger/reference/idebugprogramdestroyevent2-getexitcode.md) yöntemi.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Özel Hata Ayıklama Altyapısı Oluşturma](../../extensibility/debugger/creating-a-custom-debug-engine.md)