---
title: Yığın çerçeveleri | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- stack frames, debugging
- debugging [Debugging SDK], stack frames
- stack frames
ms.assetid: b5e439d4-1e9d-4e13-9cad-bb8b136d4ca8
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: feb2bc9d87486b6f83cf4b19ecec24c8c03edee5
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/16/2018
ms.locfileid: "31128005"
---
# <a name="stack-frames"></a>Yığın çerçeveleri
Hata ayıklayıcı mimarisi bakımından bir **yığın çerçevesi**:  
  
-   Bir iş parçacığı yürütme bağlamı sağlayan yığının bir soyutlamadır. Bir iş parçacığı her zaman bir işlev içinde yürütür. Yığın çerçevesi işlev bağımsız değişkenleri ve yerel değişkenler için tutar. Visual Studio ile hata ayıklama için dil veya ayıklanacak ortamında yığın çerçeveleri desteklemesi gerekir.  
  
-   İçin her ikisini de tanımlamak ve kendisini açıklar ve ilişkili iş parçacığı geri dönebilirsiniz. Yığın çerçevesi aynı zamanda geçerli yönerge işaretçisi yanı sıra ilişkili belgeleri temsil eden kod bağlamını ve ifade değerlendirme bağlamı geri dönebilirsiniz.  
  
-   Adını, türünü ve değerini yerel değişkenleri ve bağımsız değişkenler açıklayan ve çeşitli IDE hata ayıklama pencerelerinde görüntüleneceği özelliklere sahiptir.  
  
-   Tarafından temsil edilen bir [IDebugStackFrame2](../../extensibility/debugger/reference/idebugstackframe2.md) arabirimi, genellikle bir hata ayıklama altyapısı (DE) veya bir iş parçacığının gruplarındaki sonucu olarak sanal makine tarafından oluşturulmuş.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Hata ayıklayıcı bağlamları](../../extensibility/debugger/debugger-contexts.md)   
 [Hata ayıklayıcı kavramları](../../extensibility/debugger/debugger-concepts.md)   
 [Altyapısı hata ayıklama](../../extensibility/debugger/debug-engine.md)   
 [IDebugStackFrame2](../../extensibility/debugger/reference/idebugstackframe2.md)